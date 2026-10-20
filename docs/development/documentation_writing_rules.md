# Documentation Writing Rules

> **Author:** Ali Emre Arlı
> **Module:** Documentation
> **Version:** 1.0.0
> **Last Updated:** 2026-10-20
> **Status:** Active

This file defines the mandatory rules for writing, formatting, verifying, and maintaining documentation in the ÖRÜ project. Documentation establishes the project's architecture, contracts, and implementation requirements. All source code must conform to these specifications. Everyone contributing to the project must follow this standard.

___

# 0.0. Table of Contents

* 1.0. Scope and Enforcement
    * 1.1. Scope
    * 1.2. Rule Enforcement
    * 1.3. Version Management
    * 1.4. Changes and Approval
    * 1.5. Exceptions and Deviations
    * 1.6. Completion and Acceptance

* 2.0. Fundamental Principles
    * 2.1. Precision and Unambiguity
    * 2.2. Completeness and Consistency
    * 2.3. Verifiability and Traceability
    * 2.4. Explicit Assumptions and Limitations
    * 2.5. Use of Artificial Intelligence

* 3.0. Documentation Structure and Formatting
    * 3.1. Document Organization
    * 3.2. Markdown and Formatting Rules
    * 3.3. Naming and Terminology
    * 3.4. Code Examples, Diagrams, and References

* 4.0. Writing and Specification Rules
    * 4.1. Writing Style and Language
    * 4.2. Normative Language
    * 4.3. Requirements and Constraints
    * 4.4. Preconditions, Postconditions, and Invariants
    * 4.5. Errors, Failures, and Side Effects

* 5.0. Architecture and Contracts
    * 5.1. Architectural Documentation
    * 5.2. Contract Specification
    * 5.3. Component Responsibilities and Dependencies
    * 5.4. Security and Trust Boundaries
    * 5.5. Implementation Conformance

* 6.0. Accuracy and References
    * 6.1. Technical Accuracy and Verification
    * 6.2. Sources and Citations
    * 6.3. Version-Specific Information
    * 6.4. Examples and Reference Integrity

* 7.0. Review and Maintenance
    * 7.1. Review and Acceptance Criteria
    * 7.2. Change Management
    * 7.3. Conflict and Inconsistency Resolution
    * 7.4. Non-Conformance and Corrections
    * 7.5. Documentation Lifecycle

___

# 1.0. Scope and Enforcement

This section defines the scope of this standard, its enforcement requirements, and the procedures governing its modification and application. All contributors must follow these rules to ensure that documentation remains consistent, authoritative, and compliant with the project's requirements.

## 1.1. Scope

This standard applies to all documentation within the ÖRÜ project. Every documentation document must comply with the applicable rules defined herein, regardless of its type, purpose, or location within the project.

• • •

## 1.2. Rule Enforcement

All rules defined in this standard are mandatory. Technical inaccuracies, contradictory requirements, incomplete contracts, and other technical violations that affect correctness or implementation conformance must be resolved before a change can be accepted. Formatting and other non-technical violations must be addressed according to their priority and must not be ignored.

• • •

## 1.3. Version Management

This standard must use explicit versioning and maintain a change history. Changes must be traceable to their corresponding revisions. Previous versions must remain inspectable through the project's version control history.

• • •

## 1.4. Changes and Approval

Changes to this standard require review and approval by the designated responsible person before they take effect. Unapproved changes must not be treated as authoritative.

• • •

## 1.5. Exceptions and Deviations

Exceptions and deviations from this standard are not permitted. If a requirement cannot be satisfied, the relevant documentation or this standard must be corrected through the established change procedure.

• • •

## 1.6. Completion and Acceptance

A documentation change cannot be considered complete while unresolved technical violations remain. Formatting and other non-technical violations must also be addressed, but minor non-technical violations do not independently block acceptance when the applicable technical acceptance requirements are satisfied.

___

# 2.0. Fundamental Principles

This section establishes the fundamental principles governing all ÖRÜ documentation. These principles define the expected quality, consistency, reliability, and responsible preparation of project documentation. All documentation must adhere to these principles within its intended scope.

• • •

## 2.1. Precision and Unambiguity

Normative statements must be precise and unambiguous, defining requirements and expected behavior in a manner that prevents conflicting interpretations. Informative content may use a more flexible writing style, provided that it does not introduce ambiguity into normative requirements or misrepresent technical facts.

• • •

## 2.2. Completeness and Consistency

Each document must completely address its assigned scope and clearly identify its dependencies on other documents. Information owned by another document should be referenced rather than redundantly maintained. However, the same subject may be documented from different perspectives, for different audiences, or for different purposes, provided that these descriptions remain consistent with the authoritative requirements.

• • •

## 2.3. Verifiability and Traceability

Technical claims and requirements must be verifiable to the extent appropriate to their nature. External technical claims must be supported by reliable sources when verification or attribution is necessary. Requirements and design decisions must be traceable to their sources, related decisions, or verification methods when such traceability is necessary to establish correctness and consistency. Unverified claims must not be presented as established facts.

• • •

## 2.4. Explicit Assumptions and Limitations

Assumptions, prerequisites, constraints, limitations, and unresolved uncertainties that affect the interpretation, correctness, security, or implementation of a document must be explicitly stated. Normative requirements must not depend on unstated assumptions that could materially alter their meaning or expected behavior.

• • •

## 2.5. Use of Artificial Intelligence

Artificial intelligence is permitted and encouraged as an aid to documentation work, including drafting, editing, analysis, research, and consistency checking, provided that its use complies with this standard.

Architectural decisions and contract definitions remain the responsibility of the developer. AI may assist with analyzing alternatives, identifying problems, and proposing improvements, but it must not independently establish or change the project's architecture or contracts. AI-generated content must be reviewed by a human before acceptance, and its technical claims and references must be verified as appropriate.

If AI is used in the creation or modification of a document, this use must be disclosed within the document itself at an appropriate location. The disclosure must be sufficiently clear to identify that AI assistance was used, without requiring unnecessary implementation details.

Developers using AI for documentation must consult the applicable guidance in `docs/ai/`, particularly `ai_documentation_rules.md`. Other relevant guidance includes `ai_coding_rules.md`, `ai_memory_bank.md`, and `ai_projects_goals.md`. These files provide complementary project-specific context and rules and must be used according to their respective purposes.

___

# 3.0. Documentation Structure and Formatting

This section defines the organizational and formatting principles for ÖRÜ documentation. Its purpose is to keep documents discoverable, consistent, readable, and maintainable without imposing unnecessary structural restrictions. Directory layouts and formatting conventions must support the project's actual needs and may evolve through the established change process.

## 3.1. Document Organization

Documentation must be organized according to its subject, purpose, and intended audience. The project uses `docs/` as the documentation root, with subdirectories serving distinct organizational purposes. The directory structure may evolve as the project grows; this standard does not require every possible directory to exist.

The following directories describe the intended purposes of the project's documentation organization:

- `architecture/` contains architectural descriptions, system structure, component relationships, and relevant design decisions.
- `dev/` contains developer-oriented documentation, development procedures, contribution guidance, and development standards, including the coding style guide and code of conduct.
- `api/` contains documentation for public APIs and their externally observable contracts.
- `abi/` contains documentation for application binary interfaces and their compatibility requirements, where applicable.
- `roles/` describes system roles, responsibilities, and permissions, where applicable.
- `user/` contains documentation intended for end users.
- `admin/` contains documentation intended for administrators.
- `ai/` contains project-specific guidance and context for AI-assisted work, including applicable rules, project decisions, and goals.

These directory descriptions define organizational intent rather than an unconditional requirement to maintain every directory. Directories may be added, renamed, reorganized, or removed when justified by the project's needs, provided that the resulting structure remains clear and consistent.

Documents may address the same subject from different perspectives or for different audiences. For example, user documentation may explain how to use a feature while developer documentation describes its implementation. Such documents must remain consistent with the authoritative requirements and contracts. Information that has a single authoritative definition should not be independently maintained in multiple places in ways that could cause contradictions.

Documents with multiple major sections MUST include a table of contents. Short documents with a simple structure MAY omit it.

• • •

## 3.2. Markdown and Formatting Rules

Markdown formatting must be consistent, structurally meaningful, and readable in source form as well as in rendered output. Formatting rules are mandatory where specified by this standard; stylistic choices outside those rules must not undermine clarity, accessibility, or consistency.

Headings must follow a consistent hierarchy. A heading level must not be skipped when introducing a subordinate section. Heading levels must reflect the logical structure of the document rather than being selected for visual appearance alone. Headings at the same level must represent comparable structural importance.

Lists must use consistent syntax and indentation. Nested lists must clearly express their hierarchy. Code blocks must use fenced Markdown syntax and specify the relevant language whenever the language is known. Inline code formatting must be used for code identifiers, file paths, commands, configuration keys, and other literal technical elements when appropriate.

Tables must be used when they make structured information easier to compare or understand. They must not replace explanatory prose when the relationships or constraints require further clarification.

Formatting must preserve meaning. Visual presentation must not be the sole means of communicating a requirement, distinction, warning, or other technically significant information.

• • •

## 3.3. Naming and Terminology

Documentation filenames must use lowercase letters and underscores to separate words, with the `.md` extension for Markdown documents. For example, `coding_style_guide.md` and `network_architecture.md` follow this convention. Filenames should use ASCII characters and avoid spaces or unnecessary special characters.

Technical terms, component names, identifiers, and abbreviations must be used consistently across the documentation. A term with a specialized or potentially ambiguous meaning must be defined when necessary to prevent misinterpretation. A glossary may be introduced when the project's terminology becomes sufficiently extensive to benefit from centralized reference.

Names used for components, APIs, ABI elements, protocols, and other implementation-defined entities must match their authoritative definitions. Documentation must not introduce alternative names that could be mistaken for distinct entities or official terminology.

• • •

## 3.4. Code Examples, Diagrams, and References

Code examples, diagrams, and references must accurately represent the system and support the purpose of the document. Their level of detail and verification must be appropriate to the claims made about them.

Code examples must use fenced Markdown blocks with an appropriate language identifier whenever known. Examples presented as working, compilable, or executable must be verified to the extent necessary to support that claim. Partial, illustrative, or schematic examples must be identified as such when readers could otherwise mistake them for complete implementations. Examples must not silently contradict authoritative interfaces, contracts, or implementation requirements.

Diagrams must be used when they materially improve the explanation of architecture, component relationships, data flow, protocol behavior, or state transitions. They must have a clear purpose and remain consistent with the documented system. Text-based, version-controllable diagram formats should be preferred when they adequately serve the intended purpose. A diagram must not be treated as authoritative when its contents conflict with the applicable normative specification or contract.

References must enable readers to identify and locate the information being referenced. Internal references should use appropriate project-relative paths and identify a relevant heading or section when necessary. External references must provide enough information to identify the intended source. Version, release, commit, or other source-specific details must be included when necessary to make a reference precise and reproducible.

Links and references must be checked for correctness when introduced or modified. Broken, outdated, ambiguous, or misleading references must be corrected. Referenced material must support the claim for which it is cited; the existence of a link alone does not establish the validity of a claim.

___

# 4.0. Writing and Specification Rules

This section defines the rules for writing explanations, specifying requirements, and documenting technical behavior in ÖRÜ. Documentation exists to communicate information effectively. Its writing style may vary according to its purpose and audience, but normative requirements and contracts must define technical behavior precisely and unambiguously.

## 4.1. Writing Style and Language

Documentation must communicate its intended meaning clearly and appropriately for its audience. Writers may use a natural, conversational, humorous, or formal style, provided that the style remains suitable for the document's purpose and does not obscure technical information.

Explanatory content does not need to follow an academic or strictly formal writing style. Conciseness, readability, and effective communication should be prioritized over unnecessary formality. Technical terminology must remain accurate regardless of the writing style.

Normative requirements and contracts are subject to stricter rules than general explanatory content. Informal language must not introduce ambiguity into contractual obligations, technical constraints, or specified behavior.

• • •

## 4.2. Normative Language

Normative statements must use standardized terminology to express the level of obligation. ÖRÜ documentation adopts the RFC-style normative keywords `MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT`, and `MAY`.

These keywords have the following meanings when used normatively:

- **`MUST`**: An absolute requirement that must be satisfied for conformance.
- **`MUST NOT`**: An absolute prohibition.
- **`SHOULD`**: A recommendation that should be followed unless a justified reason exists to choose another approach.
- **`SHOULD NOT`**: A practice that should be avoided unless a justified reason supports its use.
- **`MAY`**: An optional behavior or permitted choice.

When these keywords are used in their normative sense, they must be written in uppercase. Their appearance in ordinary explanatory text does not automatically make that text normative.

Normative statements must distinguish mandatory behavior from recommendations and permitted alternatives. The intended obligation must not depend solely on the reader's interpretation of informal wording.

• • •

## 4.3. Requirements and Constraints

Requirements must describe expected behavior, applicable constraints, or conditions for conformance with sufficient precision for their intended purpose. The level of detail must be appropriate to the requirement and its technical significance.

Where applicable, a requirement should identify the relevant component or operation, expected behavior, applicable conditions, constraints, and means of verification. Verification criteria must be explicitly stated when necessary to establish whether the requirement has been satisfied.

Technical limits must be expressed using precise values and appropriate units. Where relevant, requirements must identify whether a limit is a minimum, maximum, exact value, inclusive boundary, or exclusive boundary. Vague expressions must not replace exact limits when those limits affect implementation, interoperability, security, or conformance.

Dependencies between requirements must be documented when they affect implementation, interpretation, or verification. Relevant dependencies must be listed where appropriate. The responsible author or team must resolve conflicts between requirements before the affected specification is considered finalized.

Requirements must not contradict authoritative contracts or other applicable normative requirements. Unresolved technical contradictions must be corrected before the relevant documentation change can be accepted.

• • •

## 4.4. Preconditions, Postconditions, and Invariants

Every specified operation must document its preconditions and postconditions. These conditions define the circumstances under which an operation may be invoked and the guarantees that apply after its execution.

- **Preconditions** must identify the conditions that must hold before an operation is invoked, including relevant input constraints, required states, resource ownership conditions, or other requirements for valid execution.
- **Postconditions** must describe the guarantees established by an operation, including relevant changes to state, output values, resource ownership, or other observable results.
- **Invariants** must identify conditions that must remain true throughout the applicable scope of a system, component, operation, or data structure.

Invariants must be documented at the relevant level of the system and must be consistent with the applicable architecture and contracts.

Conditions must be sufficiently precise to distinguish valid from invalid states and to establish the guarantees expected from an operation. Where behavior depends on whether a precondition is satisfied, the applicable contract must define the resulting behavior.

• • •

## 4.5. Errors, Failures, and Side Effects

Documentation must define error and failure behavior sufficiently to establish the consequences of unsuccessful operations and the guarantees available to callers or other affected components.

Where applicable, error documentation must identify:

- The conditions that cause an error or failure.
- The observable result, including error codes, return values, status values, or other applicable indications.
- The resulting state of the affected operation, component, or resource.
- The required or permitted recovery behavior, including retries, cleanup, cancellation, or connection termination where relevant.

Side effects must be documented for all relevant execution outcomes, including successful execution, unsuccessful execution, and partial failure. Documentation must identify applicable state changes, resource allocation or release, message transmission, ownership changes, and other effects that can influence subsequent operations.

When an operation fails, its contract must define whether changes are retained, reverted, or left partially applied, as applicable. Atomicity and rollback guarantees must not be implied unless explicitly specified. Resource ownership, cleanup obligations, and retry safety must be documented when they affect correct usage.

Security-relevant error conditions must explicitly address their applicable security implications and required behavior. This includes failures involving untrusted input, authentication or authorization, resource exhaustion, and other conditions that may affect the system's security. Error handling must not leave critical security behavior dependent on unstated assumptions.

___

# 5.0. Architecture and Contracts

This section defines the requirements for documenting ÖRÜ's architecture, architectural decisions, technical contracts, component responsibilities, dependencies, security boundaries, and implementation conformance. Architectural documentation and contracts are integral parts of project documentation. They must collectively provide a consistent, precise, and verifiable description of the intended system and its required behavior.

## 5.1. Architectural Documentation

All architectural decisions must be documented, without exception. Architectural documentation must describe the decisions governing the system's structure, component relationships, design constraints, and relevant implementation choices. Recording architectural decisions is mandatory, not optional.

Each architectural decision must document the decision itself, its rationale, the alternatives considered, and the consequences of the chosen approach. The level of detail must be sufficient to understand why the decision was made, which constraints it establishes, and how it affects the system.

Architectural documentation must remain consistent with the approved architecture and applicable contracts. When implementation conflicts with an approved architectural decision, the implementation must be corrected to conform to that decision. Changes to the architecture must follow the established change and approval procedures; implementation differences must not silently redefine the approved architecture.

Architectural documents must identify relevant relationships and dependencies between components and reference applicable contracts where necessary. Architectural explanations must not contradict normative requirements or replace the authoritative definitions of contractual behavior.

• • •

## 5.2. Contract Specification

Contracts are normative project documentation that define required behavior and the obligations of their implementations and consumers. Every contract must specify its applicable scope and define behavior precisely enough to prevent materially different interpretations.

A contract must document all applicable aspects of the behavior it governs, including:

- Interfaces, inputs, outputs, and their constraints.
- Preconditions, postconditions, and applicable invariants.
- Error conditions, failure behavior, and recovery guarantees.
- Observable side effects and state changes.
- Resource ownership, lifetime, allocation, release, and cleanup obligations.
- Dependencies, execution constraints, and other conditions that affect correct use.
- Security-relevant guarantees, assumptions, and limitations.

The contract must define relevant boundary conditions and distinguish guaranteed behavior from optional behavior, implementation details, and unspecified behavior. Unspecified behavior must not be used to conceal ambiguity concerning required behavior.

API and ABI contracts must be documented separately in their respective directories and documents:

- `api/` contains API contracts.
- `abi/` contains ABI contracts.

API and ABI contracts must remain conceptually distinct and must define the requirements applicable to their respective interfaces. Their physical separation is mandatory. Where they depend on shared requirements or architectural decisions, the relevant documents must reference those authoritative definitions.

Contracts must remain consistent with approved architectural decisions and other applicable normative documentation. Contract changes must follow the established change and approval procedures.

• • •

## 5.3. Component Responsibilities and Dependencies

Documentation must describe component responsibilities and internal design in sufficient detail to establish each component's role, boundaries, and relationships within the system. Component documentation must identify the component's purpose, responsibilities, internal structure where relevant, interfaces, and interactions with other components.

Component responsibilities must be described precisely enough to distinguish the work assigned to a component from the work assigned to other components. Relevant limitations and responsibilities that belong to other components must be made clear. Documentation must not leave important responsibilities or interactions dependent on unstated assumptions.

All relevant direct and indirect dependencies must be documented. Dependency documentation must describe the dependency relationships necessary to understand the system's structure, including transitive dependencies, dependency direction, and relevant lifecycle or initialization relationships. The complete dependency graph must be documented wherever necessary to represent the system accurately.

Dependency constraints must be stated explicitly when they govern the architecture. If a dependency is prohibited, restricted, or required to follow a particular direction, the applicable documentation must identify that constraint. Circular dependencies and other relationships that affect architectural correctness must be documented and addressed according to the applicable architectural requirements.

Component documentation must remain consistent with the approved architecture and applicable contracts. Changes to component responsibilities or dependency relationships must be reflected in the relevant documentation through the established change process.

• • •

## 5.4. Security and Trust Boundaries

Security architecture and trust boundaries must be documented comprehensively. Relevant architectural documentation must include a threat model covering the system's assets, adversaries, attack surfaces, threats, trust assumptions, and applicable mitigations.

Trust boundaries must be identified wherever components, peers, processes, or other entities differ in their level of trust or authority. Documentation must explain the security significance of these boundaries and specify the controls required to enforce them.

Security documentation must address applicable concerns, including:

- Untrusted peers and network inputs.
- Authentication, identity verification, and authorization.
- Cryptographic keys, sensitive information, and their handling.
- Trust relationships between components and external entities.
- Threats arising from malformed input, malicious behavior, resource exhaustion, and protocol misuse.
- Security controls, their assumptions, and their limitations.
- Failure behavior and required security properties when a control cannot operate as intended.

Security guarantees must be stated precisely and must distinguish established properties from assumptions. Documentation must identify the conditions on which a guarantee depends and clarify what the system does not guarantee. Unsupported claims about security, privacy, anonymity, or resistance to attacks must not be presented as established facts.

Security requirements must be reflected in the applicable architecture and contracts. Relevant documents must reference one another where necessary to maintain consistency and traceability. A threat model does not replace the detailed security requirements governing individual components or operations.

• • •

## 5.5. Implementation Conformance

The implementation must conform exactly to the applicable approved contracts, architectural requirements, and other normative specifications, except during the explicitly permitted MVP development phase.

During MVP development, implementation may precede full contractual conformance. The preferred approach is to establish an initial MVP and subsequently bring the implementation into conformance with the approved contracts. MVP status is a limited development-phase allowance, not a permanent exemption from contractual requirements.

Outside the MVP phase, implementation must not intentionally deviate from applicable contracts. Conformance must be assessed through appropriate methods, including testing, code review, static analysis, or other verification techniques suitable for the requirements concerned.

When implementation and an approved contract disagree, the implementation must be corrected to conform to the contract. The contract must not be changed merely to legitimize existing implementation behavior. Contract changes require the established review and approval procedure and must reflect an intentional, authorized change to the required behavior.

During MVP development, deviations and incomplete conformance must remain identifiable and must not be represented as full conformance. Before the MVP is considered contractually conformant, the relevant discrepancies must be resolved and the implementation must be verified against the applicable requirements.

Unresolved non-conformance outside the permitted MVP phase must be corrected before the affected change can be accepted. Documentation, implementation, and verification results must remain consistent with the approved contracts and architectural decisions.

___

# 6.0. Accuracy and References

This section establishes the requirements for technical accuracy, verification, source attribution, version identification, and reference integrity in ÖRÜ documentation. Technical information must be sufficiently reliable and traceable for its intended purpose. Documents must identify their version and maintenance history, distinguish verified facts from uncertain information, and preserve the context necessary to interpret technical claims correctly.

## 6.1. Technical Accuracy and Verification

Technical claims must be verified using methods appropriate to their nature, significance, and verifiability. Verification methods may include authoritative documentation, technical standards, source code inspection, tests, experiments, measurements, and analysis. No single verification method must be assumed sufficient for every type of claim.

Claims affecting architecture, protocol behavior, security, interoperability, API or ABI compatibility, and implementation conformance must be supported by appropriate evidence. The evidence must be relevant to the specific claim and sufficiently reliable to justify its presentation as established fact.

Unverified assumptions, hypotheses, estimates, and claims may be included when they are relevant to the document's purpose. Their status must be explicitly identified, and material uncertainties, limitations, and dependencies must be stated. Unverified information must not be presented as established fact or used as the sole justification for a normative requirement without appropriate qualification.

Verification must distinguish between a specification's stated requirements and an implementation's observed behavior. Evidence that an implementation behaves in a particular way does not, by itself, establish that the behavior conforms to the applicable specification or contract.

• • •

## 6.2. Sources and Citations

Technical claims, external requirements, third-party behavior, standards, and other information requiring traceability must be supported by appropriate sources. Internal architectural decisions, requirements, and contracts must also be traceable to their authoritative project documents when such traceability is necessary to establish their origin or meaning. General knowledge does not require unnecessary citations.

Reliable primary sources, including official standards, authoritative project documentation, official API references, and relevant source code, should be preferred. Reliable secondary sources may be used when appropriate. Source selection must consider authority, relevance, scope, version, and whether the source actually supports the associated claim.

Sources must be identified using a consistent citation method. Each document must include a bibliography or equivalent source list when its references require one. Citations may direct readers to that bibliography as a recommended practice, provided that the relationship between a claim and its supporting source remains clear and traceable.

Where necessary, citations must identify the relevant section, page, version, release, commit, or other details required to locate the supporting information. A source's existence or apparent authority does not establish that it supports the claim being made.

When sources conflict, the author must evaluate their authority, scope, version, and relevance. Official or authoritative sources should take precedence over less authoritative sources when they govern the same subject and scope. If a contradiction cannot be resolved, the uncertainty must be disclosed and the affected claim must not be presented as definitively established.

• • •

## 6.3. Version-Specific Information

Every document must include a detailed document record identifying its metadata and maintenance history. At a minimum, the document record must identify the document's author, the module or subject to which it applies, its version, and the date of its most recent update. Additional metadata must be included where necessary to identify the document's scope, status, ownership, or applicability.

Every document must have an explicit version. Version information must be maintained consistently with the project's version-management and change-history requirements. The document's version and update history must remain traceable through the applicable documentation and version-control processes.

Changelogs must include the version associated with each recorded change. Entries must provide enough information to identify the relevant revision and understand the nature of the change. Version and history information must not be omitted merely because a document is considered internal or unlikely to change frequently.

Technical information that depends on a particular software release, protocol version, standard revision, dependency version, or other versioned reference must identify the applicable version. Where compatibility or behavior differs between versions, the relevant differences and supported scope must be documented explicitly.

API and ABI documentation must reflect ÖRÜ's stable-additive-only compatibility policy. Existing API or ABI elements must not be silently redefined or removed in a manner that violates the applicable compatibility requirements.

Deprecated API or ABI elements must remain documented. Their documentation must identify their deprecated status, the reason and justification for deprecation, and the recommended alternative where one exists. Deprecation records must be retained rather than erased merely because an element is no longer recommended for use. Documentation changes must preserve the historical and compatibility information necessary to understand existing interfaces and their evolution.

• • •

## 6.4. Examples and Reference Integrity

Code examples, commands, configuration samples, protocol messages, and other technical examples must accurately represent the behavior or structure they are intended to demonstrate. Their level of verification must correspond to the claims made about them.

Examples presented as executable, compilable, or operational must be verified to the extent necessary to support those claims. Partial, schematic, illustrative, or otherwise incomplete examples must be identified as such whenever their presentation could cause readers to mistake them for complete or directly usable implementations.

Examples must remain consistent with the applicable contracts, architectural requirements, and version-specific behavior. Protocol examples, interface declarations, and configuration samples must not contradict authoritative specifications. Where an example depends on a specific version, environment, or prerequisite, that dependency must be stated.

References must point to the intended sources and provide enough information to locate the relevant material. Internal references must remain consistent with the project's documentation structure, while external references must identify the intended external resource and its relevant version or scope where necessary.

References must be checked for correctness when they are introduced or modified. Known broken, outdated, or misleading references must be corrected. When a referenced resource changes or becomes unavailable, the affected documentation must be reviewed to determine whether its claims remain accurate and whether the reference requires replacement or additional context.

Examples and references must support the claims they accompany. Neither a plausible example nor the presence of a citation alone establishes technical correctness.

___

# 7.0. Review and Maintenance

This section defines the review, acceptance, change management, conflict resolution, correction, and lifecycle requirements for ÖRÜ documentation. Documentation must remain accurate, consistent with approved architectural decisions and contracts, and suitable for its intended purpose throughout the project's development. Review and maintenance procedures must ensure that technical violations are identified and resolved, changes remain traceable, and obsolete information does not mislead contributors.

___

## 7.1. Review and Acceptance Criteria

Every documentation change must undergo review before acceptance. The scope and depth of the review must be proportionate to the change's impact and risk. Changes affecting architecture, contracts, protocol behavior, security, API or ABI compatibility, or implementation conformance require more comprehensive review than changes limited to non-technical details.

Acceptance must be based on a holistic assessment that includes:

- Conformance with this standard and other applicable documentation rules.
- Technical accuracy and adequate verification of relevant claims.
- Consistency with approved architectural decisions, contracts, and other authoritative requirements.
- Completeness within the document's intended scope.
- Correctness and traceability of sources, references, examples, and version-specific information where applicable.
- Sufficient precision to prevent materially different interpretations of normative requirements.
- Completion of the required review and resolution of identified technical violations.

Review and acceptance must be traceable through the project's version-control system or established project workflow. The records must provide sufficient information to identify the reviewed change and its review or acceptance status.

A change must not be accepted while unresolved technical violations remain. Non-technical violations must also be corrected; however, minor formatting or stylistic issues do not independently block acceptance when all applicable technical acceptance criteria are satisfied.

• • •

## 7.2. Change Management

Changes to documentation must follow a controlled process proportionate to their impact. The process must identify affected documents, requirements, contracts, architectural decisions, and dependent components where relevant. Changes affecting normative behavior, architecture, security, or compatibility must receive the appropriate review and authorization before becoming authoritative.

Changes to this standard require team consensus. No unilateral change may be treated as an approved revision. Other documentation changes must follow the applicable project review and approval procedures.

Documentation must not be changed merely to legitimize existing implementation behavior or conceal a discrepancy. When an approved requirement or contract remains unchanged, the implementation must be corrected to conform to it. If a requirement or contract genuinely needs to change, that change must be intentional, justified, reviewed, and approved through the established procedure. The implementation and all affected documentation must then be brought into consistency with the newly approved requirements.

Code changes must not silently invalidate or redefine authoritative documentation. When a code change affects documented behavior, the change must be evaluated against the existing approved requirements and contracts. If the implementation no longer conforms, it must be corrected unless an intentional and authorized change to the applicable requirements has been approved.

Documentation updates required by a change must be included in the change's acceptance criteria. The scope of the update must be determined by the actual impact; documents that are not affected must not be modified unnecessarily.

Changes must preserve the traceability of decisions, requirements, and relevant historical information through the project's version-control and documentation processes.

• • •

## 7.3. Conflict and Inconsistency Resolution

Conflicts between documents, requirements, contracts, architectural decisions, or implementation behavior must be resolved through a controlled process. The process must identify the scope and consequences of the conflict, determine which authoritative requirements and approved decisions apply, and establish the corrections necessary to restore consistency.

The resolution process must:

- Identify the conflicting statements, requirements, or observed behaviors.
- Determine the authoritative sources and approved decisions governing the affected subject.
- Evaluate the scope, dependencies, and technical consequences of the conflict.
- Coordinate the resolution with the responsible contributors and obtain the required approval.
- Update affected documents, contracts, or implementation components as necessary to restore consistency.
- Verify the resulting state against the applicable requirements.

The most recently modified document or implementation must not automatically take precedence. Authority must be determined by the applicable approval and change-management procedures, the scope of the relevant requirements, and the established hierarchy of authoritative project documentation.

Implementation behavior must not, by itself, override an approved contract or architectural decision. If the implementation conflicts with an unchanged authoritative requirement, the implementation must be corrected. If the requirement itself needs to change, the change must first be authorized through the applicable procedure.

Unresolved technical conflicts must be documented with their known impact and must not be concealed by an arbitrary interpretation. The affected change must not be accepted until the conflict is resolved. Unrelated work may continue when it is not materially affected by the unresolved conflict.

• • •

## 7.4. Non-Conformance and Corrections

Documentation that violates this standard, an applicable contract, an approved architectural decision, or another authoritative requirement must be corrected. Non-conformance must be assessed according to its technical significance and impact.

Technical violations affecting correctness, security, interoperability, contractual behavior, or implementation conformance must be resolved before the affected change can be accepted. Minor non-technical violations must also be addressed, but they do not independently prevent acceptance when the applicable technical acceptance criteria have been satisfied.

Corrections must restore consistency with the applicable authoritative requirements. A correction must not introduce an unauthorized change to architecture, contracts, or specified behavior merely to accommodate an existing implementation.

When correcting non-conforming documentation, contributors must assess whether related documents, examples, references, tests, or implementation components are also affected. Necessary corrections must be included in the applicable change so that the inconsistency is not merely transferred elsewhere.

Corrections must preserve relevant history through version control. Where a correction materially changes a requirement, contract, architectural decision, or other significant technical statement, its change history must provide sufficient information to identify the nature and context of the change.

• • •

## 7.5. Documentation Lifecycle

Every document must be managed throughout its lifecycle, including creation, review, acceptance, maintenance, versioning, and eventual retirement or archival when applicable. Lifecycle management must preserve the document's authority, applicability, and historical context.

New documents must comply with this standard before acceptance. Existing documents must be reviewed and updated when relevant requirements, architecture, contracts, implementation constraints, dependencies, or other material information change. Changes must follow the established review, approval, version-management, and acceptance procedures.

Documents that are no longer current or applicable must not remain presented as authoritative current documentation. Their status and scope must be clearly identified, and their historical content must be preserved when it remains relevant to understanding previous decisions, requirements, interfaces, or compatibility.

Retired documents must be retained as historical records when appropriate to preserve traceability and the history of the project. Their status must clearly indicate that they are retired or superseded, and they should link to replacement documentation when a replacement exists. Historical documents must not be mistaken for current normative requirements.

Archival or retirement must not silently erase information required to understand existing or deprecated interfaces, previous contractual obligations, compatibility constraints, or approved architectural decisions. In particular, deprecated API and ABI elements must remain documented in accordance with the project's compatibility requirements.

The lifecycle status of a document must be consistent with its actual use and authority. Documentation maintenance must ensure that current requirements remain discoverable, superseded information remains distinguishable, and historical decisions remain traceable through the project's established records.

___

## Notes

> **AI Usage Notice:** This document was written by artificial intelligence in accordance with the architecture, rules, and standards provided by the developer, and has been reviewed by a human.
