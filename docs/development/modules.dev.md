# Modules Development Guide

> **Author:** Ali Emre Arlı
> **Module:** Development
> **Version:** 1.0.1
> **Last Updated:** 2026-10-21
> **Status:** Draft

This document describes the module organization of the ÖRÜ project. It defines each module's purpose, responsibilities, and dependencies, and the rules that govern how modules relate to one another. It is the starting point for module-specific documentation and does not replace the architecture document or any contract.

___

# 0.0. Table of Contents

* 1.0. Introduction
    * 1.1. Purpose
    * 1.2. Scope
    * 1.3. Terminology

* 2.0. Architectural Decisions
    * 2.1. Monolithic Design
    * 2.2. Source Layout and Header Trees
    * 2.3. Layered Dependency Rule
    * 2.4. Separation of Connection, Routing, and Message

* 3.0. Module Overview
    * 3.1. Layers and Modules
    * 3.2. Dependency Graph
    * 3.3. Directory Layout

* 4.0. Module Specifications
    * 4.1. runtime
    * 4.2. utils
    * 4.3. security
    * 4.4. protocols
    * 4.5. connection
    * 4.6. user
    * 4.7. routing
    * 4.8. message
    * 4.9. vendor and Entry Point

* 5.0. Changing the Module Structure
    * 5.1. Adding a Module
    * 5.2. Changing Module Boundaries

* 6.0. Current State and Open Issues
    * 6.1. MVP Status
    * 6.2. Known Discrepancies
    * 6.3. Open Decisions

* Notes

___

# 1.0. Introduction

This section defines the purpose and scope of this document and the terms it uses.

## 1.1. Purpose

ÖRÜ is a decentralized, friend-to-friend network. Its implementation is divided into modules, each owning one kind of responsibility. This document records what those modules are, what each one is responsible for, and which modules each one may depend on, so that contributors can decide where a change belongs before making it.

• • •

## 1.2. Scope

This document covers the top-level modules of the ÖRÜ source tree, their responsibilities, and their dependency relationships. It does not define module interfaces, message formats, or security properties. Those are defined by the applicable contracts and by `oru.architecture.md`.

Contributors MUST consult this document before modifying module boundaries, as required by `contributor_guide.md`, Section 5.2.

• • •

## 1.3. Terminology

- **Module:** A top-level directory of the project that owns one responsibility, such as `connection` or `routing`.
- **Internal header:** A header located under `src/include/<module>/`. Internal headers define the interfaces between modules.
- **Public header:** A header located under `include/oru/`. Public headers define the interface offered to users of the library.
- **Layer:** A numbered group of modules used to define dependency direction (Section 3.1).
- **Neighbor:** A peer with which the local node has exchanged keys face to face and is directly connected.

___

# 2.0. Architectural Decisions

This section records the architectural decisions that govern module organization. Each decision states its rationale, the alternatives considered, and its consequences, as required by `documentation_writing_rules.md`, Section 5.1.

## 2.1. Monolithic Design

**Decision.** ÖRÜ is built as a single tightly coupled library. Modules are organizational units inside one codebase. They are not independently versioned components.

**Rationale.** A separate API and ABI contract for every internal module would add maintenance cost without benefit to users. Modules are tightly related by nature, because a message passes through message, routing, connection, and protocols in sequence.

**Alternatives considered.** Independently versioned internal libraries with stable per-module interfaces.

**Consequences.**

- Internal headers MAY change between releases. Only the public API and ABI under `include/oru/` are subject to the stable-additive-only compatibility policy.
- Tight coupling is accepted, but it MUST be bounded by the dependency rule in Section 2.3.

• • •

## 2.2. Source Layout and Header Trees

**Decision.** The project uses two header trees:

- `include/oru/` contains public headers only. Users include them as `<oru/oru.h>`.
- `src/include/<module>/` contains internal headers. Modules include them as `"<module>/<file>.h"`. This directory is the only internal include root.

**Rationale.** A single internal include root means a module path is resolved in exactly one place. Separating public from internal headers keeps the user-facing surface small.

**Alternatives considered.** Headers placed next to their `.c` files.

**Consequences.**

- A module that needs another module's interface MUST include it from `src/include/`.
- Implementation files (`.c`) and private, module-local headers remain in the module directory.
- Header guards in `src/include/` and in module directories MUST be different, so that a same-named header in two locations cannot collide.
- Headers in `include/oru/` MUST NOT include internal headers.

• • •

## 2.3. Layered Dependency Rule

**Decision.** Modules are arranged in layers (Section 3.1). A module MUST include and call only modules in layers below its own, plus the vendor libraries in Section 4.9.

**Rationale.** Monolithic does not have to mean unstructured. A single rule keeps the dependency graph acyclic, lets any layer be understood and tested using only the layers beneath it, and makes the location of a change predictable.

**Alternatives considered.** No dependency restriction; a strict one-layer-down rule.

**Consequences.**

- A module MUST NOT depend on a module in the same layer or a higher layer unless the dependency is explicitly listed in Section 3.2.
- Circular dependencies MUST NOT exist.
- Upward communication, such as a lower layer notifying a higher one, MUST use callbacks registered by the higher layer.

• • •

## 2.4. Separation of Connection, Routing, and Message

**Decision.** Three modules each answer one question about a message in transit:

| Module | Question it answers | Hops |
|---|---|---|
| `message` | How is a message prepared, split, scheduled, and reassembled? | Not applicable |
| `routing` | Through which neighbors can a given recipient be reached? | Many |
| `connection` | How does the local node talk to one neighbor right now? | One |

**Rationale.** Preparing a message, choosing a path, and moving bytes to a neighbor change for different reasons and at different rates.

**Consequences.**

- `message` MUST NOT open or manage sockets.
- `routing` MUST NOT inspect or modify message contents.
- `connection` MUST NOT make path decisions or know a message's final destination.
- Direct mode (Section 4.5) is a special kind of connection, not a routing method. Routing only supplies the policy on whether it is permitted for a given message.

___

# 3.0. Module Overview

This section summarizes the modules, their layers, and their dependencies.

## 3.1. Layers and Modules

Layers are numbered from the bottom. A module may depend only on modules with a lower layer number.

| Layer | Module | Responsibility (summary) |
|---|---|---|
| 1 | `runtime` | Logging, storage, event loop, threading |
| 1 | `utils` | String and filesystem helpers |
| 2 | `security` | Local identity and cryptographic operations |
| 3 | `protocols` | Transport protocols, obfuscation, wire format |
| 4 | `connection` | One open link to one neighbor |
| 5 | `user` | Known peers and trust relationships |
| 6 | `routing` | Path discovery and path selection |
| 7 | `message` | Message preparation, splitting, scheduling, reassembly |
| 8 | `src/oru.c` | Wires all modules together and exposes the public API |

• • •

## 3.2. Dependency Graph

Arrows point from a module to the modules it is permitted to depend on.

```text
oru.c
  └─> message ─> routing ─> user ─> connection ─> protocols ─> security
                    │                    │                        │
                    └────────────────────┴────────────────────────┴─> runtime, utils
```

The following direct dependencies are permitted:

| Module | Permitted direct dependencies |
|---|---|
| `oru.c` | `message`, `routing`, `user`, `connection`, `security`, `runtime`, `utils` |
| `message` | `routing`, `security`, `runtime`, `utils` |
| `routing` | `user`, `connection`, `security`, `runtime`, `utils` |
| `user` | `connection`, `security`, `runtime`, `utils` |
| `connection` | `protocols`, `security`, `runtime`, `utils` |
| `protocols` | `security`, `runtime`, `utils` |
| `security` | `runtime`, `utils` |
| `runtime`, `utils` | None between each other (see Section 6.3) |

Transitive dependencies follow from this table. For example, `message` depends transitively on `connection` through `routing`.

• • •

## 3.3. Directory Layout

```text
Oru/
├── include/oru/         public headers
├── src/
│   ├── include/         internal headers, grouped per module
│   └── oru.c            entry point
├── runtime/             log, storage, event_loop, thread
├── utils/               string, filesystem
├── security/            identity, cryptography
├── protocols/           TCP, UDP, QUIC, obfuscation
├── connection/          link, keepalive, direct
├── user/                known peers, key exchange, trust
├── routing/             router, discovery, p2p
├── message/             sender, receiver
├── vendor/              third-party code
├── docs/
├── license/
└── tests/
```

This layout is a snapshot. Section 6.2 lists where the current tree differs from it.

___

# 4.0. Module Specifications

Each subsection describes a module's purpose, responsibilities, and explicit non-responsibilities. Entries marked **planned** have a directory but no implementation yet.

## 4.1. runtime

**Layer:** 1

**Purpose.** Provides the execution environment that all other modules rely on.

**Responsibilities.**

- `log`: logging, wrapping `vendor/log.c`.
- `storage`: persistent storage of local state.
- `event_loop`: event dispatching (planned).
- `thread`: threading primitives (planned).

**Non-responsibilities.** It MUST NOT contain protocol, networking, or cryptographic logic.

• • •

## 4.2. utils

**Layer:** 1

**Purpose.** Provides small general-purpose helpers.

**Responsibilities.**

- `string`: string helpers.
- `filesystem`: filesystem and path helpers.

**Non-responsibilities.** It MUST NOT contain code specific to ÖRÜ's networking or security behavior.

• • •

## 4.3. security

**Layer:** 2

**Purpose.** Owns the local node's identity and the cryptographic operations used by the other modules.

**Responsibilities.**

- `identity`: the local node's own key pair.
- `cryptography`: a wrapper over the cryptographic primitives in `vendor/Monocypher` (planned).

**Non-responsibilities.** It does not store other peers' public keys or trust state; that belongs to `user` (Section 4.6).

• • •

## 4.4. protocols

**Layer:** 3

**Purpose.** Holds ÖRÜ's own transport implementations and everything that defines how bytes are carried.

**Responsibilities.**

- `TCP`, `UDP`, `QUIC`: transport protocol implementations (`QUIC` is planned).
- `obfuscation`: traffic obfuscation (planned).
- Wire format: packet layout and versioning (planned; location to be decided, see Section 6.3).

**Non-responsibilities.** It carries bytes only. It MUST NOT know which peer the bytes belong to, and it MUST NOT perform message splitting or path selection.

• • •

## 4.5. connection

**Layer:** 4

**Purpose.** Manages one open link between the local node and one neighbor.

**Responsibilities.**

- `connection`: link lifecycle, and the choice of which transport from `protocols` a link uses.
- `keepalive`: liveness checking of a link (`ping_pong`).
- `direct`: direct mode, in which a link is opened to a node that is not a neighbor.

**Direct mode requirements.**

- Direct mode MUST be disabled by default.
- Enabling direct mode MUST show the user a warning that anonymity does not apply to that connection. The warning MUST state that both parties learn each other's IP address and that network providers can observe that the two parties are communicating.
- A direct connection request MUST be sent through the anonymous path, and a direct connection MUST NOT be opened unless both parties approve it.

**Non-responsibilities.** It MUST NOT decide paths or know a message's final destination.

• • •

## 4.6. user

**Layer:** 5

**Purpose.** Represents the other people the local node knows. This module was previously named `peer`.

**Responsibilities.**

- The set of known users and their public keys.
- The face-to-face key exchange used to add a neighbor (for example, via QR code).
- Trust state of each known user.
- Keys exchanged remotely between two nodes that have already communicated, so that they become neighbors.

**Non-responsibilities.** It does not hold the local node's own key pair (`security`), and it does not find paths to users who are not neighbors (`routing`).

• • •

## 4.7. routing

**Layer:** 6

**Purpose.** Finds ways to reach a recipient who is not a direct neighbor.

**Responsibilities.**

- `discovery`: asking neighbors whether they know a recipient, using a blinded identifier, and propagating the query onward.
- Verifying that a reply comes from the real recipient, using the recipient's signature.
- Maintaining the paths learned and selecting paths for a message.
- `p2p`: the default, anonymous routing mode.
- Providing the policy on whether direct mode is permitted for a message.

**Non-responsibilities.** It MUST NOT read or modify message contents and MUST NOT open sockets. It uses `connection` to reach neighbors.

• • •

## 4.8. message

**Layer:** 7

**Purpose.** Prepares outgoing messages for delivery and reassembles incoming ones.

**Responsibilities.**

- `sender`: encrypt the message for the recipient, split it into equal-sized fragments with padding, apply erasure coding, and schedule fragments over multiple paths across roughly five minutes.
- `receiver`: collect fragments, reassemble the message once enough fragments have arrived, decrypt it, and deliver it.
- Fragment, erasure coding, padding, and scheduler logic are planned and are currently expected to live under `sender` and `receiver`, or in new submodules (see Section 6.3).

**Non-responsibilities.** It MUST NOT select paths (`routing`) and MUST NOT communicate with neighbors directly (`connection`).

• • •

## 4.9. vendor and Entry Point

**vendor/.** Contains third-party code: `log.c`, `Monocypher`, and `uthash`. Third-party code MUST be kept only in this directory. Their headers are exposed to the project through `src/include/vendor/`. Dependency changes MUST follow `contributor_guide.md`, Section 4.3.

**src/oru.c.** The only file allowed to depend on every module. It initializes modules and implements the public API declared in `include/oru/oru.h`.

___

# 5.0. Changing the Module Structure

This section defines how the module structure may be changed.

## 5.1. Adding a Module

A new module MUST NOT be added without team consensus. A proposal to add a module MUST state:

- The module's purpose and responsibilities.
- The layer it belongs to and the modules it depends on.
- The reason an existing module cannot own the responsibility.

When a module is added, this document, the dependency table in Section 3.2, and `oru.architecture.md` MUST be updated in the same change.

• • •

## 5.2. Changing Module Boundaries

Moving a responsibility from one module to another, changing a module's layer, or adding a dependency that Section 3.2 does not permit is an architectural change. It MUST follow the review and approval procedure in `contributor_guide.md`, Section 2.4. Such a change MUST NOT be justified solely by existing implementation behavior.

___

# 6.0. Current State and Open Issues

This section records known gaps between this document and the implementation, and decisions that are not yet made.

## 6.1. MVP Status

The project is in the MVP development phase. Differences between the implementation and this document are permitted during this phase if they remain identifiable, as required by `documentation_writing_rules.md`, Section 5.5. Section 6.2 is the register of those differences.

• • •

## 6.2. Known Discrepancies

| Item | Current state | Expected state |
|---|---|---|
| Naming inside `user` | The internal header is `src/include/user/user.h`, while the module files are still `user/peer.c`, `user/peer.h`, and `user/types/peer_type.h` | Consistent `user` naming |
| `ping_pong` internal header | `src/include/connection/keepalive.h` is named for the new location, while the source files are still named `ping_pong.*` | Consistent naming |
| `direct` source files | `connection/direct/direct_routing.*` use routing naming | Renamed to reflect that direct mode is a connection feature |
| `utils/filesystem/oru_save.h` and `runtime/storage` | Overlapping responsibilities | One owner |
| `protocols/QUIC`, `protocols/obfuscation`, `runtime/event_loop`, `runtime/thread`, `security/cryptography`, `routing/types`, `runtime/types` | Empty directories | Implemented or removed |
| `types/` subdirectories | Single-header directories in several modules | To be decided (Section 6.3) |
| Public header | `include/liboru.h` | `include/oru/oru.h`, included as `<oru/oru.h>` (Section 2.2) |

• • •

## 6.3. Open Decisions

The following decisions have not been made. Until they are, contributors MUST NOT treat any of them as settled.

1. **Wire format location.** Whether the packet format belongs in `protocols` or in a separate module.
2. **Location of message internals.** Whether fragmenting, erasure coding, padding, and scheduling are submodules of `message` or files inside `sender` and `receiver`.
3. **Same-layer dependencies.** Whether `runtime` may depend on `utils`, in particular `storage` on `filesystem`.
4. **`types/` subdirectories.** Whether types stay in separate `types/` directories or move into each module's header.
5. **Name of `message`.** Whether the module keeps its name or is renamed, for example to `delivery`.
6. **Cryptography access.** Whether modules other than `security` may use `vendor/Monocypher` directly.

___

## Notes

> **Changelog**
>
> | Version | Date | Change |
> |---|---|---|
> | 1.0.0 | 2026-10-21 | Initial draft. |
> | 1.0.1 | 2026-10-21 | Updated Section 6.2 to match the current tree: `src/include/peer/` was renamed to `src/include/user/user.h`, and the public header is located at `include/liboru.h`. |

> **AI Usage Notice:** This document was written by artificial intelligence in accordance with the architecture, rules, and standards provided by the developer.
