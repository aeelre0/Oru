# Contributor Guide

> **Author:** Ali Emre Arlı
> **Module:** Development
> **Version:** 1.0.0
> **Last Updated:** 2026-10-20
> **Status:** Draft

This document serves as the primary entry point for anyone who wants to contribute to the ÖRÜ project. It introduces contributor roles and responsibilities, explains how to prepare the development environment, and provides a structured path for understanding the project's rules, architecture, and contribution workflow. All contributors must follow the applicable project standards and consult authoritative documentation before making changes.

___

# 0.0. Table of Contents

* 1.0. Introduction
    * 1.1. Purpose
    * 1.2. Scope
    * 1.3. Intended Audience

* 2.0. Contributor Roles and Responsibilities
    * 2.1. Definition of a Contributor
    * 2.2. Contributor Roles
    * 2.3. Responsibilities and Expectations
    * 2.4. Technical and Architectural Boundaries

* 3.0. Onboarding and Documentation Reading Order
    * 3.1. Initial Entry Point
    * 3.2. Mandatory Initial Reading
    * 3.3. Architecture and Module Documentation
    * 3.4. Additional Documentation

* 4.0. Development Environment Setup
    * 4.1. Supported Development Tools
    * 4.2. Repository Setup
    * 4.3. Dependencies and Vendor Directory
    * 4.4. Build and Test Environment

* 5.0. Understanding the ÖRÜ Project
    * 5.1. Project Architecture
    * 5.2. Module Organization
    * 5.3. Contracts and Implementation Requirements
    * 5.4. Security and Trust Boundaries

* 6.0. Contribution Workflow
    * 6.1. Identifying and Understanding a Task
    * 6.2. Planning Changes
    * 6.3. Implementing Changes
    * 6.4. Updating Documentation
    * 6.5. Preparing a Contribution

* 7.0. Verification and Review
    * 7.1. Build and Test Verification
    * 7.2. Coding and Documentation Compliance
    * 7.3. Review and Acceptance
    * 7.4. Non-Conformance and Corrections

* 8.0. Questions and Troubleshooting
    * 8.1. Resolving Development Issues
    * 8.2. Handling Unclear or Conflicting Requirements
    * 8.3. Requesting Clarification

* 9.0. Related Resources
    * 9.1. Project Overview and Architecture
    * 9.2. Contribution Standards
    * 9.3. Technical References
    * 9.4. Contact and Communication

* Notes

___

# 1.0. Introduction

This section establishes the purpose, scope, and intended audience of the Contributor Guide. It defines the role of this document within the ÖRÜ project and clarifies who is expected to use it.

## 1.1. Purpose

This document provides a common starting point for individuals contributing to the ÖRÜ project. It explains the responsibilities of contributors, identifies the documentation they must read, and outlines the procedures and requirements they must follow when contributing to the project.

• • •

## 1.2. Scope

This document covers contributor onboarding, development environment preparation, project familiarization, contribution workflows, and verification and review expectations. It also directs contributors to the authoritative documentation governing the project's architecture, contracts, coding practices, and documentation standards.

This document does not replace or override those authoritative documents. Contributors MUST consult and follow the applicable specifications, contracts, and standards when performing project work.

• • •

## 1.3. Intended Audience

This document is intended for everyone contributing to the ÖRÜ project, regardless of their role. This includes, but is not limited to, developers, testers, reviewers, and documentation contributors.

Readers are expected to consult the project documentation relevant to their responsibilities and MUST NOT assume that familiarity with one area of the project is sufficient to make changes in another.

___

## 2.0. Contributor Roles and Responsibilities

This section defines who qualifies as a contributor to the ÖRÜ project, identifies the recognized contributor roles, and establishes the responsibilities and boundaries applicable to contributors. It distinguishes individual contribution autonomy from the review and acceptance requirements for changes intended to be published in the project's mainline repository.

## 2.1. Definition of a Contributor

A contributor is any individual who contributes to the ÖRÜ project through activities such as software development, testing, documentation, review, maintenance, design, or other project-related work.

Contributor status is not limited to individuals who directly modify source code. Contributions in any relevant area of the project are covered by this definition.

• • •

## 2.2. Contributor Roles

The ÖRÜ project recognizes the following contributor roles:

- **Developer:** Contributes to software implementation and related technical work.
- **Tester:** Contributes to testing and verification activities.
- **Reviewer:** Examines proposed changes for correctness, consistency, and compliance with applicable project requirements.
- **Documentation Contributor:** Creates, reviews, or maintains project documentation.
- **Maintainer:** Contributes to the ongoing maintenance of the project.
- **Designer:** Contributes to the design of project components, systems, or architecture.

These roles describe areas of contribution and responsibility. An individual MAY perform more than one role.

• • •

## 2.3. Responsibilities and Expectations

All contributors are responsible for ensuring that their contributions comply with the applicable project contracts, specifications, standards, and approved architectural decisions.

Contributors MUST:

- Follow the applicable project documentation and requirements.
- Ensure that their contributions are consistent with the relevant contracts and specifications.
- Identify and communicate known issues, uncertainties, and relevant limitations in their contributions.
- Update relevant documentation when their changes affect documented behavior, interfaces, requirements, or architectural decisions.
- Follow the applicable review and approval processes when proposing changes for inclusion in the mainline repository.

Important project decisions MUST be made through team consensus. Individual contributors MAY propose decisions and changes within their areas of work, but proposals that affect shared project decisions remain subject to the applicable team decision-making process.

• • •

## 2.4. Technical and Architectural Boundaries

Contributors MAY independently develop and propose changes within their areas of work. However, changes that affect the project's architecture, contracts, or other shared technical decisions MUST undergo the applicable review and approval process before being adopted.

Contributors MUST follow existing applicable contracts and standards. When a change to an existing contract, standard, or architectural decision is necessary, the contributor MUST follow the relevant change process rather than unilaterally treating the existing requirement as modified.

Contributors who want their work to be published in the project's mainline repository MUST submit the proposed changes for review. Such changes are subject to review before acceptance into mainline. The ability to develop or propose a change does not, by itself, grant the authority to publish it directly to the mainline repository.

The review and acceptance process is intended to ensure that proposed changes are evaluated against the project's applicable requirements and shared decisions.

___

# 3.0. Onboarding and Documentation Reading Order

This section defines the initial documentation reading order for contributors joining the ÖRÜ project. It identifies the documents that MUST be read before beginning project contributions and explains how contributors should consult additional documentation relevant to their tasks.

## 3.1. Initial Entry Point

Individuals joining the ÖRÜ project MUST first read the project's `README` file to obtain an initial understanding of the project.

After reading the `README`, contributors MUST read `docs/dev/contributor_guide.md` to understand contributor roles, responsibilities, onboarding requirements, and the applicable contribution procedures.

• • •

## 3.2. Mandatory Initial Reading

Before beginning any project contribution, contributors MUST read the following documents:

- `code_of_conducts.md`
- `documentation_writing_rules.md`
- `coding_style_guide.md`, specifically its `0.5. Core Coding Rules` section.

Contributors MUST comply with the applicable requirements established by these documents.

Reading the `0.5. Core Coding Rules` section satisfies the initial coding-style reading requirement. Contributors are not required to read the entire `coding_style_guide.md` during onboarding. Its remaining sections MUST be consulted as needed when performing work to which those sections apply.

• • •

## 3.3. Architecture and Module Documentation

After completing the mandatory initial reading, contributors MUST read the following documents to develop an understanding of the project's architecture and module organization:

- `modules.dev.md`
- `oru.architecture.md`

These documents MAY be read in either order. Both MUST be consulted as part of the initial onboarding process.

• • •

## 3.4. Additional Documentation

In addition to the documents specified in the preceding sections, contributors MUST identify and consult the project documentation relevant to their assigned tasks and proposed changes.

The required documentation depends on the scope and nature of the work. Contributors MUST consult applicable contracts, specifications, standards, and other authoritative project documents before making changes that fall within their scope.

Contributors MUST complete the mandatory initial reading defined in Sections 3.1 and 3.2 before beginning project contributions. Additional documentation MUST be consulted as required to perform the relevant work correctly and in compliance with project requirements.

___

# 4.0. Development Environment Setup

This section describes the supported development tools, repository preparation, dependency organization, and build and test environment for the ÖRÜ project. It provides contributors with the baseline information needed to prepare their local development environments without assuming commands or procedures that have not yet been established.

## 4.1. Supported Development Tools

The ÖRÜ project uses the C11 language standard and supports the following compilers:

- **GCC:** A supported C compiler.
- **Clang:** A supported C compiler.

The project also supports the following development tools:

- **clangd:** A language server for C development and editor integration.
- **Git:** The version control system used to work with the project repository.
- **CMake:** The project's build system.
- **Debugger:** A debugging tool used to investigate program behavior and diagnose defects.

The supported development environment is Linux.

Contributors MUST use tools and configurations compatible with the project's established requirements. Specific minimum tool versions and additional configuration requirements are not defined in this section.

• • •

## 4.2. Repository Setup

Contributors MUST obtain a local working copy of the ÖRÜ repository before beginning development work.

The repository MUST be prepared in accordance with the project's established structure and applicable development requirements. Contributors SHOULD familiarize themselves with the repository layout before modifying project files.

This section does not prescribe repository addresses, clone commands, branch names, or additional setup commands that have not been established by the project.

• • •

## 4.3. Dependencies and Vendor Directory

The ÖRÜ project organizes its external dependencies under the `vendor/` directory.

Contributors MUST respect the existing dependency organization when working with external libraries or other third-party components. Dependency-related changes MUST comply with the applicable project contracts, standards, and requirements.

At present, no additional external dependency installation requirement has been established for the development environment.

Any future dependency-related requirements MUST be handled in accordance with the project's applicable development and dependency management procedures.

• • •

## 4.4. Build and Test Environment

The ÖRÜ project uses CMake as its build system. Contributors MUST use a CMake-compatible development environment and a supported C compiler to build the project.

The project supports GCC and Clang under Linux, using the C11 language standard.

Specific build commands, configuration options, and test execution procedures are not defined in this section. Contributors MUST consult the applicable project documentation for established instructions and MUST NOT assume that unverified commands or test procedures are authoritative.

The test environment and its execution procedures have not yet been specified in this guide. Contributors MUST NOT interpret this absence as confirmation that the project has no tests or that testing is unnecessary.

___

# 5.0. Understanding the ÖRÜ Project

This section explains how contributors are expected to understand the ÖRÜ project's architecture, module organization, contracts, and security requirements before making changes. It identifies the relevant documentation and establishes how contributors must handle architectural constraints, contractual requirements, and undocumented technical assumptions.

## 5.1. Project Architecture

The `oru.architecture.md` document is the primary reference for understanding the architecture of the ÖRÜ project.

Contributors MUST consult this document to understand the architectural structure and principles relevant to their work. Before proposing changes that affect the architecture, contributors MUST evaluate those changes against the documented architecture and follow the applicable review and approval processes.

This guide does not redefine the project's architecture. The applicable architectural documentation remains the reference for architectural requirements and decisions.

• • •

## 5.2. Module Organization

The `modules.dev.md` document is the starting point for understanding the organization of the project's modules.

Contributors MUST consult this document to identify the modules relevant to their work. They MUST also read the applicable documentation for any module they intend to modify and consider relevant dependencies and interactions with other modules.

Changes affecting module boundaries, interactions, or shared responsibilities MUST be evaluated against the applicable architectural documentation and contracts.

• • •

## 5.3. Contracts and Implementation Requirements

Project contracts define requirements that implementations MUST satisfy. Contributors MUST identify and follow the applicable contracts before implementing changes and before submitting completed work for review.

During MVP development, temporary implementation non-conformities MAY exist. Such non-conformities MUST remain identifiable and be tracked for correction in accordance with the applicable project requirements.

However, the existence of an MVP development phase does not exempt submitted contributions from contractual requirements. Contributors MUST ensure that completed code, tests, and other submitted artifacts comply with the applicable contracts before submitting them for review.

Contributors MUST NOT unilaterally modify or disregard an existing contract. Proposed contract changes MUST follow the applicable review and approval process.

When a contributor identifies an existing implementation that does not conform to an applicable contract, the contributor MUST document and report the discrepancy. Any correction or proposed contract change MUST be handled through the relevant review and decision-making process.

• • •

## 5.4. Security and Trust Boundaries

Contributors MUST consult the applicable project security documentation when working on components or changes relevant to security, trust, or communication between peers.

Security requirements, threat assumptions, and trust boundaries MUST be derived from the applicable project documentation. This guide does not establish new security properties or replace the project's security specifications.

Contributors MUST NOT assume that a security property exists merely because it is desirable or commonly associated with P2P or mesh networks. Properties such as authentication, encryption, anonymity, and peer trust MUST NOT be treated as implemented or guaranteed unless supported by the applicable project documentation and implementation requirements.

When security requirements, trust assumptions, or relevant documentation are unclear or inconsistent, contributors MUST document and report the uncertainty and seek clarification through the applicable project review process.

___

# 6.0. Contribution Workflow

This section describes the workflow contributors SHOULD follow when identifying tasks, planning and implementing changes, updating documentation, and submitting completed contributions for review. It establishes the expectations for preparing contributions while preserving the project's applicable contracts, standards, and architectural decisions.

## 6.1. Identifying and Understanding a Task

Contributors MAY identify and propose tasks independently. Before beginning work, they MUST examine the relevant requirements, applicable project documentation, and existing implementation to understand the task and avoid unnecessary duplication.

Contributors MUST identify the contracts, specifications, standards, and module documentation relevant to the proposed work. They MUST also consider whether existing work or ongoing changes may affect the task.

When the task's requirements or intended scope are unclear, contributors SHOULD seek clarification before proceeding with changes that depend on unresolved assumptions.

• • •

## 6.2. Planning Changes

Before implementing a change, contributors MUST understand its intended scope, identify the affected modules, and review the applicable contracts and architectural requirements.

Contributors MUST consider the potential effects of their proposed changes on existing interfaces, module interactions, documented behavior, and other relevant project requirements.

Changes that extend beyond the understood scope of a task MUST be evaluated separately. Contributors MUST NOT treat an initially limited task as authorization to introduce unrelated changes or modify shared project decisions.

Changes affecting existing contracts or architectural decisions MUST follow the applicable review and approval processes.

• • •

## 6.3. Implementing Changes

Contributors MUST implement changes in accordance with the applicable contracts, specifications, coding standards, and approved architectural decisions.

Contributors MUST NOT unilaterally disregard or modify established requirements. When an implementation change requires a modification to an existing contract, standard, or architectural decision, the contributor MUST follow the applicable change process.

If a contributor identifies a discrepancy between an existing implementation and an applicable requirement, the discrepancy MUST be documented and reported. Any proposed correction or change to the governing requirement MUST be handled through the relevant review and decision-making process.

Implementation work MUST remain within the understood scope of the task unless an expanded scope has been appropriately evaluated.

• • •

## 6.4. Updating Documentation

Contributors MUST evaluate whether their changes affect existing project documentation.

When a change affects documented behavior, interfaces, contracts, requirements, module responsibilities, architecture, or other documented information, the relevant documentation MUST be updated as part of the contribution.

Documentation changes MUST comply with `documentation_writing_rules.md` and other applicable project standards.

Contributors SHOULD avoid unrelated documentation changes that do not contribute to the correctness, completeness, or consistency of the work being submitted.

• • •

## 6.5. Preparing a Contribution

Contributors MUST submit completed contributions for review through the applicable project submission process when they intend their work to be incorporated into the project's mainline repository.

A contribution submitted for formal review MUST:

- Be complete within its declared scope.
- Conform to the applicable contracts, specifications, standards, and approved architectural decisions.
- Include the relevant code, tests, documentation, or other artifacts required by the task.
- Include the results of applicable verification activities, such as relevant build or test results, where those activities are established and applicable.
- Include updates to affected documentation when required.

Contributors MUST NOT present incomplete work as a completed contribution for formal review. Drafts and partial work MAY be discussed within the team for feedback before formal submission.

Submitting a contribution does not guarantee its acceptance. Submitted work is subject to review, and acceptance depends on compliance with the applicable project requirements and the outcome of the review process.

Contributors MUST NOT assume that submitting a contribution grants permission to publish it directly to the mainline repository.

___

# 7.0. Verification and Review

This section defines the verification and review requirements for contributions to the ÖRÜ project. It establishes expectations for build and test verification, coding and documentation compliance, review and acceptance, and the correction of non-conformities before a contribution can be accepted.

## 7.1. Build and Test Verification

Contributors MUST perform the applicable build and test verification activities established for their contributions before submitting them for review.

When relevant build procedures are available and applicable, contributors MUST execute them and include the results in their submissions. Contributors MUST NOT claim that a build has succeeded unless the result has been verified.

Contributors MUST execute applicable tests and include the relevant test results in their submissions. A contribution MUST NOT be considered complete while an applicable test failure remains unresolved.

When a build or test cannot be executed, contributors MUST clearly document the limitation and report it as part of the submission. They MUST NOT present unperformed verification activities as completed.

• • •

## 7.2. Coding and Documentation Compliance

Contributions MUST be evaluated for correctness, compliance with applicable contracts and specifications, adherence to coding standards, consistency with approved architectural decisions, and appropriate handling of relevant error conditions.

Contributors MUST ensure that their code complies with `coding_style_guide.md` and other applicable coding requirements. Reviewers and other participants in the review process MUST consider compliance with these requirements when evaluating proposed changes.

For every contribution, contributors MUST evaluate whether existing documentation needs to be updated. When a change affects documented behavior, interfaces, contracts, requirements, architecture, module responsibilities, or other documented information, the relevant documentation MUST be updated as part of the contribution.

Documentation changes MUST comply with `documentation_writing_rules.md` and other applicable documentation requirements.

A contribution MUST NOT be accepted while unresolved non-conformities with applicable contracts, specifications, standards, or approved architectural decisions remain.

• • •

## 7.3. Review and Acceptance

Contributions intended for inclusion in the mainline repository MUST undergo review before acceptance. The review process MUST evaluate the contribution against the applicable project requirements, including contracts, specifications, coding standards, documentation standards, and approved architectural decisions.

The review process MUST consider the correctness and completeness of the proposed changes, the results of applicable verification activities, and whether relevant documentation has been updated.

Review and acceptance MUST follow the project's team decision-making principles. Acceptance of a contribution MUST require team consensus.

The right to propose, implement, or review a change does not, by itself, grant authority to accept it or publish it directly to the mainline repository.

A contribution MUST NOT be accepted until applicable requirements have been satisfied and the required consensus has been reached.

• • •

## 7.4. Non-Conformance and Corrections

When a contribution fails to comply with an applicable contract, specification, standard, approved architectural decision, or other governing requirement, it MUST NOT be accepted until the non-conformity has been resolved.

The identified non-conformities MUST be communicated to the contributor so that the necessary corrections can be made. The contributor MUST address the identified issues and resubmit the updated contribution for review.

Corrections MUST preserve compliance with all applicable requirements. Contributors MUST NOT resolve a non-conformity by unilaterally disregarding or modifying the requirement that governs it. Proposed changes to existing contracts, standards, or architectural decisions MUST follow the applicable change and approval processes.

After resubmission, the updated contribution MUST undergo review before it can be accepted. The review MUST determine whether the identified non-conformities have been resolved and whether the updated contribution continues to satisfy the applicable requirements.

___

# 8.0. Questions and Troubleshooting

This section establishes how contributors are expected to investigate development issues, handle unclear or conflicting requirements, and request clarification from the team. It aims to support consistent problem-solving while preventing unresolved uncertainties from leading to unsupported assumptions or unauthorized changes to project requirements.

## 8.1. Resolving Development Issues

When encountering a development issue, contributors SHOULD first investigate the problem by examining the relevant project documentation, applicable contracts and specifications, existing implementation, and available error information.

If the issue cannot be resolved through reasonable investigation, contributors SHOULD seek assistance from the team through the established project communication channels.

Contributors MUST distinguish between verified information and assumptions when investigating or reporting issues. They MUST NOT treat an unverified assumption as an established project requirement or technical fact.

When an issue prevents work from proceeding correctly, contributors MUST identify the affected work and avoid making changes that depend on unresolved assumptions.

• • •

## 8.2. Handling Unclear or Conflicting Requirements

When a requirement is unclear, incomplete, or inconsistent with other applicable requirements, contributors MUST document the uncertainty or conflict and report it to the team.

Contributors MUST NOT unilaterally disregard, override, or modify an applicable contract, specification, standard, or approved architectural decision to resolve a conflict.

Changes that depend on an unresolved, work-blocking uncertainty MUST be suspended until the necessary clarification or decision has been obtained. Work that does not depend on the unresolved issue MAY continue, provided that it remains compliant with applicable project requirements.

When resolving a conflict requires modifying an existing requirement, contract, standard, or architectural decision, the proposed modification MUST follow the applicable review and approval process.

• • •

## 8.3. Requesting Clarification

When requesting clarification, contributors SHOULD provide sufficient information for the team to understand the issue and make an informed decision.

A clarification request SHOULD identify:

- The relevant document, contract, specification, or other source of the requirement.
- The specific uncertainty, ambiguity, or conflict.
- The clarification or decision being requested.
- The potential consequences of the unresolved issue, where relevant and reasonably identifiable.

Contributors MUST use the project's established communication channels when requesting clarification. They MUST NOT assume that a particular communication platform, issue-tracking workflow, or other tool is mandatory unless it has been established by the project.

If a contact email address is provided at the end of this guide, contributors MAY use that address to request clarification or seek assistance. The address MUST be taken from the published guide; contributors MUST NOT assume that an unspecified email address exists.

Clarifications and decisions that affect shared project requirements, contracts, standards, or architectural decisions MUST be handled through the applicable team decision-making process.

___

# 9.0. Related Resources

This section provides links to the documentation and technical references that contributors may need when working on the ÖRÜ project. It also provides a contact address for project-related questions and communication.

## 9.1. Project Overview and Architecture

- `README` — Provides an introduction to the ÖRÜ project and its purpose.
- `oru.architecture.md` — Defines the primary architectural reference for the project.
- `modules.dev.md` — Describes the organization of project modules and serves as the starting point for module-specific documentation.

• • •

## 9.2. Contribution Standards

- `code_of-conducts.md` — Defines the expected conduct of project contributors.
- `coding_style_guide.md` — Defines the project's coding standards and conventions. Contributors MUST consult Section `0.5. Core Coding Rules` during onboarding and refer to other sections as applicable.
- `documentation_writing_rules.md` — Defines the requirements for creating, maintaining, and reviewing project documentation.

• • •

## 9.3. Technical References

Contributors MUST consult the technical references applicable to their work, including relevant contracts, specifications, module documentation, and security documentation.

The specific references required depend on the affected components and the nature of the proposed changes. Contributors MUST use the applicable authoritative documents when determining implementation and verification requirements.

• • •

## 9.4. Contact and Communication

For project-related questions, clarification requests, or other communication concerning contributions to ÖRÜ, contributors MAY contact the project via the following email address:

**Email:** oruproject@protonmail.com

When contacting the project, contributors SHOULD clearly describe the subject of their inquiry and provide relevant context to facilitate an effective response.

___

## Notes

> **AI Usage Notice:** This document was written by artificial intelligence in accordance with the architecture, rules, and standards provided by the developer, and has been reviewed by a human.
