# ÖRÜ

> **Author:** Ali Emre Arlı
> **Module:** Project Overview
> **Version:** 1.0.0
> **Last Updated:** 2026-10-21
> **Status:** Draft

ÖRÜ is a decentralized, friend-to-friend communication library written in C. Nodes connect only to people they know and have met in person, and messages travel between them without any central server. This document introduces the project, summarizes how it is designed to work, states its current limitations, and points to the documentation that governs it.

___

# 0.0. Table of Contents

* 1.0. Introduction
    * 1.1. What ÖRÜ Is
    * 1.2. Project Goals
    * 1.3. Project Status

* 2.0. Design Overview
    * 2.1. Friend-to-Friend Network
    * 2.2. Finding a Recipient
    * 2.3. Delivering a Message
    * 2.4. Direct Mode
    * 2.5. Network Growth

* 3.0. Limitations and Non-Guarantees
    * 3.1. Development Phase
    * 3.2. Properties That Are Not Guaranteed
    * 3.3. Design Trade-Offs

* 4.0. Project Structure
    * 4.1. Modules
    * 4.2. Repository Layout

* 5.0. Building
    * 5.1. Requirements
    * 5.2. Build and Test Instructions

* 6.0. Documentation and Contributing
    * 6.1. Reading Order
    * 6.2. Contribution Rules

* 7.0. License and Contact

* Notes

___

# 1.0. Introduction

This section explains what ÖRÜ is, what it aims to achieve, and how far its development has progressed.

## 1.1. What ÖRÜ Is

ÖRÜ is a library for exchanging messages over a network that has no central server, no fixed entry address, and no global directory of users. Each node knows only a small number of other nodes, namely the people whose keys it has exchanged face to face. Communication with anyone else is relayed through chains of those trusted connections.

• • •

## 1.2. Project Goals

ÖRÜ is designed with the following goals:

- **No central point.** There is no server or address that the network depends on, so no single component whose loss stops the network.
- **User-controlled trust.** A node connects only to people it has chosen to trust through an in-person key exchange.
- **Limited exposure to intermediaries.** A node that relays traffic is designed to see only a small piece of it. It sees neither the full message nor its content.
- **Resilient delivery.** A message is designed to be delivered even if some of the paths it uses fail.
- **Organic growth.** The network grows as users connect to the people they know.

These are design goals. Section 3.0 states which properties are not guaranteed.

• • •

## 1.3. Project Status

ÖRÜ is in the MVP development phase. The implementation is incomplete and several parts of the design are planned but not yet implemented. See Section 3.1.

___

# 2.0. Design Overview

This section summarizes the intended behavior of ÖRÜ. It is informative. The authoritative architecture is described in `docs/architecture/oru.arch.md`, and the requirements for each component are defined by the applicable contracts.

## 2.1. Friend-to-Friend Network

The network is a graph of nodes. Each node is linked only to the few nodes it knows personally. Two people become neighbors by meeting in person and exchanging keys, for example by scanning a QR code. Because there is no server to register with, there is no address that a new node must contact to join.

• • •

## 2.2. Finding a Recipient

When a node wants to message someone who is not its neighbor, it asks its neighbors whether they know the recipient. The question uses a blinded identifier instead of the recipient's name, so that a node relaying the question is not meant to learn who is being sought. A neighbor who knows the recipient answers. A neighbor who does not passes the question to its own neighbors, and the question spreads outward.

The result is one or more short paths to the recipient. Each reply is signed by the recipient's key, so that another node cannot successfully claim to be the recipient.

• • •

## 2.3. Delivering a Message

Once paths are known, the sender prepares the message as follows:

1. The message is encrypted with the recipient's key.
2. The encrypted message is padded and split into fragments of equal size.
3. Erasure coding is applied, so that the message can be rebuilt even if some fragments do not arrive.
4. The fragments are sent over different paths, spread over roughly five minutes.

A relaying node is designed to handle only individual encrypted fragments. After the delivery period, the recipient collects the fragments, reassembles the message, and decrypts it with its own key.

• • •

## 2.4. Direct Mode

Delivery through multiple paths is slow. For latency-sensitive uses such as voice or video, both parties MAY agree to open a direct connection. The request for it is sent over the normal path.

Direct mode has a cost: both parties learn each other's IP address, and network providers can observe that the two parties are communicating. For this reason, direct mode is disabled by default, and enabling it shows a warning that anonymity does not apply to that connection.

• • •

## 2.5. Network Growth

After two nodes have communicated, they MAY choose to exchange keys remotely and become neighbors. The network therefore grows from the connections its users make.

___

# 3.0. Limitations and Non-Guarantees

This section states what ÖRÜ does not currently provide. Readers MUST NOT assume a property that is not listed as supported by the project's documentation and implementation.

## 3.1. Development Phase

ÖRÜ is in the MVP phase. The following components have directories but no implementation yet:

- QUIC transport (`protocols/QUIC`)
- Traffic obfuscation (`protocols/obfuscation`)
- Cryptography wrapper (`security/cryptography`)
- Event loop and threading (`runtime/event_loop`, `runtime/thread`)

During the MVP phase, the implementation may not yet conform to every approved contract. Known differences are tracked in `docs/development/modules.dev.md`, Section 6.2.

• • •

## 3.2. Properties That Are Not Guaranteed

The design aims at confidentiality, limited exposure to relaying nodes, and resilience to failed paths. These are goals, not established facts. In particular:

- The design has not been independently reviewed or audited.
- No property such as encryption, authentication, anonymity, or peer trust MUST be treated as implemented or guaranteed unless the applicable project documentation and implementation support it.
- The conditions under which a security property holds, and what the system does not protect against, are defined in the security documentation, not in this document.

• • •

## 3.3. Design Trade-Offs

- **Latency.** Spreading fragments over about five minutes means that standard message delivery is not instantaneous.
- **Direct mode.** A direct connection gives up the anonymity of the default mode.
- **Trust model.** Neighbors are limited to people the user has met in person, which limits the speed at which a network grows.

___

# 4.0. Project Structure

This section gives a short overview of the source tree. The authoritative description of module responsibilities and dependencies is `docs/development/modules.dev.md`.

## 4.1. Modules

| Module | Purpose |
|---|---|
| `runtime` | Logging, storage, event loop, threading |
| `utils` | String and filesystem helpers |
| `security` | Local identity and cryptographic operations |
| `protocols` | TCP, UDP, QUIC, obfuscation, and wire format |
| `connection` | A single link to a single neighbor |
| `user` | Known peers and trust relationships |
| `routing` | Finding and selecting paths to a recipient |
| `message` | Encrypting, splitting, scheduling, and reassembling messages |

• • •

## 4.2. Repository Layout

```text
Oru/
├── include/    public headers
├── src/        internal headers and entry point
├── <modules>/  source code, one directory per module
├── vendor/     third-party code
├── docs/       documentation
├── license/    license
└── tests/      tests
```

___

# 5.0. Building

This section describes how to prepare a build environment.

## 5.1. Requirements

- **Operating system:** Linux.
- **Language standard:** C11.
- **Compilers:** GCC or Clang.
- **Build system:** CMake.
- **Version control:** Git.

Optional tools include `clangd` for editor support and a debugger. Minimum versions are not currently defined.

• • •

## 5.2. Build and Test Instructions

Specific build commands and test procedures have not yet been established. They will be documented here once defined. Contributors MUST NOT treat unverified commands as authoritative.

___

# 6.0. Documentation and Contributing

This section directs readers to the project's documentation and contribution requirements.

## 6.1. Reading Order

New contributors MUST read the following documents, in this order, before contributing:

1. This `README.md`.
2. `docs/development/contributor_guide.md`.
3. `docs/development/code_of_conduct.md`.
4. `docs/development/documentation_writing_rules.md`.
5. `docs/development/coding_style_guide.md`, Section `0.5. Core Coding Rules`.
6. `docs/development/modules.dev.md` and `docs/architecture/oru.arch.md`.

• • •

## 6.2. Contribution Rules

Changes intended for the mainline repository MUST be submitted for review and MUST conform to the applicable contracts, standards, and approved architectural decisions. Changes to shared project decisions require team consensus. The complete procedure is defined in `docs/development/contributor_guide.md`.

___

# 7.0. License and Contact

ÖRÜ is distributed under the terms stated in `license/ORU_LICENSE.md`.

For project-related questions, contact the project at:

**Email:** oruproject@protonmail.com

___

## Notes

> **Changelog**
>
> | Version | Date | Change |
> |---|---|---|
> | 1.0.0 | 2026-10-21 | Initial draft. |

> **AI Usage Notice:** This document was written by artificial intelligence in accordance with the architecture, rules, and standards provided by the developer.
