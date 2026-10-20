# Coding Style Guide

> **Author:** Ali Emre Arlı
> **Module:** Documentation
> **Version:** 1.0.0
> **Last Updated:** 2026-10-18
> **Status:** Active

This file explains the "How does it look like an ideal code?" and "How can I write an ideal code?" questions inside. That's why this file contains tons of rules that have connectivity for a developer. Please stick to these rules for catching a code standard for our projects.

___

# 0. Table of Contents

* 0.5. Core Coding Rules
* 1.0. Scope and Pre-Introduction
    * 1.1. Scope
    * 1.2. Targetted Platforms
    * 1.3. Rule Enforcement
    * 1.4. Version Management of Guidelenes
    * 1.5. Exception and Deviation Procedure

* 2.0. Fundemantal Designing Principles
    * 2.1. Consistency and Predictability
    * 2.2. Clarity and Readability
    * 2.3. Simplicity and Avoiding Unnecessary Complexity
    * 2.4. Clear Contracts and Prerequisites
    * 2.5. Limitations of the Defensive Programming Approach
    * 2.6. Distinguishing Between Error Handling and Programming Errors
    * 2.7. Avoiding Unnecessary Abstraction
    * 2.8. Single Responsibility and Modularity
    * 2.9. Portability and Separation of Platform-Specific Code
    * 2.10. Balancing Performance, Readability, and Maintenance Cost
    * 2.11. The Meaning of Compiler Warnings
    * 2.12. Approach to Undefined Behavior
    * 2.13. Use of Artificial Intelligence

* 3.0 Source Formatting Guide
    * 3.1. Character Encoding and File Endings
    * 3.2. Indentation and Space Characters
    * 3.3. Line Length
    * 3.4. Use of Blank Lines
    * 3.5. Line-End Spaces
    * 3.6. Curly Brace Placement
    * 3.7. Single-line and multi-line blocks
    * 3.8. Spacing around expressions and operators
    * 3.9. Use of commas, semicolons, and colons
    * 3.10. Formatting function calls
    * 3.11. Breaking up long conditions and expressions
    * 3.12. Formatting macro calls
    * 3.13. Chained function calls and nested expressions
    * 3.14. Empty blocks and empty expressions
    * 3.15. Presence of a newline at the end of the file

* 4.0. Naming Rules
    * 4.1. General Naming Policy
    * 4.2. Character Set and Identifier Restrictions
    * 4.3. Variable Names
    * 4.4. Function Names
    * 4.5. Type Names
    * 4.6. Macro Names
    * 4.7. Constant Names
    * 4.8. Global and File-Scope Identifiers
    * 4.9. Static Function Names
    * 4.10. Parameter Names
    * 4.11. Local Variable Names
    * 4.12. Loop Counters and Temporary Variables
    * 4.13. Boolean-Like Names
    * 4.14. Pointer and Array Names
    * 4.15. Abbreviations and Acronyms
    * 4.16. Prefixes and Suffixes
    * 4.17. Project and Module Namespaces
    * 4.18. Reserved Identifiers and Name Collisions

* 5.0. Files and Including Standards
    * 5.1. Source and Header File Responsibilities
    * 5.2. File and Directory Naming
    * 5.3. Header Guards
    * 5.4. Include Ordering
    * 5.5. Quoted and Angle-Bracket Includes
    * 5.6. Direct and Transitive Dependencies
    * 5.7. Self-Contained Headers
    * 5.8. Forward Declarations
    * 5.9. Public and Internal Headers
    * 5.10. Circular Dependencies
    * 5.11. Static Functions and Internal Linkage
    * 5.12. External Linkage and Extern Declarations
    * 5.13. Global Variable Declarations and Definitions
    * 5.14. One-Definition and Linkage Constraints
    * 5.15. Platform-Specific Headers
    * 5.16. Header Compatibility and Dependencies

* 6.0. Usage of Variables and Types
    * 6.1. Fundamental Types
    * 6.2. Fixed-Width Integer Types
    * 6.3. Integer Type Selection
    * 6.4. Signed and Unsigned Types
    * 6.5. Floating-Point Types
    * 6.6. Boolean Values
    * 6.7. Void and Void Pointers
    * 6.8. Typedef Usage
    * 6.9. Const Correctness
    * 6.10. Volatile Usage
    * 6.11. Restrict Usage
    * 6.12. Variable Declaration and Initialization
    * 6.13. Variable Scope and Lifetime
    * 6.14. Variable Shadowing
    * 6.15. Type Conversions and Casts
    * 6.16. Integer Promotions and Arithmetic Conversions
    * 6.17. Integer Constants and Suffixes
    * 6.18. Enumerations
    * 6.19. Structures and Unions
    * 6.20. Bit-Fields
    * 6.21. Designated Initializers
    * 6.22. Compound Literals
    * 6.23. Static Assertions
    * 6.24. Alignment and Object Representation
    * 6.25. Implementation-Defined Type Properties
    * 6.26. Register Storage-Class Specifier
    * 6.27. Extern and Static Storage-Class Specifiers
    * 6.28. Automatic and Static Storage Duration
    * 6.29. Uninitialized Variables
    * 6.30. Variable Declaration Placement

* 7.0. Function Designing Principles
    * 7.1. Function Prototypes and Declarations
    * 7.2. Function Definitions
    * 7.3. Function Naming
    * 7.4. Parameter Ordering
    * 7.5. Parameter Types and Qualifiers
    * 7.6. Return Types and Return Values
    * 7.7. Function Preconditions and Postconditions
    * 7.8. Function Contracts and Documentation
    * 7.9. Function Responsibilities
    * 7.10. Function Length and Complexity
    * 7.11. Early Returns
    * 7.12. Multiple Exit Points
    * 7.13. Helper Functions
    * 7.14. Recursion
    * 7.15. Variadic Functions
    * 7.16. Function Pointers and Callbacks
    * 7.17. Parameter Mutation
    * 7.18. Ignored Return Values
    * 7.19. Inline Functions
    * 7.20. External and Internal Function Interfaces
    * 7.21. Function Pointer Type Definitions
    * 7.22. Function Attributes and Compiler Extensions
    * 7.23. Non-Returning Functions
    * 7.24. Function Overloading Alternatives in C

* 8.0. Expressions and Control Flow Standards
    * 8.1. Operator Precedence and Associativity
    * 8.2. Parentheses in Expressions
    * 8.3. Arithmetic Expressions
    * 8.4. Comparison Expressions
    * 8.5. Logical Operators
    * 8.6. Bitwise Operators
    * 8.7. Assignment Operators
    * 8.8. Increment and Decrement Operators
    * 8.9. Comma Operator
    * 8.10. Conditional Operator
    * 8.11. Short-Circuit Evaluation
    * 8.12. Evaluation Order and Side Effects
    * 8.13. Integer Overflow
    * 8.14. Shift Operations
    * 8.15. Division and Remainder
    * 8.16. Floating-Point Comparisons
    * 8.17. If, Else If, and Else
    * 8.18. Switch, Case, and Default
    * 8.19. For Loops
    * 8.20. While and Do-While Loops
    * 8.21. Break and Continue
    * 8.22. Goto Usage
    * 8.23. Loop Termination Conditions
    * 8.24. Infinite Loops
    * 8.25. Nested Control Structures
    * 8.26. Fall-Through Behavior
    * 8.27. Empty Loop Bodies
    * 8.28. Simplifying Complex Control Flow
    * 8.29. Explicit Boolean Conditions
    * 8.30. Multiple Assignments in Expressions
    * 8.31. Comma Operator Restrictions
    * 8.32. Side Effects in Function Arguments
    * 8.33. Integer and Pointer Comparisons
    * 8.34. Null Statement Usage

* 9.0. Pointer and Memory Management
    * 9.1. Pointer Declaration and Initialization
    * 9.2. Null Pointer Policy
    * 9.3. Pointer Arithmetic
    * 9.4. Pointer and Array Relationships
    * 9.5. Pointer Comparisons
    * 9.6. Pointer Conversions
    * 9.7. Multiple Levels of Indirection
    * 9.8. Function Pointers and Object Pointers
    * 9.9. Pointer Validity
    * 9.10. Dangling and Uninitialized Pointers
    * 9.11. Object Lifetime and Pointer Validity
    * 9.12. Pointer Ownership
    * 9.13. Borrowed and Non-Owning Pointers
    * 9.14. Pointer Parameter Contracts
    * 9.15. Pointer and Size Relationships
    * 9.16. Dynamic Memory Allocation
    * 9.17. Malloc, Calloc, Realloc, and Free
    * 9.18. Allocation Size Calculations
    * 9.19. Allocation Failure Handling
    * 9.20. Ownership Transfer
    * 9.21. Memory Leaks
    * 9.22. Double-Free and Use-After-Free
    * 9.23. Partial Initialization and Cleanup
    * 9.24. Resource Acquisition and Release
    * 9.25. Flexible Array Members
    * 9.26. Stack and Heap Usage
    * 9.27. Effective Type and Strict Aliasing
    * 9.28. Alignment Requirements
    * 9.29. Pointer-to-Pointer Parameters
    * 9.30. Const Pointers and Pointer Qualifiers
    * 9.31. Pointer Arithmetic Boundaries
    * 9.32. Memory Copying and Moving
    * 9.33. Zero-Initialization and Byte-Level Initialization
    * 9.34. Object Representation and Padding
    * 9.35. Allocation and Deallocation Contracts

* 10.0. Macros and C11 Features
    * 10.1. General Preprocessor Policy
    * 10.2. Object-Like Macros
    * 10.3. Function-Like Macros
    * 10.4. Macro Parameter Parenthesization
    * 10.5. Multiple Evaluation of Macro Arguments
    * 10.6. Stringification and Token Pasting
    * 10.7. Variadic Macros
    * 10.8. Multi-Statement Macros
    * 10.9. Macro Naming and Namespace Pollution
    * 10.10. Undef Policy
    * 10.11. Conditional Compilation
    * 10.12. Feature and Platform Detection
    * 10.13. Compile-Time Configuration
    * 10.14. Macros Versus Functions
    * 10.15. Assertion Macros
    * 10.16. Variable-Length Arrays
    * 10.17. Generic Selection
    * 10.18. Atomic Types and Operations
    * 10.19. C11 Thread Support
    * 10.20. Thread-Local Storage
    * 10.21. Alignment Specifiers and Operators
    * 10.22. Noreturn Function Specifier
    * 10.23. Optional C11 Features
    * 10.24. Restricted Compiler Extensions
    * 10.25. GCC and Clang Extension Isolation
    * 10.26. Predefined Macros
    * 10.27. Macro Continuation and Line Formatting
    * 10.28. Conditional Compilation Branch Structure
    * 10.29. Feature-Test Macros
    * 10.30. Prohibited Language Extensions

* 11.0. API & ABI Guide
    * 11.1. Public and Private Interfaces
    * 11.2. API Design Principles
    * 11.3. API Contracts
    * 11.4. Symbol Visibility
    * 11.5. External Linkage
    * 11.6. Opaque Types
    * 11.7. Public Structure Layout
    * 11.8. ABI Stability
    * 11.9. Structure Padding and Alignment
    * 11.10. Enum and Bit-Field Representation
    * 11.11. Shared and Static Libraries
    * 11.12. API and ABI Compatibility
    * 11.13. Versioning and Backward Compatibility
    * 11.14. Foreign Function Interfaces
    * 11.15. Platform API Isolation
    * 11.16. Public Header Stability
    * 11.17. Public Function Naming
    * 11.18. Ownership and Lifetime in Public APIs
    * 11.19. Error Reporting in Public APIs
    * 11.20. Reserved Names and Symbol Prefixes
    * 11.21. ABI-Sensitive Types
    * 11.22. Compatibility Across Compiler Versions

* 12.0. Error Handling
    * 12.1. Error Categories
    * 12.2. Programming Errors and Runtime Errors
    * 12.3. Preconditions and Invariants
    * 12.4. Return-Value-Based Error Reporting
    * 12.5. Error Codes and Enumerations
    * 12.6. Errno Usage
    * 12.7. Partial Failure
    * 12.8. Error Propagation
    * 12.9. Cleanup on Failure
    * 12.10. Error Messages and Logging
    * 12.11. Assertions and NDEBUG
    * 12.12. Fatal and Recoverable Errors
    * 12.13. Defensive Checks
    * 12.14. Failure-State Invariants
    * 12.15. Error Handling Contracts
    * 12.16. Error Return Conventions
    * 12.17. Error Handling in Constructors and Destructors
    * 12.18. Error Handling in Callbacks
    * 12.19. Error Handling and Resource Ownership
    * 12.20. Error Handling Anti-Patterns

* 13.0. Data Lifecycle
    * 13.1. Object Initialization
    * 13.2. Valid and Invalid Object States
    * 13.3. Initialization Functions
    * 13.4. Destruction and Cleanup Functions
    * 13.5. Resource Ownership
    * 13.6. Ownership Transfer
    * 13.7. File and File Descriptor Lifetimes
    * 13.8. Buffer Lifetimes
    * 13.9. State Transitions
    * 13.10. Reinitialization and Reset
    * 13.11. Idempotent Cleanup
    * 13.12. Partial Construction and Destruction
    * 13.13. Global and Static Object Lifecycles
    * 13.14. Thread and Synchronization Object Lifecycles
    * 13.15. Borrowed Data Lifetimes
    * 13.16. Returning Pointers to Objects
    * 13.17. Ownership in Containers
    * 13.18. Lifecycle Invariants
    * 13.19. Cleanup Ordering
    * 13.20. Resource Transfer Between Modules

* 14.0. Compiling and Verification
    * 14.1. C11 Language Mode
    * 14.2. GCC and Clang Compatibility
    * 14.3. Compiler Warning Policy
    * 14.4. Treating Warnings as Errors
    * 14.5. Compiler-Specific Warning Management
    * 14.6. Warning Suppression
    * 14.7. Static Analysis
    * 14.8. Formatting and Linting Tools
    * 14.9. Sanitizers
    * 14.10. Debug and Release Builds
    * 14.11. Optimization Levels
    * 14.12. Linker Diagnostics
    * 14.13. Multi-Compiler Verification
    * 14.14. Continuous Integration
    * 14.15. Centralized Build Configuration
    * 14.16. Portability Verification
    * 14.17. Compliance Checks
    * 14.18. Compiler Feature Detection
    * 14.19. Static and Dynamic Analysis
    * 14.20. Test Build Requirements
    * 14.21. Reproducible Builds
    * 14.22. Compiler Version Requirements

* 15.0. AI-Assisted Development
    * 15.1. General AI Usage Policy
    * 15.2. Developer Responsibility
    * 15.3. Code Review and Verification
    * 15.4. Correctness and Hallucinations
    * 15.5. Security and Trust Boundaries
    * 15.6. Licensing and Provenance
    * 15.7. Confidentiality and Sensitive Information
    * 15.8. AI-Generated Tests and Documentation
    * 15.9. Compliance with This Guide
    * 15.10. Prohibited AI Usage Patterns

___

# 0.5. Core Coding Rules

This section summarizes the most important rules of this coding style guide. It is intended to provide a concise reference for everyday development, code review, and implementation decisions.

These rules do not replace the detailed requirements defined in subsequent sections. Developers MUST consult the referenced sections whenever additional clarification, exceptions, examples, or implementation details are necessary.

Unless otherwise stated, the normative requirements in this section have the same meaning as in the corresponding sections of this guide. The use of AI-generated code does not exempt an implementation from any requirement.

## 0.5.1. Language and Portability

- **Use ISO C11.** Source code MUST conform to ISO C11 and MUST be compiled in strict C11 language mode using `-std=c11`, not `-std=gnu11`. See Section 14.1.

- **Support the approved compilers.** Code MUST be compatible with both GCC and Clang versions approved by the project. See Sections 14.2 and 14.22.

- **Avoid non-standard extensions.** Compiler-specific language extensions MUST NOT be used unless explicitly permitted by this guide. See Sections 10.24–10.25 and 10.30.

- **Prioritize portability.** Code MUST NOT depend on undocumented behavior, accidental implementation properties, or assumptions that are not guaranteed by the applicable standards. See Sections 2.9 and 14.16.

- **Isolate platform-specific code.** Platform-specific APIs and headers MUST remain within designated platform-specific implementation layers. Platform-specific types MUST NOT leak into public interfaces. See Sections 5.15, 11.15, and 2.9.

- **Verify portability in practice.** Portability MUST be validated through appropriate compilation and testing on supported platforms. Using standard C constructs alone is insufficient. See Section 14.16.

• • •

## 0.5.2. Fundamental Design Principles

- **Prefer clarity over cleverness.** Code MUST be understandable to developers who maintain it later. Unnecessarily obscure, compressed, or clever implementations SHOULD be avoided. See Sections 2.2 and 2.3.

- **Keep implementations simple.** Additional abstraction, indirection, and complexity MUST have a clear purpose. See Section 2.7.

- **Maintain consistent behavior.** Similar problems SHOULD be solved using consistent patterns throughout the project unless a documented reason justifies a difference. See Section 2.1.

- **Define explicit contracts.** Functions and public interfaces MUST have clear responsibilities, preconditions, postconditions, and failure behavior where applicable. See Sections 2.4, 7.7, and 7.8.

- **Separate responsibilities.** Functions and modules SHOULD have focused responsibilities and well-defined boundaries. See Section 2.8.

- **Distinguish programming errors from runtime errors.** Invalid assumptions in the implementation MUST NOT be confused with expected operational failures. See Sections 2.6 and 12.1–12.2.

- **Do not overuse defensive programming.** Checks MUST address meaningful failure conditions, untrusted inputs, or violated runtime requirements rather than indiscriminately duplicating established guarantees. See Sections 2.5 and 12.13.

- **Treat undefined behavior as a correctness defect.** Code MUST NOT rely on undefined behavior, even if it appears to work with a particular compiler or optimization level. See Section 2.12.

• • •

## 0.5.3. Source Formatting

- **Use consistent formatting.** Source files MUST follow the project's centralized formatting rules. See Sections 3.1–3.15 and 14.8.

- **Use consistent indentation.** Indentation and whitespace MUST follow the formatting rules defined in Section 3.2.

- **Use braces consistently.** Braces MUST follow the placement and block-formatting conventions defined in Sections 3.6–3.7.

- **Separate logical blocks.** Blank lines SHOULD separate logically distinct statements and blocks without fragmenting closely related code. See Section 3.4.

- **Avoid trailing whitespace.** Lines MUST NOT contain unnecessary trailing whitespace. See Section 3.5.

- **Terminate files correctly.** Every source and header file MUST end with a newline character. See Section 3.15.

- **Keep expressions readable.** Long conditions, nested expressions, and lengthy function calls SHOULD be split into readable multiline forms when necessary. See Sections 3.8–3.13.

• • •

## 0.5.4. Naming

- **Follow the naming convention.** Identifiers MUST use the naming conventions defined in Section 4, including lowercase `snake_case` where applicable.

- **Use project-prefixed public symbols.** Publicly visible symbols MUST use the project's designated prefix and appropriate module or component namespaces. See Sections 4.8 and 4.17.

- **Use uppercase macro names.** Macros MUST follow the uppercase naming convention defined in Section 4.6.

- **Choose meaningful names.** Names SHOULD communicate the purpose and role of an identifier without unnecessary verbosity. See Sections 4.3–4.16.

- **Avoid ambiguous abbreviations.** Abbreviations SHOULD be used only when their meaning is clear and consistent within the project. See Section 4.15.

- **Avoid reserved identifiers.** Identifiers reserved by ISO C or the implementation MUST NOT be used for project-defined names. See Section 4.18.

- **Avoid namespace collisions.** Public symbols MUST be named so that they do not conflict with other project modules, libraries, or reserved namespaces. See Sections 4.17–4.18.

• • •

## 0.5.5. Files and Headers

- **Separate declarations from implementation.** Public declarations MUST reside in public headers, while private implementation details MUST remain internal. See Sections 5.1 and 5.9.

- **Use header guards.** Every project header MUST have a unique and consistent header guard. See Section 5.3.

- **Make headers self-contained.** A header MUST include or otherwise validly establish the declarations and definitions required for its own public declarations to compile. See Section 5.7.

- **Include direct dependencies.** Source files and headers MUST NOT rely on unrelated headers to include required dependencies transitively. See Section 5.6.

- **Keep include ordering consistent.** Include directives MUST follow the project's established include-ordering rules. See Section 5.4.

- **Avoid circular dependencies.** Headers and modules SHOULD be structured to prevent circular dependencies. See Section 5.10.

- **Use internal linkage for private functions.** Functions used exclusively within one source file SHOULD be declared static. See Section 5.11.

- **Keep public interfaces stable.** Changes to public declarations MUST be evaluated for source compatibility and ABI impact. See Sections 11.16 and 11.12.

• • •

## 0.5.6. Types and Variables

- **Initialize variables at declaration.** Variables MUST be initialized when declared, using an appropriate initial value or initializer. See Section 6.12.

- **Declare local variables at block beginnings.** Local variable declarations MUST appear at the beginning of their enclosing block, before executable statements. See Section 6.30.

- **Avoid unnecessary scope.** Variables SHOULD have the narrowest scope consistent with their intended use. See Section 6.13.

- **Use types according to their purpose.** The selected type MUST provide the required range, representation guarantees, and semantics. See Sections 6.1–6.5.

- **Use fixed-width integers when width matters.** Types such as `uint32_t` and `int64_t` SHOULD be used when an exact integer width is required and the corresponding type is available. See Sections 6.2–6.3.

- **Handle signedness explicitly.** Signed and unsigned values MUST NOT be mixed carelessly in arithmetic, comparisons, or conversions. See Sections 6.4, 6.15, and 6.16.

- **Use `const` appropriately.** Objects and pointed-to data that must not be modified through a particular interface SHOULD be qualified with `const` where applicable. See Section 6.9.

- **Use `volatile` only when justified.** `volatile` MUST NOT be used as a general synchronization mechanism or as a substitute for proper concurrency control. See Section 6.10.

- **Avoid implementation-dependent representations in public interfaces.** Public ABI contracts MUST NOT depend on unspecified enum, bit-field, or other implementation-dependent representations. See Sections 6.18–6.20 and 11.10.

- **Do not use prohibited language features.** VLAs, `register`, function-local `static` variables, `_Generic`, C11 atomics, and C11 `<threads.h>` MUST NOT be used under this guide's established restrictions. See Sections 6.26, 10.16–10.19, and 6.28.

- **Use permitted C11 features carefully.** `_Thread_local`, `_Alignas`, `_Alignof`, and `_Noreturn` MAY be used only under the conditions established in Section 10.

• • •

## 0.5.7. Functions and Contracts

- **Use approved return types.** Public functions MUST return either `int` or `void`, according to the project's function-interface policy. See Sections 7.6 and 11.2.

- **Use status codes consistently.** Public functions returning `int` MUST follow the centralized status-code convention: zero indicates success, and negative values indicate defined errors or failure statuses. See Sections 7.6 and 12.4–12.5.

- **Return output data through output parameters.** Public functions MUST use the established output-parameter convention when returning data in addition to a status code. See Sections 7.6 and 11.2.

- **Document public contracts.** Every public function MUST have a complete normative contract in its designated Markdown documentation file. See Section 7.8.

- **Define preconditions and postconditions.** Function contracts MUST specify relevant input requirements, output guarantees, ownership effects, and failure behavior. See Sections 7.7–7.8.

- **Keep functions focused.** Functions SHOULD perform a clearly defined task and SHOULD NOT accumulate unrelated responsibilities. See Sections 7.9–7.10.

- **Avoid unnecessary parameter mutation.** Parameters SHOULD NOT be modified unless mutation is required by the function's contract. See Section 7.17.

- **Handle return values.** Return values MUST NOT be ignored when they communicate errors, resource-acquisition results, or other required information. See Section 7.18.

- **Use `void` when no status is needed.** A public function MAY return `void` when no status reporting is required by its contract. See Section 7.6.

• • •

## 0.5.8. Expressions and Control Flow

- **Make complex expressions readable.** Parentheses SHOULD be used when they improve clarity, especially in expressions involving multiple operators. See Sections 8.1–8.2.

- **Avoid side-effect-heavy expressions.** Expressions SHOULD NOT combine unrelated modifications, increments, or function calls in ways that make evaluation behavior difficult to understand. See Sections 8.12 and 8.32.

- **Respect evaluation order.** Code MUST NOT rely on an unspecified evaluation order or otherwise invoke undefined behavior. See Sections 8.11–8.12.

- **Handle integer overflow deliberately.** Signed integer overflow MUST NOT occur. Arithmetic involving potentially overflowing values MUST be checked or otherwise constrained. See Section 8.13.

- **Handle shifts safely.** Shift operations MUST satisfy the applicable C11 requirements for operand types and shift counts. See Section 8.14.

- **Avoid fragile floating-point comparisons.** Floating-point values SHOULD be compared using methods appropriate to the operation and required numerical precision. See Section 8.16.

- **Make control flow explicit.** Conditions, loop termination criteria, and switch behavior MUST be clear and reviewable. See Sections 8.17–8.28.

- **Avoid accidental fall-through.** Switch cases MUST NOT fall through unintentionally. Intentional fall-through MUST be clearly documented using the project's approved convention. See Section 8.26.

- **Use `goto` only according to the cleanup policy.** Early exits involving cleanup MUST follow the established `goto end` convention. See Sections 7.11–7.12 and 12.9.

- **Avoid unnecessary control-flow complexity.** Deeply nested or difficult-to-follow control structures SHOULD be simplified when doing so preserves correctness. See Section 8.28.

• • •

## 0.5.9. Pointers and Memory Management

- **Initialize pointers.** Pointer variables MUST be initialized before use. See Section 9.1.

- **Use null pointers consistently.** `NULL` MUST be used for null pointer values according to the project's null-pointer policy. See Section 9.2.

- **Validate pointer contracts.** Pointer validity, permitted null values, object lifetime, and access requirements MUST be established by the relevant function or object contract. See Sections 9.9–9.14.

- **Make ownership explicit.** Every dynamically allocated object MUST have a clearly defined ownership and release policy. See Sections 9.12 and 9.20.

- **Distinguish owned and borrowed pointers.** Non-owning pointers MUST NOT be used after the lifetime of their referenced objects has ended. See Section 9.13.

- **Check allocation failures.** Allocation results MUST be checked before the allocated memory is accessed. See Sections 9.16–9.19.

- **Check allocation-size calculations.** Size calculations MUST be checked for overflow before allocating memory. See Section 9.18.

- **Release owned resources.** Dynamically allocated memory and other owned resources MUST be released according to their ownership contracts. See Sections 9.21 and 9.24.

- **Prevent memory-management defects.** Double-free, use-after-free, invalid access, and memory leaks MUST be prevented. See Sections 9.21–9.22.

- **Handle partial initialization.** Failure during initialization MUST leave resources in a state that can be safely cleaned up. See Sections 9.23 and 13.12.

- **Release resources in reverse acquisition order.** Resources SHOULD be released in reverse acquisition order unless dependencies or the resource contracts require a different order. See Sections 9.24 and 13.19.

- **Respect object representation.** Memory copying, pointer conversions, alignment, effective type, and object representation MUST comply with the applicable C11 requirements. See Sections 9.27–9.34.

• • •

## 0.5.10. Macros and Preprocessor

- **Prefer functions over macros.** Functions SHOULD be preferred when they provide equivalent behavior without unnecessary loss of type safety or other required properties. See Section 10.14.

- **Parenthesize macro parameters.** Function-like macro parameters MUST be parenthesized wherever required to preserve the intended expression semantics. See Section 10.4.

- **Avoid multiple evaluation.** Macro arguments MUST NOT be evaluated multiple times when doing so could produce incorrect behavior or unintended side effects. See Section 10.5.

- **Keep macros simple.** Complex control flow and multi-statement macro implementations SHOULD be avoided. See Sections 10.8 and 10.14.

- **Avoid namespace pollution.** Macros MUST use appropriate project prefixes and MUST NOT unnecessarily affect unrelated translation units. See Section 10.9.

- **Centralize conditional compilation.** Platform and feature selection MUST follow the project's established configuration policy. See Sections 10.11–10.13.

- **Do not detect compilers using compiler-specific predefined macros in source code.** Macros such as `__GNUC__` and `__clang__` MUST NOT be used in project source code. Standard-defined macros MAY be used for legitimate standard-feature detection. See Section 10.26 and Section 14.18.

- **Restrict feature-test macros.** POSIX feature-test macros MAY be used when necessary and documented. `_GNU_SOURCE` MUST NOT be enabled under the project's default policy. See Section 10.29.

• • •

## 0.5.11. API and ABI

- **Separate public and private interfaces.** Public interfaces MUST expose only what users of the module need. Internal implementation details SHOULD remain private. See Sections 11.1 and 11.6.

- **Keep public interfaces predictable.** Public API behavior, ownership, lifetime, and failure semantics MUST be explicitly defined. See Sections 11.2–11.3.

- **Protect ABI stability.** Changes to public structure layouts, exported symbols, calling conventions, or ABI-sensitive types MUST be evaluated for binary compatibility. See Sections 11.7–11.12.

- **Do not rely on enum or bit-field layout.** Public ABI definitions MUST NOT assume compiler-independent enum or bit-field representation. See Sections 11.9–11.10.

- **Use explicit representations when required.** Fixed-width types and explicitly defined bit masks SHOULD be preferred when stable binary representations are required. See Sections 6.2 and 11.21.

- **Version incompatible changes.** Breaking ABI changes MUST follow the project's versioning and migration policy. See Section 11.13.

- **Keep platform dependencies isolated.** Public interfaces MUST NOT unnecessarily expose platform-specific types or implementation details. See Section 11.15.

- **Evaluate API and ABI compatibility separately.** Source compatibility MUST NOT be assumed to guarantee binary compatibility, or vice versa. See Section 11.12.

• • •

## 0.5.12. Error Handling

- **Distinguish error categories.** Expected operational failures MUST be distinguished from programming errors and violated internal invariants. See Sections 12.1–12.3.

- **Follow the status-code convention.** Public functions returning status codes MUST follow the project's centralized error-reporting policy. See Sections 12.4–12.5.

- **Propagate errors deliberately.** Errors MUST NOT be silently discarded when callers need them to make correct decisions. See Section 12.8.

- **Clean up after failure.** Functions that acquire resources MUST release or transfer those resources correctly on every relevant failure path. See Sections 12.7 and 12.9.

- **Keep `errno` isolated.** `errno` MUST remain within the designated platform layer and MUST be mapped to project status codes before crossing the relevant abstraction boundary. See Section 12.6.

- **Do not confuse assertions with input validation.** Assertions MUST NOT replace validation of untrusted input or required runtime error handling. See Sections 12.11 and 12.13.

- **Define failure-state invariants.** Functions MUST leave affected objects and resources in states consistent with their documented failure contracts. See Sections 12.14–12.15.

- **Keep logging responsibility clear.** Logging SHOULD be performed by the layer responsible for handling or reporting the error, rather than indiscriminately by every layer. See Section 12.10.

• • •

## 0.5.13. Data Lifecycle

- **Define object states.** Objects MUST have clearly defined valid states and initialization requirements. See Sections 13.1–13.3.

- **Define destruction behavior.** Destruction and cleanup operations MUST follow the object's ownership and lifetime contract. See Sections 13.4–13.5.

- **Make ownership transfer explicit.** Ownership transfers between modules MUST be documented and unambiguous. See Section 13.6.

- **Handle partial construction.** Partially initialized objects MUST be safely recoverable or destructible according to their contracts. See Section 13.12.

- **Respect borrowed-data lifetimes.** Borrowed data MUST NOT outlive the objects or storage from which it originates. See Sections 13.8 and 13.15.

- **Keep state transitions valid.** State-changing operations MUST preserve the invariants required for subsequent operations. See Sections 13.9 and 13.18.

- **Make cleanup predictable.** Cleanup operations SHOULD be safe to perform according to their documented repeatability and ownership guarantees. See Section 13.11.

• • •

## 0.5.14. Compilation and Verification

- **Resolve compiler warnings.** Warnings MUST be investigated and resolved where applicable. Projects MUST NOT rely on universally enabling `-Werror` as a substitute for a sound warning policy. See Sections 14.3–14.4.

- **Centralize build configuration.** Common compiler, linker, and verification settings MUST be managed centrally. Module-specific deviations MUST be documented and reviewed. See Sections 14.5 and 14.15.

- **Do not suppress warnings.** Warning suppression MUST NOT be used to conceal defects or avoid resolving diagnostics. See Section 14.6.

- **Use static analysis.** Static analysis tools SHOULD be used regularly and incorporated into CI where practical. See Section 14.7.

- **Apply formatting checks.** Formatting and linting rules MUST be centrally defined and verified using the project's approved tools. See Section 14.8.

- **Use sanitizers where supported.** AddressSanitizer and UndefinedBehaviorSanitizer SHOULD be used in appropriate testing and CI environments where supported. See Section 14.9.

- **Test with both supported compilers.** CI MUST verify compilation with both GCC and Clang. See Section 14.13.

- **Verify the required configurations.** Release builds MUST be supported. Debug builds and additional optimization-level checks SHOULD be used where appropriate. See Sections 14.10–14.11.

- **Verify behavior, not just compilation.** Successful compilation MUST NOT be treated as proof of correctness. Tests and relevant analysis MUST be performed according to the project's requirements. See Sections 14.7–14.9 and 14.20.

- **Automate compliance checks.** Applicable style, build, test, and analysis checks SHOULD be automated in CI. Requirements that cannot be automated MUST remain subject to review. See Sections 14.14 and 14.17.

- **Maintain reproducibility.** Build inputs, tool versions, and relevant configuration SHOULD be documented to support reproducible builds. See Section 14.21.

• • •

## 0.5.15. AI-Assisted Development

- **Use AI as an assistant.** AI MAY be used for technical questions, repetitive work, debugging, testing, documentation, and other development tasks. See Section 15.1.

- **Keep architectural authority with developers.** AI MAY propose architectural decisions, but the responsible developer MUST evaluate and approve them. See Sections 15.1–15.2.

- **Retain full responsibility.** Developers MUST understand, review, verify, and test AI-generated code before accepting it. See Section 15.2.

- **Apply ordinary review requirements.** AI-generated code MUST undergo the same review, compilation, testing, and verification requirements as manually written code. See Section 15.3.

- **Verify technical claims.** AI-generated explanations, API usage, and technical assumptions MUST be checked where their correctness affects the implementation. See Section 15.4.

- **Require human supervision.** AI-generated commands and changes MUST remain subject to appropriate authorization and review. Risky operations MUST require explicit approval. See Section 15.5.

- **Evaluate licensing risks.** Developers MUST evaluate relevant licensing and provenance risks before incorporating AI-generated content. Superficial modifications MUST NOT be treated as automatically resolving those risks. See Section 15.6.

- **Protect confidential information.** Secrets MUST NOT be submitted to AI tools through ordinary development prompts. Confidential data MUST be handled according to the applicable authorization and privacy requirements. See Section 15.7.

- **Verify AI-generated tests and documentation.** Tests MUST be evaluated for meaningful coverage, and documentation MUST be checked against actual implementation behavior. See Section 15.8.

- **Maintain the required AI project files.** Projects using AI-assisted development MUST maintain `ai_memory_bank.md`, `ai_project_goals.md`, and `ai_coding_rules.md`. See Section 15.9.

- **Mark AI-generated code.** AI-generated code that retains its AI-generated character MUST be marked using `// AI Content` and `// End AI Content`. Code genuinely rewritten by a developer MAY be removed from these marked regions. See Section 15.10.

- **Do not bypass this guide.** AI-generated code MUST comply with all applicable requirements. AI assistance MUST NOT be used to justify skipping reviews, tests, security controls, or coding rules. See Sections 15.9–15.10.

• • •

## 0.5.16. Final Development Checklist

Before submitting a change for review, developers SHOULD verify the following:

- [ ] The implementation conforms to ISO C11 and the project's portability requirements.
- [ ] Names, formatting, file organization, and interfaces follow this guide.
- [ ] Variables are initialized and types are used appropriately.
- [ ] Functions have clear responsibilities and documented contracts where required.
- [ ] Expressions and control flow avoid undefined behavior and unintended side effects.
- [ ] Pointer ownership, memory allocation, object lifetimes, and cleanup are correct.
- [ ] Errors are reported, propagated, and handled according to the project's conventions.
- [ ] Public API and ABI compatibility have been evaluated where applicable.
- [ ] Compiler warnings, static analysis, formatting, and required CI checks have been addressed.
- [ ] Tests cover relevant normal behavior, boundary conditions, and failure paths.
- [ ] AI-generated content, if any, has been reviewed, verified, and marked according to Section 15.
- [ ] Required AI project documentation is current when AI-assisted development is used.
- [ ] No prohibited compiler extensions, unsafe assumptions, unresolved licensing concerns, or unauthorized disclosures have been introduced.

Failure to satisfy a checklist item MUST be addressed before submission when the corresponding requirement is mandatory. Checklist completion does not replace the detailed requirements of this guide or the developer's responsibility for the implementation.

___

# 1.0. Scope

## 1.1. Scope

Every project has their own style rules and coding principles just like `Linux` or `BSD`. These principles provides a standardization and also comfort to a developer. Just like these projects, our works have standardization that specialized for us. This file explains these rules and guidelens inside for developers.

• • •

## 1.2. Targetted Platforms

* **Operating System:** Linux and its derivatives,
* **Language and Version:** C11,
* **Base:** Free BSD Style(9), Linux Kernel Coding Style,
* **Compilers:** GCC and CLang

• • •

## 1.3. Rule Enforcement

These rules have binding force for programmers who want to contribute to this project. If you want your code to be included in the mainline, you have to obey and stick to these rules. Even though having a style for programming, you have to obey our rules for protecting code standardisation in this project. Therefore, if we say, "This file defines how you can write ideal code," it doesn't be wrong!

• • •

## 1.4. Version Management of Guidelenes

This file doesn't contain the rules that wouldn't be changed after writing. Although these rules have binding force, we believe that rules define the boundaries, and these boundaries might change in years, even in days. You can see the version of our file in the below.

* **File Version:** v1.0.0.

Whenever we change a part, you will see the deprecated and changing parts in the related section by their version numbers. This is a good example for inspecting changes in our evolving process.

The codes that were written in the old standards have to be changed in the next update of the related code file.

• • •

## 1.5. Exception and Deviation Procedure

Our standards may contain irregular rules in some different topics. These explain the reasons and exceptions inside. You have to obey the rules that are defined in the title that you read up on.

___

# 2.0. Fundamental Designing Principles

While you are writing code, you are designing a product for the end-user. This means that you are the provider. Just like every person, programs have a character inside that is shaped to product. Our principles are explained in this section.

## 2.1. Consistency and Predictability

A code piece has to be consistent and predictable for a person who reads the code after publishing. Violation of consistency harms the logic of the function, while predictability affects the result. This means that these properties are not only ordinary properties instead effects the logic and results of a code piece.

• • •

## 2.2. Clarity and Readability

A code piece has to avoid the unclear and complex operations. You know there is a very famous saying, "If you can explain your works to a 5-year-old, you made it right!"

You can look up the warnings of the LSP that you use in this section, basically.

• • •

## 2.3. Simplicity and Avoiding Unnecessary Complexity

A code piece has to solve its intended problem without introducing unnecessary complexity. Every additional condition, abstraction, or layer of indirection makes the implementation more difficult to understand and maintain. Complexity should exist only when it serves a purpose that justifies its cost.

Simplicity does not mean writing fewer lines at all costs. The objective is to make the actual logic of the program as straightforward as possible, even if that requires more explicit code.

• • •

## 2.4. Clear Contracts and Prerequisites

Every function has a contract that defines the conditions under which it operates and the behavior it guarantees. These contracts establish the responsibilities of both the caller and the implementation.

When a prerequisite is explicitly defined by a contract, the caller is responsible for satisfying it. The implementation should be designed around the guarantees of its contract rather than assuming that every caller may violate its requirements.

Clear contracts make responsibilities explicit and allow individual components to be implemented and understood without repeatedly reconsidering assumptions that have already been established.

• • •

## 2.5. Limitations of the Defensive Programming Approach

Defensive programming is not an unconditional requirement for writing reliable software. Although validating external inputs and handling environmental failures are necessary in appropriate contexts, checking every internal assumption can introduce unnecessary complexity and obscure the intended logic.

When a component operates under a clearly defined contract, its implementation should be able to rely on that contract. Repeatedly checking conditions that the contract already guarantees adds complexity without necessarily improving reliability.

Defensive measures should therefore be justified by the actual requirements and boundaries of the program, rather than by the assumption that every conceivable failure must be handled at every level.

• • •

## 2.6. Distinguishing Between Error Handling and Programming Errors

A program must distinguish between failures that arise during normal operation and defects in its implementation. An external resource may be unavailable, an operation may fail, or an input may be invalid. Such situations can be legitimate runtime conditions that require an appropriate response.

Programming errors are different. They indicate that the implementation has violated an established contract, invariant, or requirement. Treating these defects as ordinary runtime failures can conceal their causes and allow the program to continue under conditions for which its behavior is no longer reliable.

Error handling should address failures that the program is expected to encounter, while programming errors should be treated according to their nature and the guarantees of the affected component.

• • •

## 2.7. Avoiding Unnecessary Abstraction

An abstraction should simplify the design by hiding irrelevant details or establishing a meaningful boundary. It should not exist merely to make the implementation appear more general, reusable, or sophisticated.

Every abstraction introduces another concept that the reader must understand. When an abstraction does not provide a sufficient benefit, its additional indirection can make the program more difficult to understand than a direct implementation.

The design should introduce abstractions when they solve an identifiable problem, not merely because the possibility of future reuse exists.

• • •

## 2.8. Single Responsibility and Modularity

A component should have a clearly identifiable responsibility. Components that combine unrelated responsibilities become harder to understand because their behavior depends on concerns that do not naturally belong together.

Modularity allows a program to be divided into components whose responsibilities and relationships can be understood independently. These boundaries should reflect the actual design of the program rather than arbitrary divisions introduced solely to reduce the size of individual functions or files.

A well-structured program makes it clear where a responsibility belongs and limits the amount of unrelated code that must be considered when that responsibility changes.

• • •

## 2.9. Portability and Separation of Platform-Specific Code

Portable code should depend on guarantees that are shared across its intended target platforms. Assumptions about a particular operating system, compiler, hardware architecture, or implementation should not silently become requirements of otherwise portable components.

Platform-specific functionality is sometimes unavoidable. Such functionality should be separated from general-purpose logic when that separation provides a meaningful architectural benefit.

Portability does not require avoiding every platform-specific feature. It requires making platform dependencies explicit and preventing them from unnecessarily restricting components that do not depend on them.

• • •

## 2.10. Balancing Performance, Readability, and Maintenance Cost

A code piece is not designed exclusively for execution speed. Its implementation must also remain understandable and reasonably inexpensive to maintain.

Performance improvements can justify additional complexity when they address a meaningful requirement. However, complexity introduced for negligible or hypothetical performance benefits can make the program harder to reason about without providing a corresponding advantage.

Design decisions should account for the actual behavior of the program, its performance requirements, and the long-term cost of maintaining the implementation. Neither readability nor performance should be treated as an unconditional priority independent of the problem being solved.

• • •

## 2.11. The Meaning of Compiler Warnings

Compiler warnings provide information about constructs that may indicate defects, questionable assumptions, or unintended behavior. They are valuable feedback during development, but their meaning depends on the specific diagnostic and the context in which it occurs.

A warning does not automatically prove that the implementation is incorrect, and the absence of warnings does not prove that it is correct. Compiler diagnostics must be understood rather than treated as unquestionable judgments about the program.

The purpose of examining warnings is to understand what the compiler has identified, determine whether the code violates an intended guarantee, and make an informed decision about the implementation.

• • •

## 2.12. Approach to Undefined Behavior

Program correctness depends on the guarantees provided by the C language standard and the documented behavior of the interfaces on which the program relies. An implementation must not depend on behavior for which the applicable specifications provide no guarantees.

Undefined behavior is particularly dangerous because its consequences are not restricted to the immediate operation that causes it. The compiler may make optimization decisions based on the assumption that undefined behavior does not occur, making the resulting behavior different from what the programmer expects.

Code should therefore be designed around explicitly guaranteed behavior rather than observations made under a particular compiler, optimization level, or hardware architecture.

• • •

## 2.13. Use of Artificial Intelligence

Artificial intelligence may assist with designing, writing, reviewing, and explaining code. However, its output is a proposal to be evaluated, not an authoritative source of correctness.

Generated code must satisfy the same language requirements, project contracts, and design principles as any other implementation. Plausible explanations and convincing-looking code do not guarantee that the proposed solution is correct or appropriate.

Responsibility for the resulting implementation remains with the developer. Artificial intelligence should support technical judgment rather than replace the understanding required to make and justify design decisions.

___

# 3.0. Source Formatting Guide

Source formatting is an important part of writing readable code. When programmers follow the same formatting rules, other developers can understand the code more easily and contribute to the project without spending unnecessary time understanding its structure.

These rules define how source code has to be formatted. They aim to provide a consistent structure across the project and make the code easier to read, review, and maintain.

## 3.1. Character Encoding and File Endings

All source and header files have to use UTF-8 encoding and LF (`\n`) line endings. CRLF (`\r\n`) and CR (`\r`) line endings are not allowed.

ASCII characters should be used in code, including identifiers, keywords, operators, and other language constructs. Turkish characters and other non-ASCII characters may be used in comments when necessary.

Example:

```c
int process_value(int value)
{
	return value;
}
```

The following example is not allowed:

```c
int value = 10;
```

Consistent encoding and line endings prevent unnecessary differences between files and reduce problems when working with different operating systems and development tools.

• • •

## 3.2. Indentation and Space Characters

Each indentation level has to use four space characters. TAB characters must not be used for indentation. Spaces may be used for alignment when necessary.

Indentation has to represent the logical structure of the code. It should not be used to create unnecessary visual arrangements.

Example:

```c
if (condition) {
    process_value();
    if (another_condition) {
        handle_value();
    }
}
```

The following example is not allowed because the indentation does not represent the block structure consistently:

```c
if (condition) {
        process_value();
    if (another_condition) {
            handle_value();
        }
}
```

Consistent indentation allows the reader to identify block boundaries and understand the structure of the program without examining every brace.

• • •

## 3.3. Line Length

A source code line should not exceed 80 columns.

Long expressions, function calls, declarations, and other statements have to be divided into multiple lines when necessary. The line length limit is intended to keep code readable without requiring excessive horizontal scrolling.

Example:

```c
result = process_data(input, input_length,
		      output, output_capacity);
```

The following example is not allowed:

```c
result = process_data(input, input_length, output, output_capacity, flags, options, callback);
```

Comments and string literals should also be written with the line length limit in mind. When a string literal has to be split, the resulting code must preserve the intended string value.

The 80-column limit provides a consistent width for code review, terminal use, and side-by-side comparisons.

• • •

## 3.4. Use of Blank Lines

Blank lines should separate logically distinct parts of the code. They should improve readability by making changes in purpose or responsibility visible.

A single blank line should normally separate consecutive functions and distinct logical sections within a function. Multiple consecutive blank lines should not be used to create unnecessary visual space.

Example:

```c
static int validate_input(int value)
{
	if (value < 0)
		return -1;

	return 0;
}

int process_input(int value)
{
	int status;

	status = validate_input(value);
	if (status != 0)
		return status;

	return 0;
}
```

Blank lines should be used to show the logical structure of the implementation, not to compensate for unclear code organization.

• • •

## 3.5. Line-End Spaces

Trailing spaces and TAB characters at the end of a line are not allowed. Empty lines have to contain no whitespace characters.

Example:

```c
int process_value(int value)
{
	return value;
}
```

A line containing spaces or TAB characters after the last visible character is not allowed.

Trailing whitespace creates unnecessary changes in diffs and may cause problems with some editors and development tools. Keeping lines clean makes source files more consistent.

• • •

## 3.6. Curly Brace Placement

Control structures should place the opening brace on the same line as the condition. Function definitions should place the opening brace on the following line.

The closing brace should be aligned with the beginning of the statement that opened the block.

Example:

```c
if (condition) {
	process_value();
} else {
	handle_failure();
}

void process_data(void)
{
	initialize_data();
}
```

This rule separates function definitions visually from control structures while keeping control flow compact and consistent.

• • •

## 3.7. Single-line and Multi-line Blocks

Single-line blocks are not allowed. Every block has to use separate lines for its opening brace, body, and closing brace.

Curly braces are mandatory for the bodies of control structures, including `if`, `else`, `for`, `while`, and `do-while`, even when the body contains only one statement.

Allowed:

```c
if (ready) {
	start_process();
}
```

Not allowed:

```c
if (ready) start_process();
```

Not allowed:

```c
if (ready) { start_process(); }
```

Braces make block boundaries explicit and prevent mistakes when statements are added or removed. Requiring multi-line blocks also keeps the formatting consistent across the project.

• • •

## 3.8. Spacing Around Expressions and Operators

Spaces have to be used consistently around operators and within expressions.

Binary operators, including assignment, arithmetic, comparison, and logical operators, should have one space on both sides. Unary operators should be placed directly next to their operands. Function names should not be separated from their opening parentheses by a space.

Examples:

```c
result = left + right;
is_valid = value >= minimum;
pointer = &value;
value = *pointer;
index++;
process_value(value);
```

Pointer declarations should use the following form:

```c
int *pointer;
const char *name;
```

Type casts should not contain a space between the opening parenthesis and the type:

```c
result = (int)value;
```

Array indexing should not contain spaces inside the brackets:

```c
value = array[index];
```

Consistent spacing makes expressions easier to scan and helps readers distinguish operators from their operands.

## 3.9. Use of Commas, Semicolons, and Colons

Commas should be followed by one space. Semicolons should not be preceded by a space. Unnecessary spaces before closing punctuation are not allowed.

Example:

```c
process_value(first, second, third);

struct point point = {
	.x = 10,
	.y = 20,
};
```

The final comma in a multi-line initializer is allowed and recommended because it makes later additions easier to review.

The ternary conditional operator (`?:`) is not allowed by this guide. Conditional logic should use other constructs, such as `if` and `else`, to keep the control flow explicit.

Consistent punctuation spacing improves readability and prevents different formatting styles from appearing in the same codebase.

• • •

## 3.10. Formatting Function Calls

Function calls should remain on one line when they fit within the line length limit and remain readable. Long calls should be split across multiple lines.

For multi-line function calls, the opening parenthesis should remain on the first line, each argument should occupy its own line, and the closing parenthesis should be placed on a separate line.

Example:

```c
result = process_data(
	input,
	input_length,
	output,
	output_capacity
);
```

This format should be used for calls with many parameters, especially when the arguments have different meanings or types.

Function calls should not be split arbitrarily when a short, readable form is available. The purpose of multi-line formatting is to make arguments easy to identify and review.

• • •

## 3.11. Breaking Up Long Conditions and Expressions

Long conditions and expressions should be divided into multiple lines when they exceed the line length limit or become difficult to read.

Logical operators such as `&&` and `||` should remain at the end of the preceding line. Continuation lines should be indented consistently.

Example:

```c
if (input_is_valid &&
    output_is_available &&
    buffer_has_capacity) {
	process_data();
}
```

The following example is not allowed:

```c
if (input_is_valid
    && output_is_available
    && buffer_has_capacity) {
	process_data();
}
```

Long arithmetic expressions and nested conditions should also be formatted to make their structure clear. Parentheses should be used when they improve clarity, not as a replacement for understanding operator precedence.

Breaking up expressions makes the individual conditions easier to review without changing their meaning.

• • •

## 3.12. Formatting Macro Calls

Macro definitions and calls should follow the same general formatting rules as other source code. Multi-line macro definitions should use backslashes for line continuation, with the backslash placed at the end of each continued line.

Example:

```c
#define PROCESS_VALUE(value, minimum, maximum) \
	((value) >= (minimum) && \
	 (value) <= (maximum))
```

Macro parameters should be parenthesized when necessary to preserve the intended operator precedence. The complete replacement expression should also be parenthesized when appropriate.

Trailing whitespace after a line-continuation backslash is not allowed because it can interfere with preprocessing.

Macros should be formatted so that their boundaries and replacement expressions remain easy to identify. Their use should not introduce unnecessary ambiguity into the surrounding code.

• • •

## 3.13. Chained Function Calls and Nested Expressions

Chained calls and nested expressions should be formatted according to their logical structure. Expressions should not be compressed into a single line merely to reduce the number of lines.

When nested expressions become difficult to understand, intermediate variables should be used to give meaningful names to their results.

Example:

```c
int input_status;
int output_status;

input_status = validate_input(input);
output_status = validate_output(output);

if (input_status == 0 && output_status == 0) {
	process_data(input, output);
}
```

This is preferable to combining multiple unrelated operations into a deeply nested expression.

The objective is to make the order of operations and the purpose of each result clear. Additional variables should be introduced when they improve understanding, not merely to increase the number of statements.

• • •

## 3.14. Empty Blocks and Empty Expressions

Empty blocks are not allowed unless they are intentional and necessary for the operation being implemented. Every intentional empty block has to contain a comment explaining why it is empty.

Example:

```c
while (*cursor != '\0') {
	/*
	 * Intentionally empty: the loop waits for the
	 * condition to change through an external mechanism.
	 */
}
```

Empty loop expressions are allowed when they serve a clear purpose. For example, `for (;;)` may be used to express an unconditional loop.

```c
for (;;) {
	wait_for_event();

	if (should_exit())
		break;
}
```

The same principle applies to `while (true)` when the necessary boolean definition is available. An unconditional loop must have a valid and understandable exit path unless its purpose explicitly requires it to run indefinitely.

Empty statements and empty loop expressions should not be used accidentally. Their intent must be clear from the implementation.

• • •

## 3.15. Presence of a Newline at the End of the File

Every source and header file has to end with a newline character (`\n`). Files should not contain multiple unnecessary blank lines at the end.

Example:

```c
int process_value(int value)
{
	return value;
}
```

The final closing brace must be followed by a newline character.

A final newline keeps file endings consistent and prevents unnecessary differences in version control, compiler diagnostics, and text-processing tools.

___

# 4.0. Naming Rules

Naming is an important part of code design. A name should explain the purpose of an identifier and make its role understandable to the reader. Consistent naming also helps developers identify relationships between functions, variables, types, and modules.

This guide uses `snake_case` as the general naming style. Public identifiers follow a project and module naming structure, while internal identifiers should remain clear without unnecessary prefixes. Names should prioritize clarity over shortness.

## 4.1. General Naming Policy

Identifiers should use `snake_case` unless a specific rule defines another format. Names should describe the purpose, responsibility, or meaning of the identifier.

Public identifiers should follow the following structure:

`[app]_[module]_[functionality]`

Additional submodule names may be included when necessary. The structure should make the identifier's ownership and purpose clear.

Example:

```c
int us_encoder_dictionary_initialize(void);
int us_encoder_dictionary_add(void);
```

Internal identifiers do not have to follow the public naming structure. They should use clear and consistent names according to their scope and purpose.

Names should not be shortened only to reduce their length. A longer name is acceptable when it explains the functionality more clearly.

• • •

## 4.2. Character Set and Identifier Restrictions

Identifiers may contain English letters (`A-Z`, `a-z`), digits (`0-9`), and underscores (`_`). Identifiers must not begin with a digit.

Non-ASCII characters, spaces, hyphens, and other special characters are not allowed in identifiers.

Allowed:

```c
int process_data(void);
int buffer_size;
int item_count;
```

Not allowed:

```c
int process-data;
int buffer_size_bytes;
int 2items;
int dosya_ölçüsü;
```

The examples above illustrate the character restrictions; the exact spelling of an identifier must also follow the other naming rules in this guide.

Using a restricted character set keeps identifiers portable and avoids unnecessary problems with compilers, tools, and different development environments.

• • •

## 4.3. Variable Names

Variable names should describe the value they represent or the responsibility they serve. Internal variables should generally use `snake_case` without unnecessary application or module prefixes.

Example:

```c
size_t buffer_size;
size_t connection_count;
char *file_path;
```

Names such as `data`, `value`, and `status` may be used when their meaning is clear from the surrounding code. However, overly generic names should be avoided when they make the purpose of a variable difficult to understand.

Global variables are restricted. When a global variable is necessary, its name must follow the public naming structure defined in Section 4.1.

Variable names should help the reader understand the implementation without requiring them to repeatedly inspect where the variables are declared or modified.

• • •

## 4.4. Function Names

Function names must describe the operation performed by the function. Public functions must follow the `[app]_[module]_[functionality]` naming structure. Additional submodule names may be included when necessary.

Example:

```c
int us_encoder_dictionary_initialize(void);
int us_encoder_dictionary_add(void);
int us_encoder_dictionary_remove(void);
```

Function names should normally use verbs that describe their actions. Names such as `initialize`, `read`, `calculate`, and `remove` make the intended behavior easier to identify.

Internal functions should be defined in their source files without unnecessary declarations in headers. File-local `static` functions are generally discouraged in this project, but may be used when their scope is appropriate.

Function names should prioritize an accurate description of their behavior over shortness.

• • •

## 4.5. Type Names

Type names, including `struct`, `enum`, and `union` tags, must follow the public naming structure when they form part of the application's shared interface.

Example:

```c
struct us_encoder_dictionary_record {
	const char *name;
	size_t index;
};

enum us_encoder_connection_state {
	US_ENCODER_CONNECTION_STATE_DISCONNECTED,
	US_ENCODER_CONNECTION_STATE_CONNECTED
};

union us_encoder_data_value {
	int integer;
	float decimal;
};
```

Additional submodule names may be included when they help identify the type's purpose.

`typedef` usage is restricted. Existing types may be renamed through `typedef` when there is a clear reason, including when a different name is needed in another source file. `typedef` should not be introduced merely to hide the underlying type or create unnecessary aliases.

Type names should make the type's role and ownership clear without introducing additional naming conventions that conflict with the general policy.

• • •

## 4.6. Macro Names

Macro names must use uppercase `UPPER_SNAKE_CASE`. Public macros must follow the same application, module, and functionality structure, with their names written in uppercase.

Example:

```c
#define US_ENCODER_DICTIONARY_MAX_SIZE 1024
#define US_ENCODER_DICTIONARY_DEFAULT_SIZE 256
```

Function-like macros must follow the same naming rule:

```c
#define US_ENCODER_DICTIONARY_IS_EMPTY(dictionary) \
	((dictionary)->count == 0)
```

Macro names should be distinguishable from ordinary function and variable names. Their names should describe the value or operation they represent.

Consistent macro naming makes preprocessor definitions easy to identify and helps prevent confusion between macros and ordinary C identifiers.

• • •

## 4.7. Constant Names

Constant names must follow the naming rules of their respective identifier categories. The fact that a value is constant does not automatically require its variable name to use uppercase letters.

`const` variables should use `snake_case`, while macros and named enumeration constants should use uppercase `UPPER_SNAKE_CASE`. Public identifiers must also follow the application and module naming structure.

Example:

```c
const size_t us_encoder_dictionary_default_size = 256;

#define US_ENCODER_DICTIONARY_MAX_SIZE 1024

enum us_encoder_dictionary_limit {
	US_ENCODER_DICTIONARY_MIN_SIZE = 1,
	US_ENCODER_DICTIONARY_STANDARD_SIZE
};
```

Explicit values in enumeration definitions should generally be avoided when the compiler can assign the required values automatically. Explicit assignments are acceptable when particular numeric values are required by the design or interface.

For example, explicit enumeration values may be necessary when the values are part of a file format, protocol, or external interface.

Constant naming should make the value's meaning and intended use clear without confusing C's different forms of constants.

• • •

## 4.8. Global and File-Scope Identifiers

Global variables are restricted and should be introduced only when the design requires them. Public functions and variables must follow the `[app]_[module]_[functionality]` naming structure.

Example:

```c
int us_encoder_dictionary_initialize(void);

extern size_t us_encoder_dictionary_count;
```

File-scope identifiers with internal linkage do not necessarily require the complete public naming structure. Their names should describe their purpose within the source file.

Example:

```c
static size_t dictionary_capacity;
```

External identifiers should have names that clearly establish their ownership and reduce the possibility of collisions with identifiers from other modules or libraries.

The naming policy does not replace the rules governing linkage and visibility. A clear name does not make a global variable necessary, nor does it justify exposing an internal implementation detail through a public interface.

• • •

## 4.9. Static Function Names

`static` functions should generally be avoided when the design can be expressed clearly without them. Internal functions should normally be defined directly in their source files without unnecessary declarations in headers.

When a `static` function is necessary, its name should reflect its scope and responsibility.

A function intended for a specific module may use the following structure:

```c
static int dictionary_validate_entry(void);
```

A function associated with application-wide functionality may use an application-level prefix when appropriate:

```c
static int us_encoder_validate_configuration(void);
```

The complete public naming structure is not automatically required for every internal function. The chosen name should make the function's purpose and intended scope clear.

This policy is a recommendation about design and naming, not a prohibition against `static` functions. Internal linkage remains appropriate when it provides a meaningful boundary.

• • •

## 4.10. Parameter Names

Parameter names should describe the information received by a function and the role of each argument. They should generally use `snake_case`.

Example:

```c
int us_encoder_dictionary_add(
	const char *name,
	size_t name_length,
	size_t *record_index
);
```

Parameters should be understandable without requiring the reader to inspect the complete function implementation. Names such as `input`, `output`, `length`, and `capacity` may be used when their meaning is clear from the function's purpose.

Short names may be used for mathematical operations and other contexts in which their meaning is established by convention.

Parameter names should provide enough information to make function declarations useful as part of the interface.

• • •

## 4.11. Local Variable Names

Local variables should follow the same general naming rules as other variables. They should use `snake_case` and describe their purpose without unnecessary prefixes.

Example:

```c
int us_encoder_dictionary_add(
	const char *name,
	size_t name_length
)
{
	size_t index;
	int status;

	index = 0;
	status = 0;

	/* Implementation */

	return status;
}
```

Names such as `index`, `length`, and `status` are acceptable when their roles are clear from the surrounding code.

Local variables do not require application or module prefixes unless there is a specific reason to include them. Their limited scope already provides context.

The objective is to make the function easy to understand without adding repetitive information to every local identifier.

• • •

## 4.12. Loop Counters and Temporary Variables

Single-letter names are recommended for loop counters and short-lived variables when their purpose is clear from the immediate context.

Common examples include `i`, `j`, `k`, `l`, `m`, `n`, `z`, and `h`.

Example:

```c
for (size_t i = 0; i < item_count; i++) {
	process_item(items[i]);
}
```

Nested loops may use additional letters when each counter has a clear and distinct role.

```c
for (size_t i = 0; i < row_count; i++) {
	for (size_t j = 0; j < column_count; j++) {
		process_cell(i, j);
	}
}
```

Single-letter names should not be used when the variable represents a more complex concept or remains important beyond a small, easily understood operation.

Temporary variables should also use meaningful names when their purpose cannot be understood from the immediate context. Names such as `tmp` and `temp` should not replace a clearer description when one is available.

• • •

## 4.13. Boolean-Like Names

Boolean variables and functions should have names that make their true and false meanings clear. Names should describe a state, condition, capability, or decision.

Examples:

```c
bool is_valid;
bool has_permission;
bool can_read;
bool should_retry;
```

Public Boolean-like functions must follow the application and module naming structure.

Example:

```c
bool us_encoder_dictionary_is_empty(void);
bool us_encoder_dictionary_has_entry(const char *name);
```

Names should describe the actual condition being represented. Generic names such as `check`, `flag`, or `result` should be avoided when they do not explain the meaning of the value.

The naming convention should help readers understand what a true or false result means without having to inspect the implementation.

• • •

## 4.14. Pointer and Array Names

Pointer and array names should follow the general variable naming rules. Their names should describe the data they represent or the role they serve.

Example:

```c
char *buffer;
char **arguments;
int values[10];
```

The `_ptr` suffix may be used to distinguish a pointer from another identifier with a similar name. This suffix is recommended when the distinction improves clarity, but it is not mandatory.

Example:

```c
char *buffer_ptr;
char *buffer;
```

A suffix should not be added mechanically to every pointer. The type declaration already provides information about the object, and unnecessary suffixes can make names longer without improving their meaning.

Array names should describe the collection or its contents rather than merely identifying the fact that the object is an array.

• • •

## 4.15. Abbreviations and Acronyms

Abbreviations and acronyms may be used when they are widely understood within the relevant technical context. Unclear or unnecessarily shortened names should be avoided.

Examples:

```c
size_t file_descriptor;
size_t cpu_usage;
int http_request_status;
```

Common abbreviations such as `cpu`, `http`, and `id` are acceptable when they make the identifier clear to the intended audience.

Names such as `proc_data_cfg` should generally be avoided when `process_data_config` communicates the meaning more clearly.

Abbreviations should not be expanded merely for the sake of making names longer. The purpose is to improve understanding, not to prohibit established technical terminology.

• • •

## 4.16. Prefixes and Suffixes

Prefixes and suffixes may be used when they provide useful information about an identifier's role, ownership, or relationship to other identifiers. They should not be applied mechanically.

Examples:

```c
char *buffer_ptr;
size_t buffer_size;
size_t buffer_count;
```

The `_ptr` suffix is recommended when distinguishing a pointer from a related object improves readability. Suffixes such as `_size` and `_count` may be used when they accurately describe the value.

Prefixes such as `g_` for global variables and `s_` for static variables are not required. Scope and linkage should normally be determined from the declaration and source organization rather than encoded into every identifier.

The application and module naming structure remains mandatory for public identifiers. Other prefixes and suffixes are optional unless a more specific rule requires them.

• • •

## 4.17. Project and Module Namespaces

Public identifiers must follow the `[app]_[module]_[functionality]` structure. Additional submodule names may be included to identify more specific components.

Example:

```c
int us_encoder_dictionary_entry_add(void);
int us_encoder_dictionary_entry_remove(void);
int us_encoder_configuration_load(void);
```

The application prefix identifies the project, the module prefix identifies the relevant component, and the remaining name describes the functionality.

Names should be as descriptive as necessary to explain their purpose. Long identifiers are acceptable when the additional words provide useful information.

Internal identifiers do not need to repeat the complete public prefix when their scope already establishes their ownership. Public naming should remain consistent across source files and headers.

This structure helps reduce name collisions and makes the origin and purpose of public symbols easier to recognize.

• • •

## 4.18. Reserved Identifiers and Name Collisions

Identifiers must comply with the restrictions defined by the C standard, the compiler, and the target operating systems and libraries.

Names reserved by the C implementation or by the interfaces used by the project must not be used for application-defined identifiers. In particular, identifiers beginning with an underscore should be avoided because several such naming forms are reserved for the implementation.

Example:

```c
int us_encoder_dictionary_initialize(void);
```

The following form should not be used:

```c
int _dictionary_initialize(void);
```

Public identifiers should follow the application and module naming structure to reduce the likelihood of collisions with other components and libraries.

Naming conventions do not remove the need to respect reserved identifiers. Even a properly prefixed identifier must not conflict with a reserved name or violate restrictions imposed by the language implementation.

The objective is to maintain a clear and consistent naming space while respecting the requirements of C and the target platform.

___

# 5.0. Files and Including Standards

## 5.1. Source and Header File Responsibilities

Source and header files MUST have clearly separated responsibilities.

Header files (`.h`) MUST primarily contain declarations required by other source files. Source files (`.c`) MUST contain function definitions and implementation details.

Header files MAY contain the following when necessary:

- Type definitions.
- Macro definitions.
- Function declarations.
- External object declarations.
- `static inline` functions when justified.
- Other declarations required by the public or internal interface.

Function definitions SHOULD be placed in source files unless there is a clear reason to define them in a header.

Public headers MUST expose only the declarations required by the public API. Implementation details MUST NOT be exposed without a specific reason.

Internal headers MAY expose implementation details required for communication between modules.

Example:

```c
/* parser.h */

#ifndef PROJECT_PARSER_PUBLIC_H_
#define PROJECT_PARSER_PUBLIC_H_

struct parser_result;

int parser_parse(
    const char *input,
    struct parser_result *result);

#endif /* PROJECT_PARSER_PUBLIC_H_ */
```

```c
/* parser.c */

#include "parser.h"

int parser_parse(
    const char *input,
    struct parser_result *result)
{
    /* Implementation. */
}
```

The example demonstrates the separation between declarations and definitions. The actual implementation MUST satisfy the declared contract.

• • •

## 5.2. File and Directory Naming

File and directory names MUST use `snake_case`.

Source and header files SHOULD use descriptive names that reflect their responsibilities.

Examples:

```text
file_parser.c
file_parser.h
file_parser_internal.h
network/
network_connection.c
network_connection.h
```

Public header file names MUST NOT use a `PUBLIC` suffix. Internal header file names SHOULD use the `_internal.h` suffix.

The `PUBLIC` and `HEADER` suffixes are reserved for header guard identifiers, as described in Section 5.3.

Names SHOULD be descriptive enough to identify the file's purpose without requiring the reader to inspect its implementation.

• • •

## 5.3. Header Guards

Every header MUST have a header guard.

Header guard identifiers MUST use uppercase letters and underscores. They MUST contain enough information to avoid collisions between different headers.

Public header guards MUST use the `PUBLIC_H_` suffix.

Internal header guards MUST use the `HEADER_H_` suffix.

The guard SHOULD include the project, module, and header identity as appropriate.

Example public header:

```c
#ifndef PROJECT_PARSER_PUBLIC_H_
#define PROJECT_PARSER_PUBLIC_H_

/* Public declarations. */

#endif /* PROJECT_PARSER_PUBLIC_H_ */
```

Example internal header:

```c
#ifndef PROJECT_PARSER_HEADER_H_
#define PROJECT_PARSER_HEADER_H_

/* Internal declarations. */

#endif /* PROJECT_PARSER_HEADER_H_ */
```

Header guard names MUST NOT use reserved identifiers. In particular, identifiers beginning with an underscore followed by an uppercase letter or another underscore MUST NOT be used.

`#pragma once` MUST NOT replace header guards.

• • •

## 5.4. Include Ordering

Include directives MUST follow a consistent group order.

The recommended order is:

1. The header corresponding to the current source file.
2. C standard library headers.
3. Platform-specific headers.
4. Third-party library headers.
5. Internal headers included through configured include directories.
6. Headers belonging to the same module, included using quoted paths.

A blank line SHOULD separate different groups.

Within each group, headers MAY be sorted alphabetically or according to a consistent importance-based order. The selected approach MUST remain consistent within the project.

Example:

```c
#include "file_parser.h"

#include <stddef.h>
#include <stdint.h>
#include <stdlib.h>

#include <sys/types.h>

#include <third_party/library.h>

#include <network/connection_internal.h>

#include "parser_helpers.h"
#include "parser_state.h"
```

This example illustrates the group structure. Actual platform and third-party headers MUST be selected according to the source file's dependencies.

A source file MUST include its corresponding header first when such a header exists. This helps reveal missing declarations and dependencies in the header.

• • •

## 5.5. Quoted and Angle-Bracket Includes

Angle brackets (`<...>`) MUST be used for C standard library headers, platform headers, third-party headers, and internal headers accessed through configured include directories.

Double quotes (`"..."`) MUST be used for headers belonging to the same module and accessed through local paths.

The project MUST configure its include search paths so that these conventions work consistently.

The intended directory structure is:

```text
project/
├── include/
│   └── parser.h
├── src/
│   ├── include/
│   │   └── parser_internal.h
│   └── parser.c
└── ...
```

The `/include/` directory contains public API headers intended for external consumers.

The `/src/include/` directory contains internal headers used for communication between modules. These headers are not public API merely because they can be included using angle brackets.

Example:

```c
#include <stddef.h>
#include <parser_internal.h>

#include "parser_helpers.h"
```

Here, `parser_internal.h` is resolved through a configured include directory, while `parser_helpers.h` belongs to the same module.

Build-system configuration MUST provide the required include paths. A `.clangd` configuration MAY be used to provide include paths to Clang-based tools, but it MUST NOT be treated as a replacement for build-system configuration.

• • •

## 5.6. Direct and Transitive Dependencies

A source or header file MUST explicitly include the headers required for the declarations it uses, unless a valid forward declaration is sufficient.

Files MUST NOT rely on unrelated headers to include required declarations indirectly.

A transitive dependency occurs when a file obtains a declaration through another header rather than including the header that provides it directly.

Such dependencies SHOULD be avoided because changes in unrelated headers can otherwise break the file.

Example:

```c
#include <stddef.h>

struct connection;

struct session {
    struct connection *connection;
    size_t position;
};
```

The example does not require the complete definition of `struct connection` because it only declares a pointer to that type.

If the source file accesses members of `struct connection`, it MUST include the header that provides the complete definition.

Dependencies MUST reflect actual requirements. Unnecessary includes SHOULD be removed when they are no longer needed.

• • •

## 5.7. Self-Contained Headers

Public headers MUST be self-contained.

A public header MUST provide the declarations and direct dependencies required for consumers to include and use it according to its interface.

A public header MUST NOT require consumers to include unrelated headers first merely to make its declarations valid.

Internal headers MAY have more flexibility because they belong to the implementation and do not promise the same level of stability. However, they SHOULD remain independently includable whenever practical.

Including a header MUST NOT cause duplicate-definition errors or other avoidable compilation errors.

Header-only inclusion MUST be considered separately from linking. A header can be included successfully while the implementation of a declared function is still provided by a source file or library.

Example:

```c
/* session.h */

#ifndef PROJECT_SESSION_PUBLIC_H_
#define PROJECT_SESSION_PUBLIC_H_

#include <stddef.h>

struct session;

size_t session_get_position(const struct session *session);

#endif /* PROJECT_SESSION_PUBLIC_H_ */
```

The header includes `<stddef.h>` because it uses `size_t`. A consumer SHOULD NOT need to include `<stddef.h>` first.

Automatic independent compilation tests for every header are NOT mandatory. Nevertheless, public headers MUST satisfy the self-contained requirement.

• • •

## 5.8. Forward Declarations

Forward declarations SHOULD be used whenever they are sufficient and help reduce unnecessary dependencies.

A forward declaration is appropriate when a file needs to refer to a type without accessing its complete definition.

Example:

```c
struct connection;

struct session {
    struct connection *connection;
};
```

In this example, the definition of `struct connection` is not required to declare a pointer to it.

A complete type definition MUST be available when the code requires the type's size, accesses its members, or otherwise requires its full definition.

Example:

```c
#include "connection.h"

struct session {
    struct connection connection;
};
```

Here, the complete definition is required because `connection` is stored directly as a structure member.

C11 does not permit arbitrary forward declarations of enumeration types in the same way that it permits incomplete structure and union declarations. Enumeration declarations MUST follow the applicable C language rules.

Forward declarations MUST NOT introduce conflicting or incompatible type declarations.

The purpose of this rule is to reduce unnecessary coupling, not to avoid required includes.

• • •

## 5.9. Public and Internal Headers

Public and internal headers MUST be separated.

Public headers MUST reside under `/include/`. They define the API intended for external consumers.

Internal headers MUST reside under `/src/include/`. They define interfaces needed for communication between modules inside the project.

Public headers are part of the supported interface and MUST follow the public API and ABI stability requirements described in Section 5.16.

Internal headers do not carry the same stability guarantee. They MAY change when implementation requirements change, and modules that depend on them MUST be updated when necessary.

Internal headers MAY expose implementation-specific types and data structures.

When a module provides functions for operating on its own data structures, other modules SHOULD use those functions instead of directly modifying the structures' fields.

Example:

```c
/* Public interface. */

struct parser;

struct parser *parser_create(void);
void parser_destroy(struct parser *parser);
```

The public consumer can use the parser without knowing its internal representation.

An internal header may define the structure:

```c
/* parser_internal.h */

struct parser {
    unsigned int state;
    size_t position;
};
```

Other modules SHOULD use the parser's provided interface to modify its state when such an interface exists.

This approach reduces coupling and makes changes to internal representations easier.

• • •

## 5.10. Circular Dependencies

Circular dependencies between headers MUST NOT be introduced.

Circular dependencies between modules SHOULD also be eliminated. A module dependency graph SHOULD have a clear direction.

A header guard prevents repeated processing of the same header during preprocessing, but it does not resolve architectural dependency problems.

Example of a problematic design:

```text
module_a -> module_b
module_b -> module_a
```

Such a design SHOULD be refactored to remove the cycle.

Possible solutions include:

- Moving shared declarations into a separate module.
- Introducing an interface that both modules can depend on.
- Reversing a dependency where appropriate.
- Separating unrelated responsibilities.

Forward declarations MAY help remove unnecessary header dependencies, but they MUST NOT be used to hide an unresolved architectural dependency.

• • •

## 5.11. Static Functions and Internal Linkage

The use of static for file-local functions is at the developer's discretion, provided the function's visibility matches its intended use.

Functions that are intended to be used across source files MUST have an appropriate declaration in the corresponding internal or public header.

Functions that are private implementation details SHOULD remain in their source files and MUST NOT be declared in public headers.

When a function must be restricted to a single translation unit, `static` SHOULD be used to give it internal linkage.

Example:

```c
static int parser_validate_input(const char *input)
{
    /* File-local implementation. */
}
```

A helper function MUST NOT be exposed through an internal or public header solely to avoid using `static`.

The choice of linkage MUST reflect the intended visibility of the function. Avoiding `static` MUST NOT become a reason to expose implementation details unnecessarily.

• • •

## 5.12. External Linkage and Extern Declarations

External linkage SHOULD be restricted to symbols that must be accessed from other translation units.

Public functions MUST be declared in their public headers.

Functions shared between internal modules SHOULD be declared in the relevant internal headers.

Declarations MUST NOT be duplicated unnecessarily across unrelated source files.

The `extern` keyword MAY be used when an external declaration is required. However, source files SHOULD NOT introduce arbitrary `extern` declarations when the appropriate public or internal header already provides the declaration.

Example:

```c
/* parser.h */

#ifndef PROJECT_PARSER_PUBLIC_H_
#define PROJECT_PARSER_PUBLIC_H_

int parser_parse(const char *input);

#endif /* PROJECT_PARSER_PUBLIC_H_ */
```

A source file that uses `parser_parse` SHOULD include `parser.h` rather than declaring the function again.

External linkage MUST NOT be used merely because it is convenient. Symbols SHOULD remain private to their translation unit when cross-file access is unnecessary.

• • •

## 5.13. Global Variable Declarations and Definitions

Global variables MUST be restricted and MUST have a clear justification.

Global mutable state SHOULD be avoided when the same functionality can be provided through an explicit module interface or an owned data structure.

A global variable that must be shared between translation units MUST have a declaration in an appropriate header and exactly one definition in a source file.

Example:

```c
/* application_state.h */

#ifndef PROJECT_APPLICATION_STATE_HEADER_H_
#define PROJECT_APPLICATION_STATE_HEADER_H_

extern unsigned int application_state;

#endif /* PROJECT_APPLICATION_STATE_HEADER_H_ */
```

```c
/* application_state.c */

#include "application_state.h"

unsigned int application_state = 0;
```

The declaration does not define the object. The definition allocates storage for it.

Global variables exposed through public headers SHOULD be avoided unless they are an intentional part of the public API. Their presence increases coupling and can make future API and ABI changes more difficult.

A module SHOULD own its state and expose operations for accessing or modifying it when practical.

• • •

## 5.14. One-Definition and Linkage Constraints

External functions and objects MUST have a single definition in the program, subject to the applicable C language rules.

Headers MUST NOT contain ordinary external function or object definitions that would produce duplicate definitions when included by multiple source files.

Declarations and definitions MUST be distinguished correctly.

Example:

```c
/* counter.h */

#ifndef PROJECT_COUNTER_HEADER_H_
#define PROJECT_COUNTER_HEADER_H_

extern unsigned int counter;

#endif /* PROJECT_COUNTER_HEADER_H_ */
```

```c
/* counter.c */

#include "counter.h"

unsigned int counter = 0;
```

The header declares the object, while the source file defines it.

The rule MUST be applied according to the kind of entity involved. C11 has different rules for functions, objects, tentative definitions, types, macros, and `static` entities.

Header guards do not prevent duplicate definitions across separate translation units.

`static inline` functions and other permitted header definitions MUST follow the relevant C11 rules and MUST NOT create incompatible declarations or avoidable linkage conflicts.

• • •

## 5.15. Platform-Specific Headers

Platform-specific headers SHOULD be isolated from platform-independent implementation code.

Platform headers MAY appear in public headers when the public API genuinely requires platform-specific types or declarations. Such exposure MUST be deliberate.

Platform-specific dependencies SHOULD NOT leak into public headers without a clear API requirement.

When a public interface exposes platform-specific types, that dependency becomes part of the public contract and can affect portability, source compatibility, and ABI stability.

Platform-specific implementation details SHOULD remain in source files or internal headers whenever possible.

Example:

```c
/* Platform-independent public interface. */

struct file_handle;

int file_open(struct file_handle **handle, const char *path);
void file_close(struct file_handle *handle);
```

The implementation may use platform-specific file APIs internally without exposing their types to consumers.

If a public API intentionally exposes a platform-specific type, the decision MUST be documented and its compatibility consequences MUST be considered.

• • •

## 5.16. Header Compatibility and Dependencies

Public headers define the supported interface of the project. Their stability MUST be treated as a primary design concern.

Public API changes MUST preserve the established contract unless a breaking change is intentionally introduced under the project's compatibility policy.

The contract includes more than function declarations and data types. It also includes the documented purpose of a function, the kind of result it produces, and the way that result is provided to the caller.

For example, a public parsing function that returns its output through a pointer parameter MUST NOT silently change to returning a structure by value in a later version.

Example:

```c
int parser_parse(
    const char *input,
    struct parser_result *result);
```

Changing this interface to return `struct parser_result` by value changes the public contract and requires an intentional breaking API change.

Similarly, a public function MUST NOT silently stop performing its documented operation or begin performing additional externally observable operations that change its established contract.

Internal implementation details MAY change freely when the public contract remains intact.

The following rules apply:

- Public function declarations and public data representations MUST be changed deliberately.
- Function purpose and documented output behavior MUST remain consistent across compatible releases.
- Parameter meanings, return values, error behavior, ownership rules, and output mechanisms MUST be treated as part of the contract when specified.
- Public structure layouts MUST be considered part of the ABI when exposed to consumers.
- Opaque structures SHOULD be preferred in public APIs whenever practical.
- Internal data structures MAY be exposed through internal headers, but modules SHOULD use the owning module's interface to operate on them.
- ABI-affecting changes MUST be identified and evaluated before release.
- Platform-specific declarations exposed publicly MUST be included in compatibility assessments.
- Public headers MUST avoid unnecessary dependencies that could make consumers' builds or compatibility more fragile.

Source compatibility and ABI compatibility are distinct. A change may require recompilation or break existing source code, while another change may preserve source compatibility but break already compiled consumers.

The project MUST evaluate both when changing public interfaces.

Internal headers under `/src/include/` do not carry the same stability guarantee. They MAY change as implementation requirements evolve, provided dependent modules are updated accordingly.

Portability remains important, but it MUST NOT be used as a reason to weaken the public API and ABI stability requirements. Public interfaces MUST be designed deliberately, and changes to their contracts MUST be explicit rather than accidental.

___

# 6.0. Usage of Variables and Types

This section defines the rules for selecting, declaring, initializing, and using variables and types in C11. Its purpose is to make type semantics explicit, reduce unintended conversions, prevent invalid memory access, and maintain predictable interfaces.

Variables MUST have a clearly defined purpose, an appropriate type, and a valid initial value. Type selection MUST reflect the intended range, representation, lifetime, and ownership of the data.

The rules in this section apply to both internal implementation and public interfaces. Public API and ABI requirements MUST take precedence over internal implementation preferences.

## 6.1. Fundamental Types

Fundamental types MUST be selected according to the purpose of the value. The use of less common fundamental types MUST have a clear technical justification.

The following types are preferred for ordinary use:

- `int` for general-purpose integer values and counters.
- `char` for character data and character arrays.
- `float` as the default floating-point type when its precision is sufficient.
- `double` when additional precision or an interface requirement justifies its use.
- `size_t` for object sizes, memory lengths, and values associated with `sizeof`.

The use of `short`, `long`, `long long`, `long double`, and other less commonly required fundamental types SHOULD be limited to cases where their range, precision, or compatibility properties are necessary.

The choice of a fundamental type MUST NOT rely on an assumed size or representation unless the C standard guarantees that property.

For example, `int` MUST NOT be assumed to be exactly 32 bits, and `char` MUST NOT be assumed to be signed.

```c
int item_count = 0;
size_t buffer_size = 0;
float normalized_value = 0.0f;
double precise_result = 0.0;
```

`float` is the preferred default for floating-point variables under this guide's memory-conscious policy. However, this preference MUST NOT be interpreted as a guarantee that `float` is always faster than `double`. The required precision and the characteristics of the target implementation MUST be considered.

• • •

## 6.2. Fixed-Width Integer Types

Fixed-width integer types from `<stdint.h>` MUST be used when an exact integer width is part of the requirement.

Examples include:

- Binary file formats.
- Network protocols.
- Explicitly defined binary representations.
- Hardware interfaces requiring a specified integer width.
- Interoperability contracts requiring an exact-width type.

```c
#include <stdint.h>

uint32_t message_length = 0;
int32_t temperature_offset = 0;
uint64_t record_identifier = 0;
```

Types such as `uint32_t` and `int64_t` are optional in C11. They are available only when the implementation provides a suitable integer type with the required properties.

Fixed-width types MUST NOT be used indiscriminately for every integer variable. Ordinary counters, sizes, and other implementation-oriented values SHOULD use the type most appropriate to their purpose.

The use of a fixed-width type does not, by itself, define byte order, structure layout, or a portable serialization format. These properties MUST be specified separately when relevant.

• • •

## 6.3. Integer Type Selection

Integer types MUST be selected according to the meaning and expected range of the value.

The following conventions MUST be followed:

- General-purpose counters SHOULD use `int` when its range is sufficient.
- Object sizes, memory lengths, and values derived from `sizeof` MUST use `size_t` where appropriate.
- Values requiring an exact width MUST use a suitable fixed-width integer type.
- Identifiers and keys MUST use a type appropriate to their documented range and interface contract.
- Values that may legitimately be negative MUST use a signed type.

For example:

```c
int retry_count = 0;
size_t file_length = 0;
uint32_t protocol_version = 0;
int exit_status = 0;
```

The choice of a type MUST NOT be based solely on a variable's name. An identifier does not automatically require an unsigned type, and a variable representing a length does not automatically require `size_t` if its interface contract specifies a different representation.

The selected type MUST be able to represent every valid value that the variable may hold.

• • •

## 6.4. Signed and Unsigned Types

Unsigned integer types SHOULD be preferred when non-negativity is an explicit property of the value and the selected range is appropriate.

Signed types MUST be used when negative values are meaningful.

The use of unsigned types MUST be deliberate. A value MUST NOT be declared unsigned merely because negative values are not expected in normal operation.

Signed and unsigned operands MUST NOT be mixed in arithmetic expressions or comparisons. When values of different signedness must interact, their ranges MUST be validated and their conversion MUST be made explicit before the operation.

For example, the following comparison is unsafe as a general pattern:

```c
int index = -1;
unsigned int limit = 10U;

/* Do not compare mixed signed and unsigned values directly. */
```

A negative signed value converted to an unsigned type can become a large positive value. Such conversions may produce results that differ from the apparent mathematical meaning of an expression.

The programmer MUST verify that a conversion preserves the intended value before performing arithmetic or comparison.

Unsigned arithmetic also wraps modulo the range of its type. This behavior MUST NOT be mistaken for a substitute for overflow checking.

• • •

## 6.5. Floating-Point Types

`float` MUST be the default floating-point type when its precision and range are sufficient.

`double` SHOULD be used when additional precision is required, when a public interface specifies it, or when a calculation's numerical requirements justify it.

`long double` SHOULD be reserved for cases where its additional implementation-provided precision or range is explicitly needed.

```c
float progress_ratio = 0.0f;
double accumulated_error = 0.0;
```

Floating-point types MUST NOT be treated as interchangeable representations of the same precision. The precision, range, rounding behavior, and representation of floating-point values can depend on the implementation.

Floating-point values MUST NOT be compared for exact equality when the calculation may introduce rounding error, unless exact equality is specifically required by the operation's semantics.

The choice between `float` and `double` SHOULD account for memory use, numerical accuracy, compatibility, and measured performance. The assumption that `float` is always faster MUST NOT be used as the sole justification for selecting it.

• • •

## 6.6. Boolean Values

The C11 boolean type MUST be used for values that represent an ordinary true-or-false condition.

The `<stdbool.h>` header MUST be included when using `bool`, `true`, and `false`.

```c
#include <stdbool.h>

bool is_ready = false;
bool has_data = true;
```

Boolean variables MUST NOT use arbitrary integer values to represent conditions when `bool` expresses the intended meaning more clearly.

However, functions whose return values follow the project's status-code contract MUST use that contract rather than treating their return values as ordinary booleans.

Status-returning functions MUST use the project's documented status constants, including the success code and any defined error codes. A status code MUST be compared with its documented value; it MUST NOT be interpreted as a boolean merely because it is an integer.

For example, when `STATUS_SUCCESS` is defined as zero:

```c
int status = foo_exists();

if (status == STATUS_SUCCESS) {
    /* The query completed and foo exists. */
} else if (status == STATUS_DOES_NOT_EXIST) {
    /* The query completed and foo does not exist. */
} else {
    /* Another error occurred. */
}
```

The exact meaning of each status code MUST be documented in the relevant interface. A function MUST NOT use zero to mean boolean true when its status contract defines zero as success and the result is expected to be used as a conventional C boolean expression.

• • •

## 6.7. Void and Void Pointers

The `void` return type MUST be used for functions that do not return a value.

`void *` MAY be used when an interface genuinely requires a generic pointer to an object whose concrete type is determined elsewhere.

```c
void reset_state(void);

void process_object(void *object);
```

A `void *` MUST NOT be used when a more specific pointer type communicates the intended object type and ownership more clearly.

In C, an object pointer can be converted to `void *` and back to its original object pointer type with the required value preserved. Function pointers are not interchangeable with object pointers and MUST NOT be treated as such.

A generic pointer interface MUST document any required assumptions about the pointed-to object, including its type, lifetime, mutability, and ownership.

Functions that do not accept parameters SHOULD declare `(void)` in their parameter list rather than using an empty parameter list.

• • •

## 6.8. Typedef Usage

The `typedef` specifier MUST be used restrictively.

Structure, enumeration, and union types MUST be declared using their actual tags by default. A `typedef` MUST NOT be added merely to remove the `struct`, `enum`, or `union` keyword.

```c
struct connection {
    int descriptor;
    bool is_open;
};

enum connection_state {
    CONNECTION_STATE_CLOSED,
    CONNECTION_STATE_OPEN
};

union value_storage {
    int integer_value;
    float floating_value;
};
```

A type alias MAY be introduced in another file when a genuine interface, abstraction, or compatibility requirement justifies it.

When such an alias is used, the contract MUST make the original type and its ownership or defining module clear. The alias MUST NOT obscure important type information or make the origin of a value ambiguous.

For example, a module MAY expose a documented alias for a type defined elsewhere when the alias serves a specific interface purpose. The alias MUST NOT imply that the underlying type is public or ABI-stable when it is not.

The use of `typedef` for function pointers or other types MUST likewise have a clear purpose rather than serving as an automatic naming convention.

• • •

## 6.9. Const Correctness

The `const` qualifier SHOULD be used wherever it accurately expresses that an object or pointed-to value must not be modified through a particular access path.

Function parameters SHOULD use `const` when the function does not need to modify the referenced object.

```c
int calculate_length(const char *text);
```

Local variables SHOULD be declared `const` when their values do not need to change after initialization.

```c
const size_t header_length = 16U;
```

The `const` qualifier on a pointer and the `const` qualifier on the pointed-to object have different meanings.

```c
const int *read_only_value;
int *const fixed_pointer = NULL;
```

The first declaration prevents modification of the pointed-to integer through that pointer. The second prevents reassignment of the pointer itself after initialization.

`const` MUST NOT be used as a substitute for documenting ownership, synchronization, or lifetime. It also MUST NOT be removed through a cast to modify an object that was originally defined as `const`; doing so results in undefined behavior.

• • •

## 6.10. Volatile Usage

The `volatile` qualifier MUST be used only when a documented requirement justifies volatile access semantics.

Appropriate use cases MAY include:

- Memory-mapped hardware registers.
- Platform interfaces that explicitly require volatile accesses.
- Certain objects accessed by signal handlers, subject to C11's specific restrictions.

```c
volatile unsigned int *device_register;
```

The use of `volatile` MUST be justified by the relevant platform or interface requirements. It MUST NOT be added merely because a variable is accessed in multiple places or because the programmer wants to prevent all compiler optimizations.

`volatile` MUST NOT be used as a substitute for atomic operations, mutexes, or other synchronization mechanisms between threads. It does not guarantee atomicity or establish the required inter-thread synchronization.

Code using volatile-qualified objects SHOULD be isolated to the relevant hardware or platform interface when practical.

• • •

## 6.11. Restrict Usage

The `restrict` qualifier MAY be used when a pointer-access contract genuinely satisfies the restrictions required by C11 and the optimization benefit justifies the additional contract.

```c
void add_arrays(
    size_t length,
    const float *restrict left,
    const float *restrict right,
    float *restrict result);
```

In this example, the caller and implementation MUST respect the aliasing requirements implied by the `restrict` declarations for the objects accessed during the relevant execution.

`restrict` MUST NOT be added merely as an optimization hint without verifying the actual pointer relationships.

Violating the applicable `restrict` requirements can result in undefined behavior. The programmer MUST ensure that the contract remains valid for every supported call path.

Where the necessary aliasing conditions cannot be established, ordinary pointers MUST be used instead.

• • •

## 6.12. Variable Declaration and Initialization

Variables MUST be declared at the beginning of their respective blocks.

A block is the relevant compound statement enclosed by braces. This rule does not require every variable in a function to be declared at the beginning of the function; nested blocks MAY have their own declarations at their beginnings.

Every variable MUST be initialized at its declaration.

```c
void process_data(void)
{
    int item_count = 0;
    size_t buffer_length = 0;
    char *buffer = NULL;

    if (buffer == NULL) {
        /* Handle the initial state. */
    }
}
```

Declarations MUST be grouped in a predictable manner, and initialization values MUST reflect the intended initial state of the variable.

Pointers MAY be initialized to `NULL` when no valid target is available initially. Numeric variables MAY be initialized to zero when zero is a valid and appropriate initial value. Other types MUST receive a valid initial value appropriate to their semantics.

The requirement to initialize variables does not mean that zero is the correct initial value for every object. The programmer MUST select a meaningful initial value.

• • •

## 6.13. Variable Scope and Lifetime

Variables MUST have the narrowest practical scope and the shortest appropriate lifetime.

Global variables MUST be avoided. State SHOULD be created and owned by the highest-level caller that needs to manage it, then passed explicitly to the functions that require it.

```c
int process_item(int item_value, int retry_limit);
```

Functions SHOULD depend on their parameters and documented interfaces rather than assuming that a global variable exists.

File-scope variables MAY be used when a module genuinely requires persistent internal state, but their use MUST be justified and their visibility MUST be restricted where possible.

Automatic storage duration SHOULD be preferred for ordinary local variables. Static storage duration MUST be used only when the lifetime requirement justifies it.

The scope and lifetime of a variable MUST NOT exceed what is necessary to fulfill its purpose.

• • •

## 6.14. Variable Shadowing

Variable shadowing MUST be avoided.

A declaration MUST NOT reuse the name of a variable already visible in an enclosing scope when doing so would obscure which object is being referenced.

```c
int item_count = 10;

if (item_count > 0) {
    int remaining_count = item_count;
    /* Use remaining_count rather than shadowing item_count. */
}
```

Distinct names SHOULD express distinct roles. Shadowing MUST NOT be used as a shortcut for reusing an existing name when the new variable represents a different object or a different stage of processing.

This rule applies to local variables and other identifiers where reuse would reduce clarity.

• • •

## 6.15. Type Conversions and Casts

Type conversions MUST preserve the intended meaning of the value.

Unnecessary casts MUST be avoided. Casts MAY be used when a conversion is required, when the intended conversion needs to be explicit, or when a documented interface requires a particular type.

```c
double ratio = (double) numerator / denominator;
```

The cast in this example ensures that floating-point division is performed when `numerator` and `denominator` are integer values.

Casts MUST NOT be used merely to suppress compiler warnings. A warning about incompatible types, possible data loss, signedness, or pointer misuse MUST be investigated and resolved at the appropriate level.

Before converting an integer to a narrower type, the programmer MUST ensure that the value is within the destination type's representable range.

Pointer casts MUST be used only when the conversion is valid under the C standard and the target interface's requirements.

The use of a cast does not guarantee that the conversion is safe. Every nontrivial cast MUST have a clear technical justification.

• • •

## 6.16. Integer Promotions and Arithmetic Conversions

Integer promotions and the usual arithmetic conversions MUST be considered whenever they affect the meaning or range of an expression.

Signed and unsigned operands MUST NOT be mixed in arithmetic expressions or comparisons. If values of different signedness must interact, the programmer MUST validate their ranges and convert them to a suitable common type before the operation.

```c
int signed_count = 0;
unsigned int unsigned_limit = 10U;

/* Validate and convert values before combining them. */
```

Intermediate expressions MUST NOT be assumed to use the type of the destination variable. The types of the operands determine the type in which the operation is performed, subject to C's conversion rules.

The programmer MUST consider:

- Integer promotions.
- The usual arithmetic conversions.
- Signed integer overflow.
- Unsigned integer wraparound.
- Loss of precision or range during conversion.
- Comparisons between values with different types.

Signed integer overflow MUST NOT be relied upon; in C11, it results in undefined behavior. Unsigned arithmetic wraps modulo the range of its type, but that behavior MUST be used only when it matches the intended algorithm.

When the intended arithmetic cannot be expressed safely with the original operand types, the programmer SHOULD use validated conversions and appropriately typed intermediate variables.

• • •

## 6.17. Integer Constants and Suffixes

Integer constants MUST have types appropriate to their intended use.

The `U`, `L`, and `LL` suffixes MAY be used as needed to select an appropriate unsigned or long integer constant type. The suffix and the constant's value MUST be considered together.

```c
unsigned int retry_limit = 10U;
unsigned long long maximum_records = 1000000ULL;
```

Suffixes MUST NOT be added mechanically. The programmer MUST understand how the constant's type affects arithmetic, comparisons, and conversions.

When a constant represents a fixed-width value, the associated type and range MUST be appropriate to the relevant contract.

Integer constants MUST NOT be assumed to have the same type merely because they have similar numerical values. In particular, unsuffixed decimal and hexadecimal constants can have different type-selection behavior under the C rules.

The chosen suffix MUST make the intended arithmetic clear without concealing an underlying type mismatch.

• • •

## 6.18. Enumerations

Enumeration types SHOULD be used for internal collections of named, related values, such as states or modes.

```c
enum connection_state {
    CONNECTION_STATE_CLOSED,
    CONNECTION_STATE_OPEN,
    CONNECTION_STATE_ERROR
};
```

Enumeration types MUST NOT be exposed as part of a public API or ABI unless they are explicitly approved as part of that stable contract.

Explicit enumeration values SHOULD be avoided unless the values must match a defined external representation, protocol, or other documented requirement.

The implementation MUST NOT assume that an enumeration has a particular size or representation unless that property is guaranteed by a separate contract.

Enumeration constants MUST follow the project's naming rules. The use of an enumeration MUST improve clarity over unrelated numeric constants.

• • •

## 6.19. Structures and Unions

Structures MUST be the default choice for grouping related data.

```c
struct file_info {
    size_t file_size;
    int access_status;
};
```

A structure SHOULD contain fields that belong together conceptually. Its fields MUST have types appropriate to their meanings and valid value ranges.

Unions MAY be used when multiple alternative representations genuinely need to share storage.

```c
union value_storage {
    int integer_value;
    float floating_value;
};
```

When a union is used, the code MUST have a clear rule for determining which member is active and how that member may be accessed. The programmer MUST NOT assume that writing one member makes every other member safely readable as an equivalent value.

Structures and unions intended for public API or ABI use MUST be explicitly identified as part of the stable interface. Internal structures and unions MUST NOT be treated as stable merely because they appear in an internal header.

Public structure layouts require particular care because field types, order, alignment, and size can affect ABI compatibility.

• • •

## 6.20. Bit-Fields

Bit-fields MAY be used for internal flags, compact state representations, and other memory-sensitive fields when their use provides a meaningful benefit.

```c
struct internal_flags {
    unsigned int is_ready : 1;
    unsigned int has_error : 1;
    unsigned int mode : 3;
};
```

Bit-fields are implementation-dependent in important respects, including aspects of allocation, ordering, and storage-unit layout. Their exact representation MUST NOT be assumed to be portable across implementations.

Bit-fields MUST NOT be exposed directly as part of a public API or ABI that requires a stable, portable representation.

Bit-fields MUST NOT be used as a direct definition of a portable file format or network protocol. Such formats SHOULD be encoded and decoded explicitly using documented integer representations and bit operations.

The use of bit-fields SHOULD be justified by memory constraints, a clear internal representation requirement, or another concrete technical benefit. Their use MUST NOT compromise correctness or make the representation unnecessarily difficult to maintain.

• • •

## 6.21. Designated Initializers

Designated initializers MAY be used when they improve clarity, particularly when initializing structures with several fields or fields whose order is not immediately obvious.

```c
struct file_info info = {
    .file_size = 0,
    .access_status = 0
};
```

Designated initializers SHOULD be used selectively rather than automatically for every initializer.

For short and straightforward initializers, ordinary positional initialization MAY be used when the field order is clear.

When positional initialization is used, the order and types of the initialized members MUST be understood and correct. The initializer MUST NOT rely on an incorrect assumption about member ordering.

Designated initializers MUST follow C11 syntax and MUST NOT be confused with C++ designated-initializer rules or extensions.

• • •

## 6.22. Compound Literals

Compound literals SHOULD be avoided.

Although compound literals are a standard C feature, they can make object lifetime and the origin of a value less obvious, especially when used inside complex expressions or when pointers to the resulting objects are retained.

Named variables with explicit declarations and initializers SHOULD be preferred when they make the data flow, lifetime, or ownership easier to understand.

```c
struct file_info info = {
    .file_size = 0,
    .access_status = 0
};
```

Compound literals MAY be used only when there is a clear reason and the alternative would be materially less clear or practical. Their use MUST NOT obscure object lifetime, pointer validity, or ownership.

• • •

## 6.23. Static Assertions

The C11 `_Static_assert` facility MAY be used to verify critical compile-time assumptions.

Its use SHOULD be rare and reserved for conditions that genuinely need compile-time enforcement, such as a required constant relationship or a representation assumption that the implementation must satisfy.

```c
#include <limits.h>

_Static_assert(CHAR_BIT >= 8, "Unsupported byte width");
```

Static assertions MUST express a condition that can be evaluated at translation time. They MUST NOT be used as a substitute for runtime validation of data that can vary during execution.

When an assumption is important to correctness or compatibility, a static assertion MAY be preferable to relying on a comment alone. The restriction on frequent use MUST NOT prevent the verification of critical requirements.

• • •

## 6.24. Alignment and Object Representation

Alignment and object representation MUST NOT be assumed to be identical across implementations.

The `_Alignas` specifier SHOULD generally be avoided unless a documented alignment requirement justifies it. The `_Alignof` operator MAY be used when alignment information is genuinely required.

Memory layout MAY be optimized by carefully designing structures, including arranging fields to reduce unnecessary padding or introducing explicit padding fields when appropriate.

```c
struct internal_record {
    uint32_t identifier;
    uint16_t flags;
    unsigned char reserved[2];
};
```

Explicit padding MAY be useful for a documented internal layout or performance requirement. However, adding a padding array does not, by itself, guarantee the alignment of the structure or its members. The compiler may still insert padding according to its own alignment rules.

The `sizeof` result, member offsets, alignment, and padding MUST NOT be assumed to match another compiler or platform unless the relevant requirements are explicitly guaranteed and verified.

Raw structure memory MUST NOT be treated as a portable serialization format. Padding bytes and implementation-specific layout can make such representations unsuitable for files, protocols, and stable external interfaces.

Alignment optimizations SHOULD be based on a documented requirement or measured benefit rather than unsupported assumptions.

• • •

## 6.25. Implementation-Defined Type Properties

Code MUST NOT rely on implementation-defined type properties without a documented and verified requirement.

Relevant properties MAY include:

- The sizes of fundamental types.
- The signedness of plain `char`.
- The representation and range of integer types.
- The representation and precision of floating-point types.
- Structure padding and alignment.
- The representation of enumeration types.

When a platform-specific property is required, the code MUST document the dependency and verify the required condition where practical.

Fixed-width types SHOULD be used when an exact integer width is necessary. However, their use does not eliminate the need to specify byte order, serialization rules, alignment, or other representation details.

Code that depends on a particular implementation MUST NOT be presented as universally portable C11 code.

• • •

## 6.26. Register Storage-Class Specifier

The `register` storage-class specifier MUST NOT be used.

The compiler is responsible for deciding whether a variable should be held in a register or stored elsewhere. Explicit use of `register` is unnecessary for the intended optimization policy and can impose additional language restrictions, including restrictions on taking the variable's address.

```c
int calculate_total(int item_count)
{
    int total = 0;

    /* The compiler decides how to store total. */
    return total + item_count;
}
```

Performance-sensitive code SHOULD be optimized through appropriate algorithms, profiling, and compiler optimization settings rather than through the `register` specifier.

• • •

## 6.27. Extern and Static Storage-Class Specifiers

External linkage MUST be restricted to identifiers that genuinely need to be accessible across translation units.

Declarations of public interfaces MUST be placed in the appropriate public headers. Internal cross-module interfaces MUST be declared in the appropriate internal headers.

The `extern` specifier MAY be used when required by the interface or declaration. However, unnecessary external declarations and duplicated declarations SHOULD be avoided.

The `static` specifier SHOULD be used when file-local linkage is required, including for private functions and variables that must not be exposed to other translation units.

```c
static int calculate_internal_value(int input_value)
{
    return input_value * 2;
}
```

Neither `extern` nor `static` is categorically prohibited. Their use MUST reflect the intended linkage and visibility of the identifier.

External linkage MUST NOT be granted merely for convenience. Functions and objects MUST be exposed only when the module or public contract requires them to be accessible outside their defining translation unit.

Function-local static variables are governed separately by Section 6.28 and MUST NOT be used.

• • •

## 6.28. Automatic and Static Storage Duration

Automatic storage duration SHOULD be the default for local variables.

Function-local variables with static storage duration MUST NOT be used. Persistent state SHOULD instead be managed explicitly by the owning module and supplied to functions through parameters or documented interfaces.

```c
int calculate_next_value(int current_value)
{
    int next_value = current_value + 1;

    return next_value;
}
```

File-scope objects with static storage duration MAY be used when a module requires persistent internal state. Their use MUST be justified, and their visibility MUST be restricted where possible.

The design SHOULD prefer explicit state ownership and parameter passing over hidden persistent state.

Static storage duration MUST NOT be introduced merely to preserve a local variable's value between function calls. Where persistent state is necessary, the state and its lifetime SHOULD be visible in the module's design.

• • •

## 6.29. Uninitialized Variables

Every variable MUST be initialized at the point of declaration.

A variable MUST NOT be read before it has received a valid value. This rule applies to scalar objects, pointers, arrays, structures, unions, and other object types.

```c
int item_count = 0;
size_t buffer_size = 0;
char *buffer = NULL;
```

The initial value MUST be appropriate to the variable's intended meaning. Zero is appropriate only when zero represents a valid initial state. A pointer MAY be initialized to `NULL` when it does not yet refer to a valid object.

Structures and unions MUST be initialized according to the requirements of their intended use. The programmer MUST NOT assume that declaring an object automatically initializes all of its members to zero.

For aggregate objects, an initializer that initializes all members to their appropriate initial values SHOULD be preferred. Where zero initialization is appropriate, a valid aggregate initializer MAY be used.

```c
struct file_info info = {0};
```

The use of an initializer MUST NOT be treated as proof that every possible future operation on the object is valid. Pointers, lengths, ownership states, and other related fields MUST still maintain their documented invariants.

• • •

## 6.30. Variable Declaration Placement

All variable declarations MUST appear at the beginning of their respective blocks.

This rule applies to function bodies and nested compound statements. It does not require all variables in a function to be declared at the beginning of the function if some variables belong to a nested block.

```c
void process_items(int item_count)
{
    int processed_count = 0;
    int current_item = 0;

    if (item_count > 0) {
        int remaining_count = item_count;

        current_item = remaining_count;
        processed_count = 1;
    }

    (void)current_item;
    (void)processed_count;
}
```

Declarations MUST NOT be interspersed with executable statements within the same block. When a variable is needed only for a particular operation, a nested block MAY be introduced so that its declaration remains at the beginning of that block.

Every declared variable MUST also follow the initialization requirement in Section 6.29.

The purpose of this rule is to provide a consistent declaration layout, make variable lifetimes easier to inspect, and reduce ambiguity when reviewing code.

___

# 7.0. Function Designing Principles

Functions MUST be designed around clearly defined responsibilities, explicit interfaces, predictable control flow, and documented contracts. A function's implementation MUST comply with its contract, and its callers MUST satisfy the preconditions specified by that contract.

The following rules establish a consistent approach to function declarations, definitions, parameter handling, return values, error handling, resource management, documentation, and interface design.

## 7.1. Function Prototypes and Declarations

Every function MUST be declared before its first use. A function declaration MUST provide an explicit return type and parameter type information.

* Function declarations MUST use prototypes with explicitly specified parameter types.
* Functions that accept no parameters MUST declare `(void)` rather than an empty parameter list.
* Public functions MUST be declared in their appropriate public headers.
* Internal functions shared between source files MUST be declared in an appropriate internal header.
* Functions used exclusively within one source file MUST be declared within that source file before their first use. Their declarations SHOULD be placed near the beginning of the file, following the established source-file organization.
* File-local functions MUST use `static` to restrict their linkage to the current translation unit.
* Function declarations MUST NOT be duplicated unnecessarily across unrelated headers or source files.
* A function declaration MUST be consistent with its definition in return type, parameter types, qualifiers, and other relevant type information.

A declaration introduces a function's interface; a definition provides its implementation. These terms MUST NOT be used interchangeably.

Correct example:

```c
int buffer_process(const char *buffer, size_t length);

void buffer_reset(void);
```

Incorrect example:

```c
int buffer_process();
void buffer_reset();
```

In C11, an empty parameter list in a declaration does not provide the same prototype guarantees as `(void)`.

**Rationale:** Explicit prototypes enable compiler type checking, reduce accidental interface mismatches, and make function dependencies easier to understand.

• • •

## 7.2. Function Definitions

Function definitions MUST follow a consistent formatting and structural convention.

* Each function definition MUST have one explicit return type and one descriptive function name.
* All parameters MUST have explicitly declared types.
* Functions accepting no parameters MUST use `(void)`.
* Opening and closing braces MUST follow the project's established brace style.
* Indentation MUST remain consistent throughout the function body.
* Local variable declarations MUST appear at the beginning of their respective blocks, as required by Section 6.
* The main execution path SHOULD remain visually distinguishable from error handling and cleanup paths.
* Conditional branches, loops, and nested blocks MUST use consistent formatting.
* Return statements MUST comply with the function's declared return type and return-value contract.
* A function definition MUST implement the behavior specified by its documented contract.
* Function definitions MUST NOT contain unrelated operations merely to avoid introducing another function.

Example:

```c
int buffer_process(const char *buffer, size_t length)
{
    int status = STATUS_SUCCESS;

    /* Function implementation. */

    return status;
}
```

The example illustrates formatting only. The actual implementation MUST satisfy the function's complete contract.

**Rationale:** A uniform definition style improves reviewability and reduces the cognitive effort required to understand unfamiliar code.

• • •

## 7.3. Function Naming

Function names MUST comply with the project's naming conventions established in Section 4.

* Function names MUST use lowercase `snake_case`.
* Names MUST describe the operation performed rather than merely the implementation mechanism.
* Public function names MUST follow the `app_module_functionality` naming pattern, replacing each component with the appropriate project, module, and operation identifiers.
* Internal functions SHOULD follow the same naming conventions, even when they do not require a public prefix.
* Boolean-like concepts MUST be distinguished from operations that return status codes.
* Names SHOULD make the intended operation apparent without requiring the reader to inspect the implementation.
* Abbreviations MUST remain understandable and consistent with the naming rules.
* Function names MUST NOT conflict with reserved identifiers or standard-library names in ways that create portability or correctness problems.

Examples:

```c
int app_buffer_initialize(struct buffer *buffer);

int app_buffer_is_empty(const struct buffer *buffer);
```

Under the project's return-type policy, `app_buffer_is_empty()` returns a status code rather than a C `bool`. Its contract MUST define precisely which status code represents each result.

Names such as `get_value()` or `process_data()` MAY be used when appropriate, but MUST NOT replace more descriptive names when the operation can be identified more precisely.

**Rationale:** Consistent names communicate module ownership and operation intent while reducing ambiguity across public and internal interfaces.

• • •

## 7.4. Parameter Ordering

Function parameters MUST follow a consistent order:

1. Input parameters.
2. Context or state parameters.
3. Output parameters.

Input parameters provide the data required for an operation. Context or state parameters provide the object, environment, or execution state within which the operation takes place. Output parameters receive results produced by the function.

Example:

```c
int app_parser_parse(
    const char *input,
    struct parser_context *context,
    struct parse_result *output);
```

The ordering above is illustrative; the types and names MUST reflect the actual interface.

* Parameters within each group SHOULD be ordered consistently according to their logical relationships.
* A parameter MUST NOT be placed in a different group merely to imitate another function's signature.
* Parameters serving multiple purposes SHOULD be avoided. If unavoidable, their input and output behavior MUST be explicitly documented.
* Ownership, lifetime, mutability, and validity MUST be specified independently of parameter order.

**Rationale:** A predictable parameter order makes interfaces easier to scan, call, review, and document.

• • •

## 7.5. Parameter Types and Qualifiers

Parameter types MUST express the intended data representation and usage as precisely as reasonably possible.

* Parameter types MUST be explicit.
* Input pointers that are used only to read the pointed-to object MUST use `const` in the appropriate pointer type.
* Pointers to objects that a function is contractually permitted to modify MUST NOT be declared as pointers to const-qualified objects when that would contradict the interface.
* Pointer parameters MUST have clearly defined validity, lifetime, and ownership requirements.
* When a pointer refers to a buffer, its relationship to the buffer's length and capacity MUST be documented.
* Output parameters MUST identify the object or memory region in which the result is delivered.
* Parameter types MUST NOT be weakened or obscured solely to make an implementation easier to write.
* Pointer parameters SHOULD NOT be introduced when an appropriate by-value parameter is clearer and more suitable.
* Parameters MUST NOT be modified unless their modification is explicitly permitted by the function contract.

Example:

```c
int app_buffer_copy(
    const char *source,
    size_t source_length,
    char *destination,
    size_t destination_capacity);
```

The contract for this example MUST define the required validity and capacities of both buffers, the permitted overlap behavior, and the conditions under which the destination is modified.

`const` restricts modification through the relevant qualified access path. It does not automatically make every object reachable through nested pointers immutable.

**Rationale:** Explicit types and qualifiers communicate intent and improve compiler diagnostics. Detailed pointer contracts are particularly important in C because the language does not automatically manage object ownership or validate pointer arguments.

• • •

## 7.6. Return Types and Return Values

Functions MUST use either `int` or `void` as their return type under this project's function-interface policy.

* Functions that report success, failure, or another defined status MUST return `int`.
* Functions that do not need to communicate a return status MUST return `void`.
* Functions MUST NOT return `bool`, `size_t`, arbitrary pointer types, or structure types directly. When such information is needed, an appropriate output parameter MUST be used.
* The project's `status.h` definitions MUST be used for status values wherever applicable.
* `0` MUST represent success, and negative values MUST represent explicitly defined error or status conditions according to the project's status contract.
* Functions MUST NOT return undocumented status values.
* Callers MUST interpret status values according to their documented meanings rather than assuming that all nonzero values represent the same condition.
* A function MUST return a status consistent with the operation's documented outcome.
* Functions returning `void` MUST NOT attempt to communicate a result through a return expression.

Example:

```c
int app_buffer_initialize(struct buffer *buffer);
void app_buffer_reset(struct buffer *buffer);
```

The first function communicates its outcome through a status code. The second performs its documented operation without returning a status.

A query that determines whether an object exists MAY communicate the result using a dedicated status value, provided that the status contract defines the distinction unambiguously. Callers MUST compare against the documented status values rather than treating every negative result as equivalent.

**Rationale:** A restricted return-type policy establishes one consistent mechanism for status reporting and result delivery. It also requires output ownership and validity to be documented explicitly.

• • •

## 7.7. Function Preconditions and Postconditions

Every function MUST have explicitly defined preconditions and postconditions in its contract.

**Preconditions** specify what the caller MUST guarantee before invoking the function. **Postconditions** specify what the function guarantees after execution, including relevant success and failure outcomes.

A function contract MUST describe, where applicable:

* Required parameter validity and permitted value ranges.
* Required buffer lengths, capacities, and pointer relationships.
* Required initialization state of input objects.
* Ownership and lifetime requirements.
* Conditions that must hold for the operation to be valid.
* The result guaranteed on success.
* The state of output objects after success or failure.
* Side effects and modifications to existing state.
* Resource acquisition, release, and ownership transfer.
* The meaning of every possible documented status result.

Functions SHOULD NOT repeat checks for conditions that their callers are contractually required to guarantee, unless the function's contract or applicable safety requirements explicitly require those checks.

However:

* Ordinary operational failures, such as an allocation failure, MUST be handled according to the function contract.
* Untrusted input MUST be validated at the appropriate trust boundary.
* Memory safety and language requirements MUST NOT be disregarded merely because a contract exists.
* Contract violations MUST NOT be treated as though C automatically provides safe recovery.

Example:

```c
int app_buffer_write(
    struct buffer *buffer,
    const char *input,
    size_t input_length);
```

Its contract might require that `buffer` refer to an initialized, writable buffer and that `input` identify a readable region of at least `input_length` bytes. It MUST also specify whether the operation can fail because of insufficient capacity and what state is guaranteed after that failure.

**Rationale:** Explicit preconditions and postconditions establish a clear division of responsibility between callers and implementations. They reduce redundant checks without leaving operational errors or memory-safety requirements undefined.

• • •

## 7.8. Function Contracts and Documentation

Every function MUST have a complete, accessible, normative contract in a separate Markdown document within the appropriate project documentation hierarchy.

The default location for developer-facing function contracts MUST be `docs/development/`. Related architectural or role-specific documentation MAY be maintained in the appropriate locations, such as:

* `docs/architecture/` for architecture, component relationships, and system logic.
* `docs/development/` for developer documentation and normative function contracts.
* `docs/user/` for user-facing guides and usage instructions.
* `docs/roles/` for role definitions and responsibilities, where applicable.
* `docs/admin/` or another explicitly defined role-specific directory for administrator documentation.

The contract's canonical location MUST be clear. Duplicated normative contracts MUST NOT be maintained independently in multiple files.

Each function contract MUST document all applicable items:

* Function purpose and responsibility.
* Parameter meanings and requirements.
* Preconditions and postconditions.
* Return type and status-code meanings.
* Output parameter validity and ownership.
* Memory ownership, lifetime, and transfer rules.
* Side effects and state changes.
* Resource management behavior.
* Error conditions and failure guarantees.
* Relevant concurrency, reentrancy, and platform restrictions.

Every function MUST be documented, including internal and file-local functions. The amount of detail MUST be sufficient to define the function's contract; the requirement does not mean every function needs an unnecessarily long document.

Source files SHOULD additionally contain concise Doxygen-style or equivalent documentation comments when those comments improve local readability, explain implementation-specific details, or help connect the implementation to its external contract.

Source-level documentation is recommended, not mandatory. It MUST NOT replace the required Markdown contract. Any source-level description MUST remain consistent with the canonical contract.

**Rationale:** A separate normative contract provides a stable, reviewable reference for developers without making source comments the only repository of behavioral requirements.

• • •

## 7.9. Function Responsibilities

Every function MUST have one clearly identifiable primary logical responsibility.

* A function MUST NOT combine unrelated operations into one implementation.
* Operations that have independent purposes SHOULD be separated into distinct functions.
* A function MAY perform the validation, status reporting, and cleanup necessary to fulfil its primary responsibility. These supporting operations do not automatically constitute separate responsibilities.
* Error handling and resource cleanup MUST remain consistent with the function's main purpose.
* Functions SHOULD NOT be split arbitrarily when doing so would obscure the operation or create meaningless abstractions.
* Exceptions to the single-responsibility rule MUST have a clear technical justification.

For example, a function responsible for initializing a buffer MAY allocate the required storage, establish its initial state, and release partially acquired resources if initialization fails. It SHOULD NOT also perform unrelated file processing.

**Rationale:** Clear responsibility boundaries simplify testing, contracts, maintenance, and reuse. Necessary supporting operations remain part of the responsibility they serve.

• • •

## 7.10. Function Length and Complexity

Functions MUST be evaluated according to logical clarity, control-flow complexity, and responsibility rather than a fixed line-count limit.

* No universal maximum number of lines is imposed.
* A function SHOULD be divided when it contains multiple independently understandable operations.
* Deeply nested control flow SHOULD be avoided when a clearer structure is available.
* Repeated logic SHOULD be considered for extraction into a helper function.
* Long sequences of unrelated state changes SHOULD be separated.
* A short function MUST NOT be considered well designed merely because it has few lines.
* A long function MUST NOT be split solely to satisfy an arbitrary line limit.
* Functions whose control flow is difficult to follow MUST be simplified or divided.

**Rationale:** Logical structure is a more meaningful measure of function quality than line count alone. This rule supports the strict responsibility policy without imposing arbitrary numerical limits.

• • •

## 7.11. Early Returns

Early exit handling SHOULD be used to keep the main execution path clear and avoid unnecessary nesting. Under this standard, however, early exits MUST follow the project's label-based control-flow convention.

* A function that uses early exits MUST have an `end` label.
* Early-exit paths MUST transfer control to `end` using `goto end` rather than returning directly from the middle of the function.
* The actual function return MUST occur at the designated final return point.
* Early-exit conditions SHOULD be handled before the main operation whenever doing so improves clarity.
* Each early-exit path MUST establish the appropriate return status before transferring control.
* Early-exit paths MUST NOT bypass required resource cleanup.
* Functions that do not use early exits are not required to introduce an `end` label solely for stylistic reasons.

Example:

```c
int app_buffer_validate(const char *buffer, size_t length)
{
    int status = STATUS_SUCCESS;

    if (buffer == NULL) {
        status = STATUS_INVALID_ARGUMENT;
        goto end;
    }

    if (length == 0) {
        status = STATUS_INVALID_ARGUMENT;
        goto end;
    }

    /* Main operation. */

end:
    return status;
}
```

This example illustrates the required control-flow shape. The contract determines whether a null pointer or zero length is invalid in a particular function.

**Rationale:** Early exit conditions keep the main path readable. Routing them through an explicit final label makes the function's termination structure immediately recognizable.

• • •

## 7.12. Multiple Exit Points

Functions MUST follow the single-final-return convention when using the project's early-exit pattern.

* A function using the early-exit convention MUST have one designated final `return` statement at the `end` label.
* Early-exit paths MUST use `goto end` or, when resource cleanup is required, the appropriate cleanup path leading to `end`.
* Direct `return` statements from intermediate branches MUST NOT be used in such functions.
* A function that does not use early exits MAY return normally without introducing an unnecessary label.
* Resource acquisition and cleanup MUST be correct on every reachable execution path.
* Multiple `goto` statements targeting the same label are permitted when they simplify the control flow.
* Control flow MUST NOT jump into a region that violates C11 constraints, including constraints involving variable-length array declarations.
* The use of labels MUST make the function's control flow easier to understand, not obscure it.

The convention is a project-specific rule rather than a C11 language requirement.

**Rationale:** A consistent final-return convention makes status propagation predictable and allows readers to locate the function's actual return point quickly.

• • •

## 7.13. Helper Functions

Helper functions SHOULD be introduced whenever extracting a small operation gives it a meaningful name, clarifies responsibility, or improves readability.

* Helper functions MAY be small, including functions containing only a few statements.
* A helper function SHOULD represent a coherent operation or a meaningful concept.
* Repeated logic SHOULD be considered for extraction.
* A helper function MUST have a clear purpose and an appropriate interface.
* Helper functions MUST follow the same declaration, naming, contract, and return-type rules as other functions.
* File-local helper functions MUST use `static` when they are restricted to one translation unit.
* Helpers MUST NOT be placed in public headers merely to avoid using `static`.
* Private helpers SHOULD NOT be exposed through public interfaces without a legitimate interface requirement.

**Rationale:** Meaningful helper names allow readers to understand intent without repeatedly interpreting low-level implementation details. Small size is not a reason to avoid abstraction when it adds clarity.

• • •

## 7.14. Recursion

Recursive functions SHOULD be avoided by default. Iterative solutions SHOULD be preferred when they provide equivalent clarity and behavior.

Recursion MAY be used when it naturally represents the problem or materially simplifies the implementation. In such cases:

* The termination condition MUST be explicit.
* Each recursive call MUST make progress toward termination.
* Maximum or expected recursion depth MUST be considered.
* Stack consumption MUST be appropriate for the target environment and input limits.
* Failure and error propagation MUST comply with the function contract.
* Recursion MUST NOT be selected solely because it makes the source code shorter.
* The reason for using recursion SHOULD be documented when the choice is not self-evident.

**Rationale:** Avoiding unnecessary recursion improves predictability of stack usage and reduces the risk of stack exhaustion. Justified recursive algorithms remain permitted.

• • •

## 7.15. Variadic Functions

Variadic functions, which accept a variable number of arguments through `...`, SHOULD be limited to cases in which they provide a clear technical benefit.

Appropriate use cases MAY include formatting, logging, and similar interfaces where a variable argument list is intrinsic to the operation.

* A variadic function MUST have a documented argument contract.
* The contract MUST specify how the number and types of arguments are determined.
* Any format string or sentinel convention MUST be documented.
* The implementation MUST use the facilities in `<stdarg.h>` correctly.
* Required argument types and default argument promotions MUST be considered.
* Variadic arguments MUST NOT be assumed to carry runtime type information.
* Variadic functions MUST NOT be introduced when a fixed, explicitly typed interface would be clearer and safer.
* Variadic interfaces SHOULD NOT be exposed publicly unless their flexibility is justified.

**Rationale:** C variadic arguments do not provide automatic argument-count or type validation. Restricting their use reduces ambiguity and the risk of undefined behavior.

• • •

## 7.16. Function Pointers and Callbacks

Function pointers and callbacks SHOULD be used only when they provide a clear architectural benefit. Direct function calls SHOULD be preferred when dynamic behavior is unnecessary.

Appropriate use cases MAY include event notification, configurable operations, dispatch tables, and interfaces that allow callers to supply behavior.

When function pointers or callbacks are used:

* Their signatures MUST be explicit and compatible with the target function type.
* Their invocation conditions MUST be documented.
* The callback's expected behavior and return-status interpretation MUST be defined.
* The lifetime and validity requirements of callback-related context pointers MUST be specified.
* The contract MUST define whether callbacks may be invoked more than once, recursively, or asynchronously, where relevant.
* Ownership of any callback context MUST be explicit.
* Error propagation and failure behavior MUST be documented.
* Callback pointers MUST NOT be invoked when their required validity conditions are not satisfied.
* Function pointers MUST NOT be used merely to replace a straightforward direct call.

Example:

```c
typedef int (*buffer_operation_fn)(
    struct buffer *buffer,
    void *context);
```

This typedef is illustrative. Its contract would need to define the operation's expected behavior and the context pointer's lifetime and ownership.

**Rationale:** Function pointers provide flexibility but introduce additional contracts concerning invocation, lifetime, and control flow. Their use should be intentional.

• • •

## 7.17. Parameter Mutation

Parameters MAY be modified only when their modification is consistent with the function contract.

* Input data that is intended to remain unchanged MUST be represented with appropriate `const` qualification.
* Modifying an object through a pointer parameter MUST be explicitly permitted by the contract.
* Changes to caller-owned objects MUST be documented.
* Output and input/output parameters MUST be distinguishable from read-only inputs through their types, names, and documentation.
* The implementation MUST NOT modify caller-owned state merely because the parameter type technically permits it.
* Local copies SHOULD be used when they improve clarity or prevent unintended changes and are appropriate for the object size and semantics.

The fact that a parameter is passed by value does not necessarily mean that the pointed-to object is private. A pointer parameter is copied by value, but it may still refer to caller-owned memory.

**Rationale:** Explicit mutation rules preserve predictable interfaces and prevent accidental changes to caller-owned state.

• • •

## 7.18. Ignored Return Values

Whether a function's return value MUST be checked or MAY be ignored MUST be defined by its contract.

* Functions returning status codes SHOULD require callers to inspect the result unless the contract explicitly states that ignoring it is permitted.
* Functions whose results affect resource ownership, state consistency, or operation success MUST have their results handled according to the contract.
* Callers MUST NOT silently discard a status when doing so could violate a documented requirement.
* A return value MAY be ignored when the contract explicitly permits this and no required result or status is lost.
* Ignoring a result MUST NOT be used as a substitute for handling an error.
* The implementation and documentation SHOULD make mandatory result handling clear.

Example:

```c
int status = app_buffer_initialize(&buffer);

if (status != STATUS_SUCCESS) {
    goto end;
}
```

The exact status handling MUST follow the project's `status.h` contract. The example does not imply that every non-success status should be handled identically.

**Rationale:** Explicit rules for ignored results prevent failures from being silently discarded while allowing intentional omission when the contract permits it.

• • •

## 7.19. Inline Functions

C11 `inline` functionality MAY be used selectively when there is a clear technical reason, such as a suitable small operation or an interface requirement.

* Ordinary functions SHOULD remain the default.
* `inline` MUST NOT be used merely because a function is short.
* Developers MUST NOT assume that `inline` guarantees the compiler will substitute the function body at every call site.
* Inline definitions MUST comply with C11 linkage and definition rules.
* The distinction between `static inline`, `inline`, and external definitions MUST be understood and preserved.
* Header-defined `static inline` functions MAY be used when their internal linkage and header usage are appropriate.
* Inline functions MUST comply with the project's return-type, naming, documentation, and contract rules.
* Any compiler-specific behavior MUST be documented and isolated as required by Section 7.22.

**Rationale:** Inline functionality can be useful, but its language semantics and actual optimization behavior must not be confused. Correct linkage is more important than speculative optimization.

• • •

## 7.20. External and Internal Function Interfaces

Public and internal function interfaces MUST be separated explicitly.

* Public functions MUST expose only the interfaces intended to form the module's stable external contract.
* Public declarations MUST be placed in the appropriate public headers.
* Functions shared among internal source files MUST use an appropriate internal interface.
* Functions used by only one source file MUST use internal linkage through `static`.
* Internal implementation helpers MUST NOT be exposed publicly solely for convenience.
* Public interfaces MUST document behavioral expectations, not merely parameter and return types.
* Internal interfaces MAY change without preserving public API or ABI compatibility, subject to the project's internal dependencies.
* Public API and ABI changes MUST be evaluated against the documented compatibility policy.
* External linkage MUST be introduced only when required by an intended interface.

**Rationale:** Explicit separation limits accidental dependencies on implementation details and protects the stability of public interfaces.

• • •

## 7.21. Function Pointer Type Definitions

`typedef` MAY be used for function pointer types when it improves readability, represents a reusable callback contract, or prevents repeated complex declarations.

* A `typedef` MUST NOT be introduced without a clear purpose.
* Complex or repeatedly used function pointer signatures SHOULD be considered for a named type.
* Simple, one-off function pointer declarations MAY be written directly.
* A function pointer typedef MUST have a descriptive name that identifies its role.
* The associated callback contract MUST remain accessible and explicit.
* A typedef MUST NOT obscure important distinctions between callback signatures.
* The restrictions on `typedef` established in Section 6 remain applicable.

Example:

```c
typedef int (*buffer_operation_fn)(
    struct buffer *buffer,
    void *context);
```

A named function pointer type does not replace documentation of parameter meanings, callback behavior, context lifetime, or status results.

**Rationale:** Selective typedef usage improves readability without introducing unnecessary aliases or hiding important type information.

• • •

## 7.22. Function Attributes and Compiler Extensions

Standard C11 facilities MUST be preferred over compiler-specific function attributes and extensions.

* Compiler-specific attributes MAY be used when they provide a justified correctness, diagnostic, or performance benefit.
* The reason for using a nonstandard attribute MUST be documented.
* Portability implications MUST be assessed.
* GCC- or Clang-specific behavior MUST NOT be assumed to be standard C11 behavior.
* Extensions that affect function semantics or caller expectations MUST be isolated where practical.
* Compiler-specific definitions SHOULD be wrapped in a portability layer when that prevents unnecessary duplication and preserves clear semantics.
* Unsupported attributes MUST NOT silently change the intended contract.
* A standard C11 alternative SHOULD be preferred when it provides the required behavior without material disadvantages.

For example, GCC and Clang provide attributes that can describe properties such as unused results or non-returning functions. Such attributes are not interchangeable with standard C language guarantees.

**Rationale:** Prioritizing standard C11 reduces compiler dependence and makes the code easier to port, test, and maintain.

• • •

## 7.23. Non-Returning Functions

Functions that do not return normally MUST be rare and explicitly identified.

* A function MUST NOT be treated as non-returning merely because its current implementation happens not to return.
* A function designated as non-returning MUST NOT return control to its caller through normal function completion.
* The C11 `_Noreturn` function specifier MAY be used when the function genuinely satisfies its requirements.
* The use of `_Noreturn` MUST comply with C11.
* Compiler-specific alternatives MUST follow Section 7.22.
* The contract MUST explain the function's purpose and termination behavior.
* Callers MUST NOT rely on a normal return value from a genuinely non-returning function.
* Functions MUST NOT be marked non-returning to suppress warnings or conceal incomplete control flow.

Example:

```c
_Noreturn void app_terminate(void);
```

This declaration is appropriate only if the function does not return to its caller. The fact that its return type is `void` does not, by itself, mean the function is non-returning.

**Rationale:** Explicit non-returning semantics improve control-flow reasoning and allow compilers to diagnose unreachable or inconsistent code.

• • •

## 7.24. Function Overloading Alternatives in C

C does not provide C++-style function overloading. Functions MUST therefore use explicit, distinct names when their parameter types or behavior represent different operations.

* Different operations SHOULD use separate descriptive function names.
* Function names MUST comply with Section 7.3.
* Functions MUST NOT be overloaded through ambiguous naming conventions.
* Macro-based overloading SHOULD NOT be used.
* `_Generic`-based dispatch SHOULD NOT be used as a substitute for the project's explicit function naming policy.
* Common behavior SHOULD be shared through ordinary helper functions when this improves clarity.
* `void *` MAY be used when a genuinely generic object interface is required, but its type and ownership contract MUST be explicit.
* Enums MAY be used to select among a defined set of operations when that produces a clearer interface.
* Callback-based customization MAY be used when it provides a justified architectural benefit, subject to Section 7.16.
* The absence of overloading MUST NOT be used as a reason to weaken parameter types or obscure function responsibilities.

Example:

```c
int app_buffer_copy_bytes(
    struct buffer *destination,
    const void *source,
    size_t length);

int app_buffer_copy_string(
    struct buffer *destination,
    const char *source);
```

These functions use distinct names to express different contracts. Their exact parameter types and behavior MUST match their documented responsibilities.

**Rationale:** Explicit function names preserve discoverability, predictable type checking, and clear contracts without relying on macro-based dispatch mechanisms.

___

# 8.0. Expressions and Control Flow Standards

This section defines the standards for writing expressions, arithmetic operations, comparisons, logical conditions, assignments, and control-flow statements in C11.

Expressions and control structures must make program behavior easy to understand, review, and maintain. Code should avoid unnecessary complexity, implicit assumptions, ambiguous evaluation behavior, and side effects that obscure the relationship between operations.

The rules in this section complement the type, variable, and function policies established in the preceding sections. They do not replace the requirements of the C11 language standard or the documented contracts of individual functions.

## 8.1. Operator Precedence and Associativity

Expressions must be written so that their intended evaluation structure is immediately apparent.

- Parentheses should be used to explicitly communicate grouping in complex expressions, even when the language's operator precedence rules already determine the result.
- Expressions containing multiple operators with different precedence levels should be grouped to make the intended relationships clear.
- Expressions must not depend on the reader remembering subtle precedence rules to understand their meaning.
- Expressions should be simplified or divided into intermediate steps when explicit grouping alone does not make them sufficiently clear.
- Operator precedence and associativity must not be used as justification for compressing logically distinct operations into a single expression.

For example:

```c
int result = (base + offset) * scale;
```

This is preferred over relying on the reader to infer the intended grouping in a more complicated expression.

Parentheses do not change the fundamental evaluation-order guarantees of C. They establish grouping, not an arbitrary execution order for every operand.

• • •

## 8.2. Parentheses in Expressions

Parentheses should be used generously when they improve readability or make an expression's structure more explicit.

- Expressions containing nested operations should use parentheses to communicate the intended grouping.
- Conditions combining multiple comparisons or logical operators should be grouped to make their structure apparent.
- Parentheses should distinguish the intended operands of arithmetic, comparison, bitwise, and logical operations.
- Redundant parentheses around simple expressions should generally be avoided when they provide no meaningful clarification.
- Parentheses must not be treated as a substitute for splitting an excessively complex expression into smaller steps.

For example:

```c
if ((count > 0) && (count <= limit)) {
    process_items();
}
```

The grouping explicitly communicates the relationship between the two comparisons.

Parentheses must be placed according to C11 syntax and must not introduce a different interpretation from the intended operation.

• • •

## 8.3. Arithmetic Expressions

Arithmetic expressions should be simple, explicit, and easy to verify.

- Multi-stage arithmetic should be divided into separate statements when doing so improves readability.
- Intermediate variables should be used to represent meaningful calculation stages.
- The types of operands and intermediate results must be considered when evaluating arithmetic operations.
- Signedness, integer promotions, usual arithmetic conversions, and the representable ranges of result types must be understood before an operation is performed.
- Arithmetic must not rely on accidental behavior caused by implicit conversions.
- Calculations involving sizes, offsets, indexes, or allocation lengths must account for the possibility of exceeding the destination type's representable range.
- Floating-point calculations must account for precision and rounding where these affect correctness.
- Arithmetic expressions should not be compressed merely to reduce the number of lines.

For example:

```c
size_t total_size;
size_t header_size;
size_t payload_size;

header_size = calculate_header_size();
payload_size = calculate_payload_size();

total_size = header_size + payload_size;
```

The addition in this example is straightforward, but the implementation must still ensure that the sum is representable in `size_t` before relying on the result.

Separating arithmetic into intermediate statements improves visibility but does not automatically prevent overflow, precision loss, or invalid conversions. Those properties must be addressed explicitly.

• • •

## 8.4. Comparison Expressions

Comparison expressions must use compatible types and communicate the intended relationship between values.

- Values should be compared using compatible types whenever practical.
- Unnecessary implicit conversions should be avoided.
- Signed and unsigned integer values must not be mixed in comparisons without understanding the conversion rules and their consequences.
- Comparisons should use the operator that directly expresses the intended relationship.
- Pointer comparisons must follow the pointer-comparison rules defined by C11.
- Comparisons involving sizes, indexes, and limits must account for the types used to represent those values.
- Complex comparisons should be divided into simpler conditions when doing so improves clarity.
- The comparison must not depend on an accidental conversion that changes the intended meaning.

For example:

```c
if (index < item_count) {
    process_item(index);
}
```

Both values should use suitable compatible types for their intended purposes.

A cast must not be introduced merely to silence a diagnostic. Any necessary conversion must preserve the intended semantics and must be justified by the surrounding contract.

• • •

## 8.5. Logical Operators

Logical operators must express logical relationships clearly.

- The logical operators `&&`, `||`, and `!` must be used for logical operations.
- Bitwise operators must not be substituted for logical operators.
- Conditions combining several logical relationships should be divided into smaller conditions when their structure becomes difficult to understand.
- Parentheses should be used to communicate the intended grouping of compound conditions.
- Logical expressions must not contain unnecessary side effects.
- Conditions should communicate the actual requirement being tested rather than relying on obscure combinations of operators.
- When a condition contains several independent requirements, intermediate Boolean values may be introduced if they make the logic easier to understand.

For example:

```c
bool has_items;
bool within_limit;

has_items = (item_count != 0);
within_limit = (item_count <= item_limit);

if (has_items && within_limit) {
    process_items();
}
```

The intermediate variables are appropriate when the named conditions improve comprehension. They should not be introduced mechanically when a direct expression is already clear.

• • •

## 8.6. Bitwise Operators

Bitwise operators are reserved for operations that genuinely require manipulation of individual bits or bit representations.

- Bitwise operators may be used for masks, flags, bit fields, and other representation-level operations.
- Bitwise operators must not be used as substitutes for logical operators.
- Bit masks should be defined and applied in a manner that makes the intended bits explicit.
- Integer types should be selected with regard to the required bit width and signedness.
- Unsigned integer types should generally be preferred for bit manipulation when their semantics are appropriate.
- Shift operations must follow the separate restrictions in Section 8.14.
- Bitwise expressions that combine several masks or operations should use parentheses to make their structure explicit.
- The representation and width assumptions of a bitwise operation must be documented when they are not evident from the types and surrounding code.

For example:

```c
unsigned int flags;
unsigned int required_flags;

required_flags = FLAG_READY | FLAG_ENABLED;

if ((flags & required_flags) == required_flags) {
    activate_module();
}
```

This checks whether all required bits are set. It does not replace a logical condition involving unrelated Boolean requirements.

• • •

## 8.7. Assignment Operators

Assignment operators may be used according to C11 semantics, subject to the restrictions defined in this section.

- Assignments should be written as separate statements when this improves readability.
- Assignment must not be performed inside an `if`, `else if`, `while`, or other conditional expression.
- Assignments must not be combined with unrelated operations merely to reduce the number of statements.
- Assignment expressions must not obscure whether a value is being compared or modified.
- Compound assignment operators, including `+=`, `-=`, `*=`, and `/=`, may be used when they express the operation clearly.
- Compound assignments must not be used to hide conversions, overflow risks, or other behavior that would be clearer in an explicit operation.
- Multiple assignments must not be combined into a single expression, as specified in Section 8.30.

For example:

```c
status = get_status();

if (status != STATUS_SUCCESS) {
    handle_error(status);
}
```

The assignment is separate from the condition. This avoids confusing assignment with equality comparison and makes the program's sequence of operations explicit.

• • •

## 8.8. Increment and Decrement Operators

Increment and decrement operations must generally appear as separate statements.

- The operators `++` and `--` should be used in standalone expressions.
- Prefix increment and decrement should be preferred when they communicate the intended operation clearly.
- Postfix forms may be used when the original value is specifically required by the operation.
- Increment or decrement must not be combined with other accesses to the same variable in an expression.
- Increment and decrement must not be hidden inside function arguments, conditions, or other expressions.
- The selected integer type must be able to represent the resulting value whenever the operation requires a representable result.
- Counter updates should be placed where their effect on loop progress is easy to identify.

For example:

```c
index++;
process_item(index);
```

If the original value is required, it should be preserved explicitly:

```c
size_t current_index;

current_index = index;
index++;

process_item(current_index);
```

The goal is to make the relationship between the old value, the updated value, and subsequent operations unambiguous.

• • •

## 8.9. Comma Operator

The C comma operator must not be used.

- Expressions must be separated into distinct statements when they represent distinct operations.
- The comma operator must not be used to combine side effects or compress control-flow logic.
- Expressions must not depend on comma-operator evaluation to sequence operations.
- The prohibition applies regardless of whether the expression would otherwise be valid C11.

This rule concerns the **comma operator**, not commas used as syntactic separators.

Commas remain valid where required by C syntax, including function argument lists, variable declarations, enumerator lists, and other language constructs that use commas as separators.

For example, the following is prohibited:

```c
index++, process_item(index);
```

The operations must instead be written as separate statements:

```c
index++;
process_item(index);
```

• • •

## 8.10. Conditional Operator

The conditional operator `?:` must not be used.

Conditional selection must be expressed using `if`, `else if`, and `else` statements.

For example, the following is prohibited:

```c
int result = (condition) ? first_value : second_value;
```

Write the selection explicitly:

```c
int result;

if (condition) {
    result = first_value;
} else {
    result = second_value;
}
```

This policy establishes one consistent form for conditional branching and avoids embedding control decisions inside expressions.

The prohibition applies to the conditional operator itself. It does not prohibit ordinary `if`/`else` statements or logical operators used within their conditions.

• • •

## 8.11. Short-Circuit Evaluation

The short-circuit behavior of `&&` and `||` may be used when it expresses the intended control flow clearly.

- The left operand of `&&` is evaluated before the right operand; the right operand is evaluated only if the left operand is nonzero.
- The left operand of `||` is evaluated before the right operand; the right operand is evaluated only if the left operand is zero.
- Short-circuit behavior may be used to protect an operation from being evaluated when its prerequisite condition is false.
- Conditions that rely on short-circuit behavior must remain easy to understand.
- Side effects must not be introduced into logical expressions merely to take advantage of short-circuit evaluation.
- Complex logical conditions should be split into separate statements when doing so makes the control flow clearer.

For example:

```c
if ((buffer != NULL) && (buffer_length > 0)) {
    process_buffer(buffer, buffer_length);
}
```

The second condition is evaluated only when `buffer != NULL` evaluates to true.

The validity of a pointer or any other prerequisite must be established by the actual program logic and contract. Short-circuit evaluation must not be assumed for bitwise operators or other constructs that do not provide the same guarantee.

• • •

## 8.12. Evaluation Order and Side Effects

Expressions must not rely on unspecified or unsequenced evaluation behavior.

- Side effects that require a particular order must be placed in separate statements.
- Multiple modifications of the same scalar object must not occur within a full expression when the operations are unsequenced relative to one another.
- Expressions must not depend on the order in which function arguments are evaluated.
- Parentheses must not be used under the mistaken assumption that they establish a general left-to-right evaluation order.
- Function calls with side effects should be separated when their relative execution order matters.
- The behavior of an expression must be determined from the C11 sequencing rules rather than from the behavior observed on one compiler or architecture.

For example, an expression that modifies and reads the same scalar object without the required sequencing is not an acceptable way to express an operation.

Instead, write the operations explicitly:

```c
counter++;
process_counter(counter);
```

Separate statements make the intended sequencing clear and avoid dependencies on compiler-specific behavior.

• • •

## 8.13. Integer Overflow

Integer arithmetic must account for the representable range of the relevant types.

- Signed integer overflow must never be relied upon.
- Arithmetic operations must be evaluated for possible overflow before their results are used.
- Calculations involving untrusted values, sizes, offsets, counts, and allocation lengths must account for the input ranges and result limits.
- Unsigned arithmetic must not be assumed to detect overflow automatically. Unsigned operations wrap modulo the range defined by the type, which may still violate the intended logic.
- When overflow is possible, the implementation must use an appropriate precondition, range check, or alternative calculation that prevents an invalid result from being relied upon.
- Intermediate calculations must also be checked when their types can overflow, even if the final destination type has a wider range.
- Conversions to narrower integer types must be evaluated for loss of information.
- Code must not rely on compiler optimization behavior that assumes signed overflow never occurs.

For example, an addition can be checked before execution:

```c
if (left > SIZE_MAX - right) {
    status = STATUS_OVERFLOW;
    goto end;
}

total = left + right;
```

This illustrates the general principle for nonnegative `size_t` operands. Other signed or unsigned calculations require checks appropriate to their specific types and ranges.

Overflow handling should be consistent with the function's documented contract and error-reporting policy.

• • •

## 8.14. Shift Operations

Shift operations must be written with explicit attention to operand types, signedness, and shift counts.

- Shift operations should generally use unsigned integer operands when bit-level manipulation is intended.
- The right operand of a shift must not be negative.
- The shift count must be less than the width of the promoted left operand.
- Signed left shifts must not be used without accounting for the C11 rules governing representability and signed operands.
- Right-shifting a negative signed integer must be avoided because its behavior is implementation-defined in C11.
- Shift counts should be expressed in a manner that makes their valid range apparent.
- Integer promotions must be considered before determining the width and behavior of the shifted operand.
- Shift operations must not be used as replacements for arithmetic operations unless the resulting semantics are appropriate for the types and values involved.

For example:

```c
unsigned int mask;

mask = 1U << bit_index;
```

This is appropriate only when `bit_index` is within the valid range for the promoted left operand.

The type of the literal alone does not guarantee that every shift count is valid. Width assumptions must be explicit where they affect correctness.

• • •

## 8.15. Division and Remainder

Division and remainder operations must satisfy the preconditions required by C11.

- The divisor must not be zero.
- The implementation must account for signed division cases in which the mathematical quotient is not representable in the result type, including the minimum representable signed value divided by `-1`.
- Preconditions should be documented in the relevant function contract.
- Inputs originating outside a trusted internal boundary must be validated when their values can violate these preconditions.
- Division and remainder expressions should be written so that the divisor and relevant types are easy to identify.
- The behavior of negative operands must not be inferred from mathematical modulo conventions that differ from C11 semantics.
- Division and remainder operations must not be used without considering integer truncation and the representability of intermediate results.

For example:

```c
if (divisor == 0) {
    status = STATUS_INVALID_ARGUMENT;
    goto end;
}

quotient = dividend / divisor;
remainder = dividend % divisor;
```

Any additional conditions required to make the quotient representable must also be satisfied before the operations are performed.

A documented precondition does not remove the need to validate untrusted input at the relevant trust boundary.

• • •

## 8.16. Floating-Point Comparisons

Floating-point comparisons must reflect the intended numerical requirement.

- Exact equality comparisons may be used when exact equality is meaningful for the values involved.
- Exact equality must not be assumed to be appropriate for every result produced by floating-point arithmetic.
- When approximate equality is required, an explicit tolerance must be selected according to the problem's numerical requirements.
- Absolute and relative tolerances should be distinguished where their behavior differs materially.
- Tolerances must not be chosen arbitrarily or merely to make a test pass.
- Comparisons must account for the possibility of NaN and infinity when these values can occur.
- A comparison involving NaN must not be assumed to behave like an ordinary comparison between finite numbers.
- Floating-point values should not be converted to integers merely to simplify a comparison unless the conversion is valid and preserves the intended meaning.

For example, a comparison against an exact constant may be appropriate when the value is guaranteed to originate from a representation that makes exact equality meaningful.

When approximate equality is required, the comparison should express the chosen tolerance explicitly. The appropriate formula depends on the expected scale, range, and numerical properties of the values.

• • •

## 8.17. If, Else If, and Else

Conditional branches must use explicit blocks.

- Every `if`, `else if`, and `else` body must be enclosed in braces, including bodies containing only one statement.
- Conditions should express one clear decision whenever practical.
- Compound conditions should be divided when their logic becomes difficult to follow.
- Branches must be formatted consistently.
- Assignments must not appear inside conditions.
- Empty branches should be avoided unless there is a justified reason for their existence; any intentional empty branch must make its purpose clear.
- Nested conditional structures should be simplified when their depth obscures the intended behavior.
- Branch ordering should reflect the intended decision logic and must not make a broader condition unintentionally prevent a narrower condition from being evaluated.

For example:

```c
if (status == STATUS_SUCCESS) {
    process_result();
} else if (status == STATUS_NOT_FOUND) {
    handle_missing_result();
} else {
    handle_error(status);
}
```

The explicit blocks make each branch's boundaries clear and reduce the risk of errors when statements are added later.

• • •

## 8.18. Switch, Case, and Default

`switch` statements must have explicit and understandable branch behavior.

- Each `case` must have a clearly identifiable body and termination behavior.
- Each branch should terminate with an appropriate `break`, `return`, or other clearly justified control-flow statement unless an explicitly documented fall-through is intended.
- The use of `default` must be considered deliberately. It should handle unexpected or otherwise unhandled values when that behavior is appropriate to the contract.
- A missing `default` must be justified when omission is intentional.
- Case labels and their corresponding statements must be formatted consistently.
- Multiple case labels may share a body when they intentionally represent the same behavior.
- `switch` statements must not be used when their branching logic would be clearer as a straightforward `if`/`else` structure.
- Fall-through behavior is governed by Section 8.26.

For example:

```c
switch (status) {
case STATUS_SUCCESS:
    process_result();
    break;

case STATUS_NOT_FOUND:
    handle_missing_result();
    break;

default:
    handle_error(status);
    break;
}
```

The purpose of each branch and the behavior after its execution must be clear from the code.

• • •

## 8.19. For Loops

`for` loops should be preferred for counter-based iteration with clearly identifiable initialization, continuation, and update operations.

- The initialization, termination condition, and update expression should be simple and easy to understand.
- Complex loop headers should be simplified by moving meaningful operations into separate statements.
- Loop counters must use types appropriate for their ranges and intended operations.
- The loop's termination condition and progress must be clear.
- Counter updates must not rely on overflow or unintended conversions.
- Side effects in the loop header must not make the execution sequence difficult to follow.
- A `for` loop should not be selected merely because it is shorter than an equivalent construct.

For example:

```c
for (size_t index = 0; index < item_count; index++) {
    process_item(index);
}
```

The loop is appropriate when the counter, bound, and increment accurately express the intended iteration.

When the initialization, update, or termination logic becomes complicated, the loop should be redesigned or simplified rather than compressed into its header.

• • •

## 8.20. While and Do-While Loops

`while` and `do-while` loops may both be used according to which construct expresses the intended behavior most clearly.

- A `while` loop should be used when its condition must be evaluated before each iteration.
- A `do-while` loop should be used when executing the body at least once is part of the intended behavior.
- The loop condition must be easy to identify and understand.
- Side effects in loop conditions should be avoided when they obscure the loop's behavior.
- Loop progress and termination must be clear.
- The closing `while` condition of a `do-while` loop must be formatted consistently with the project's control-flow style.
- The choice between these constructs should be based on their semantics rather than personal preference or line count.

For example:

```c
while (has_pending_items()) {
    process_next_item();
}
```

A `do-while` loop is appropriate when the initial execution must occur before the condition is tested, such as when a sequence of operations must run at least once.

Neither construct is inherently preferable in every situation.

• • •

## 8.21. Break and Continue

`break` and `continue` may be used when they make loop control clearer.

- `break` should be used when terminating the nearest enclosing loop or `switch` is the clearest expression of the intended behavior.
- `continue` should be used when skipping the remainder of the current loop iteration improves clarity.
- These statements must not be used to conceal complicated control flow.
- Their effects must remain apparent to the reader.
- Nested loops must be considered carefully because `break` and `continue` affect only the nearest applicable loop.
- When leaving several levels of nested control flow is required, the structure should be simplified where practical rather than relying on confusing combinations of flags and jumps.
- Loop conditions should not be made unnecessarily complicated merely to avoid a clear and justified `break` or `continue`.

For example:

```c
for (size_t index = 0; index < item_count; index++) {
    if (!item_is_valid(index)) {
        continue;
    }

    process_item(index);
}
```

This use of `continue` is appropriate because it clearly skips processing for an invalid item.

• • •

## 8.22. Goto Usage

The `goto` statement may be used for structured cleanup and error-handling paths. Arbitrary jumps that obscure control flow must be avoided.

- `goto` should primarily be used to transfer control to a clearly named cleanup or function-ending label when the function's resource-management structure benefits from it.
- Functions using early-exit paths must follow the `end` label policy established in Section 7.
- Functions managing memory or transferring ownership must follow the applicable `cleanup` label policy established in Section 7.
- A function may jump directly to `end` when no acquired resource requires cleanup.
- When an acquired resource requires release, the relevant exit path must perform that cleanup before reaching the final return.
- Multiple resources should be released in reverse acquisition order when that order is required for correct resource management.
- Labels should be named according to their purpose, particularly `cleanup` and `end` where those names are established by the project policy.
- Jumps must not bypass required initialization, resource release, or other operations necessary for correctness.
- `goto` must not be used to create unnecessarily tangled control flow or to replace a straightforward structured statement.

For example:

```c
int status;

status = STATUS_SUCCESS;

/* Operations that may acquire resources. */

if (operation_failed()) {
    status = STATUS_OPERATION_FAILED;
    goto cleanup;
}

goto end;

cleanup:
release_resources();

end:
return status;
```

This is an illustrative control-flow pattern. The actual placement and use of `cleanup` must reflect whether resources were acquired and require release. A function must not release resources that it never acquired, and it must not bypass required cleanup.

• • •

## 8.23. Loop Termination Conditions

Loop termination conditions must be supported by the function's contract or the design of the algorithm.

- The termination condition must accurately express when iteration should stop.
- The loop must have a valid progress mechanism whenever termination is expected.
- The progress mechanism and its assumptions should be documented when they are not obvious from the implementation.
- Loop bounds and counters must use suitable types and ranges.
- The implementation must not rely on integer overflow, signed overflow, or unintended conversion behavior to reach the termination condition.
- Loops that depend on external state must have a defined mechanism for observing changes to that state.
- A contract may establish assumptions about the number of iterations or the availability of data, but the implementation must still conform to those assumptions.
- When termination is not guaranteed by design, that fact must be intentional and consistent with the function's purpose.

A loop with a contractually defined termination condition is acceptable only when its implementation and surrounding assumptions support that condition.

• • •

## 8.24. Infinite Loops

Intentional infinite loops must use the `while (true)` form.

- The `true` macro from `<stdbool.h>` must be available wherever this form is used.
- Infinite loops must be intentional and consistent with the function's purpose.
- The mechanism for leaving the loop, when one exists, must be clear.
- Loops that wait for external events must use an appropriate waiting or blocking mechanism rather than consuming CPU unnecessarily.
- Infinite loops must not be used to conceal missing termination conditions in algorithms that are expected to finish.
- Exit conditions should be expressed through clear control flow, such as a justified `break`, `return`, or other appropriate operation.
- The loop body must make its progress, waiting, or event-processing behavior apparent.

For example:

```c
#include <stdbool.h>

while (true) {
    if (shutdown_requested()) {
        break;
    }

    process_next_event();
}
```

The loop is appropriate when the function is intended to continue processing events until a shutdown condition occurs.

• • •

## 8.25. Nested Control Structures

Nested control structures should be kept as simple as practical.

- Deeply nested conditions and loops should be simplified when their structure makes the program difficult to understand.
- Early exits may be used to reduce unnecessary nesting, subject to the function-ending and cleanup policies in Section 7.
- Helper functions should be introduced when a meaningful name can clarify a distinct operation or decision.
- Compound conditions should be simplified when their individual requirements are difficult to distinguish.
- Nested structures must not be flattened in a way that changes the program's semantics.
- The chosen structure must preserve the intended error handling, resource management, and execution order.
- No arbitrary maximum nesting depth is imposed; the deciding factor is readability and logical complexity.

For example, a deeply nested validation sequence may be rewritten using separate validation steps and clear error paths. The result should communicate the order of checks and the reason for each branch without obscuring the original behavior.

• • •

## 8.26. Fall-Through Behavior

Fall-through between `switch` cases must be intentional and explicitly documented.

- Each `case` should normally terminate with `break`, `return`, or another appropriate control-flow statement.
- A case must not fall through into the next case accidentally.
- Intentional fall-through must be accompanied by a clear comment at the transition point.
- The comment must make the intended continuation explicit rather than merely describing the surrounding code.
- Consecutive case labels sharing the same body do not constitute fall-through between separate executable bodies.
- Fall-through must not be used merely to reduce duplicated statements when doing so makes control flow less clear.
- Compiler-specific fall-through annotations may be considered only when separately permitted by the project's portability policy; a clear source-level comment remains the baseline requirement.

For example:

```c
switch (mode) {
case MODE_INITIALIZE:
    initialize_state();
    /* Fall through intentionally to perform the common setup. */

case MODE_CONFIGURE:
    configure_state();
    break;

default:
    handle_invalid_mode(mode);
    break;
}
```

The example demonstrates the required explicit indication of intent. The particular transition must still be appropriate for the algorithm, and the comment must not be used to justify an accidental fall-through.

• • •

## 8.27. Empty Loop Bodies

Empty loop bodies should be avoided unless they serve a justified purpose.

- An intentionally empty loop body must use an explicit block rather than a lone semicolon.
- A comment must explain why the loop body is empty and what condition or external event governs its termination.
- Empty loops must not be used when they cause unnecessary CPU consumption or obscure a missing progress mechanism.
- Waiting and polling behavior should use an appropriate mechanism for the system and application.
- The loop's termination condition must remain clear.
- Empty loop bodies must not be introduced accidentally through a misplaced semicolon.

For example:

```c
while (!operation_completed()) {
    /* Intentionally empty: completion is observed through the condition. */
}
```

This form makes the empty body visible, but it does not automatically make busy-waiting appropriate. If the condition is checked continuously without a blocking or yielding mechanism, the implementation must be evaluated for its CPU and scheduling impact.

• • •

## 8.28. Simplifying Complex Control Flow

Complex control flow must be simplified when its structure makes behavior difficult to understand.

- Complicated conditions should be divided into smaller, meaningful conditions.
- Deeply nested branches should be reduced when doing so improves clarity.
- Helper functions should be used when they give a meaningful name to a distinct operation or decision.
- Early exits should be considered when they make the main execution path easier to follow, subject to Section 7.
- Simplification must preserve the intended behavior, evaluation requirements, and error-handling semantics.
- Conditions must not be simplified by removing checks that are required for correctness or safety.
- Repeated logic should be consolidated when doing so improves consistency and maintainability.
- A simplified implementation should remain consistent with the function's single primary responsibility.
- The number of lines alone must not determine whether a control structure is considered simple.

The preferred implementation is the one whose decision points, state changes, and error paths are easiest to verify without sacrificing correctness.

• • •

## 8.29. Explicit Boolean Conditions

Conditions should express the intended truth test explicitly.

- Integer values that represent counts, sizes, indexes, or status values should generally be compared explicitly against the relevant value.
- Expressions such as `count != 0` should be preferred when they communicate the intended test more clearly than an implicit nonzero test.
- The truth conditions of pointers must follow Section 8.33.
- Boolean values may be used directly when their type and meaning are clear.
- Conditions should not depend on obscure conversions or assumptions about the representation of values.
- A comparison must reflect the semantic meaning of the value rather than simply whether its representation is nonzero.
- Logical negation should be used when it expresses the intended meaning clearly; unnecessary double negation should be avoided.

For example:

```c
if (item_count != 0) {
    process_items();
}
```

This explicitly states that the count must be nonzero.

An explicit comparison does not replace validation of the value's range or other preconditions.

• • •

## 8.30. Multiple Assignments in Expressions

Multiple assignments must not be combined into a single expression.

- Each assignment should be performed as a separate statement.
- Assignment expressions must not be chained to initialize or update several independent variables in one statement.
- Assignments must not be combined with unrelated operations to compress the code.
- Assignments inside function arguments or conditional expressions must not be used.
- The order of assignments should be visible from the sequence of statements.
- Intermediate values should be named when doing so clarifies their meaning.

For example, the following is prohibited:

```c
first = second = initial_value;
```

Write the assignments separately:

```c
first = initial_value;
second = initial_value;
```

This policy makes each state change explicit and avoids hiding multiple modifications inside one expression.

• • •

## 8.31. Comma Operator Restrictions

The comma operator is prohibited throughout the codebase.

- The comma operator must not be used to sequence expressions.
- Expressions previously combined through the comma operator must be separated into distinct statements.
- The restriction applies in loop headers and all other expression contexts.
- The prohibition is independent of whether a particular use would be valid and well-defined under C11.
- Commas required by C syntax as separators remain permitted.

The distinction between a comma operator and a syntactic separator is important. For example, commas separating function arguments are not comma-operator expressions.

The restriction in this subsection reinforces the general prohibition in Section 8.9 and must be applied consistently.

• • •

## 8.32. Side Effects in Function Arguments

Function arguments must not contain side effects.

- Argument expressions should compute or provide values without modifying program state.
- Operations that modify variables must be performed in separate statements before the function call.
- Side-effecting function calls must be performed before the enclosing call when their results or execution order are required.
- Argument evaluation must not depend on a particular order of evaluation.
- Increment and decrement operations must not be embedded in arguments.
- Assignment expressions must not be embedded in arguments.
- Expressions involving several state changes must be divided into separate operations.
- Intermediate variables should be introduced when they make the values being passed to a function easier to understand.

For example, the following style is prohibited:

```c
process_values(index++, update_state());
```

Instead, prepare the arguments explicitly:

```c
size_t current_index;
int update_status;

current_index = index;
index++;

update_status = update_state();

process_values(current_index, update_status);
```

The sequence above makes the order of operations explicit. The chosen order must reflect the intended semantics of the original algorithm.

• • •

## 8.33. Integer and Pointer Comparisons

Integer and pointer comparisons must make the type relationship and intended operation explicit.

- Pointer conditions must use explicit comparisons with `NULL`.
- A pointer should be checked using `ptr != NULL` or `ptr == NULL`, as appropriate.
- Implicit conversion of a pointer to a truth value must not be used as a substitute for an explicit null comparison.
- Pointer comparisons must use compatible pointer types and follow C11's rules.
- Integer values must not be compared with pointers through unjustified casts or conversions.
- A null pointer constant must be used in an appropriate context; `NULL` should be used consistently for null-pointer checks.
- Pointer ordering comparisons must not be performed between unrelated objects when the comparison is not defined by C11.
- Integer comparisons must account for signedness and integer conversions.
- Pointer validity, object lifetime, and ownership must not be inferred solely from a non-null comparison.

For example:

```c
if (buffer != NULL) {
    process_buffer(buffer);
}
```

The comparison explicitly expresses the null-pointer test.

A non-null pointer is not necessarily valid for dereferencing. Its lifetime, ownership, alignment, and other relevant requirements remain governed by the applicable contract and C11 rules.

• • •

## 8.34. Null Statement Usage

Null statements should be used only when they are explicitly necessary.

- A null statement must not be introduced accidentally through a misplaced semicolon.
- When an intentionally empty body is required, an explicit block should generally be preferred.
- If a null statement is genuinely required by a construct, its purpose must be clear from the surrounding code and, where appropriate, a comment.
- Null statements must not be used to conceal missing operations or incomplete control flow.
- Empty loop bodies must follow the more specific rules in Section 8.27.
- The use of an empty statement must not make it difficult to determine which statements belong to a conditional or loop body.

For example, avoid writing a conditional followed by a stray semicolon:

```c
if (condition);
{
    perform_operation();
}
```

The semicolon terminates the `if` statement, leaving the following block independent of the condition. This is almost certainly unintended and must not appear in conforming project code.

When an operation is intentionally empty, the implementation should make that intent explicit and preserve the clarity of the surrounding control flow.

___

# 9.0. Pointer and Memory Management

Pointer and memory management rules define how objects are addressed, how memory is acquired and released, and how object lifetime, ownership, bounds, and access rights are maintained. All pointer operations MUST comply with the C11 abstract machine and the requirements of the object being accessed.

A pointer value alone does not establish that an object exists, that the object is alive, that the pointer may be dereferenced, or that a sufficient number of bytes or elements are accessible. Those properties depend on the pointer's origin, the target object's lifetime, the applicable type and alignment requirements, and the relevant function or data-structure contract.

The following principles apply throughout this section:

- Every pointer variable is initialized at declaration.
- Pointer validity and ownership are distinct concepts.
- Pointer arithmetic is constrained by the relevant array object and C11 rules.
- Functions that accept or return pointers document the relevant lifetime, bounds, ownership, and failure behavior.
- Dynamic allocations have an identifiable owner and a defined release path.
- Resource acquisition and cleanup follow the function's documented control-flow and cleanup policy.
- Raw object representations are not assumed to be portable serialization formats.
- Contracts clarify responsibility but do not make undefined behavior valid.

## 9.1. Pointer Declaration and Initialization

Every pointer variable MUST be initialized at the point of declaration. A pointer that does not yet designate an object MUST be initialized to `NULL`.

```c
int *value_ptr = NULL;
const char *text_ptr = NULL;
size_t *size_ptr = NULL;
```

When a valid object is already available, initialize the pointer directly from that object:

```c
int value = 42;
int *value_ptr = &value;
```

Do not leave a pointer uninitialized until a later statement, even when the pointer is expected to be assigned before use. Declaration-time initialization makes the variable's initial state explicit and prevents accidental reads along an unexpected control-flow path.

A pointer MUST NOT be dereferenced, used for pointer arithmetic, or otherwise treated as an object pointer until it has a valid value for the intended operation. Initializing a pointer to `NULL` does not make dereferencing it valid.

If a pointer is reassigned, the new value MUST satisfy the requirements of every subsequent operation. When a pointer no longer designates a usable object, update or discard it according to the relevant ownership and lifetime rules. Assigning `NULL` to one pointer does not invalidate or repair other pointers that previously referred to the same object.

• • •

## 9.2. Null Pointer Policy

`NULL` MUST be used to express a null pointer value. Pointer checks MUST be explicit.

```c
if (value_ptr == NULL) {
    /* Handle the null case. */
}

if (value_ptr != NULL) {
    /* Use the pointer only if the remaining validity requirements hold. */
}
```

Do not use implicit pointer truthiness:

```c
/* Avoid. */
if (value_ptr) {
    /* ... */
}
```

A non-null pointer is not necessarily valid. It may be dangling, improperly aligned for the target type, outside the permitted range, or otherwise unsuitable for the intended operation. A null check addresses only whether the pointer is null.

Functions MUST document whether each pointer parameter accepts `NULL`. A function MUST NOT silently assume that `NULL` means an empty collection, a request to allocate memory, or an optional argument unless its contract explicitly defines that meaning.

Do not use integer zero as an ad hoc pointer representation. Use `NULL` for pointer initialization and comparisons, and rely on standard C conversions where they apply.

• • •

## 9.3. Pointer Arithmetic

Pointer arithmetic is permitted only when the operation complies with C11's pointer arithmetic rules. A contract MUST identify the relevant array or element range when that information is not evident from the interface.

For an array object, pointer arithmetic may produce a pointer to an element within that same array or to the position one element past the end. The one-past pointer MUST NOT be dereferenced. Pointer arithmetic MUST NOT be used to create a pointer before the beginning of an array or beyond its one-past position.

```c
int values[4] = {10, 20, 30, 40};
int *value_ptr = &values[0];

value_ptr += 2;
/* value_ptr now points to values[2]. */

value_ptr = &values[4];
/* One past the end: valid to form, not valid to dereference. */
```

The example above uses a valid one-past position. It MUST NOT be interpreted as permission to access `values[4]`.

Pointer arithmetic MUST NOT be used as a substitute for bounds validation. If an index or offset comes from an external input or another untrusted source, validate it before performing arithmetic or accessing the resulting location.

Arithmetic involving unrelated objects MUST NOT be assumed to produce a meaningful traversal range. A contract cannot override C11's rules for pointer arithmetic.

• • •

## 9.4. Pointer and Array Relationships

Arrays and pointers are distinct C language constructs and MUST NOT be treated as interchangeable types.

An array object has a fixed number of elements for its lifetime. In most expressions, an array expression is converted to a pointer to its first element. This conversion does not turn the array object into a pointer variable and does not preserve the array's length in the resulting pointer.

```c
int values[8] = {0};
int *value_ptr = values;
```

Here, `values` remains an array, while `value_ptr` is a pointer. The pointer can be reassigned; the array object cannot be reassigned as a whole.

Function parameters declared with array syntax are adjusted to pointer parameters:

```c
void process_values(int values[8]);
```

For function parameter type purposes, this is adjusted to a pointer parameter. The declaration does not automatically enforce that the caller supplies eight elements. The function contract MUST specify the required accessible element count when it matters.

When an operation accesses multiple elements, the interface SHOULD provide the pointer and element count together, unless the size is otherwise unambiguously available from a containing object or contract.

Use actual arrays when fixed-size array storage and array semantics are intended. Use pointers when indirection, traversal, optionality, or an interface contract calls for a pointer. Do not infer array length from a pointer.

• • •

## 9.5. Pointer Comparisons

Pointer comparisons MUST use compatible pointer types and MUST comply with C11's comparison rules. Null pointer comparisons MUST be explicit.

Equality comparisons (`==` and `!=`) may be used when the compared pointer values are suitable for such comparison. Ordering comparisons (`<`, `<=`, `>`, and `>=`) MUST be restricted to relationships for which C11 defines the result, such as positions within the same array object and its one-past position.

Do not use relational pointer comparisons to infer a general memory order between unrelated objects. A platform's observed address layout does not establish a portable C ordering relationship.

```c
if (left_ptr == right_ptr) {
    /* The pointer values compare equal. */
}
```

Pointer equality does not prove that the target is alive or accessible. Two pointer values that compare equal do not, by themselves, establish ownership, bounds, or permission to dereference.

• • •

## 9.6. Pointer Conversions

Pointer conversions MUST be avoided unless they serve a clear, documented purpose. Unnecessary casts MUST NOT be used to suppress incompatible-pointer diagnostics or to disguise an incorrect interface.

C11 permits standard conversions between `void *` and pointers to object types. Such conversions ordinarily do not require explicit casts in C:

```c
void *storage = NULL;
int *value_ptr = NULL;

storage = value_ptr;
value_ptr = storage;
```

These conversions do not remove the requirements concerning object lifetime, alignment, effective type, or valid access.

Conversions between pointers to different object types MUST be made only when the intended access is valid under C11 and the required alignment and type rules are satisfied. Converting a pointer does not change the underlying object's effective type or automatically make an otherwise invalid dereference valid.

Function pointers and object pointers MUST NOT be assumed to be interchangeable. Any platform-specific conversion between them requires a documented platform dependency and a concrete technical justification.

Integer-to-pointer and pointer-to-integer conversions MUST be avoided unless required by a documented platform interface. Such conversions may be implementation-defined or otherwise non-portable and MUST NOT be used as a general-purpose way to store, validate, or manipulate pointers.

• • •

## 9.7. Multiple Levels of Indirection

Multiple levels of indirection MUST be used only when required by the API, data model, or algorithm. Unnecessary levels SHOULD be removed when doing so improves clarity without weakening the interface.

A `T **` parameter may be appropriate when a function must change the caller's pointer value, produce a pointer through an output parameter, or work with a pointer-based data structure. It MUST NOT be used merely to avoid returning a status or to make a simple interface appear more general.

```c
int create_buffer(unsigned char **buffer_out, size_t size);
```

The contract for an interface such as this MUST explain whether `buffer_out` itself may be `NULL`, whether the function allocates storage, what happens on failure, and who owns the resulting allocation.

When several levels of indirection are necessary, document the role of each level and the ownership and lifetime relationships involved. Deeply nested pointer structures SHOULD receive particular scrutiny because they can make validity and cleanup responsibilities difficult to follow.

• • •

## 9.8. Function Pointers and Object Pointers

Function pointers and object pointers MUST be used according to their distinct purposes.

Object pointers designate objects or positions associated with objects. Function pointers designate functions and are used for indirect calls, callbacks, dispatch tables, or other interfaces that require callable behavior.

```c
int (*operation_ptr)(int value) = NULL;
```

The declaration above defines a pointer to a function that accepts an `int` and returns an `int`. Its signature MUST match the function used to initialize or call it.

C11 does not guarantee portable conversion between function pointers and object pointers. Do not store a function pointer in `void *`, cast between the two categories, or assume they have the same representation unless a documented platform-specific interface explicitly requires it.

Function pointer contracts SHOULD define the callback signature, invocation conditions, context lifetime, reentrancy or threading expectations where relevant, and the meaning of any returned status. A callback MUST NOT be invoked after its target function or required context has become invalid.

• • •

## 9.9. Pointer Validity

Pointer validity MUST be determined by the applicable function, object, and data-structure contracts. Repeating the same defensive check at every use is not required when a valid precondition is already established and remains true.

Before a pointer is used, the relevant requirements MUST hold:

- The pointer value is suitable for the intended operation.
- The target object, if any, is within its lifetime.
- The access is permitted for the pointed-to type and effective type.
- Alignment requirements are satisfied.
- The access remains within the permitted object or array bounds.
- Required read or write permissions are respected.
- Any size, ownership, and aliasing requirements are satisfied.

A non-null value alone is not proof of validity. A pointer may be non-null while dangling, out of bounds, improperly aligned, or unsuitable for the intended access.

Functions MUST validate untrusted external values and relationships at trust boundaries when those values could otherwise cause invalid access. An internal function may rely on a documented caller precondition, but the precondition MUST be established by the caller and MUST NOT be contradicted by the implementation.

Contracts clarify where responsibility lies. They do not make invalid pointer operations safe, and they do not remove the need to handle operational failures such as allocation failure.

• • •

## 9.10. Dangling and Uninitialized Pointers

Uninitialized pointer values MUST NOT be read or used. Every pointer MUST follow the declaration-time initialization rule in Section 9.1.

A pointer MUST NOT be used to access an object after that object's lifetime has ended. Such a pointer is commonly described as dangling. Dereferencing it, using it to access the former object, or using it in an operation that requires a valid pointer to that object is prohibited.

After releasing an owned allocation, the owner SHOULD clear or otherwise retire its pointer so that subsequent control flow cannot accidentally reuse it. Assigning `NULL` is a useful local safeguard:

```c
free(buffer_ptr);
buffer_ptr = NULL;
```

This does not update other pointers that may refer to the same allocation. Those aliases MUST be handled according to the ownership and lifetime contract.

A pointer MUST NOT be retained beyond the lifetime of the object it designates unless the pointer is updated to designate a different valid object or is otherwise no longer used as a pointer to the expired object. Contracts MUST make the relevant lifetime boundaries clear.

• • •

## 9.11. Object Lifetime and Pointer Validity

A pointer may be used to access an object only while the object's lifetime is active and the access satisfies all other C11 requirements.

The lifetime rules apply to automatic, static, allocated, and other object storage durations. An automatic object commonly declared within a block ceases to exist when its lifetime ends. Returning its address or retaining that address for later access MUST NOT be used as a way to extend the object's lifetime.

```c
int *invalid_result(void)
{
    int local_value = 10;

    return &local_value;
}
```

The returned pointer does not designate a live `local_value` after the function returns. This pattern MUST NOT be used.

Static-duration objects remain alive for the duration specified by C11. Dynamically allocated storage remains allocated until it is released, subject to the allocation's actual lifetime and correct ownership management.

A pointer's lifetime and its target object's lifetime are different concepts. A pointer variable may remain in scope after its target object has ceased to exist; that does not make the target accessible.

Contracts for stored or returned pointers MUST identify any required lifetime relationship, including whether the caller must keep an object alive for a later operation.

• • •

## 9.12. Pointer Ownership

Dynamic allocations SHOULD have one clearly identifiable owner by default. The owner is responsible for ensuring that the allocation is eventually released or that ownership is transferred according to a documented contract.

Shared ownership is permitted only when it is an intentional part of the design and the mechanism for determining when the allocation can be released is explicit. Merely storing the same address in multiple pointer variables does not establish shared ownership.

Ownership contracts MUST identify:

- Which component owns the allocation.
- Who is responsible for releasing it.
- Whether and when ownership can be transferred.
- Whether the allocation may be borrowed by other components.
- What happens to ownership when an operation succeeds or fails.
- Whether shared ownership is supported and, if so, how the final release is determined.

Ownership is not the same as reachability. A pointer may refer to an object without owning it, and an owner may transfer its responsibility without changing the object's address.

• • •

## 9.13. Borrowed and Non-Owning Pointers

A borrowed or non-owning pointer refers to an object whose storage is managed elsewhere. A borrowed pointer MUST NOT be used to release the allocation unless its contract explicitly grants that responsibility.

Borrowed pointers may be stored beyond the current function call only when the target object's lifetime and the applicable contract guarantee that subsequent use remains valid. Temporary use during a call is common, but it is not a universal requirement.

Contracts involving borrowed pointers SHOULD identify:

- The component that owns the target object.
- The minimum lifetime required for the borrow.
- Whether the receiving function may retain the pointer.
- Whether the pointed-to object may be modified.
- Whether the pointer may be `NULL`.
- Whether the pointer refers to one object or to a bounded sequence of elements.

A borrowed pointer MUST NOT outlive the target object in a way that permits access after the object's lifetime ends. If the target may be released or replaced while the borrowed pointer is retained, the design MUST provide a valid lifetime guarantee or an appropriate mechanism for preventing stale access.

• • •

## 9.14. Pointer Parameter Contracts

Pointer parameters MUST be documented according to their actual requirements. Contracts SHOULD specify all relevant properties without adding unrelated requirements.

Depending on the interface, a pointer parameter contract SHOULD define:

- Whether `NULL` is accepted and what it means.
- Whether the pointer designates one object or the first element of a sequence.
- The number of accessible elements or bytes.
- Whether the function may read from or write to the target.
- Whether the target must remain alive for the duration of the call or longer.
- Whether the function may retain the pointer after returning.
- Whether ownership is borrowed, transferred, or shared.
- Any relevant alignment and effective-type requirements.
- Any aliasing restrictions between this pointer and other parameters.
- What happens on success and failure.

A function MUST NOT retain a pointer beyond the permitted lifetime merely because the pointer was valid when the function was called. If the function stores the pointer, the contract MUST define how long the stored reference remains valid and who ensures that the target outlives it.

When a function accepts both a pointer and a length, the contract MUST define the unit of the length. Use element counts for element-oriented interfaces and byte counts for byte-oriented interfaces. These units MUST NOT be conflated.

• • •

## 9.15. Pointer and Size Relationships

Interfaces that operate on multiple elements or bytes SHOULD accept a pointer and an explicit length together, unless the size is unambiguously available through another documented interface or data structure.

The length MUST have a clearly defined unit. `size_t` SHOULD be used for object sizes, byte counts, and element counts that follow the C library's size conventions.

```c
int process_values(const int *values, size_t value_count);
```

The contract for this function MUST specify the required relationship between `values` and `value_count`, including whether a null pointer is accepted when the count is zero.

A pointer does not carry its array length. The size MUST NOT be inferred from the pointer value, the address of another object, or an undocumented assumption about allocation size.

The implementation MUST ensure that pointer arithmetic and memory access remain within the actual object bounds. Supplying a length parameter does not make an incorrect length valid.

Calculations used to derive a byte count or element offset MUST be checked for overflow when overflow is possible. The checks MUST occur before the potentially overflowing operation.

• • •

## 9.16. Dynamic Memory Allocation

Dynamic allocation MUST be chosen according to the object's size, lifetime, ownership, performance requirements, and failure-handling requirements. Dynamic allocation MUST NOT be used without a clear need.

Automatic storage is generally suitable for objects with appropriately bounded size and scope. Static storage may be appropriate when the object's lifetime is program-wide or otherwise static. Dynamic storage is useful when the size is determined at runtime, when an object must outlive the current block, or when the data model requires independently managed storage.

The implementation MUST NOT assume that dynamic allocation is always preferable for large objects or that automatic storage is always preferable for small objects. Stack limits, allocation overhead, lifetime requirements, and platform constraints must be considered.

Every allocation MUST have a documented ownership and release strategy. Allocation failure MUST be handled according to Section 9.19. Allocation sizes MUST be computed safely as described in Section 9.18.

• • •

## 9.17. Malloc, Calloc, Realloc, and Free

The standard allocation functions MUST be used in accordance with their C11 contracts.

### `malloc`

`malloc` allocates the requested number of bytes and returns a pointer to the allocated storage or a null pointer if the allocation fails. The returned storage is not automatically initialized to a meaningful value.

The allocation size MUST be correct, and the returned pointer MUST be checked before the allocation is used. Any required object initialization MUST occur before the object is read.

### `calloc`

`calloc` allocates storage for an array of elements and initializes all allocated bytes to zero. The multiplication used to determine the allocation size MUST be safe; implementations of the standard library provide the semantics specified for `calloc`, but application-side size calculations and subsequent length calculations must still be correct.

All-bits-zero is not a universal guarantee of the semantic zero value for every C type. Do not rely on `calloc` alone to establish every required pointer, floating-point, or aggregate invariant.

### `realloc`

The result of `realloc` MUST be stored in a temporary pointer so that failure does not overwrite the only pointer to the original allocation.

```c
void *resized_ptr = NULL;

resized_ptr = realloc(buffer_ptr, new_size);

if (resized_ptr == NULL) {
    /* For a nonzero requested size, buffer_ptr still owns the original allocation. */
} else {
    buffer_ptr = resized_ptr;
}
```

This pattern applies to a nonzero requested size. A zero-size request MUST be handled separately under the project's explicit zero-size policy rather than relying on implementation-specific or version-sensitive behavior.

On successful reallocation, the allocation may move. Pointers into the old allocation MUST NOT be used as if they still referred to the resized object. Recompute interior pointers from the new base pointer when needed and when the new bounds permit it.

The contract MUST define what happens to ownership and valid pointers on both success and failure.

### `free`

`free` MUST receive either a null pointer or a pointer value permitted by the C allocation functions for release. Passing an invalid pointer, releasing the same allocation more than once, or accessing the released object is prohibited.

After release, the owning pointer SHOULD be set to `NULL` or otherwise retired so it cannot be accidentally reused. This local safeguard does not repair other aliases.

### Zero-size operations

The project MUST define how zero-size allocation and reallocation requests are handled. Prefer an explicit branch for zero-size requests rather than relying on the special behavior of `realloc` with a zero size.

• • •

## 9.18. Allocation Size Calculations

Allocation sizes and memory ranges MUST be calculated without integer overflow. `size_t` SHOULD be used for sizes and byte counts, but using `size_t` alone does not prevent overflow.

For example, before calculating `element_count * sizeof(*element_ptr)`, verify that the multiplication is representable:

```c
if (element_count > SIZE_MAX / sizeof(*element_ptr)) {
    /* Report the size error using the applicable status policy. */
}
```

The implementation MUST perform the check before multiplication. Checking the resulting value after an overflowing multiplication is too late.

For addition, verify that the operands can be added without exceeding `SIZE_MAX` before performing the addition. Similar checks are required for offsets, header-plus-payload sizes, alignment adjustments, and other calculations that may exceed the representable range.

When a size originates from an external source, validate it against application limits as well as representability limits. A value can fit in `size_t` and still be too large for the application's intended operation.

The same principles apply to pointer offsets and element counts. Do not perform invalid pointer arithmetic and then attempt to detect the problem afterward.

• • •

## 9.19. Allocation Failure Handling

Allocation failure MUST be handled according to the function's documented contract and the project's status-code policy.

Functions that can recover from allocation failure SHOULD report the failure through the established status mechanism. For example, a function returning an `int` status may use the project's designated allocation-failure status code. The exact code MUST be defined centrally rather than invented independently by each function.

When allocation fails, the function MUST preserve or release existing resources according to its contract. It MUST NOT leak earlier allocations, return an unusable output pointer as though the operation succeeded, or leave ownership ambiguous.

If the operation has partially initialized state, the failure path MUST perform the required cleanup before returning. Cleanup MUST release only resources that were actually acquired.

Controlled process termination may be appropriate for a component whose documented contract cannot recover from a critical allocation failure. Such termination MUST be an explicit policy, not an accidental substitute for error handling in a reusable function.

• • •

## 9.20. Ownership Transfer

Ownership transfer MUST be explicit in the applicable function or data-structure contract. The contract MUST define when the transfer occurs and who owns the allocation after both successful and failed operations.

A function that accepts ownership MUST specify whether ownership transfers at function entry, after validation, after successful processing, or at another clearly defined point. A function that returns an allocation MUST identify the recipient responsible for releasing it.

When an operation fails before ownership transfers, the original owner MUST retain responsibility unless the contract explicitly defines another outcome. When ownership has transferred, the former owner MUST NOT release or use the allocation as an owner unless ownership is transferred back under a documented rule.

The implementation SHOULD use clear control flow so that each path has an unambiguous owner. A status return MUST NOT leave ownership transfer implicit.

Ownership transfer does not necessarily change the address of an allocation. Conversely, a pointer changing value does not, by itself, establish that ownership has transferred.

• • •

## 9.21. Memory Leaks

Every dynamic allocation MUST have an identifiable owner and a valid release path, unless its lifetime is intentionally managed by a documented longer-lived allocation strategy.

The owner MUST ensure that the allocation is released when it is no longer required or that ownership is transferred to another component. Ownership transfer also transfers the corresponding release responsibility.

Functions that acquire multiple allocations MUST define cleanup behavior for partial success. If a later operation fails, previously acquired resources MUST be released or transferred according to the contract.

A pointer being overwritten or going out of scope does not release the allocation it referenced. The implementation MUST NOT discard the only owning pointer while leaving the allocation allocated unintentionally.

Long-lived allocations and process-lifetime allocations are not automatically leaks if their lifetime and purpose are intentional and documented. Their lifetime MUST nevertheless be deliberate rather than the result of lost ownership.

• • •

## 9.22. Double-Free and Use-After-Free

Double-free and use-after-free are prohibited.

An allocation MUST be released only by a component authorized to release it, and it MUST be released no more than once. After release, no pointer may be used to access the former object.

Setting the owning pointer to `NULL` after release is a useful safeguard:

```c
free(storage_ptr);
storage_ptr = NULL;
```

However, setting one pointer to `NULL` does not update aliases held elsewhere. The design MUST prevent those aliases from being used after the object's lifetime ends. This may be achieved through clear ownership, limited borrow lifetimes, invalidation protocols, or other mechanisms appropriate to the architecture.

Do not rely on allocator behavior, memory contents, or observed program output to determine whether a released pointer remains usable. Once the object's lifetime has ended, the former allocation MUST NOT be accessed.

• • •

## 9.23. Partial Initialization and Cleanup

Functions that manage dynamic memory MUST contain a `cleanup` label, in accordance with the function-control-flow rules established in Section 7. The label MUST remain present even if a particular implementation path does not currently reach it.

The cleanup path MUST release acquired resources in reverse order of acquisition when that order is required for correct teardown. It MUST NOT attempt to release resources that were never acquired.

A function may jump directly to `end` when no cleanup is required for the resources acquired along that path. If an acquired resource must be released, the path MUST pass through the required cleanup operations before reaching `end`.

A representative pattern is:

```c
int process_data(void)
{
    int status = 0;
    unsigned char *buffer_ptr = NULL;
    FILE *file_ptr = NULL;

    buffer_ptr = malloc(256);

    if (buffer_ptr == NULL) {
        status = STATUS_ALLOCATION_FAILURE;
        goto end;
    }

    file_ptr = fopen("input.dat", "rb");

    if (file_ptr == NULL) {
        status = STATUS_IO_FAILURE;
        goto cleanup;
    }

    /* Process the data. */

cleanup:
    if (file_ptr != NULL) {
        fclose(file_ptr);
    }

    free(buffer_ptr);
    buffer_ptr = NULL;

end:
    return status;
}
```

The example is illustrative; the exact status names and resource policy must match the project. In this pattern, the allocation failure path goes directly to `end` because no resource was acquired. The later failure path goes through `cleanup` because the allocation already exists.

Cleanup code MUST preserve the original failure status unless the contract explicitly defines a different error-reporting policy. If cleanup itself can fail, the contract MUST define how that failure is reported without obscuring the primary failure unexpectedly.

• • •

## 9.24. Resource Acquisition and Release

Resources other than dynamically allocated memory, including files, locks, handles, and operating-system resources, MUST have explicit acquisition and release responsibilities.

The applicable contract SHOULD identify:

- How the resource is acquired.
- Whether acquisition can fail.
- Who owns the resource.
- Whether the resource may be borrowed or transferred.
- Which operation releases it.
- Whether release can fail and how that failure is reported.
- How partial initialization and early exits are handled.

Resource-specific rules MUST be respected. For example, a file handle is normally released with the corresponding file-closing operation, not `free`; a lock must be released according to its synchronization contract.

Where a function acquires multiple resources, cleanup SHOULD be structured so that the acquisition order and release order are clear. Resources SHOULD generally be released in reverse acquisition order when dependencies make that order necessary.

The presence of a cleanup label does not excuse incorrect release behavior. Each path MUST release exactly the resources it has acquired and remains responsible for.

• • •

## 9.25. Flexible Array Members

Flexible array members MAY be used when they provide a clear representation or allocation advantage for variable-length data. Their use MUST comply with C11's structure-layout and allocation rules.

A flexible array member is declared as the final member of a structure and uses an incomplete array type:

```c
struct packet {
    size_t payload_size;
    unsigned char payload[];
};
```

The allocation size MUST include the structure's fixed portion and the required space for the flexible array elements. The calculation MUST be checked for overflow before allocation.

The number of accessible elements MUST be recorded or otherwise available through a reliable contract. Access MUST remain within the allocated storage and the logical element count.

Do not assume that `sizeof(struct packet)` includes storage for any flexible array elements. Do not treat a structure containing a flexible array member as an ordinary fixed-size object whose full payload can be copied merely by assigning the structure value.

Copying, transferring, or serializing such an object MUST account for its variable-length payload explicitly. The contract MUST define how the payload length is obtained and validated.

• • •

## 9.26. Stack and Heap Usage

The choice between automatic storage, static storage, and dynamic allocation MUST be based on object lifetime, size, ownership, performance, and platform constraints.

Automatic storage is appropriate for objects whose lifetime and size are suitable for the containing scope. Static storage is appropriate when a longer, statically defined lifetime is required. Dynamic allocation is appropriate when runtime sizing, independent lifetime, or the data model requires it.

Do not impose a universal byte threshold for choosing automatic versus dynamic storage. Stack limits vary by platform, execution environment, thread configuration, and program structure. Large automatic arrays may therefore be inappropriate even if their size is fixed.

Dynamic allocation introduces allocation-failure paths, ownership responsibilities, and release requirements. It MUST NOT be used solely to avoid understanding an object's lifetime.

The terms “stack” and “heap” are common implementation concepts, not a substitute for C's storage-duration rules. The guide MUST describe the required lifetime and ownership behavior rather than assuming that every implementation uses a particular physical memory layout.

• • •

## 9.27. Effective Type and Strict Aliasing

All object accesses MUST comply with C11's effective-type and aliasing rules. A pointer cast does not, by itself, make an access through an incompatible type valid.

Access to an object's stored value MUST use a permitted lvalue type under C11. The standard's permitted cases include compatible types, appropriately qualified versions of compatible types, corresponding signed or unsigned types, certain aggregate or union types containing permitted members, and character types used to inspect object representation. The exact rule applicable to an access MUST be satisfied.

Character types, including `unsigned char`, may be used to inspect an object's byte representation:

```c
unsigned char representation[sizeof(value)];
memcpy(representation, &value, sizeof(value));
```

The example assumes `value` is an existing object and `representation` has the stated capacity. Inspecting the representation does not guarantee that it has a portable encoding or that its bytes can be used to reconstruct the value on another platform.

`memcpy` SHOULD be used when bytes need to be copied between objects without performing an invalid access through an incompatible pointer type. Source and destination validity, size, and lifetime requirements still apply.

Do not disable strict-aliasing optimizations or introduce compiler-specific aliasing assumptions as a substitute for writing code that follows the standard. Any compiler-specific requirement MUST be justified and documented separately.

• • •

## 9.28. Alignment Requirements

Objects MUST be accessed only through pointers that satisfy the alignment requirements of the accessed type.

The implementation SHOULD rely on the alignment naturally provided by standard object declarations and standard allocation functions. Special alignment requirements MUST be introduced only when a type, platform interface, hardware requirement, or data representation needs them.

C11 provides `_Alignof` to query a type's alignment requirement and `_Alignas` to request alignment for an object declaration. Use these facilities only when their purpose and portability implications are understood.

```c
_Alignas(16) unsigned char storage[64];
```

The example requests a particular alignment for `storage`; it does not establish that the same declaration is appropriate or supported in every environment. The requirement MUST be justified by the relevant interface or implementation constraint.

Manually adding padding bytes does not, by itself, guarantee that an object or member has a particular alignment. Alignment and padding are related but distinct properties.

Do not cast a pointer to a more strictly aligned pointer type and then dereference it unless the target address satisfies that type's alignment requirement. A conversion does not correct misalignment.

• • •

## 9.29. Pointer-to-Pointer Parameters

Pointer-to-pointer parameters MUST be used only when their role in the interface is clear. Common justified uses include updating the caller's pointer, returning an allocated object through an output parameter, or managing a pointer-based data structure.

```c
int allocate_values(int **values_out, size_t value_count);
```

The function contract MUST define whether `values_out` may be `NULL`, whether the output is initialized on entry, what happens when allocation fails, and who owns the resulting allocation.

When an output pointer is supplied, the function SHOULD define the state of the output on failure. It MUST NOT leave the caller unable to determine whether an allocation was produced or who owns it.

A pointer-to-pointer parameter does not automatically imply ownership transfer. The ownership contract MUST explicitly distinguish changing a pointer value from transferring responsibility for the pointed-to allocation.

Use a simpler pointer parameter when the function only needs to read or modify the pointed-to object and does not need to modify the caller's pointer value.

• • •

## 9.30. Const Pointers and Pointer Qualifiers

Pointer qualifiers MUST be used according to their C11 semantics and the interface's actual requirements.

### `const`

Use `const` to express that an object is not to be modified through a particular access path:

```c
const char *text_ptr = NULL;
char *const fixed_ptr = NULL;
```

In the first declaration, the pointed-to characters cannot be modified through `text_ptr`. In the second declaration, the pointer itself cannot be reassigned after initialization, while the pointed-to object is not made const by that declaration.

Use the appropriate form to express whether the pointer value, the pointed-to object, or both are intended to remain unchanged. `const` does not guarantee that no other alias can modify the object.

### `volatile`

Use `volatile` only when required by a specific interface or implementation requirement, such as certain memory-mapped hardware accesses or other externally observable access semantics.

`volatile` MUST NOT be used as a thread synchronization primitive. It does not provide the atomicity, inter-thread ordering, or data-race protection required for thread synchronization. Use appropriate C11 atomic facilities or a suitable synchronization mechanism when concurrent access requires them.

### `restrict`

Use `restrict` only when the associated access and aliasing contract is genuinely satisfied. It gives the implementation additional assumptions about access to an object through the relevant pointer relationships. Violating those assumptions can produce undefined behavior.

Do not add `restrict` merely as a performance hint. The contract and all relevant call sites MUST satisfy the requirements imposed by its use.

Other qualifiers MUST be used only when their semantics are understood and the resulting contract is correct.

• • •

## 9.31. Pointer Arithmetic Boundaries

Interfaces that perform pointer arithmetic SHOULD represent the accessible range with a pointer and a corresponding length when the range is not otherwise unambiguously available.

The length MUST identify whether it counts elements or bytes. The implementation MUST validate offsets and lengths before computing addresses or accessing memory.

For an array containing `count` elements, valid element indices range from zero through `count - 1` when `count` is nonzero. A one-past pointer may be formed at the end of the array but MUST NOT be dereferenced. Special care is required when `count` is zero, because expressions such as `count - 1` can underflow when `count` is unsigned.

A pointer and length pair does not automatically prove that the claimed range exists. The caller's contract MUST guarantee the underlying object and its actual accessible extent.

Do not calculate a pointer outside the permitted array range and then attempt to validate it afterward. Validate the index or offset first, and perform only pointer arithmetic permitted by C11.

• • •

## 9.32. Memory Copying and Moving

Use `memcpy` when the source and destination memory regions do not overlap. Use `memmove` when the regions may overlap.

The byte count MUST be valid for both source and destination. The source and destination pointers MUST designate memory suitable for the requested operation, and the regions MUST remain within their respective accessible bounds.

```c
memcpy(destination_ptr, source_ptr, byte_count);
```

This is valid only when the source and destination regions do not overlap and both regions provide at least `byte_count` accessible bytes. If overlap is possible, use `memmove` instead.

Memory-copy functions copy object representations as bytes. They do not perform deep copying, duplicate the ownership of pointed-to allocations, or automatically establish a valid logical state for every type.

When copying structures that contain pointers, determine whether a shallow copy is intended. A shallow copy duplicates pointer values, not the allocations those pointers refer to. It MUST NOT accidentally create multiple owners or extend an object's lifetime.

Flexible array members and variable-length payloads require explicit size handling. Raw copying of a fixed-size structure object does not automatically copy the additional storage associated with a flexible array member.

• • •

## 9.33. Zero-Initialization and Byte-Level Initialization

Object initialization MUST follow the semantics required by the object's type. Byte-level zeroing MUST NOT be treated as universally equivalent to assigning the semantic zero value.

C initialization syntax can initialize objects according to the language's rules:

```c
int count = 0;
int *value_ptr = NULL;

struct record {
    int id;
    const char *name;
};

struct record item = {0};
```

The initializer `{0}` initializes the aggregate according to C's initialization rules. It is distinct from assuming that writing zero bytes into arbitrary existing storage always produces a valid semantic state.

`memset` sets each byte to the specified byte value. `calloc` initializes allocated bytes to all-bits-zero. Neither operation guarantees that all possible object types acquire the desired semantic values or that every possible object representation becomes valid merely because its bytes are zero.

Use `memset` when byte-level initialization is the actual requirement, such as clearing a byte buffer. Use typed initialization when the desired result is a typed C value.

If a structure requires specific invariants, pointer values, resource states, or member relationships, establish those explicitly rather than relying only on byte-level clearing.

• • •

## 9.34. Object Representation and Padding

Object representation, including padding bytes, MUST NOT be assumed to provide a portable serialization format.

C implementations may use padding within structures and may represent types differently across platforms, compiler options, or application binary interfaces. Padding bytes do not necessarily contain stable, meaningful values.

Do not use `memcmp` as a general semantic equality test for structures. Two structures whose corresponding members compare equal may still have different object representations because of padding or other representation details. Compare the relevant members explicitly or define a suitable equality operation.

Raw structure bytes MUST NOT be written directly as a portable file format, network protocol, or stable cross-platform ABI representation unless the format is explicitly platform-specific and its assumptions are documented.

Portable serialization SHOULD encode fields explicitly, with defined byte order, widths, and validation rules. When object representation must be inspected, use permitted character-type access and account for the implementation-dependent nature of the result.

Do not assume that manual padding fields eliminate all implementation-dependent layout behavior. If exact layout is required by an external ABI or hardware interface, the constraints MUST be documented and verified for the target implementation.

• • •

## 9.35. Allocation and Deallocation Contracts

Every function that allocates, reallocates, transfers, or releases dynamic memory MUST have a contract that defines the relevant parts of the allocation's lifecycle. The canonical function contract MUST be documented in the separate Markdown file required by Section 7.

As applicable, the contract MUST specify:

- The allocation's intended size and how that size is calculated.
- The conditions under which allocation can fail.
- How success and failure are reported.
- Whether output pointers are initialized or modified on failure.
- Which component owns the allocation before and after the call.
- Whether ownership is transferred, borrowed, or shared.
- Which component is responsible for releasing the allocation.
- Whether and how the allocation may be resized.
- Which previously derived pointers become invalid after reallocation or release.
- The lifetime and bounds requirements for pointers returned or retained.
- How partial initialization is cleaned up.
- Whether zero-size requests are possible and how they are handled.
- Any relevant alignment, effective-type, or representation requirements.

The contract MUST describe failure behavior precisely enough that callers can determine whether they still own an existing allocation, whether an output pointer may be used, and what cleanup is required.

A function MUST NOT leave ownership ambiguous on any documented success or failure path. The implementation MUST preserve the project's status-code conventions and the `end`/`cleanup` control-flow policy established in earlier sections.

The allocation contract does not replace the requirements for correct pointer use. All callers and implementations MUST continue to satisfy C11's object lifetime, alignment, bounds, effective-type, and pointer arithmetic rules.

___

# 10.0. Macros and C11 Features

This section defines the project's policies for preprocessor directives, macros, C11 language and library features, compiler extensions, compile-time configuration, and platform-specific behavior.

The primary objectives are to maintain portability across GCC and Clang, avoid unnecessary dependencies on compiler-specific behavior, preserve compatibility with different C library implementations, and keep source code explicit and maintainable.

The project targets ISO C11. Standard C11 constructs are preferred over preprocessor-based alternatives whenever they provide equivalent functionality. Compiler identity, implementation-specific behavior, and non-standard language extensions must not become implicit dependencies of application code.

The following principles govern this section:

- Standard C11 features are preferred over compiler-specific extensions.
- Compiler extensions are prohibited.
- Optional C11 features are prohibited.
- Predefined macros supplied by the compiler may be used only when permitted by this section.
- Project-defined macros are permitted when they follow the project's naming and usage policies.
- Conditional compilation must have a clear purpose and must remain understandable.
- Platform-specific interfaces must be isolated from portable application code.
- Macros must not introduce hidden side effects, unexpected control flow, or unnecessary namespace pollution.
- Compile-time configuration must be explicit, documented, and consistent across the project.

## 10.1. General Preprocessor Policy

The preprocessor MUST be used deliberately and only when its capabilities are appropriate for the task.

The preferred order of consideration is:

1. Standard language constructs.
2. Normal functions and explicitly declared objects.
3. Enumeration constants and other appropriate standard C constructs.
4. Object-like or function-like macros when preprocessor behavior is genuinely required.
5. Conditional compilation when a compile-time distinction cannot reasonably be expressed otherwise.

Preprocessor directives MUST NOT be introduced merely to shorten code, obscure implementation details, or replace ordinary language constructs without a concrete technical justification.

Macros MUST be designed to minimize unexpected behavior and MUST follow the naming, parameter handling, evaluation, and namespace rules defined in this section.

Preprocessor directives SHOULD be placed at the beginning of a line, with indentation and spacing consistent throughout the project.

The project MUST NOT depend on undocumented compiler behavior, accidental macro expansion, or implementation-specific preprocessing semantics.

• • •

## 10.2. Object-Like Macros

Object-like macros MAY be used for compile-time constants, configuration switches, header guards, conditional compilation, and other justified preprocessor tasks.

An object-like macro SHOULD NOT be used merely to give a name to a value when an enumeration constant or another standard C construct is more appropriate.

For example:

```c
#define APP_DEFAULT_CAPACITY 64
```

is acceptable when a preprocessor constant is needed.

However, macros do not have ordinary C object types, storage duration, or scope. Their use MUST account for these differences.

Object-like macros MUST use uppercase names with underscores separating words. Project-defined macros MUST use the project's designated prefix where appropriate.

Macros representing values MUST be defined so that their expansions have clear and predictable meanings in every permitted context.

Macros MUST NOT be used to conceal complex expressions, introduce hidden side effects, or simulate ordinary variables without a clear requirement.

• • •

## 10.3. Function-Like Macros

Function-like macros MAY be used when preprocessor behavior is required, including token manipulation, stringification, compile-time selection, and other operations that cannot be expressed equivalently by an ordinary function.

Normal functions MUST be preferred when they provide the required behavior.

Function-like macros MUST NOT be introduced solely to avoid function-call overhead. Performance-sensitive decisions MUST be supported by an actual technical requirement rather than an assumption that macros are inherently faster.

Function-like macros MUST have clearly defined parameters and predictable expansions.

Their implementation MUST account for operator precedence, argument evaluation, type behavior, and possible interactions with surrounding expressions.

Macros MUST NOT introduce hidden state changes or unexpected control flow.

When a macro performs several statements, the requirements of Section 10.8 apply.

• • •

## 10.4. Macro Parameter Parenthesization

Every occurrence of a function-like macro parameter MUST be parenthesized in the replacement list unless the parameter is used in a preprocessing context where ordinary expression parentheses are inapplicable.

The complete replacement expression SHOULD also be enclosed in parentheses when it represents a single expression.

For example:

```c
#define APP_SQUARE(value) ((value) * (value))
```

This prevents common operator-precedence errors when the macro is used inside a larger expression.

The parentheses do not prevent multiple evaluation of an argument. That problem is addressed separately in Section 10.5.

Stringification and token-pasting operators MUST follow the C11 preprocessing rules rather than being treated as ordinary expression operators.

• • •

## 10.5. Multiple Evaluation of Macro Arguments

Function-like macros MUST be designed to avoid unnecessary multiple evaluation of their arguments.

Where practical, a macro SHOULD evaluate each argument no more than once.

If repeated evaluation cannot be avoided, the macro's contract MUST clearly identify the behavior, and callers MUST NOT supply arguments with side effects unless those effects are explicitly safe under the macro's evaluation semantics.

For example:

```c
#define APP_SQUARE(value) ((value) * (value))
```

A call such as `APP_SQUARE(index++)` is prohibited because the argument is evaluated more than once and changes program state.

Parenthesizing a macro parameter does not solve this problem.

If single evaluation is important and an ordinary function can provide the required behavior, the function MUST be preferred.

Macro contracts SHOULD document any evaluation restrictions that are not immediately obvious from the call site.

• • •

## 10.6. Stringification and Token Pasting

The preprocessor operators `#` and `##` MAY be used for stringification and token pasting.

Their use MUST remain understandable and MUST follow the rules of ISO C11 preprocessing.

Stringification MAY be used when a string representation of a macro argument is required. Token pasting MAY be used when constructing identifiers or preprocessing tokens is a genuine requirement.

These operators MUST NOT be used to obscure ordinary identifier names, simulate an unnecessary abstraction system, or generate code whose behavior is difficult to determine.

The result of token pasting MUST form a valid preprocessing token under the applicable C11 rules. Token pasting MUST NOT be assumed to provide arbitrary textual concatenation.

When token pasting or stringification depends on macro expansion order, the implementation MUST account for the distinction between direct parameter substitution and expansion before stringification or token pasting.

• • •

## 10.7. Variadic Macros

Variadic macros MAY be used when a variable number of arguments is necessary, such as in justified logging, formatting, or diagnostic interfaces.

Their use SHOULD remain limited to interfaces where variable argument counts provide a concrete benefit.

Variadic macros MUST follow the C11 preprocessing rules. Compiler-specific extensions to variadic macro syntax MUST NOT be used.

The macro's contract MUST define the expected arguments, their interpretation, and any formatting or type requirements.

Variadic macros MUST NOT be used to simulate function overloading or a general-purpose type system.

When a standard variadic function can provide the required behavior more clearly, it SHOULD be preferred.

• • •

## 10.8. Multi-Statement Macros

Macros that expand to multiple statements SHOULD be avoided when an ordinary function or another standard C construct can provide equivalent behavior.

When a multi-statement macro is necessary, it MUST use a structure that behaves as a single statement in ordinary control-flow contexts.

The following form MUST be used for multi-statement macros when applicable:

```c
#define APP_UPDATE_STATE(value) \
    do { \
        update_state(value); \
        record_state(); \
    } while (0)
```

The `do { ... } while (0)` form prevents common problems when the macro is used in an `if` statement or another control-flow construct.

The macro MUST NOT depend on accidental interactions with the caller's local variables. Macro parameters and expansions MUST be designed to minimize name collisions and unexpected evaluation.

A multi-statement macro SHOULD NOT be used when the same operation can be expressed more clearly as a function.

• • •

## 10.9. Macro Naming and Namespace Pollution

Project-defined macros MUST use uppercase names with underscores separating words.

Project-defined macros MUST use an appropriate project-specific prefix to minimize collisions with other headers, libraries, and platform interfaces.

For example:

```c
#define APP_BUFFER_CAPACITY 256
#define APP_FEATURE_ENABLED 1
```

Generic macro names such as `MAX`, `MIN`, `ERROR`, and `DEBUG` MUST NOT be introduced into public headers without a compelling and documented reason.

Macros MUST NOT use names reserved to the implementation by ISO C.

Identifiers beginning with double underscores or an underscore followed by an uppercase letter are reserved for the implementation at all scopes. Identifiers beginning with an underscore are also reserved at file scope.

Project-defined macros MUST NOT use these reserved identifier forms.

Public headers MUST minimize their macro footprint. A macro that is required only by one implementation file SHOULD be defined in that implementation file rather than in a public header.

• • •

## 10.10. Undef Policy

The `#undef` directive SHOULD be avoided unless removing a macro serves a clear purpose.

Macro definitions SHOULD be designed to minimize collisions and unnecessary dependence on macro lifetime.

Appropriate uses of `#undef` include removing a temporary helper macro after a preprocessing operation or preventing an unwanted macro definition from affecting subsequent code.

A macro MUST NOT be undefined merely as a routine stylistic practice when doing so provides no meaningful benefit.

Before using `#undef`, developers SHOULD consider whether the macro can instead be given a more specific name or confined to a narrower implementation scope.

The use of `#undef` MUST NOT be relied upon to make a reserved identifier available for project use or to make an otherwise prohibited compiler extension acceptable.

Header guards MUST remain effective throughout the intended inclusion behavior of their headers.

• • •

## 10.11. Conditional Compilation

Conditional compilation MAY be used for compile-time configuration, platform-specific implementation selection, and other genuine build-time distinctions.

Conditional compilation MUST NOT be used to replace ordinary runtime decisions when runtime selection is appropriate.

Conditional compilation SHOULD be limited to cases where the relevant distinction must be resolved during preprocessing or compilation.

The conditions used in `#if`, `#ifdef`, `#ifndef`, and `#elif` directives MUST be understandable and consistently named.

Where practical, related configuration decisions SHOULD be centralized instead of duplicated across unrelated source files.

Conditional compilation MUST NOT depend on compiler-specific predefined macros or GNU-specific features prohibited by Sections 10.24–10.30.

The structure and formatting of conditional compilation branches MUST follow Sections 10.28 and 10.29.

• • •

## 10.12. Feature and Platform Detection

Feature and platform detection MUST prioritize standardized mechanisms and explicitly documented build configuration.

Platform detection SHOULD be centralized in an appropriate compatibility or configuration layer.

Portable application code MUST NOT repeatedly inspect compiler-specific predefined macros to choose implementation behavior.

When platform-specific implementation is required, the project SHOULD expose a stable internal interface and select the implementation through controlled build configuration.

Detection MUST distinguish between:

- The C language standard supported by the implementation.
- The operating system and platform interfaces available.
- The capabilities of the C library.
- Optional language or library features.
- Project-specific configuration.

A compiler's identity MUST NOT be treated as proof that a particular operating-system interface or library capability is available.

The presence of a macro MUST NOT be treated as proof of runtime capability unless the relevant contract guarantees that relationship.

• • •

## 10.13. Compile-Time Configuration

Compile-time configuration MAY be used when a decision must affect compilation, linking, platform selection, or the resulting program's structure.

Configuration options MUST have documented names, meanings, defaults, and permitted values.

Configuration macros MUST use project-specific prefixes and MUST follow Section 10.9.

Invalid or contradictory configuration combinations SHOULD be rejected during compilation.

The project MUST avoid maintaining multiple independent definitions of the same configuration value.

Configuration definitions SHOULD be centralized in documented build settings or appropriate configuration headers.

Compile-time configuration MUST NOT be used as an excuse to maintain unnecessary alternative implementations or to obscure the behavior of the default build.

Configuration that changes public structures, function declarations, or other ABI-relevant properties MUST be controlled consistently across all translation units that use the affected interfaces.

• • •

## 10.14. Macros Versus Functions

Normal functions MUST be preferred over function-like macros when both can provide the required behavior with equivalent semantics.

Functions provide ordinary type checking, a defined function interface, and a single evaluation of each argument expression according to the function-call semantics of C.

Macros MAY be used when preprocessor operations, compile-time substitution, or another specific requirement makes them appropriate.

Macros MUST NOT be selected solely on the assumption that they provide better performance.

The choice between a macro and a function SHOULD consider:

- Type safety.
- Argument evaluation.
- Debugging and diagnostic clarity.
- Code readability.
- Namespace pollution.
- Interface stability.
- The actual requirements of the operation.

A macro that only forwards arguments to a function SHOULD generally be avoided unless it provides a concrete additional capability.

• • •

## 10.15. Assertion Macros

The standard `assert` macro from `<assert.h>` MAY be used to detect violated internal assumptions and programming invariants.

Assertions MUST NOT replace ordinary error handling, validation of untrusted input, or recovery from expected operational failures.

Assertions MUST NOT be relied upon to perform required side effects. When `NDEBUG` is defined before `<assert.h>` is included, assertions are disabled and their expressions are not evaluated.

For example, an operation required for program correctness MUST NOT be placed solely inside an assertion:

```c
assert(initialize_component() == 0);
```

If initialization is required, it MUST be performed explicitly and its result handled according to the function's contract.

Assertions SHOULD express conditions that indicate a programming defect or violated internal invariant rather than ordinary conditions that the program is expected to encounter.

Public API contracts MUST define their required input conditions independently of assertions.

• • •

## 10.16. Variable-Length Arrays

Variable-length arrays (VLAs) MUST NOT be used.

This prohibition applies to variable-length array declarations whose bounds are determined at runtime.

Alternative approaches SHOULD be selected according to the required lifetime, capacity, ownership, and failure-handling behavior. These may include fixed-size arrays with documented limits or dynamically allocated storage when appropriate.

Dynamically allocated storage MUST follow the project's memory-management rules.

The prohibition of VLAs MUST NOT be bypassed through compiler extensions or alternative syntax that provides equivalent non-standard behavior.

• • •

## 10.17. Generic Selection

The C11 `_Generic` selection construct MUST NOT be used.

Type-dependent behavior SHOULD be expressed through explicit interfaces, separate functions, or another standard C design that does not depend on generic selection.

Function-like macros MUST NOT use `_Generic` to simulate function overloading or conceal materially different behavior behind an apparently uniform interface.

This prohibition applies regardless of whether a particular compiler implements `_Generic` correctly or efficiently.

• • •

## 10.18. Atomic Types and Operations

C11 atomic types and operations MUST NOT be used.

This prohibition includes the standard atomic interfaces provided by `<stdatomic.h>` and the C11 atomic constructs and operations covered by that facility.

Atomic operations MUST NOT be replaced by `volatile` accesses. The `volatile` qualifier does not provide atomicity, inter-thread synchronization, or data-race prevention.

If concurrent access to shared data is required, the implementation MUST use an approved synchronization mechanism appropriate to the target platform and the relevant data-access pattern.

Synchronization requirements MUST be explicit. Unsynchronized conflicting accesses to shared objects MUST NOT be assumed safe.

The prohibition of C11 atomics does not itself prohibit every form of concurrency. However, any concurrency mechanism used by the project MUST have a defined implementation strategy and documented portability requirements.

• • •

## 10.19. C11 Thread Support

The C11 thread API MUST NOT be used.

This prohibition includes the thread interfaces provided by `<threads.h>`, including the C11 thread creation, synchronization, and thread-management facilities.

The project MUST NOT assume that a C11 implementation provides `<threads.h>` or that the corresponding facilities are available on every target.

If threading is required, a separate platform-specific concurrency layer MAY be used where permitted by the project's platform policy. For example, a POSIX implementation may use POSIX thread interfaces when the target platform provides them.

Platform-specific concurrency interfaces MUST be isolated from portable application code and MUST have documented synchronization, lifetime, error-handling, and portability requirements.

This rule does not authorize compiler extensions or override the prohibitions in Sections 10.18, 10.23, 10.24, and 10.30.

• • •

## 10.20. Thread-Local Storage

The C11 `_Thread_local` storage-class specifier MAY be used when thread-local storage is genuinely required and the relevant implementation supports it.

Its use SHOULD be limited to cases where per-thread object storage provides a clear benefit over explicit context passing or another suitable design.

Thread-local objects MUST have clearly understood initialization and lifetime behavior.

Developers MUST NOT assume that thread-local storage automatically makes an object safe to share between threads or eliminates the need for synchronization when shared state is accessed.

Where the platform or implementation does not support the required behavior, the project MUST use an explicitly approved alternative or reject that build configuration.

• • •

## 10.21. Alignment Specifiers and Operators

The C11 alignment facilities `_Alignas` and `_Alignof` MAY be used when a concrete alignment requirement exists.

The implementation's natural alignment SHOULD be preferred unless a documented technical requirement justifies a stricter alignment.

Alignment requirements MUST be compatible with the applicable C11 constraints and the capabilities of the target implementation.

Developers MUST NOT assume that an arbitrary requested alignment is supported.

Manual padding MUST NOT be treated as a guarantee of alignment. Structure layout and padding do not, by themselves, guarantee that an object begins at a particular alignment boundary.

Alignment decisions affecting public structures MUST account for ABI compatibility and the requirements of every supported target.

• • •

## 10.22. Noreturn Function Specifier

The C11 `_Noreturn` function specifier MAY be used for functions that do not return control to their callers.

It MUST be used only when the function's behavior satisfies the C11 requirements for a non-returning function.

Functions that may return normally MUST NOT be declared `_Noreturn`.

The specifier SHOULD be used when it materially improves the clarity of the function's contract, control-flow analysis, or compiler diagnostics.

The use of `_Noreturn` MUST NOT be replaced by a compiler-specific non-returning function attribute.

A function's actual behavior MUST agree with its declaration.

• • •

## 10.23. Optional C11 Features

Optional C11 features MUST NOT be used by default.

For this policy, optional features are features for which ISO C11 does not require every conforming implementation to provide the relevant support.

The presence of a feature in the C11 standard does not, by itself, guarantee that the feature is mandatory on every implementation.

The prohibition includes optional features otherwise identified in this guide, including variable-length arrays, C11 atomics, and C11 thread support.

Where a feature is explicitly prohibited elsewhere in this guide, that prohibition remains in effect independently of its optional status.

Required application behavior MUST NOT depend implicitly on the availability of optional C11 facilities.

The project MUST prefer implementations based on the supported baseline and its approved platform interfaces.

The fact that GCC and Clang both support a feature MUST NOT automatically make an optional or non-standard feature acceptable.

• • •

## 10.24. Restricted Compiler Extensions

Compiler-specific language extensions MUST NOT be used.

The project targets ISO C11 rather than a compiler-specific dialect. GCC and Clang MUST be used as C11 compilers, not as sources of additional language semantics.

The prohibition includes GNU-specific language constructs, compiler-specific attributes, built-ins that are not part of ISO C11, and other non-standard syntax or semantics.

Standard C11 facilities MUST be preferred even when a compiler extension appears shorter or more convenient.

A platform API that is external to ISO C is not automatically a compiler language extension. Such APIs MUST be evaluated under the project's platform-interface policy and MUST NOT be confused with permission to use non-standard language syntax.

The project's source code MUST NOT require GNU C extensions to compile correctly.

• • •

## 10.25. GCC and Clang Extension Isolation

GCC- and Clang-specific language extensions MUST NOT be introduced into application code.

The project SHOULD be structured so that changing between GCC and Clang does not require changes to ordinary application source code.

Compiler-specific predefined macros MUST NOT be used to create alternate application behavior.

Where a platform integration requires an implementation-specific mechanism, the requirement MUST be reviewed separately from compiler language extensions. The existence of a compiler-specific implementation technique does not automatically authorize its use.

Any approved platform-specific integration MUST be isolated behind an explicit interface and MUST NOT expose compiler-specific constructs through public application headers.

The isolation requirement MUST NOT be interpreted as permission to use prohibited compiler extensions inside a compatibility layer.

• • •

## 10.26. Predefined Macros

Compiler-specific predefined macros MUST NOT be used in project source code.

This prohibition includes macros used to identify GCC, Clang, GNU language modes, or other compiler-specific implementation details, such as `__GNUC__` and `__clang__`.

The project MUST NOT use these macros to select alternate implementations, enable compiler extensions, or introduce compiler-dependent behavior.

Standard-defined predefined macros, such as `__STDC_VERSION__`, MAY be used when required for legitimate standards-related detection, subject to the restrictions on optional C11 features and conditional compilation.

Standard-defined macros and compiler-specific macros MUST NOT be treated as equivalent categories.

Project-defined macros are permitted when they follow the naming and configuration rules in this guide. For example, `APP_FEATURE_ENABLED` is a project-defined macro rather than a compiler-provided predefined macro.

Project-defined macros MUST NOT impersonate implementation-reserved identifiers or serve as a means of indirectly enabling prohibited compiler extensions.

The presence of a predefined macro MUST NOT be treated as proof that an unrelated platform or library capability is available.

• • •

## 10.27. Macro Continuation and Line Formatting

Multi-line macro definitions MUST use explicit and consistent formatting.

The backslash used for line continuation MUST be the final character on the physical source line. No spaces, tabs, comments, or other characters may follow it.

For example:

```c
#define APP_PROCESS_VALUE(value) \
    do { \
        process_value(value); \
    } while (0)
```

Continuation lines SHOULD use consistent indentation.

Macros SHOULD be kept short enough that their expansion remains understandable. Complex macro definitions SHOULD be replaced by ordinary functions or simpler constructs where practical.

Developers MUST NOT rely on whitespace or line formatting to change the intended preprocessing behavior.

Changes to multi-line macros MUST be reviewed for accidental removal of continuation characters, unintended token concatenation, and altered argument evaluation.

• • •

## 10.28. Conditional Compilation Branch Structure

Conditional compilation branches MUST be structured for clarity and minimal complexity.

Branches SHOULD represent mutually exclusive conditions where the intended behavior requires mutual exclusivity.

Unnecessary nested conditional compilation MUST be avoided.

Each `#if`, `#ifdef`, or `#ifndef` directive MUST have a corresponding `#endif`, with consistent indentation and formatting.

Where multiple alternatives are required, `#elif` SHOULD be preferred over deeply nested conditionals when it makes the decision structure clearer.

The conditions MUST be based on permitted configuration or standard-defined detection mechanisms.

Conditional compilation MUST NOT be used to conceal incompatible implementations, duplicate unrelated logic, or create unnecessary compiler-specific behavior.

The default configuration MUST remain clear, and supported alternatives MUST be documented.

• • •

## 10.29. Feature-Test Macros

Feature-test macros MAY be used when they are necessary to request specific interfaces from the target system or its C library.

Their use MUST be documented and consistent across the relevant build configuration.

Feature-test macros MUST be defined before including system headers whose declarations or definitions they affect.

Where a feature-test macro affects multiple translation units or public interfaces, it SHOULD be defined centrally through the build configuration rather than independently in arbitrary source files.

The project SHOULD prefer standardized feature-test interfaces where available and MUST avoid enabling unrelated implementation-specific interfaces unnecessarily.

GNU-specific feature-test macros, including `_GNU_SOURCE`, MUST NOT be used under the project's portability policy unless a separately approved platform requirement explicitly changes that policy.

POSIX feature-test macros, such as `_POSIX_C_SOURCE`, MAY be used when the project requires the corresponding POSIX interfaces and the target environment supports them.

Feature-test macros MUST NOT be confused with compiler predefined macros or project-defined configuration macros.

• • •

## 10.30. Prohibited Language Extensions

Non-standard language extensions MUST NOT be used.

This prohibition applies to GNU C extensions and other compiler-specific language constructs, regardless of whether GCC and Clang both support them.

The project MUST NOT rely on compiler-specific attributes, built-ins, alternative syntax, or implementation-specific language behavior when an equivalent ISO C11 solution is available.

The project MUST NOT use a GNU language dialect as its source-level compatibility baseline.

Standard C11 code SHOULD be compiled with strict language-mode and diagnostic options supported by the project's toolchain. Such options SHOULD be configured to detect accidental use of non-standard constructs.

Compiler options and build configuration MUST NOT silently re-enable prohibited language extensions.

Operating-system APIs and standardized external interfaces, such as POSIX interfaces, MUST be evaluated separately from compiler language extensions. Their use does not automatically violate this rule, provided they are permitted by the project's platform policy and isolated where appropriate.

The purpose of this prohibition is to keep the language-level implementation portable across GCC and Clang and to avoid unnecessary dependence on GNU-specific behavior, including behavior that may complicate compatibility with alternative C library implementations such as musl.

___

# 11.0. API & ABI Guide

This section defines the requirements for designing, documenting, exposing, maintaining, and versioning public APIs and application binary interfaces (ABIs) in C11 projects.

The objective is to maintain a small, consistent, well-documented public interface while preserving source compatibility and ABI stability across supported releases. Public interfaces MUST be treated as long-term compatibility commitments rather than implementation conveniences.

This section applies to public headers, exported symbols, public data types, shared libraries, static libraries, foreign function interfaces, and platform-dependent interfaces.

The following principles govern this section:

- Public interfaces MUST be deliberately designed and explicitly documented.
- Public API contracts MUST be maintained separately from implementation details.
- ABI compatibility MUST be preserved across supported compatible releases and supported ABI targets.
- Changes that break ABI compatibility MUST require a major version change and a documented migration plan.
- Platform-dependent APIs and compiler-dependent behavior MUST NOT leak into portable public interfaces without an explicitly documented exception.
- Public data representations MUST NOT depend on assumptions about compiler behavior, structure padding, alignment, enum representation, or bit-field layout.
- Compatibility guarantees MUST identify the platforms, architectures, ABI targets, and compiler configurations to which they apply.
- Public headers MUST remain stable and MUST undergo compatibility review before modification.

C11 language compatibility alone does not guarantee ABI compatibility. The C standard does not define one universal binary representation for every implementation, architecture, compiler, or operating system. ABI guarantees MUST therefore be scoped to explicitly supported targets.

## 11.1. Public and Private Interfaces

Public and private interfaces MUST be separated.

Public headers MUST be located under `/include/`. Internal headers MUST be located under `/src/include/`. These directories represent interface ownership and stability, not merely source organization.

Public headers define the supported interface available to external consumers. Internal headers define interfaces intended for implementation components within the project.

The following rules apply:

- Public declarations MUST be exposed through appropriate public headers.
- Internal implementation declarations MUST NOT be added to public headers merely for convenience.
- Private implementation details MUST NOT become public API commitments without an explicit design decision.
- Public headers MUST NOT require consumers to include internal headers.
- Internal headers MAY depend on public headers when required by the implementation architecture.
- Public headers MUST NOT depend on private implementation details.
- Circular header dependencies MUST be avoided.
- Header dependencies MUST be explicit and sufficient for the declarations provided by each header.
- Public and internal interfaces MUST be reviewed separately when assessing compatibility.
- Internal interfaces MAY change more freely than public interfaces, provided that such changes do not alter the public API or ABI.

Internal headers MAY be accessible to multiple project components through configured include paths. This accessibility does not make their declarations public API.

Private symbols SHOULD remain hidden from external consumers. Symbol visibility MUST be controlled according to Section 11.4.

A declaration being technically accessible at compile time does not automatically make it a supported interface. Only explicitly designated public declarations are covered by the public API contract.

• • •

## 11.2. API Design Principles

Public APIs MUST prioritize simplicity, consistency, explicit behavior, and maintainability.

Public interfaces SHOULD expose only the functionality required to fulfill documented use cases. Unnecessary abstractions, redundant entry points, speculative features, and implementation-specific details SHOULD NOT be exposed.

The following principles apply:

- Public functions MUST have clearly defined responsibilities.
- Related functions MUST follow consistent naming and parameter conventions.
- Public types MUST have explicit purposes and documented semantics.
- Function parameters MUST have unambiguous meanings.
- Return values MUST have consistent and documented interpretations.
- Ownership and lifetime requirements MUST be explicit.
- Error reporting MUST follow the project's established status policy.
- Public interfaces SHOULD allow reasonable future implementation changes without unnecessary ABI disruption.
- Features SHOULD NOT be added to the public API solely because they might be useful in the future.
- Public APIs SHOULD avoid exposing internal data structures when opaque types can provide the required functionality.
- Public interfaces MUST NOT expose implementation details that consumers do not need.
- Redundant functions MUST NOT be introduced without a meaningful compatibility, usability, or architectural justification.

API extensibility MUST NOT be achieved by weakening contracts or introducing ambiguous behavior.

When a design choice affects ABI stability, ownership, platform portability, or long-term compatibility, these consequences MUST be evaluated before the interface is approved.

Consistency with existing public APIs SHOULD be preferred unless the existing design is demonstrably unsuitable.

• • •

## 11.3. API Contracts

Every public function MUST have a complete normative contract documented in a separate Markdown file within the project's documentation hierarchy.

The canonical contract MUST reside in the appropriate documentation location. The default location for development-related documentation is `docs/development/`, although a more specific documentation hierarchy MAY be used when appropriate.

The following rules apply:

- Every public function MUST have a documented contract.
- The contract MUST define the function's purpose and observable behavior.
- All parameters MUST have documented meanings and requirements.
- Preconditions MUST be specified when they affect valid use.
- Postconditions MUST describe the guaranteed results.
- Return values and status codes MUST be documented.
- Error conditions and failure behavior MUST be documented.
- Pointer validity, ownership, lifetime, and release responsibilities MUST be documented.
- Buffer capacities, lengths, and relationships between parameters MUST be documented where applicable.
- Thread-safety and concurrency guarantees MUST be documented when relevant.
- Platform restrictions and ABI assumptions MUST be documented when applicable.
- The contract MUST distinguish guaranteed behavior from unspecified or implementation-dependent behavior.
- Any requirement to initialize, preserve, or release an object MUST be stated explicitly.

Doxygen-style comments or equivalent source comments SHOULD be used to make public declarations easier to understand. Such comments MUST NOT replace the separate normative Markdown contract.

The canonical contract SHOULD be maintained in one authoritative location. Independent copies of the same normative requirements MUST be avoided because they can become inconsistent.

Changes to public behavior MUST be reflected in the corresponding contract. A public declaration MUST NOT silently acquire new preconditions, lose previously guaranteed behavior, or change its error semantics without compatibility review.

• • •

## 11.4. Symbol Visibility

Symbols MUST be hidden by default wherever the supported toolchain and target platform provide an appropriate mechanism.

Only symbols that belong to the explicitly approved public API SHOULD be exported from a library.

The following rules apply:

- Publicly supported external symbols MUST be exported intentionally.
- Internal implementation symbols MUST NOT be exported unnecessarily.
- Private functions SHOULD use internal linkage when they are needed only within one translation unit.
- Library builds SHOULD use hidden-by-default visibility where supported.
- Export lists, visibility annotations, or equivalent platform mechanisms SHOULD be used to control the exported symbol set.
- Public symbol exports MUST be reviewed as part of API and ABI changes.
- Accidental symbol exports MUST be treated as interface defects.
- Exporting a symbol MUST NOT be interpreted as automatic approval to make it a supported public API.
- The public symbol set MUST remain consistent with the documented public interface.

C11 does not define a universal symbol-visibility mechanism. Visibility controls MAY therefore use platform-specific build settings or toolchain facilities. Such mechanisms MUST remain within the project's approved build configuration and MUST NOT introduce prohibited compiler language extensions into source code.

A project's public API inventory SHOULD be verifiable from the resulting library artifacts.

• • •

## 11.5. External Linkage

External linkage MUST be used according to the requirements of the interface and the project's modular architecture.

Public and internal header declarations MUST determine which interfaces are intentionally made available to other translation units. External linkage alone MUST NOT be treated as proof that a symbol is part of the supported public API.

The following rules apply:

- Public functions MUST have linkage appropriate to their intended use.
- Internal functions SHOULD use `static` when they are needed only within one source file.
- Internal functions MAY have external linkage when required for cooperation between implementation components.
- External linkage MUST NOT be introduced merely to avoid declaring a function `static`.
- Private symbols with external linkage MUST remain private at the library-export level.
- Public functions MUST be declared in their appropriate public headers.
- Internal functions intended for cross-component use SHOULD be declared in appropriate internal headers.
- Functions MUST NOT be exposed through public headers solely because another implementation file requires access to them.

The distinction between linkage and visibility MUST remain explicit.

Linkage determines how an identifier refers to an entity across translation units. Symbol visibility and library export controls determine whether a symbol is exposed to external consumers. Neither property alone defines the complete public API contract.

• • •

## 11.6. Opaque Types

Opaque types SHOULD be preferred when they provide meaningful ABI stability, implementation hiding, ownership control, or representation independence.

An opaque type exposes a type declaration without exposing the complete structure of its representation to consumers.

For example:

```c
struct app_session;

struct app_session *app_session_create(void);
int app_session_close(struct app_session *session);
void app_session_destroy(struct app_session *session);
```

This example illustrates an opaque type declaration; the actual public interface MUST follow the project's naming and ownership rules.

Opaque types are particularly appropriate when:

- The internal representation may change between compatible releases.
- The implementation requires control over object initialization and destruction.
- Direct field access would expose unnecessary implementation details.
- The object maintains internal invariants.
- The object manages resources whose lifetime must be controlled.
- ABI stability would otherwise be difficult to preserve.

The following rules apply:

- Public opaque types MUST have documented construction and destruction requirements.
- Ownership of pointers to opaque objects MUST be explicit.
- Functions MUST define whether they accept null pointers.
- The validity period of an opaque object MUST be documented.
- Functions MUST NOT access an object after its lifetime has ended.
- Public interfaces MUST NOT require consumers to know the internal size or field layout of an opaque object.
- Opaque types MUST NOT be introduced where their indirection or restricted access provides no meaningful benefit and conflicts with a justified public data-access requirement.

Opaque types do not automatically make an ABI stable. Function signatures, calling conventions, exported symbols, and other public types must also remain compatible.

• • •

## 11.7. Public Structure Layout

Public structure layout MUST be treated as ABI-sensitive.

Public structures MAY expose fields when direct access or caller-managed storage is a deliberate part of the interface. However, exposing a structure's complete definition creates a compatibility commitment concerning its layout and usage.

The following rules apply:

- Public structures MUST have documented field meanings and valid usage.
- Public structure field order MUST NOT be changed in a compatible ABI release unless compatibility is demonstrated for every affected supported target.
- Fields MUST NOT be added, removed, or reordered on the assumption that the change is automatically backward-compatible.
- Changes to field types, qualifiers, alignment requirements, or nested types MUST undergo ABI review.
- Public structures MUST NOT depend on unspecified padding or undocumented compiler layout behavior.
- Public structures SHOULD NOT expose fields that consumers do not need to access.
- Structures expected to evolve substantially SHOULD use an opaque representation where practical.
- Public structure initialization requirements MUST be documented.
- Consumers MUST NOT be required to initialize undocumented padding bytes.
- Public structure changes MUST be assessed for source compatibility as well as binary compatibility.

Adding a field to a public structure is not inherently ABI-compatible. It may change the structure's size, alignment, calling convention, allocation requirements, or interpretation by previously compiled consumers.

A structure change MAY be accepted in a compatible release only when its compatibility has been demonstrated for the supported ABI targets and when the documented usage patterns remain valid. Such a change MUST NOT invalidate the ABI stability requirements in Section 11.8.

Where extensibility is required, an explicitly versioned structure or another carefully designed extension mechanism MAY be used. Such a mechanism MUST be designed before it is needed and MUST have documented initialization and compatibility rules.

• • •

## 11.8. ABI Stability

ABI stability MUST be maintained across compatible releases for all explicitly supported ABI targets.

An ABI-breaking change MUST require a major version change and a documented migration plan.

The ABI stability commitment applies to the public binary interface, including relevant aspects of:

- Exported symbol names and availability.
- Function signatures and calling conventions.
- Public structure sizes, layouts, and alignment requirements.
- Public type representations.
- Ownership and lifetime behavior where it affects binary consumers.
- Error reporting conventions.
- Library initialization and destruction requirements.
- Other externally observable binary contracts.

The following rules apply:

- ABI-breaking changes MUST NOT be introduced silently into a compatible release.
- ABI changes MUST undergo explicit review.
- Supported ABI targets MUST be documented.
- ABI compatibility MUST be tested on the supported target matrix.
- Public symbols MUST NOT be removed or incompatibly changed in a compatible release.
- Public type representations MUST NOT be changed incompatibly in a compatible release.
- ABI compatibility MUST NOT be assumed merely because source code compiles successfully.
- ABI compatibility MUST NOT be assumed merely because the same C language standard is used.
- ABI guarantees MUST NOT be extended to untested architectures, compiler configurations, or operating systems.
- Any exception to the stability policy MUST be explicitly authorized and accompanied by the required major-version change and migration plan.

ABI stability does not require every platform to share an identical binary representation. It requires the supported ABI contract to remain compatible within each explicitly supported target and compatibility boundary.

A new major version MAY introduce an incompatible ABI when the change is justified. Its release documentation MUST identify the breaking changes and provide migration guidance.

• • •

## 11.9. Structure Padding and Alignment

Public ABI design MUST NOT depend on undocumented structure padding or alignment assumptions.

C11 implementations determine structure layout according to the language rules and implementation requirements. The exact offsets, padding, and alignment of structure members are not universally identical across all conforming implementations.

The following rules apply:

- Natural alignment SHOULD be preferred.
- Public interfaces MUST NOT assume that a structure has no padding.
- Public interfaces MUST NOT assume that padding bytes have a particular value.
- Padding bytes MUST NOT be used to store application state.
- Structure layout MUST NOT be inferred solely from the order or declared types of its members.
- `_Alignas` and `_Alignof` MAY be used where justified by a documented requirement and supported by the relevant C11 implementation.
- Explicit alignment requirements MUST be evaluated against the supported ABI targets.
- Manual padding fields MUST NOT be treated as a universal guarantee of structure size or alignment.
- Public structures MUST NOT rely on arbitrary alignment assumptions that are absent from the documented ABI contract.
- Alignment-sensitive changes MUST undergo ABI review.

Where a binary protocol, file format, or external hardware representation requires an exact layout, that representation MUST be handled through a deliberately specified format rather than assumptions about ordinary C structures.

Packing pragmas and other compiler-specific layout controls MUST NOT be used to create a supposedly portable ABI. Any approved platform-specific mechanism MUST be isolated, documented, and limited to the relevant target.

• • •

## 11.10. Enum and Bit-Field Representation

Public ABI design MUST NOT assume that enum types and bit-fields have a universally fixed binary representation.

C11 does not guarantee one common enum representation or bit-field layout across all implementations. Bit-field allocation, storage, and layout may depend on implementation-defined rules.

The following rules apply:

- Public ABI representations SHOULD use explicitly selected fixed-width integer types where an exact width is required.
- Public bit flags SHOULD use integer fields and explicitly defined masks and shifts.
- Public ABI contracts MUST NOT depend on undocumented bit-field allocation order.
- Public ABI contracts MUST NOT assume a particular enum size unless the supported ABI explicitly guarantees it.
- Public interfaces MUST NOT use bit-fields to represent externally specified binary layouts without a separately verified, target-specific contract.
- Internal enums MAY be used when their representation does not escape the implementation or affect the public ABI.
- Internal bit-fields MAY be used when justified by memory or representation requirements and when their implementation-dependent behavior is acceptable.
- Enum values and bit-mask values MUST be documented when they are part of the public interface.
- Public changes to enumerator values or externally defined flag bits MUST undergo compatibility review.

When a public API requires named symbolic values, an enum MAY be used as a source-level convenience only when its ABI implications are controlled. Where exact binary representation is required, an explicitly sized integer field SHOULD be used instead.

Fixed-width integer types do not eliminate every ABI concern. Their availability, alignment, calling convention implications, and use in public structures MUST still be assessed for supported targets.

• • •

## 11.11. Shared and Static Libraries

Projects MAY provide both shared and static libraries. Both library forms MUST implement the same documented public API contract unless a deliberate, documented distinction is required.

The following rules apply:

- Shared and static libraries MUST expose consistent public declarations.
- Differences in supported features MUST be documented.
- Public API behavior MUST NOT depend on whether the implementation was linked statically or dynamically unless the distinction is explicitly part of the contract.
- Shared libraries MUST control their exported symbol sets according to Section 11.4.
- Static libraries MUST NOT require consumers to depend on undocumented internal interfaces.
- Build and installation instructions MUST identify the intended public headers and library artifacts.
- ABI compatibility MUST be assessed for shared-library consumers.
- Link-time and runtime dependencies MUST be documented where they affect integration.
- Library initialization and destruction requirements MUST be explicit.
- Tests SHOULD verify that the supported library forms implement the expected public behavior.

Providing both library forms does not guarantee that objects, handles, or allocated memory can safely cross independently built library boundaries. Such behavior MUST be explicitly supported by the API contract.

Where allocation and deallocation occur in different binary components, the interface MUST define which component owns the allocation and which function is responsible for releasing it.

Static linking does not remove the need for API compatibility or clear ownership rules. It changes how implementation code is incorporated into the final executable, not the requirements for a coherent public interface.

• • •

## 11.12. API and ABI Compatibility

Source/API compatibility and ABI compatibility MUST be evaluated separately.

Source/API compatibility concerns whether existing consumer source code continues to compile and behave according to the documented contract after an update.

ABI compatibility concerns whether previously compiled consumers can continue to interact correctly with the updated library without requiring recompilation, within the supported ABI scope.

The following rules apply:

- Compatibility reviews MUST identify source-level changes.
- Compatibility reviews MUST identify binary-level changes.
- Public function signatures MUST NOT be changed incompatibly in a compatible release.
- Public symbol names and availability MUST remain compatible in a compatible release.
- Public type changes MUST be evaluated for both source and binary effects.
- Changes to documented behavior MUST be assessed even when the binary signatures remain unchanged.
- A source-compatible change MUST NOT automatically be considered ABI-compatible.
- A binary-compatible change MUST NOT automatically be considered source-compatible.
- Compatibility claims MUST specify the release boundary and supported targets to which they apply.
- Tests and review procedures SHOULD be used to detect unintended incompatibilities.

Examples of changes that can break source compatibility include removing a declaration, renaming a public function, changing a parameter type, or introducing a conflicting declaration.

Examples of changes that can break ABI compatibility include removing an exported symbol, changing a calling convention, altering a public structure layout, or changing the representation of a public type.

Behavioral compatibility is also relevant. A function whose signature remains unchanged may still violate compatibility expectations if its error behavior, ownership requirements, or documented guarantees change.

Compatibility MUST be judged against the actual public contract, not merely against whether a particular test program compiles.

• • •

## 11.13. Versioning and Backward Compatibility

The project MUST use a documented versioning policy that identifies incompatible public API and ABI changes.

Under the project's compatibility policy, ABI-breaking changes MUST require a major version change and a migration plan.

Semantic versioning SHOULD be used for public library releases when appropriate to the project's release model. If semantic versioning is adopted, the project MUST document how API and ABI compatibility determine major, minor, and patch increments.

The following rules apply:

- Major versions MUST identify releases that introduce approved incompatible API or ABI changes.
- Minor versions SHOULD add functionality without breaking the established public API and ABI contracts.
- Patch versions SHOULD contain fixes that preserve the established compatibility guarantees.
- Release notes MUST identify public API and ABI changes.
- ABI-breaking releases MUST include a migration plan.
- Removed or replaced public interfaces SHOULD have a documented migration path.
- Deprecation SHOULD precede removal when practical.
- Deprecation notices MUST identify the affected interface and its recommended replacement when one exists.
- Compatibility exceptions MUST be documented rather than implied.
- Version numbers MUST NOT be used to excuse undocumented breaking changes.

A major version increment alone does not make a breaking change acceptable. The change MUST still be justified, documented, reviewed, and accompanied by migration guidance.

The implementation MUST NOT assume that all consumers upgrade simultaneously. Where multiple library versions may coexist, symbol naming, library naming, and packaging rules SHOULD be designed to avoid unintended conflicts.

The project's versioning policy MUST distinguish public release versions from any platform-specific shared-library ABI versioning mechanism.

• • •

## 11.14. Foreign Function Interfaces

Foreign function interfaces (FFIs) MAY be provided when interoperability with other programming languages or runtimes is a supported project requirement.

FFI boundaries MUST be explicit, documented, and designed around a stable binary contract.

The following rules apply:

- FFI functions MUST use calling conventions supported by the target ABI.
- FFI-visible types MUST have explicitly documented representations.
- C-only implementation details MUST NOT be exposed as if they were portable cross-language types.
- Pointer ownership and lifetime MUST be documented.
- Allocation and deallocation responsibilities MUST be explicit.
- Error reporting MUST have a defined representation suitable for the target interface.
- Callback signatures and callback lifetimes MUST be documented.
- Foreign runtimes MUST NOT retain pointers beyond their documented validity period.
- String encoding, termination, and length conventions MUST be explicit.
- Structure layout MUST be specified and verified when structures cross the boundary.
- Resource cleanup MUST be defined for both successful and failed operations.
- Exceptions or language-specific error mechanisms MUST NOT cross a C ABI boundary unless the relevant interoperability contract explicitly defines and safely supports that behavior.

Where a foreign language uses a different type system or memory-management model, the FFI MUST provide an explicit mapping rather than relying on implicit assumptions.

C linkage or an equivalent platform-specific mechanism MAY be required when interfacing with other languages. Such mechanisms MUST be documented and isolated to the relevant interoperability layer.

The FFI MUST NOT expose private internal symbols merely to simplify integration.

• • •

## 11.15. Platform API Isolation

Platform-specific APIs MUST be isolated from portable public interfaces.

The project MAY use approved platform APIs, including POSIX APIs, where required by its supported platform policy. Platform API use is distinct from the use of non-standard compiler language extensions.

The following rules apply:

- Platform-specific dependencies SHOULD be confined to designated implementation modules or platform abstraction layers.
- Portable public headers MUST NOT expose platform-specific types unnecessarily.
- Platform-specific handles MUST NOT leak into portable public APIs without an explicit architectural justification.
- Platform-dependent behavior MUST be documented when it is observable by consumers.
- Platform selection and feature detection MUST follow the project's preprocessor and portability policies.
- Platform-specific code MUST NOT silently change the meaning of a portable public contract.
- Platform abstractions MUST define consistent behavior across supported implementations.
- Platform-specific exceptions MUST be isolated and documented.
- Platform APIs MUST NOT be confused with compiler language extensions.
- The use of a platform API MUST NOT be taken as permission to use prohibited compiler-specific language features.

Where platform-specific behavior cannot be represented portably, the project MUST either define an explicit platform-specific interface or provide a documented abstraction with clearly stated limitations.

Public headers SHOULD avoid requiring consumers to include operating-system headers unless the dependency is an intentional part of the public interface.

Platform API isolation MUST preserve the project's target portability goals without pretending that operating systems provide identical capabilities.

• • •

## 11.16. Public Header Stability

Public headers MUST be treated as stable, versioned interface artifacts.

Changes to public headers MUST undergo review for source compatibility, ABI compatibility, ownership semantics, and consistency with the normative API contracts.

The following rules apply:

- Public headers MUST NOT be changed casually to accommodate private implementation details.
- Public declarations MUST remain consistent with their documented contracts.
- New public declarations MUST be reviewed for naming, type safety, ownership, portability, and ABI consequences.
- Existing public declarations MUST NOT be removed or changed incompatibly in a compatible release.
- Public macro changes MUST be reviewed for their effects on consumer source code.
- Public type changes MUST be reviewed for layout, representation, and initialization consequences.
- Header dependencies MUST remain deliberate and documented where necessary.
- Public headers MUST NOT depend on undocumented internal headers.
- Public header changes MUST be accompanied by appropriate documentation updates.
- Compatibility-sensitive changes SHOULD be covered by compile-time and ABI regression tests.
- The exported symbols and declarations MUST remain consistent with the project's documented public API inventory.

A change may break source compatibility even if it does not change a library's binary symbols. For example, a new macro, conflicting declaration, or altered type definition can change how consumer code is compiled.

Public header review MUST therefore assess both the header's textual interface and the binary consequences of the declarations it exposes.

• • •

## 11.17. Public Function Naming

Public function names MUST follow the project's naming conventions defined in Section 4.

Public functions MUST use the project-specific naming pattern:

`app_module_functionality`

The literal `app` represents the project's chosen prefix and MUST be replaced by the actual project prefix in real declarations. The pattern is illustrative, not a requirement to use the identifier `app` in every project.

The following rules apply:

- Public function names MUST be descriptive and consistent.
- Public functions MUST use the established lowercase `snake_case` naming convention.
- Public function names MUST include the required project prefix.
- Module names MUST be consistent with the project's module naming policy.
- Function names MUST describe their purpose rather than their private implementation.
- Names MUST NOT conflict with reserved identifiers or standard-library names.
- Abbreviations SHOULD be avoided unless they are established project terminology.
- Public function names MUST remain stable across compatible releases.
- Renaming a public function MUST be treated as a compatibility-sensitive change.
- Deprecated names MAY remain available during a migration period when necessary to preserve compatibility.

Public names SHOULD describe observable behavior and MUST NOT imply guarantees that the function does not provide.

Naming consistency MUST be evaluated across the complete public API, not only within individual modules.

• • •

## 11.18. Ownership and Lifetime in Public APIs

Every public API that accepts, returns, stores, or otherwise exposes a pointer MUST define the relevant ownership and lifetime requirements.

Ownership and lifetime are normative parts of the public contract. They MUST NOT be treated as optional implementation documentation.

The following rules apply:

- The ownership status of returned pointers MUST be documented.
- The ownership status of input pointers MUST be documented when it affects the caller's obligations.
- Functions MUST specify whether they borrow, retain, transfer, or release ownership of an object.
- The required lifetime of borrowed objects MUST be documented.
- The conditions under which an object becomes invalid MUST be documented.
- Functions that allocate resources MUST define how those resources are released.
- The correct destruction function MUST be identified when an object requires explicit destruction.
- The API MUST specify whether ownership transfer occurs on success, failure, or both.
- The API MUST define the behavior of output pointers on failure where applicable.
- The API MUST document whether an object may be shared between callers or threads when relevant.
- Callers MUST NOT be required to guess whether a returned pointer is borrowed or owned.
- APIs MUST NOT require consumers to free memory using an allocator incompatible with the allocator that created it.

Where ownership is transferred to the caller, the contract MUST identify the caller's responsibilities. Where ownership remains with the library, the contract MUST define the validity period and permitted use of the borrowed object.

For APIs that manage opaque objects, creation and destruction operations SHOULD provide an explicit, consistent lifecycle.

When memory is allocated by a library, the library SHOULD provide an appropriate release function unless the contract explicitly guarantees a compatible deallocation mechanism.

Ownership documentation MUST address failure paths as well as successful operations. A failed function call MUST NOT leave ownership ambiguous.

• • •

## 11.19. Error Reporting in Public APIs

Public functions MUST follow the project's established status policy.

Functions that return status MUST use `int` as the return type. A return value of `0` indicates success. Negative values MUST correspond to defined error or status codes according to the project's `status.h` policy.

Functions that do not need to report a status MAY return `void`, provided that their contracts do not require status reporting.

The following rules apply:

- Public status-returning functions MUST document their success and failure values.
- Negative status codes MUST have defined meanings.
- Functions MUST NOT invent undocumented interpretations for existing status codes.
- Successful execution MUST be distinguishable from failure.
- Query operations MAY use dedicated status values for meaningful non-error outcomes, such as the absence of an optional item, when the status policy defines that behavior.
- A meaningful absence or negative query result MUST NOT automatically be treated as an operational failure.
- Output parameters MUST be documented, including their validity after failure.
- Functions MUST specify whether output values remain unchanged, are reset, or may contain partial results on failure.
- Functions MUST NOT rely exclusively on logging or hidden global state to communicate errors that callers need to handle.
- Status codes MUST NOT be silently discarded when the contract requires the caller to handle them.
- Public APIs MUST NOT use inconsistent return conventions without a documented and justified exception.

Public functions that return `void` MUST NOT be used where the caller requires an error result unless the contract provides another explicit and reliable error-reporting mechanism.

The error policy MUST distinguish operational failures, invalid inputs, absent results, and other documented status conditions where those distinctions matter.

The meaning of every status code MUST be stable across compatible releases. Changing a status code's meaning MUST undergo compatibility review.

• • •

## 11.20. Reserved Names and Symbol Prefixes

Identifiers MUST comply with the reserved-identifier rules of ISO C11.

Public symbols MUST use the project's required prefix. The prefix MUST be sufficiently distinctive to reduce collisions with standard-library identifiers and identifiers belonging to other libraries.

The following rules apply:

- Identifiers reserved by the C implementation MUST NOT be defined or repurposed by project code.
- Identifiers beginning with an underscore followed by an uppercase letter or another underscore MUST NOT be used for ordinary project identifiers.
- File-scope identifiers beginning with an underscore MUST be avoided because C reserves additional underscore-prefixed identifier forms at file scope.
- Standard-library names MUST NOT be repurposed for unrelated project functionality.
- Public function names MUST follow Section 11.17.
- Public types, macros, enumerators, and other externally visible names SHOULD use the project prefix or an established project-specific namespace pattern.
- Generic public macro names MUST be avoided.
- Internal identifiers MUST also respect the applicable C11 reserved-name rules.
- Symbol naming MUST remain consistent across public headers and exported libraries.

Reserved-name compliance applies to macros and typedef names as well as functions and objects.

A project prefix reduces the risk of collisions but does not authorize the use of identifiers reserved by the C standard or implementation.

Compiler-provided predefined identifiers and macros MUST be governed by the project's preprocessor policy. Project-defined macros MUST follow the established project naming convention.

• • •

## 11.21. ABI-Sensitive Types

Types exposed through a public ABI MUST be selected and designed with explicit attention to their representation and platform dependencies.

The following rules apply:

- Public interfaces SHOULD prefer standard C types whose properties satisfy the documented contract.
- Fixed-width integer types from `<stdint.h>` SHOULD be used when an exact integer width is required and the relevant type is available on the supported target.
- `size_t` SHOULD be used for object sizes and memory-size-related quantities where appropriate.
- Pointer-sized or platform-specific integer types MUST NOT be substituted for fixed-width protocol fields without a documented reason.
- Public interfaces MUST NOT assume that `int`, `long`, or pointer types have identical sizes across all supported targets.
- Public structures MUST NOT depend on undocumented enum or bit-field representation.
- Public interfaces SHOULD avoid exposing platform-specific handles and types.
- Floating-point representation assumptions MUST be documented when binary interchange depends on them.
- Public type changes MUST undergo ABI compatibility review.
- Types crossing an FFI boundary MUST have an explicitly documented mapping to the foreign interface's type system.

The use of a standard C type does not automatically make every representation portable across every ABI. The size, alignment, calling convention, and representation requirements relevant to the contract MUST be evaluated.

Where a public interface requires an exact binary representation, the contract MUST define that representation explicitly. Implementation-defined or platform-specific representations MUST NOT be treated as universal guarantees.

• • •

## 11.22. Compatibility Across Compiler Versions

Compatibility guarantees MUST be defined for an explicit set of supported compiler versions and ABI targets.

GCC and Clang MAY both be used to build the project, but support for both compilers does not automatically guarantee that their generated binaries are mutually ABI-compatible under every configuration.

The following rules apply:

- Supported compiler versions SHOULD be documented.
- ABI compatibility MUST be tested for the supported compiler and target combinations.
- Compatibility MUST NOT be claimed for untested combinations.
- Public interfaces MUST NOT depend on undocumented compiler-specific behavior.
- Compiler-specific language extensions MUST remain prohibited under the project's language policy.
- Standard C11 behavior MUST be preferred over implementation-specific alternatives.
- Compiler version changes MUST trigger appropriate compatibility and regression testing.
- Changes in compiler defaults or ABI-affecting options MUST be reviewed.
- Build configurations that affect public type layout, calling conventions, or symbol visibility MUST be controlled.
- The supported compiler matrix MUST be reviewed when adding a new architecture or platform.
- Compiler-specific predefined macros MUST NOT be used in violation of the project's preprocessor policy.
- Compiler diagnostics and strict language-mode options SHOULD be used to detect non-portable constructs.

The project MUST distinguish between source portability and binary compatibility. Two compilers may accept the same conforming C11 source while producing binaries with different ABI properties for a particular target or configuration.

ABI compatibility MUST therefore be established through the supported ABI contract and appropriate verification, not inferred from compiler names or C standard conformance alone.

When a compiler upgrade changes an ABI property within a supported target, the project MUST determine whether the change violates the existing compatibility commitment before releasing the updated library.

___

# 12.0. Error Handling

Error handling defines how functions report failures, propagate error information, preserve program invariants, and manage resources when operations cannot complete successfully.

This section establishes a consistent error-handling policy for C11 code. Error handling MUST follow the project's centralized status-code definitions, function contracts, resource-ownership rules, and cleanup conventions.

The primary objectives are:

- Make failures explicit and predictable.
- Preserve sufficient information to identify and diagnose failures.
- Maintain valid program and resource states after unsuccessful operations.
- Prevent resource leaks, silent failures, and false success reports.
- Separate error detection, error reporting, logging, and recovery responsibilities.
- Keep error handling consistent across modules and platform-specific implementations.

Error handling MUST NOT depend on compiler-specific language extensions, undefined behavior, or optional C11 facilities that implementations are not required to provide.

---

## 12.1. Error Categories

Errors SHOULD be classified according to their cause and the appropriate recovery strategy.

The following categories MUST be distinguished where applicable:

- **Programming errors:** Violations of documented function contracts, invalid internal assumptions, or broken invariants.
- **Input and validation errors:** Invalid, malformed, incomplete, or unsupported input received from an external or otherwise untrusted source.
- **Resource errors:** Failures to acquire or use resources, including memory allocation failures and resource exhaustion.
- **System errors:** Failures reported by the operating system, runtime environment, or an external service.
- **State errors:** Operations that cannot be completed because the current object, application, or resource state does not permit them.

These categories describe the nature of a failure and do not require a separate numeric status code for every category.

A single category MAY contain multiple specific error codes. Error codes MUST be defined in accordance with Section 12.5.

When a failure belongs to multiple categories, the implementation SHOULD report the most useful specific status while preserving additional diagnostic information when necessary.

Error classification MUST support meaningful handling rather than merely adding complexity to the status-code system.

• • •

## 12.2. Programming Errors and Runtime Errors

Programming errors and runtime errors MUST be treated as distinct concepts.

Programming errors arise from violations of the implementation's or caller's contractual obligations. Examples include passing an invalid pointer where a valid pointer is required, violating a documented ownership requirement, or invoking an operation in a prohibited state.

Runtime errors arise during otherwise valid operations and MUST be reported when they prevent the requested operation from completing. Examples include allocation failure, file access failure, and an unavailable external resource.

A documented precondition does not eliminate the need to validate untrusted external input. Data received from files, network connections, user input, external processes, or other trust boundaries MUST be validated before it is relied upon.

Internal functions MAY rely on established contracts when their callers are responsible for satisfying those contracts. Implementations SHOULD avoid redundant checks that do not provide meaningful additional safety.

Runtime errors MUST NOT be disguised as programming errors merely because the implementation did not anticipate them.

• • •

## 12.3. Preconditions and Invariants

Function preconditions MUST be documented in the applicable function contract.

Implementations MUST preserve their required invariants and MUST check conditions at appropriate boundaries where doing so is necessary for correctness or safety.

A function MAY rely on preconditions established by its caller when the contract explicitly assigns that responsibility to the caller. However, an implementation MUST NOT rely on invalid assumptions about untrusted data, external resources, or conditions that can legitimately change during execution.

Invariant checks SHOULD be placed where they provide meaningful protection or diagnostic value. The same invariant does not need to be checked repeatedly at every function call when its validity is already guaranteed by the surrounding design.

If an invariant is violated, the implementation MUST follow the applicable programming-error policy. It MUST NOT silently continue when doing so could corrupt state, violate ownership rules, or cause undefined behavior.

Assertions MAY be used for appropriate internal invariants, subject to Section 12.11.

• • •

## 12.4. Return-Value-Based Error Reporting

Functions MUST use explicit return-value-based error reporting when their contracts require status reporting.

In accordance with the project's function-return policy:

- Functions returning `int` MUST use the centralized status convention defined by `status.h`.
- A return value of `0` MUST indicate success.
- Negative return values MUST represent defined error or status codes.
- Output parameters MUST be used to return result data when a status code is also required.
- Functions returning `void` MAY be used when no status result is necessary or when the interface defines another explicit reporting mechanism.

Functions MUST NOT return undocumented negative values or use arbitrary positive values as errors.

A function MUST NOT report success when the requested operation failed.

The status return value and output parameters MUST have a documented relationship. Unless the function contract explicitly states otherwise, callers MUST NOT assume that output data is valid after a failed operation.

Functions MUST NOT use global variables as a general substitute for explicit error return values.

• • •

## 12.5. Error Codes and Enumerations

Project-wide status and error codes MUST be centralized in `status.h` or in the project's explicitly designated status-definition headers.

Error codes MUST have stable, documented meanings within their applicable interface.

The following rules apply:

- `0` MUST represent success.
- Negative values MUST represent defined errors or status outcomes.
- Each error code MUST have a documented meaning.
- Error codes MUST NOT be reused for unrelated meanings within the same applicable status domain.
- Callers MUST NOT depend on undocumented numeric values.
- Functions MUST return the status corresponding to the failure they report.

The project MAY define dedicated status codes for expected outcomes such as a missing entry, an unavailable optional resource, or an operation that cannot currently be performed. Such outcomes MUST be distinguished from operational failures when callers need to handle them differently.

C enumerations MAY be used to organize status definitions internally. However, public binary interfaces MUST NOT assume that an enumeration has a particular size or representation.

Where a status value crosses an ABI boundary, its representation MUST be explicitly defined and compatible with the applicable ABI contract.

Status codes MUST NOT replace diagnostic information when additional context is necessary. Implementations MAY preserve relevant operating-system codes, resource identifiers, or other diagnostic data through an explicitly documented mechanism.

• • •

## 12.6. Errno Usage

The C library's `errno` mechanism MUST NOT be used as the project's general public error-reporting interface.

Direct interaction with `errno` MUST be isolated in the designated platform or system-integration layer.

When a platform operation reports failure through `errno`, the implementation MUST:

1. Determine whether the operation failed according to that operation's documented contract.
2. Read `errno` immediately when required, before another operation can overwrite its value.
3. Translate the system-specific error into the appropriate project status code.
4. Preserve the original error information when necessary for diagnostics or recovery.

The implementation MUST NOT assume that `errno` is meaningful after a successful operation unless the relevant API explicitly defines such behavior.

Application-facing code SHOULD use project status codes rather than interpreting platform-specific `errno` values directly.

Platform-specific error translation MUST NOT silently discard distinctions that are necessary for correct recovery.

The use of `errno` MUST remain compatible with the project's portability requirements and platform API isolation rules.

• • •

## 12.7. Partial Failure

A function MUST define the state of its outputs and relevant side effects when an operation fails after partially completing its work.

Whenever practical, an operation SHOULD leave the program in a consistent state after failure.

If an operation can provide all-or-nothing behavior without unreasonable cost or complexity, the implementation SHOULD preserve that behavior.

However, implementations MUST NOT promise complete rollback when the operation affects external state that cannot reliably be restored. Examples include data already transmitted to another process, bytes already written to an external device, or irreversible operations performed by a remote service.

When rollback is impossible or incomplete:

- The function contract MUST describe relevant partial effects.
- The function MUST report failure accurately.
- The implementation MUST preserve all invariants that its contract requires.
- Output parameters MUST have a defined state after failure.
- The caller MUST be able to determine what recovery actions remain necessary.

Partially completed operations MUST NOT be reported as fully successful unless the function's contract explicitly defines partial completion as a successful outcome.

• • •

## 12.8. Error Propagation

Errors MUST be propagated explicitly to the layer responsible for handling or translating them.

A function SHOULD handle an error locally only when it can perform a meaningful recovery, complete an explicitly permitted fallback, or provide a more appropriate result under its contract.

Otherwise, the function MUST propagate the failure to its caller.

Each layer MUST preserve the essential meaning of the original failure. Translating an error into another status code is permitted when the receiving layer has a meaningful abstraction to maintain, but arbitrary translation MUST NOT destroy useful error distinctions.

Implementations MUST NOT silently discard failures.

Errors MUST NOT be logged and then treated as successful merely because a diagnostic message was produced.

When an error is propagated, any acquired resources MUST be handled according to Sections 12.9 and 12.19.

The final decision to retry, recover, abandon an operation, or terminate the application MUST be made by the layer responsible for that decision.

• • •

## 12.9. Cleanup on Failure

Failure paths MUST follow the cleanup conventions defined in Sections 7 and 9.

Functions that manage dynamically allocated memory MUST provide the required `cleanup` label and MUST use it to release or transfer ownership of resources as appropriate.

Functions that manage other resources SHOULD provide a `cleanup` label when it improves the clarity or correctness of resource management.

The `end` label MUST be used according to the established early-exit convention. Functions using early exits MUST NOT bypass their required final return structure.

The following rules apply:

- Resources that have been acquired and remain owned by the function MUST be released before the function returns, unless ownership is explicitly transferred.
- Resources MUST be released in reverse acquisition order when required by their dependencies.
- A cleanup operation MUST NOT release a resource that was never acquired.
- Cleanup paths MUST NOT assume that partially initialized resources are fully initialized.
- A failure MUST NOT cause a resource to be released twice.
- Cleanup MUST NOT overwrite the original failure status unless the contract explicitly defines how cleanup failures affect the result.

A failure occurring before any resource is acquired MAY jump directly to `end` when no cleanup is necessary.

A failure occurring after resource acquisition MUST follow the appropriate cleanup path.

Functions MUST NOT add unnecessary cleanup operations solely to make every failure path follow an identical sequence. Cleanup structure SHOULD reflect actual resource ownership and acquisition state.

If cleanup itself can fail, the implementation MUST follow a defined policy for preserving the original error and handling the cleanup failure.

• • •

## 12.10. Error Messages and Logging

Functions MUST report errors through their defined status interfaces. Logging MUST remain a separate responsibility unless the function's contract explicitly assigns logging to that function.

Libraries MUST NOT automatically log every error merely because an operation failed.

Logging SHOULD be performed by the application or the layer responsible for interpreting the failure and deciding whether it requires a diagnostic message.

This separation prevents duplicated messages, unwanted output, and interference with applications that use their own logging facilities.

When logging is appropriate:

- Messages SHOULD describe the failed operation and relevant context.
- Messages SHOULD provide enough information to support diagnosis.
- Sensitive data MUST NOT be exposed unnecessarily.
- Repeated propagation of the same failure SHOULD NOT produce redundant messages at every layer.
- Logging failures MUST NOT conceal the original operation's failure.
- Diagnostic messages MUST NOT be treated as substitutes for status codes.

The project MAY define a dedicated logging interface. If so, its behavior and failure semantics MUST be documented separately.

• • •

## 12.11. Assertions and NDEBUG

The standard `assert()` macro MAY be used to verify internal invariants and assumptions that should hold when the program is correctly implemented.

Assertions MUST NOT be used as the sole mechanism for validating untrusted input or reporting ordinary runtime failures.

Program correctness MUST NOT depend on the evaluation of an assertion expression. In particular, assertion expressions MUST NOT contain side effects required for correct execution, because defining `NDEBUG` disables assertion checks.

The following rules apply:

- Assertions SHOULD verify internal conditions that indicate a programming defect when violated.
- Runtime failures MUST be handled through the normal error-reporting mechanism.
- User input and external data MUST be validated independently of assertions.
- Assertions MUST NOT be used to release resources, modify required state, or perform necessary operations.
- Code MUST remain functionally correct when assertions are disabled, except for the intentional loss of diagnostic checks.

An assertion failure is not a substitute for a documented error return value.

Implementations MUST NOT assume that assertions are enabled in production builds.

• • •

## 12.12. Fatal and Recoverable Errors

Errors MUST be handled according to whether recovery is possible and which layer has responsibility for deciding the application's response.

Libraries and reusable modules MUST report recoverable failures through their defined interfaces. They MUST NOT terminate the entire process merely because an operation failed.

The application layer SHOULD decide whether an unrecoverable condition requires process termination.

Functions MUST NOT call `exit()` or `abort()` as a general response to an ordinary operational failure.

Termination MAY be appropriate in an application-specific top-level failure policy or in explicitly designated process-level code. Such behavior MUST be deliberate and documented.

A module MUST NOT classify an error as fatal solely because it cannot recover locally. It SHOULD propagate the error to a layer that may have additional recovery options.

When continuing execution would violate a critical invariant or cause unsafe behavior, the implementation MUST NOT pretend that normal operation can continue. The failure MUST be handled according to the applicable contract and application-level policy.

• • •

## 12.13. Defensive Checks

Defensive checks MUST be applied where they meaningfully protect correctness, safety, or trust boundaries.

External input MUST be validated before it is relied upon. This includes input from users, files, network connections, external processes, and other sources not fully controlled by the current function.

Internal functions MAY rely on documented preconditions when those preconditions are guaranteed by the calling layer.

Implementations SHOULD avoid repeatedly validating every parameter and internal state at every function boundary when doing so provides no meaningful additional protection.

However, a function MUST NOT rely on a precondition when the value can originate from an untrusted source that has not been validated.

Checks MUST be appropriate to the risk involved. In particular, memory-safety requirements MUST NOT be ignored merely because a caller is expected to follow a contract.

Defensive programming MUST NOT introduce redundant branches, obscure control flow, or inconsistent error reporting without a justified benefit.

• • •

## 12.14. Failure-State Invariants

Functions MUST preserve their documented failure-state invariants.

The function contract MUST define the relevant state of objects, output parameters, and resources when an operation fails.

Unless the contract explicitly states otherwise, a failed operation MUST NOT leave an object in an undocumented or unusable state.

The following requirements apply:

- Required invariants MUST remain valid after failure.
- Any permitted partial changes MUST be documented.
- Resource ownership MUST remain unambiguous.
- Output parameters MUST have a defined failure-state interpretation.
- Partially initialized objects MUST NOT be exposed as fully initialized objects.
- An implementation MUST NOT claim rollback when side effects cannot actually be reversed.

A function SHOULD restore the original state when rollback is feasible and required by its contract.

However, exact restoration of the entire pre-call state MUST NOT be required when external side effects or irreversible operations make it impossible. In such cases, the implementation MUST preserve the invariants it can guarantee and document the remaining effects.

Callers MUST NOT depend on unspecified object or output state after failure.

• • •

## 12.15. Error Handling Contracts

Every public function MUST document its error-handling behavior in the applicable normative contract, as required by Section 11.

The contract MUST specify, where applicable:

- The status codes the function may return.
- The conditions that produce each relevant error.
- The validity and expected contents of output parameters after failure.
- The side effects that may occur before failure.
- The state of affected objects after failure.
- Resource acquisition, release, and ownership-transfer responsibilities.
- Whether an operation may partially complete.
- Any recovery or retry conditions that callers need to understand.

The contract MUST distinguish successful outcomes from error outcomes, including expected non-error states when they have separate status codes.

The implementation MUST behave consistently with its documented contract.

A function MUST NOT return an undocumented error code or leave callers dependent on implementation details that the contract does not guarantee.

Internal functions SHOULD document error behavior to the extent necessary for correct implementation and maintenance, even when they do not require a separate public contract document.

• • •

## 12.16. Error Return Conventions

All functions returning a status MUST follow the project's centralized status convention.

The standard convention is:

- `0`: Successful completion.
- Negative defined value: Error or explicitly defined non-success status.
- Output parameters: Result data accompanying a status return.

The applicable status codes MUST be defined in `status.h` or the designated status-definition headers.

Functions MUST NOT invent local status conventions that conflict with the project-wide convention.

Functions MUST NOT return a positive value to indicate an error unless an explicitly defined external interface requires such behavior. In that case, an adapter MUST translate the external convention into the project convention.

A query function MAY use a dedicated status code to indicate an expected result such as an absent entry. Such a status MUST have a documented meaning and MUST NOT be confused with success when the distinction matters to the caller.

A function returning `void` MUST be used only when no status result is needed or the function contract defines another appropriate reporting mechanism.

The final return value MUST accurately reflect the outcome of the operation. If cleanup fails after the main operation succeeds, the implementation MUST apply a documented policy rather than silently reporting success when the cleanup failure is significant.

• • •

## 12.17. Error Handling in Constructors and Destructors

In C, functions that initialize objects or release resources MUST follow the project's explicit status and ownership conventions.

### Initialization and construction

Functions that initialize or construct an object MUST report failure through the defined status interface when initialization can fail.

The function contract MUST specify:

- The required initial state of the destination object.
- Whether the destination must be zero-initialized or otherwise prepared by the caller.
- Which resources may be acquired during initialization.
- The state of the destination object after failure.
- Whether partial initialization is possible.
- Who is responsible for releasing any resources acquired before failure.

A failed initialization MUST NOT leave the destination appearing fully initialized when it is not.

Unless explicitly documented otherwise, the caller MUST NOT use the object as a fully initialized object after initialization fails.

If initialization acquires resources before failing, the implementation MUST release those resources or document an explicit ownership transfer that makes the remaining cleanup responsibility unambiguous.

### Destruction and release

Functions that release objects or resources MUST follow the documented ownership rules.

A release function SHOULD leave the object in a clearly defined state when it completes, where the object's representation permits such a state.

A release function MUST NOT access resources after relinquishing or freeing them.

If resource release can fail, the contract MUST define how that failure is reported and whether the resource remains valid, partially released, or in an indeterminate external state.

A release function MUST NOT silently claim successful cleanup when a significant release operation failed.

Destruction MUST NOT terminate the process as a general error-handling strategy.

• • •

## 12.18. Error Handling in Callbacks

Project-defined callback interfaces MUST return `int` and MUST follow the project's status-code convention.

A callback MUST return `0` when it completes successfully and a defined negative status code when it fails or reports a documented non-success outcome.

Callback contracts MUST specify:

- The meaning of each relevant return status.
- Whether the caller may retry after a failure.
- Whether the callback may modify the supplied context or other state before failing.
- The ownership and lifetime of callback arguments.
- Whether the caller or callback is responsible for cleanup after failure.
- How callback failures affect the enclosing operation.

The caller MUST interpret callback return values according to the callback contract.

When a callback fails, the invoking function MUST either propagate the failure, translate it according to a documented abstraction, or perform an explicitly permitted recovery.

Callback failures MUST NOT be silently ignored unless the callback contract explicitly defines the returned outcome as ignorable.

Some platform APIs and external libraries require callback signatures that do not return `int`. Such interfaces MUST NOT be modified in violation of their required signatures. An adapter or wrapper MUST translate the external callback behavior into the project's status convention where feasible.

The wrapper MUST define how failures are communicated when the external callback interface cannot return a status directly. It MUST NOT invent a return convention that violates the external API's contract.

• • •

## 12.19. Error Handling and Resource Ownership

Error handling MUST preserve the resource-ownership rules defined by the relevant function contract.

For every resource managed by a function, ownership MUST remain unambiguous on both success and failure paths.

The implementation MUST establish which of the following applies:

- The current function retains ownership and releases the resource.
- Ownership is transferred to the caller.
- Ownership is transferred to another explicitly identified component.
- The resource was never successfully acquired and therefore requires no release by the function.
- The resource remains in a documented partial or externally controlled state.

When an operation fails after acquiring a resource, the function MUST release that resource if ownership remains with the function and the contract does not specify otherwise.

When ownership has been transferred successfully, the previous owner MUST NOT release the resource unless the ownership contract explicitly permits shared ownership.

A failed ownership transfer MUST NOT leave both parties believing that the other party is responsible for cleanup.

Resource cleanup MUST follow the acquisition and dependency order established by the function's implementation and contract.

Memory allocations, file handles, locks, operating-system resources, and other managed resources MUST NOT be leaked because an error path bypassed cleanup.

If a resource cannot be released reliably, the implementation MUST follow the applicable error policy and document the resulting limitations when they affect callers.

• • •

## 12.20. Error Handling Anti-Patterns

The following practices MUST NOT be used:

- **Silent failure:** Ignoring a failure when the caller or another layer needs to know about it.
- **False success:** Returning success after the requested operation failed.
- **Undefined status codes:** Returning values that have no defined meaning in the applicable status interface.
- **Inconsistent conventions:** Using incompatible success and failure conventions across project modules without an explicit adapter.
- **Lost error information:** Replacing a meaningful failure with a generic status when the distinction is necessary for correct handling or diagnosis.
- **Unnecessary error translation:** Translating errors at every layer without adding a meaningful abstraction.
- **Duplicate logging:** Logging the same propagated failure repeatedly without a diagnostic reason.
- **Assertion-based runtime handling:** Using `assert()` as the sole response to ordinary runtime failures or untrusted input.
- **Assertion side effects:** Placing required operations inside assertion expressions.
- **Unsafe cleanup:** Releasing resources that were never acquired, releasing them more than once, or accessing them after release.
- **Unclear ownership:** Leaving resource-release responsibility ambiguous on a success or failure path.
- **False rollback guarantees:** Claiming that an operation restores its original state when irreversible side effects remain.
- **Uncontrolled termination:** Terminating the process from reusable library code in response to an ordinary operational failure.
- **Error-code duplication:** Defining conflicting meanings for the same status value within the same applicable status domain.
- **Unchecked external input:** Treating a documented precondition as a substitute for validating untrusted data.
- **Failure-state ambiguity:** Leaving output parameters or affected objects in an undocumented state after failure.

Error-handling code MUST remain explicit, predictable, and consistent with the project's function, memory-management, API, and ABI policies.

When an unusual error-handling technique is necessary, its behavior and justification MUST be documented in the relevant contract or implementation documentation.

___

# 13.0. Data Lifecycle

Data lifecycle rules define how objects and resources are initialized, used, transferred, reset, and destroyed throughout their lifetime.

All objects MUST be initialized before they are used. Resource ownership, object validity, and lifetime constraints MUST be explicit wherever they affect correctness or safety.

Lifecycle management MUST follow the project's function contracts, error-handling conventions, memory-management rules, and API/ABI requirements.

The primary objectives are:

- Ensure that objects are initialized before use.
- Define valid object states and permitted state transitions.
- Make resource ownership and transfer responsibilities explicit.
- Prevent use-after-free, double-free, resource leaks, and dangling pointers.
- Define the lifetime of borrowed data and returned pointers.
- Ensure that partial initialization and failure paths are safe.
- Establish predictable cleanup and destruction ordering.
- Keep lifecycle responsibilities clear across module boundaries.

Lifecycle rules MUST NOT depend on undefined behavior, implicit ownership assumptions, or undocumented implementation details.

## 13.1. Object Initialization

Every object MUST be initialized before it is used.

Initialization MUST establish a valid initial state for every field that the object may access during its intended use. Fields that are not immediately used MUST still be initialized when required by the object's representation, invariants, or initialization contract.

Initialization MUST be appropriate to the object's type and intended behavior. Zero-initialization MUST NOT be assumed to establish a valid state for every object or resource.

The following rules apply:

- Objects with explicit initialization functions MUST be initialized through the documented initialization procedure.
- Dynamically allocated objects MUST be initialized before their fields are accessed.
- Pointer fields MUST contain valid pointer values according to their contracts, including `NULL` when no object is currently designated.
- Resource handles MUST be initialized to documented states that distinguish unacquired resources from acquired resources.
- Initialization MUST establish all invariants required by subsequent operations.
- Objects MUST NOT be exposed for normal use before initialization has completed successfully.

Implementations MUST NOT assume that uninitialized automatic storage contains meaningful values.

When initialization can fail, the function MUST follow the error-handling rules defined in Section 12 and specify the object's state after failure.

• • •

## 13.2. Valid and Invalid Object States

Object validity MUST be defined by the object's lifecycle contract.

An object MAY have multiple valid states, such as uninitialized, initialized, active, stopped, reset, or destroyed. The applicable states depend on the object's purpose and implementation.

Each operation MUST specify the states in which it may be called when this restriction affects correct behavior.

The caller MUST track lifecycle state when the API assigns that responsibility to the caller. Implementations are not required to revalidate every object field or repeat every lifecycle check at every function call.

However, this policy MUST NOT leave valid states or caller responsibilities ambiguous.

The following rules apply:

- Operations MUST NOT be performed on objects that have not reached the required state.
- An object MUST NOT be treated as initialized when initialization has failed.
- A destroyed or otherwise invalidated object MUST NOT be used unless the API explicitly permits a subsequent operation, such as reinitialization.
- Operations that change an object's state MUST follow the documented transition rules.
- Invalid lifecycle operations MUST be handled according to the applicable function contract and error-handling policy.

Implementations SHOULD use explicit state fields when doing so materially improves correctness or makes lifecycle management easier to understand. Such fields MUST NOT be added solely to duplicate guarantees already provided by the surrounding design.

• • •

## 13.3. Initialization Functions

Initialization functions MUST establish the documented initial state of an object and any resources associated with it.

When initialization can fail, the function MUST report the failure through the project's standard status convention.

An initialization contract MUST specify, where applicable:

- The required state of the destination object before the call.
- Whether the destination must be zero-initialized or prepared in another way.
- Which fields and invariants are established on success.
- Which resources may be acquired.
- The destination object's state after failure.
- The cleanup responsibilities associated with partially acquired resources.
- Whether the function may be called again after a failed attempt.

Initialization MUST NOT silently overwrite live resources owned by an already initialized object.

If reinitialization is supported, it MUST follow Section 13.10. Otherwise, the caller MUST satisfy the documented preconditions before initializing the object.

A function MUST NOT report successful initialization until the object satisfies the invariants required for normal use.

If initialization fails after acquiring resources, the implementation MUST release those resources or establish an explicit, documented ownership arrangement for them.

• • •

## 13.4. Destruction and Cleanup Functions

Destruction and cleanup functions MUST release resources owned by the object or function according to the applicable ownership contract.

The cleanup procedure MUST address all resources that require explicit release, including dynamically allocated memory, file handles, file descriptors, and platform resources.

A cleanup function MUST define the resulting object state when that state matters to subsequent operations.

The following rules apply:

- Every resource owned by the object and requiring explicit release MUST be accounted for.
- Resources MUST NOT be released more than once.
- A resource MUST NOT be accessed after it has been released.
- Cleanup MUST NOT release resources owned by another component unless ownership has been transferred or the contract explicitly permits it.
- Cleanup MUST account for partial initialization.
- Cleanup MUST follow the dependency ordering described in Section 13.19.

Using `memset()` to zero an object MUST NOT be treated as a substitute for releasing its resources. Clearing the object's bytes does not close files, release dynamically allocated memory, unlock resources, or perform other required cleanup.

Where appropriate, a cleanup function SHOULD leave the object in a documented cleaned state that supports safe repeated cleanup or subsequent reinitialization.

If cleanup can fail, the function MUST follow the error-reporting conventions in Section 12 and document any relevant post-failure state.

• • •

## 13.5. Resource Ownership

Every managed resource MUST have an identifiable owner or an explicitly documented ownership model.

The owner is responsible for ensuring that the resource is released when its lifetime ends, unless ownership is transferred according to a documented contract.

Resources include, but are not limited to:

- Dynamically allocated memory.
- Files and file descriptors.
- Operating-system handles.
- Buffers requiring explicit allocation or release.
- Objects that own other resources.
- Platform-specific resources managed through an isolated platform layer.

The following rules apply:

- Ownership MUST be unambiguous.
- Borrowing a pointer MUST NOT automatically transfer ownership.
- A resource MUST NOT be released by a component that does not own it unless the contract explicitly permits that operation.
- Shared ownership, when necessary, MUST define how the resource remains valid and when it can be released.
- Resource lifetime MUST be compatible with the lifetime of every object or operation that depends on it.
- Ownership MUST remain unambiguous on both success and failure paths.

Implementations SHOULD prefer simple ownership models that make release responsibilities easy to identify.

When ownership cannot be represented by a single owner, the contract MUST describe the alternative arrangement and its synchronization or lifetime requirements.

• • •

## 13.6. Ownership Transfer

Ownership transfer MUST be explicit and documented.

Passing a pointer to another function or module MUST NOT, by itself, be interpreted as an ownership transfer.

A transfer contract MUST define:

- The resource being transferred.
- The operation or point at which ownership changes.
- Whether the transfer can fail.
- Which component owns the resource after success.
- Which component owns the resource after failure.
- Whether the previous owner may continue accessing the resource.
- Who is responsible for eventual release.

After a successful ownership transfer, the previous owner MUST NOT release the resource or access it in a manner prohibited by the transfer contract.

If ownership transfer fails, the implementation MUST preserve the ownership arrangement specified for failure. It MUST NOT leave both components believing that the other component is responsible for cleanup.

Where practical, interfaces SHOULD make ownership transfer apparent through function names, parameter names, documentation, or clearly defined operation semantics.

Ownership transfer MUST remain consistent with the project's status-code and error-handling conventions.

• • •

## 13.7. File and File Descriptor Lifetimes

Files and file descriptors MUST have explicit lifetime and ownership rules.

The component that acquires a file handle or file descriptor MUST remain responsible for releasing it unless ownership is explicitly transferred.

The lifecycle contract MUST define the relevant opening, usage, transfer, and closing behavior.

The following rules apply:

- A file handle or descriptor MUST NOT be used after it has been closed.
- A resource MUST NOT be closed by a component that does not own it unless the contract explicitly permits it.
- Every successful acquisition MUST have a corresponding release or documented ownership transfer.
- Error paths MUST release acquired file resources when ownership remains with the current function and the contract requires cleanup.
- Cleanup MUST account for partially completed operations.
- A file descriptor MUST NOT be assumed to remain associated with the same resource after it has been closed and its numeric value reused.

Closing a file or descriptor MUST NOT be assumed to reverse operations already performed on the underlying resource.

If closing a resource can fail, the implementation MUST follow the applicable platform API contract and the project's error-reporting policy. It MUST NOT blindly retry a close operation when the platform's semantics make the resource's resulting state uncertain.

Platform-specific file and descriptor behavior MUST be handled according to the project's platform API isolation rules.

• • •

## 13.8. Buffer Lifetimes

Every buffer MUST have a defined lifetime and usage contract.

The contract MUST specify, where applicable:

- Who owns the buffer.
- Who is responsible for allocating and releasing it.
- Whether the buffer may be modified.
- How long the buffer remains valid.
- Whether the recipient may retain the pointer after the current function returns.
- Whether the buffer may be accessed concurrently.
- Whether the buffer's contents remain valid after an associated operation completes.

A function that returns a borrowed buffer MUST NOT imply that the caller owns the underlying allocation.

A buffer MUST NOT be accessed after its lifetime ends or after the owning resource has been invalidated.

When a buffer is borrowed for the duration of a function call, the recipient MUST NOT retain the pointer beyond that duration unless the contract explicitly guarantees a longer lifetime.

When a buffer is retained for later use, the contract MUST define how its lifetime is guaranteed. This MAY involve transferring ownership, copying the data, or another explicitly documented mechanism.

Implementations MUST NOT rely on a buffer remaining valid merely because its memory has not yet been overwritten.

• • •

## 13.9. State Transitions

Object state transitions MUST follow the object's documented lifecycle contract.

When an object has multiple states, the implementation and its callers MUST respect the permitted transitions between those states.

Examples include transitions from uninitialized to initialized, initialized to active, active to stopped, and active to destroyed. Not every object requires all these states.

The following rules apply:

- An operation MUST specify its required initial state when that requirement affects correctness.
- State-changing operations MUST establish their documented resulting state on success.
- Failure behavior MUST preserve the invariants required by the function contract.
- Invalid transitions MUST NOT be silently treated as valid operations.
- State transitions MUST account for resource acquisition, release, and ownership changes.
- Concurrent state transitions MUST follow the applicable synchronization requirements.

A state transition MUST NOT expose an object as ready for use before its initialization is complete.

Where a transition fails after partial progress, the resulting state MUST be defined in accordance with Section 12.

Implementations SHOULD keep state transitions explicit and avoid unnecessary hidden state changes.

• • •

## 13.10. Reinitialization and Reset

Reinitialization and reset operations MUST have explicitly defined semantics.

Reinitialization establishes an object's initial state again. Reset returns an object to a specified state, which MAY differ from its original construction state.

A reset MUST NOT automatically be assumed to release every resource, preserve every resource, or reproduce the effects of destruction followed by initialization. Its actual behavior MUST be documented.

The following rules apply:

- Reinitialization MUST NOT overwrite live resources without releasing them or transferring their ownership appropriately.
- Reset MUST preserve the ownership rules of any resources that remain associated with the object.
- Resources that are no longer needed MUST be released when required by the reset contract.
- Any resources retained after reset MUST remain valid and owned according to the documented rules.
- Failure during reset or reinitialization MUST leave the object in a documented state.
- A reset operation MUST NOT silently invalidate borrowed pointers when the contract guarantees their continued validity.

If an operation is supported only for objects in a particular state, its preconditions MUST state that requirement.

Implementations SHOULD provide separate reset and destruction operations when their semantics differ materially.

• • •

## 13.11. Idempotent Cleanup

Cleanup functions SHOULD be idempotent when doing so is practical and consistent with the resource API.

An idempotent cleanup operation may be repeated without causing additional invalid resource operations or corrupting the object's state.

For example, a cleanup function MAY treat an already-cleaned object as requiring no further action when the object's representation and contract permit that behavior.

The following rules apply:

- The cleaned state MUST be documented.
- Repeated cleanup MUST NOT double-free memory or double-close a resource.
- Cleanup MUST NOT access released resources.
- Cleanup MUST NOT accidentally release a resource acquired by a later initialization.
- The object MUST NOT be used as a fully initialized object after cleanup unless the contract explicitly permits it.
- Reinitialization after cleanup MUST follow the documented initialization rules.

Idempotent cleanup MUST NOT be interpreted as permission to use dangling pointers, stale handles, or invalid object references.

If the object cannot safely distinguish a cleaned state from another state, repeated cleanup MUST NOT be assumed safe. The contract MUST define the allowed invocation pattern instead.

• • •

## 13.12. Partial Construction and Destruction

Objects that acquire multiple resources during initialization MUST support correct handling of partial construction failures.

A construction operation may successfully acquire some resources before a later step fails. The implementation MUST account for every resource acquired before the failure.

The following rules apply:

- Each successfully acquired resource MUST be tracked sufficiently to determine whether cleanup is required.
- Resources MUST be released in the appropriate order.
- Resources that were never acquired MUST NOT be released.
- Cleanup MUST NOT assume that all fields have been initialized.
- A partially constructed object MUST NOT be exposed as a fully initialized object.
- The resulting state after failed construction MUST be documented.
- Ownership MUST remain unambiguous after failure.

A destruction function MUST handle the set of resources that may legitimately exist in the object's permitted destruction state.

If partial construction is represented by initialization flags, resource handles, or another explicit mechanism, those indicators MUST accurately reflect the resources acquired.

The implementation MUST NOT rely on arbitrary memory contents to determine which resources require release.

Where construction fails and all acquired resources can be released, the implementation SHOULD leave the destination in the documented initial or failed state.

• • •

## 13.13. Global and Static Object Lifecycles

Global and static objects SHOULD be limited to cases where their lifetime and shared-state semantics are justified.

Global or static storage duration does not eliminate the need to manage resources owned by an object.

The following rules apply:

- Initialization requirements MUST be documented.
- Resource acquisition performed during runtime initialization MUST have a defined failure policy.
- Explicit cleanup MUST be provided for resources that require release.
- Dependencies between global or static objects MUST be clear.
- Shared mutable state MUST follow the applicable synchronization requirements.
- Static storage duration MUST NOT be treated as proof that all associated resources remain valid for the entire program lifetime.

Objects with static storage duration are initialized according to C's language rules, but dynamically acquired resources associated with those objects still require explicit management.

Functions MUST NOT introduce hidden global or function-local static state as a substitute for explicit ownership and lifecycle design. Function-local static variables are prohibited by the project's function rules.

Where possible, resource-owning objects SHOULD be initialized and destroyed through explicit application or module lifecycle functions.

The project does not prohibit all global or static objects. Their use MUST remain consistent with the relevant state-management and resource-ownership rules.

• • •

## 13.14. Thread and Synchronization Object Lifecycles

Thread and synchronization objects MUST have explicit initialization, usage, and destruction rules.

This requirement applies whether the implementation uses POSIX APIs or another permitted platform interface.

The lifecycle contract MUST specify, where applicable:

- How the object is initialized.
- When it becomes safe to use.
- Which threads may access it.
- How concurrent access is synchronized.
- How thread termination or joining is handled.
- When synchronization objects may be destroyed.
- Who owns the object and is responsible for cleanup.

A synchronization object MUST NOT be destroyed while it is still in use or while operations that depend on it remain active, unless the relevant API explicitly defines such behavior as safe.

A thread's associated state MUST remain valid for as long as the thread may access it.

Before destroying an object used by other threads, the implementation MUST establish that those threads can no longer access the object and that the applicable synchronization requirements have been satisfied.

The implementation MUST NOT assume that process termination or operating-system cleanup substitutes for correct resource lifecycle management.

Thread and synchronization APIs MUST remain isolated according to the project's platform API policy. The project's prohibition on C11 `<threads.h>` and C11 atomics remains in effect.

• • •

## 13.15. Borrowed Data Lifetimes

Borrowed data is data accessed without transferring ownership of the underlying resource.

A function receiving borrowed data MUST follow the documented lifetime and access restrictions associated with that data.

The following rules apply:

- Borrowed data MUST NOT be freed by the borrower unless the contract explicitly permits it.
- Borrowed data MUST NOT be accessed after its guaranteed lifetime ends.
- A borrower MUST NOT retain a pointer beyond the permitted lifetime unless the contract explicitly guarantees continued validity.
- A borrower MUST NOT modify borrowed data unless modification is permitted by the contract.
- The owner MUST preserve the data's validity for the duration of any lifetime guarantee it has made.
- Concurrent access MUST follow the applicable synchronization and mutability rules.

A pointer being non-`NULL` does not establish that the pointed-to object is still alive or valid.

When a component needs to retain data beyond the borrowed lifetime, it MUST use an explicitly permitted strategy, such as copying the data or obtaining ownership.

The contract MUST distinguish borrowed data from transferred ownership, even when both are represented by ordinary C pointers.

• • •

## 13.16. Returning Pointers to Objects

Functions returning pointers MUST define the lifetime, ownership, and validity conditions of the returned pointer.

A function MUST NOT return a pointer to an automatic object whose lifetime ends when the function returns.

The following rules apply:

- The pointed-to object MUST remain alive for the duration guaranteed by the contract.
- The contract MUST specify whether the returned pointer is borrowed, transferred, or otherwise managed.
- The contract MUST specify who is responsible for releasing the object, if release is required.
- The contract MUST document any conditions that invalidate the pointer.
- A returned pointer MUST NOT be assumed to remain valid after the underlying object is reset, destroyed, replaced, or otherwise invalidated.
- The caller MUST follow the documented ownership and lifetime rules.

A pointer to a global or static object MAY be returned when the object has an appropriate lifetime and the API permits access to it.

A pointer to dynamically allocated storage MAY be returned when the ownership and release responsibilities are explicit.

A function returning a borrowed pointer MUST NOT imply that the caller may free the pointed-to object.

A function returning an owned pointer MUST define how the caller acquires ownership and which operation releases the resource.

• • •

## 13.17. Ownership in Containers

Containers MUST define whether they own their elements or merely store references to externally owned objects.

This requirement applies to arrays, lists, queues, maps, trees, and other structures that hold values or pointers.

The container contract MUST specify, where applicable:

- Whether elements are copied, borrowed, or owned.
- Whether insertion transfers ownership.
- Whether removal transfers ownership back to the caller.
- Whether replacing an element releases the previous element.
- Whether destroying the container destroys its elements.
- How duplicate references are handled.
- How element lifetime interacts with container lifetime.

A container MUST NOT free borrowed elements unless its contract explicitly permits that behavior.

A container that owns its elements MUST release them according to its destruction and removal contracts.

A container that does not own its elements MUST NOT imply that those elements remain valid merely because their pointers remain stored in the container.

When ownership transfers during insertion or removal, the transfer rules defined in Section 13.6 MUST apply.

If the container supports a custom element-release callback, the callback's signature, lifetime, invocation conditions, and error behavior MUST be documented.

Container operations MUST preserve ownership invariants when allocation or other operations fail.

• • •

## 13.18. Lifecycle Invariants

Lifecycle invariants MUST remain valid throughout the object's permitted states and transitions.

The relevant invariants MAY include:

- Initialization is complete before normal use.
- Each owned resource has a defined owner.
- Every resource requiring explicit release remains accounted for.
- No released resource is accessed.
- No resource is released by an unauthorized owner.
- Borrowed pointers remain within their guaranteed lifetimes.
- State transitions preserve the object's documented validity.
- Objects used by multiple threads remain valid until concurrent access has ended.

An invariant MUST be defined when its violation could cause incorrect behavior, resource leaks, memory-safety failures, or ambiguous ownership.

Implementations MUST preserve these invariants on both success and failure paths.

A function MAY rely on invariants established by its caller when the contract assigns that responsibility to the caller. It is not necessary to revalidate every invariant in every function.

However, a function MUST NOT assume that an invariant holds when the relevant contract or lifecycle state does not guarantee it.

Assertions MAY be used to check suitable internal invariants, in accordance with Section 12.11. Assertions MUST NOT be the sole mechanism for validating untrusted data or handling ordinary runtime failures.

• • •

## 13.19. Cleanup Ordering

Resources MUST be released in an order that respects their dependencies.

As a general rule, resources SHOULD be released in the reverse order of acquisition. However, the actual dependency relationships between resources take precedence over a purely mechanical reversal.

For example, a resource that depends on another resource MUST NOT remain in active use after the underlying resource has been released.

The following rules apply:

- Resources MUST NOT be released while another resource still requires them.
- Dependent objects SHOULD be destroyed before the resources they depend on.
- Cleanup MUST account for partial acquisition and initialization failures.
- Resources that were not acquired MUST NOT be released.
- Ownership transfers MUST be reflected in the cleanup order.
- Error paths MUST follow the same dependency requirements as normal destruction.

Where cleanup spans multiple modules, each module MUST release only the resources for which it remains responsible.

Implementations SHOULD organize cleanup code so that resource dependencies and release ordering are easy to understand.

When a release operation fails, the implementation MUST follow the applicable error-handling policy without assuming that the resource was successfully released.

• • •

## 13.20. Resource Transfer Between Modules

Resource transfers between modules MUST be explicitly defined by their interface contracts.

A module MUST NOT assume that passing a pointer or handle to another module automatically transfers ownership.

The transfer contract MUST specify:

- The resource being transferred.
- Whether the resource is borrowed or owned.
- The exact condition under which ownership changes.
- The ownership state after success.
- The ownership state after failure.
- The lifetime during which the receiving module may access the resource.
- The component responsible for eventual cleanup.
- Any synchronization or thread-safety requirements.

A receiving module MUST NOT release a resource that it only borrows.

A sending module MUST NOT continue to use or release a resource after a successful transfer when the transfer contract prohibits such use.

If the receiving module must retain a resource, the transfer operation MUST guarantee an appropriate lifetime or establish a valid ownership arrangement.

When a transfer fails, the modules MUST preserve the ownership responsibilities defined for that failure path.

Platform-specific resource handles MUST follow the applicable platform API contract and MUST NOT bypass the project's module-boundary or API-isolation policies.

Public resource-transfer behavior MUST be documented in the corresponding normative API contract, as required by Section 11.

All inter-module resource transfers MUST preserve the project's ownership, lifecycle, and error-handling invariants.

___

# 14.0. Compiling and Verification

This section defines the requirements for compiling, testing, analyzing, and verifying C11 source code. Its purpose is to ensure consistent compiler behavior, reliable diagnostics, portability, and compliance with this coding style guide.

All production and test code MUST follow the applicable language, naming, formatting, API, and error-handling rules defined by this guide.

The project MUST maintain a centralized build configuration that defines compiler requirements, language modes, warning policies, analysis tools, and verification procedures. Individual modules MUST NOT independently weaken these requirements.

The project MUST support both GCC and Clang. Supported compiler versions and platform configurations MUST be explicitly documented and verified.

## 14.1. C11 Language Mode

All C source files MUST be compiled in strict ISO C11 language mode.

- GCC and Clang MUST use `-std=c11` for C11 compilation.
- The GNU dialect, selected by `-std=gnu11`, MUST NOT be used.
- Compiler defaults MUST NOT determine the language standard.
- Compiler-specific language extensions MUST NOT be used.
- Optional C11 features that an implementation is not required to provide MUST NOT be used.
- Platform APIs MUST be isolated according to the platform abstraction and API isolation rules defined elsewhere in this guide.
- Compiler options affecting language conformance MUST be defined centrally.

The build configuration MUST explicitly select the language standard rather than relying on the compiler's default mode.

A successful compilation MUST NOT be treated as proof of strict ISO C11 conformance. The source code MUST also comply with the applicable language restrictions defined by this guide.

• • •

## 14.2. GCC and Clang Compatibility

GCC and Clang MUST both be supported compilers.

- All production source files MUST compile successfully with both compilers in the required configurations.
- Both compilers MUST be included in the project's continuous integration process.
- Compiler-specific behavior MUST NOT be relied upon to implement portable application logic.
- Differences in diagnostics MUST be addressed without weakening the common coding requirements.
- Compiler-specific options MAY be used when necessary, provided that they are isolated in the centralized build configuration.
- Compiler-specific language extensions MUST remain prohibited, regardless of whether both compilers implement the same extension.

The project MUST maintain a documented list of supported compiler versions. Compatibility claims MUST be limited to configurations that have actually been verified.

Code that compiles successfully with one compiler but fails with another supported compiler MUST be corrected before acceptance, unless the failure is an independently documented toolchain defect that has been explicitly approved for temporary handling.

• • •

## 14.3. Compiler Warning Policy

The project MUST maintain a centralized and documented compiler warning policy.

The warning policy MUST enable a strong set of useful diagnostics supported by the selected compiler. It MUST prioritize warnings that identify likely defects, unsafe operations, suspicious conversions, portability problems, and violations of the project's coding rules.

- Common warning requirements MUST be consistent between GCC and Clang wherever equivalent diagnostics exist.
- Compiler-specific warning options MUST be isolated in the build configuration.
- The policy MUST NOT depend exclusively on compiler defaults.
- Warnings MUST be investigated and resolved when they indicate a genuine defect or violation.
- A warning MUST NOT be ignored merely because the compiler still produces an executable.
- Differences in diagnostic wording or availability MUST NOT justify weakening unrelated warning requirements.

The project MUST document its selected warning options and their purpose. The precise warning set MAY evolve as supported compiler versions change, provided that the overall policy remains consistent with this guide.

• • •

## 14.4. Treating Warnings as Errors

The project MUST NOT require `-Werror` as a universal compilation policy.

The absence of `-Werror` MUST NOT be interpreted as permission to leave known warnings unresolved.

- Warnings MUST be reviewed and classified.
- Warnings that indicate defects, undefined behavior, portability problems, or violations of this guide MUST be resolved.
- Newly introduced warnings MUST be investigated before the corresponding change is accepted.
- A warning MUST NOT be ignored solely because it does not prevent compilation.
- CI MUST continue to enforce the project's explicit build, test, formatting, and analysis requirements independently of whether `-Werror` is enabled.

A developer MAY use `-Werror` locally or in a dedicated verification configuration. Such use MUST NOT be required for every build.

The project SHOULD periodically review warnings produced by supported compiler versions to identify newly detectable defects and outdated warning configurations.

• • •

## 14.5. Compiler-Specific Warning Management

Compiler warning options MUST be managed through the centralized build configuration.

- Warning options supported by both compilers SHOULD be configured consistently.
- Compiler-specific options MUST be applied only to the relevant compiler.
- A compiler-specific option MUST NOT be passed indiscriminately to a different compiler.
- Differences between compiler diagnostics MUST be documented when they affect the verification process.
- Per-file warning configurations MUST NOT be introduced without a documented technical justification and explicit approval.
- Compiler-specific warning management MUST NOT be used to permit prohibited language constructs or weaken the coding rules.

The build configuration MUST distinguish common warning requirements from compiler-specific implementations of those requirements.

When an equivalent diagnostic is unavailable in one compiler, the project SHOULD use another appropriate verification mechanism where practical.

• • •

## 14.6. Warning Suppression

Warning suppression is prohibited.

Source-level diagnostic suppression directives, warning-disabling compiler options, and equivalent mechanisms MUST NOT be used to conceal or bypass diagnostics.

When a warning occurs, the responsible developer MUST investigate its cause and correct the underlying problem whenever possible.

If the warning originates from third-party code, generated code, or a toolchain defect that cannot reasonably be corrected within the project, the affected code MUST be isolated from ordinary project code and handled through an explicitly approved and documented exception.

An exception MUST identify:

- The affected code or build target.
- The diagnostic involved.
- The reason the diagnostic cannot be resolved normally.
- The scope of the exception.
- The conditions under which the exception may be removed.

Exceptions MUST be as narrow as practical and MUST NOT authorize unrelated warning suppression.

A warning MUST NOT be suppressed merely to obtain a successful build.

• • •

## 14.7. Static Analysis

Static analysis MUST be performed regularly and integrated into CI.

The project MUST use suitable static analysis tools to identify defects that may not be detected by ordinary compilation.

Analysis SHOULD cover, where supported and applicable:

- Invalid memory access and suspicious pointer operations.
- Resource leaks and incorrect resource ownership.
- Uninitialized values.
- Integer conversion and arithmetic hazards.
- Unreachable code and suspicious control flow.
- Violations of applicable coding rules.
- Portability problems and potentially undefined behavior.

Static analysis findings MUST be reviewed and classified. Confirmed defects MUST be corrected before acceptance unless an explicitly approved exception applies.

The project MUST NOT treat a clean static analysis report as proof that the source code is free of defects.

Tool configurations MUST be maintained centrally. Changes to analysis rules MUST be reviewed to ensure that they do not silently remove important coverage.

• • •

## 14.8. Formatting and Linting Tools

The project MUST define centralized formatting and linting rules.

Formatting and linting tools MUST be configured consistently for all applicable source files.

- Formatting rules MUST be deterministic for a given tool version and configuration.
- The configuration MUST be version-controlled.
- CI MUST check formatting compliance.
- Linting MUST enforce applicable rules that can be checked automatically.
- Local developer preferences MUST NOT override the project configuration.
- Tool versions SHOULD be documented or pinned where necessary to maintain consistent results.

Formatting tools MUST NOT be used to introduce changes that alter program behavior.

Linting MUST complement, rather than replace, compiler diagnostics, static analysis, testing, and code review.

A formatting or linting failure MUST be resolved before a change is accepted, unless a documented and approved exception applies.

• • •

## 14.9. Sanitizers

Sanitizers MUST be used regularly in appropriate test configurations.

The project MUST use AddressSanitizer (ASan) and UndefinedBehaviorSanitizer (UBSan) where supported by the compiler, platform, and runtime environment.

- ASan SHOULD be used to detect memory errors such as out-of-bounds accesses and use-after-free defects.
- UBSan SHOULD be used to detect applicable forms of undefined behavior.
- Sanitizer-enabled test configurations MUST be included in CI where the required toolchain and runtime support them.
- Sanitizer findings MUST be investigated and corrected.
- Sanitizer configurations MUST NOT replace ordinary production builds or other verification methods.

Sanitizer availability and behavior may differ between platforms and compiler versions. The project MUST document any required configuration that cannot be tested in a particular environment.

A successful sanitizer run MUST NOT be treated as proof that a program is free of memory errors or undefined behavior.

• • •

## 14.10. Debug and Release Builds

Release builds MUST be supported and verified.

Debug builds MAY be used at the developer's discretion and MUST NOT be a mandatory project-wide build configuration.

The Release configuration MUST use the project's centralized compiler options and MUST comply with all applicable coding rules.

- Release builds MUST compile successfully with supported compilers.
- Release builds MUST NOT rely on debugging-only behavior for correctness.
- Assertions MUST NOT be required to perform operations necessary for correct program behavior.
- Code MUST remain correct when assertions are disabled through `NDEBUG`.
- Build-specific differences MUST NOT change public API or ABI contracts unintentionally.
- Release-specific compiler options MUST be documented in the centralized build configuration.

Although Debug builds are not mandatory, developers SHOULD use them when investigating defects or validating changes.

Test configurations MUST be selected to provide meaningful verification of the resulting executable. When practical, the project SHOULD test both unoptimized and optimized builds to expose defects that may depend on optimization or build configuration.

• • •

## 14.11. Optimization Levels

Optimization settings MUST be managed centrally.

The project MUST NOT rely on compiler-default optimization levels.

- Optimization levels used for development, testing, and release MUST be explicitly selected in the build configuration.
- Release optimization MUST be documented.
- The project SHOULD test more than one optimization level where practical.
- Correctness MUST NOT depend on a particular optimization level.
- Undefined behavior MUST NOT be used or tolerated on the assumption that optimization will preserve an intended result.
- Optimization flags MUST NOT be used to bypass language conformance or coding requirements.

Differences in generated machine code between optimization levels are acceptable as long as the program preserves its specified behavior and public contracts.

The project SHOULD investigate defects that occur only under optimization rather than treating them as compiler problems without evidence.

• • •

## 14.12. Linker Diagnostics

Linker diagnostics MUST be reviewed as part of the build process.

- Linker errors MUST be resolved before a build is accepted.
- Supported and useful linker warnings SHOULD be enabled through the centralized build configuration.
- Linker-specific options MUST be applied only to compatible linkers.
- Undefined references, duplicate definitions, and unexpected symbol exports MUST be investigated.
- Unexpected dependencies MUST be removed or explicitly justified.
- Linker diagnostics MUST NOT be suppressed to conceal unresolved symbols, incompatible interfaces, or other defects.

The project MUST distinguish compiler diagnostics from linker diagnostics where they are produced by separate tools.

A successful compilation is insufficient if linking fails or produces an executable that violates the project's dependency, symbol visibility, or ABI requirements.

• • •

## 14.13. Multi-Compiler Verification

GCC and Clang MUST both be used in CI.

Each supported compiler MUST compile the required production and test targets using the prescribed language mode and applicable warning configuration.

- Both compilers MUST use strict ISO C11 mode.
- Both compilers MUST be tested against the same applicable coding requirements.
- Compiler-specific build options MUST remain isolated.
- Test failures MUST be investigated independently of whether the other compiler passes.
- Compiler-specific differences MUST NOT be used as a reason to weaken shared project requirements.

The project SHOULD test additional optimization configurations where practical.

A compiler passing the build does not exempt the code from verification with the other supported compiler.

The project MUST document the compiler versions used for required verification and MUST NOT claim compatibility with untested versions.

• • •

## 14.14. Continuous Integration

CI MUST enforce the project's mandatory verification requirements.

At a minimum, CI MUST perform:

- Compilation with GCC and Clang.
- Execution of required automated tests.
- Formatting compliance checks.
- Static analysis.

Sanitizer execution MUST be included in CI where supported and applicable, in accordance with Section 14.9.

CI MUST use the centralized build configuration. It MUST NOT rely on undocumented developer-local settings to satisfy required checks.

- Required checks MUST report failures clearly.
- Failed required checks MUST prevent a change from being accepted under the project's normal integration policy.
- Tool and compiler versions MUST be documented or controlled sufficiently to make failures reproducible.
- CI configuration changes MUST be reviewed.
- Unsupported checks MUST be explicitly identified rather than silently treated as successful.

CI is a required verification mechanism, but it does not replace code review, contract review, or manual evaluation of requirements that cannot be checked reliably by automation.

• • •

## 14.15. Centralized Build Configuration

Compiler options, warning policies, formatting rules, linting configuration, static analysis settings, and required verification procedures MUST be centrally managed.

Individual modules MUST NOT independently redefine or weaken common project requirements.

The centralized configuration MUST define, as applicable:

- The required C language standard.
- Supported compiler configurations.
- Common compiler warnings and compiler-specific warning options.
- Optimization and build-type settings.
- Include paths and required build definitions.
- Formatting and linting rules.
- Static analysis and sanitizer configurations.
- Test and CI requirements.
- Documented platform-specific settings.

Module-specific settings MAY be introduced only when technically necessary and explicitly documented.

Exceptions MUST be narrow, reviewed, and consistent with this guide. Centralization MUST NOT be used as a mechanism to introduce prohibited compiler extensions or weaken mandatory coding requirements.

Changes to common build configuration MUST be reviewed for their effect on all supported modules and platforms.

• • •

## 14.16. Portability Verification

Portability MUST be verified through actual compilation and testing on supported platforms.

The use of ISO C11 syntax alone MUST NOT be considered sufficient evidence of portability.

- Every platform claimed as supported MUST have an explicitly defined verification scope.
- Required platform configurations MUST be tested using the available supported toolchains.
- Linux and BSD compatibility MUST be evaluated according to the project's declared support matrix.
- Platform-specific APIs MUST remain isolated in the appropriate platform layer.
- Public interfaces MUST NOT unintentionally expose platform-dependent types or implementation details.
- Platform-dependent behavior MUST be documented and tested where applicable.
- Unsupported configurations MUST NOT be represented as verified.

The project SHOULD test multiple libc implementations and target architectures where practical and relevant to its support goals.

Portability defects MUST be corrected rather than hidden behind compiler-specific behavior.

When a platform cannot be tested in CI, its verification status and limitations MUST be documented accurately.

• • •

## 14.17. Compliance Checks

Compliance with this coding style guide MUST be verified through automated checks and code review.

Rules that can be checked reliably by tools SHOULD be automated. Rules requiring semantic, architectural, or contextual judgment MUST be reviewed by a developer.

Compliance checks SHOULD cover:

- C11 language mode and prohibited language extensions.
- Naming and header organization.
- Formatting and linting.
- Required compiler diagnostics.
- Prohibited constructs defined by this guide.
- API and ABI requirements where automated verification is practical.
- Resource-management and ownership requirements where suitable analysis is available.

Automated compliance checks MUST NOT be treated as complete substitutes for human review.

Code review MUST consider applicable requirements that tools cannot reliably verify, including API contracts, ownership semantics, portability assumptions, and architectural boundaries.

A successful compliance check does not authorize a violation that the tools cannot detect.

• • •

## 14.18. Compiler Feature Detection

Compiler feature detection MUST follow the portability requirements of this guide.

Standard-defined predefined macros MAY be used when necessary for legitimate standard-related purposes.

Compiler-specific predefined macros, including `__GNUC__` and `__clang__`, MUST NOT be used in project source code.

- Standard-defined macros MUST be preferred for standard-related detection.
- Compiler-specific feature detection MUST NOT be used to introduce compiler-dependent application behavior.
- Compiler-specific build configuration MAY select appropriate compiler options without embedding compiler-specific detection in source code.
- Project-defined configuration macros MUST follow the project's naming and prefix requirements.
- Feature-test macros MUST follow the platform API isolation rules and MUST be defined consistently before relevant system headers are included.
- `_GNU_SOURCE` MUST NOT be defined under the project's default portability policy.

Standard feature-test mechanisms MUST be used only for their intended purposes. The presence of a standard macro MUST NOT be interpreted as proof that every optional implementation feature is available.

Compiler-specific language extensions remain prohibited regardless of any feature-detection mechanism.

• • •

## 14.19. Static and Dynamic Analysis

Static and dynamic analysis MUST be treated as complementary verification methods.

Static analysis MUST be performed regularly and integrated into CI as defined in Section 14.7.

Dynamic analysis MUST be performed through appropriate tests and runtime verification configurations, including supported sanitizer configurations defined in Section 14.9.

- Static analysis SHOULD be used to detect defects without requiring execution of the affected code.
- Dynamic analysis SHOULD be used to investigate behavior observable during execution.
- Findings from either method MUST be reviewed and classified.
- Confirmed defects MUST be corrected.
- Analysis tools MUST be configured centrally.
- Tool limitations and unsupported environments MUST be documented when they affect required verification.

Additional analysis tools MAY be adopted when they provide meaningful coverage for the project.

No single analysis tool can establish complete correctness. Analysis results MUST be evaluated alongside compiler diagnostics, automated tests, contracts, and code review.

• • •

## 14.20. Test Build Requirements

Test code MUST comply with the project's applicable C11 language requirements, warning policy, formatting rules, and coding standards.

Test-specific configuration MAY be used when necessary, but it MUST be centrally managed and MUST NOT weaken the common requirements without an explicitly approved exception.

- Test code MUST compile in strict ISO C11 mode.
- Test targets MUST use the supported compiler configurations required by CI.
- Tests MUST be compiled and executed as part of the required verification process.
- Test builds MUST NOT depend on compiler extensions prohibited by this guide.
- Test-specific dependencies and configuration MUST be documented.
- Test-only instrumentation MAY be used when necessary and must not unintentionally alter the production interface or ABI.
- Failures in test compilation or execution MUST be investigated and resolved.

Test builds SHOULD use sanitizer configurations where supported and applicable.

The test environment MUST NOT be assumed to prove production correctness merely because all tests pass. Tests must be evaluated against the relevant requirements, contracts, and failure conditions.

• • •

## 14.21. Reproducible Builds

The project SHOULD produce reproducible build outputs wherever reasonably practical.

A reproducible build is a build in which the same source inputs, build configuration, and relevant toolchain inputs produce equivalent outputs, and ideally identical output artifacts.

The project MUST document relevant build inputs sufficiently to support investigation and reproduction of build results.

- Compiler and linker versions SHOULD be controlled or documented.
- Build dependencies SHOULD be pinned or otherwise identified where practical.
- Unnecessary timestamps, nondeterministic ordering, and environment-dependent values SHOULD be avoided in generated artifacts.
- Build paths and environment variables SHOULD be controlled when they affect generated outputs.
- Generated files and build scripts SHOULD be deterministic where practical.
- Differences that prevent byte-for-byte reproducibility SHOULD be documented when relevant.

Reproducibility requirements MUST account for legitimate differences between platforms, target architectures, toolchains, and build configurations.

The project MUST NOT claim universal byte-for-byte reproducibility unless it has been demonstrated for the stated configurations.

Reproducible builds SHOULD be verified periodically when the project infrastructure supports reliable comparison of outputs.

• • •

## 14.22. Compiler Version Requirements

The project MUST explicitly document the minimum supported versions of GCC and Clang.

The minimum versions MUST be selected according to the project's actual language, diagnostic, analysis, and platform requirements. This guide does not prescribe specific version numbers.

- Required minimum versions MUST be verified in CI.
- The project SHOULD test current supported compiler releases in addition to its minimum versions.
- A compiler version MUST NOT be considered supported solely because it accepts the `-std=c11` option.
- Compiler versions used for required verification MUST be documented.
- Changes to minimum supported versions MUST be reviewed and documented.
- Compiler upgrades MUST be evaluated for changes in diagnostics, language implementation, generated code, and tool behavior.
- The project's portability and coding requirements MUST remain in effect when compiler versions change.

If a minimum supported compiler version is changed, the project's build configuration and documentation MUST be updated accordingly.

Compatibility claims MUST reflect the versions and configurations actually verified by the project. Untested compiler versions MUST NOT be described as fully supported.

___

# 15.0. AI-Assisted Development

## 15.1. General AI Usage Policy

AI-assisted development tools MAY be used throughout the software development process. Their use is permitted and encouraged when they improve productivity, assist developers in understanding technical concepts, reduce repetitive work, or support the development of reliable software.

Appropriate uses of AI-assisted tools include, but are not limited to:

- Explaining code, language features, algorithms, and technical concepts.
- Answering technical questions in a manner similar to technical documentation, forums, and community resources.
- Assisting with debugging, troubleshooting, and root-cause analysis.
- Automating repetitive or mechanical development tasks.
- Generating, reviewing, and improving tests and documentation.
- Suggesting optimizations, refactoring strategies, and alternative implementations.
- Providing architectural suggestions and discussing their advantages, disadvantages, and trade-offs.

AI-assisted tools MUST be treated as development assistants rather than autonomous project owners.

AI tools MAY propose architectural designs, component boundaries, interfaces, and implementation strategies. However, architectural decisions MUST remain under the authority of the responsible developer or development team. AI-generated proposals MUST NOT be treated as approved architectural decisions without human evaluation and approval.

AI-assisted tools MUST NOT be entrusted with unrestricted control over the project's development process. Their use MUST remain subject to the developer's supervision, the project's requirements, and this coding style guide.

The objective of AI-assisted development MUST be to support human developers in building software that benefits people. AI assistance MUST NOT replace the human responsibility for determining the project's purpose, evaluating its consequences, or ensuring that its implementation serves that purpose.

• • •

## 15.2. Developer Responsibility

The developer who incorporates AI-generated content into the project MUST assume responsibility for that content as if it had been written manually.

The origin of a code fragment MUST NOT reduce the level of responsibility assigned to the developer who accepts and integrates it.

Before accepting AI-generated code, the developer MUST:

- Understand the code's purpose, behavior, assumptions, and limitations.
- Verify that the implementation satisfies the relevant requirements.
- Ensure compliance with this coding style guide and all applicable project rules.
- Evaluate memory management, resource ownership, error handling, and other relevant correctness properties.
- Identify potential security, portability, compatibility, and maintainability issues.
- Ensure that appropriate tests have been written and executed.
- Review the resulting changes before integrating them into the project.

AI-generated code MUST NOT be accepted solely because it appears plausible, is syntactically valid, compiles successfully, or passes a limited set of tests.

Developers SHOULD use AI to reduce repetitive work and obtain technical assistance rather than delegating the entire development process to an AI system without meaningful supervision.

The developer remains responsible for the final implementation, regardless of which tools produced or modified its contents.

• • •

## 15.3. Code Review and Verification

AI-generated code MUST undergo the same review, verification, testing, and integration requirements as manually written code.

The use of AI MUST NOT exempt any code from the project's established development workflow, code review requirements, continuous integration checks, or quality standards.

AI-generated changes MUST be reviewed for:

- Correctness and consistency with the intended requirements.
- Compliance with the applicable C11 standard and project coding rules.
- Proper handling of memory, pointers, resource lifetimes, and error conditions.
- Portability across supported platforms and compilers.
- API and ABI compatibility, where applicable.
- Security implications and interactions with untrusted input.
- Unnecessary complexity, duplicated logic, and maintainability.
- Compliance with the project's architecture and established interfaces.

The developer MUST verify the resulting implementation rather than relying solely on an AI tool's description of its own output.

Where applicable, verification SHOULD include compilation with supported compilers, automated tests, static analysis, sanitizers, and other checks required by the project.

Code review MUST consider the actual implementation and its behavior. A statement from an AI tool that code has been reviewed, tested, or verified MUST NOT be accepted as evidence that the corresponding checks have actually been performed.

• • •

## 15.4. Correctness and Hallucinations

AI-generated output MUST be treated as potentially incorrect, incomplete, outdated, or inconsistent with the project's requirements.

AI-assisted tools may generate nonexistent APIs, misuse existing interfaces, invent technical constraints, misunderstand specifications, or provide explanations that do not accurately describe the implementation.

Developers MUST independently verify technical claims whenever their correctness affects the implementation, its behavior, or its compliance with project requirements.

Verification SHOULD rely on authoritative sources appropriate to the subject, including:

- The applicable ISO C standard and relevant specifications.
- Official compiler and toolchain documentation.
- Official platform and library documentation.
- The project's source code, design documents, and established contracts.
- Reproducible tests and observed program behavior.

AI-generated code MUST NOT introduce compiler-specific extensions, non-standard language features, or unsupported platform assumptions in violation of this guide.

Compilation and successful test execution MUST NOT be treated as sufficient proof of correctness. Tests may fail to cover relevant execution paths, boundary conditions, invalid inputs, or other failure scenarios.

Developers MUST ensure that the implementation has been verified to a level appropriate for its intended use and potential consequences.

• • •

## 15.5. Security and Trust Boundaries

AI-assisted tools MUST operate within permissions and trust boundaries established by the developer or project.

AI-generated commands, scripts, patches, and other executable content MUST NOT be executed or applied without appropriate human supervision.

Developers MUST review the intended effects of operations before authorizing them. Explicit approval MUST be obtained before high-risk or potentially destructive operations, including, where applicable:

- Deleting or irreversibly modifying project data.
- Executing commands with elevated privileges.
- Modifying system-wide configuration or security settings.
- Transmitting source code, files, or other data to external systems.
- Changing access permissions, credentials, or security-sensitive configuration.
- Performing operations that may have significant external side effects.

Routine operations MAY be automated within explicitly established and appropriately restricted permissions. Such automation MUST NOT grant AI tools unrestricted authority to perform unrelated or higher-risk operations.

AI-generated code MUST NOT be trusted with sensitive operations merely because it was produced in response to an explicit request. Its permissions, inputs, outputs, and effects MUST be evaluated according to the applicable security requirements.

The developer MUST remain able to inspect and understand the changes introduced by AI-assisted tools. Changes MUST be reviewable and, where reasonably possible, reversible before integration.

AI assistance MUST NOT replace security review, threat analysis, or other security controls required by the project.

• • •

## 15.6. Licensing and Provenance

AI-generated code MAY resemble existing implementations, including implementations obtained from public repositories, documentation, examples, or other sources. Its origin and licensing status may not always be apparent.

Developers MUST remain responsible for evaluating the licensing and provenance risks of AI-generated content before incorporating it into the project.

Where relevant, developers SHOULD:

- Review AI-generated code for substantial similarity to known implementations.
- Investigate suspiciously specific or distinctive code fragments.
- Verify the licensing conditions of any identified source material.
- Preserve required copyright notices, attribution, and license information.
- Replace or independently reimplement questionable fragments when their origin or licensing conditions cannot be satisfactorily established.

Making small changes to AI-generated code MAY be useful when adapting it to the project's requirements. However, renaming identifiers, changing formatting, rearranging statements, or making other superficial modifications MUST NOT be assumed to eliminate copyright, licensing, or attribution obligations.

When a code fragment presents an unresolved licensing or provenance risk, developers SHOULD avoid incorporating it until the issue has been evaluated. Where the applicable license or legal requirements prohibit its use, the fragment MUST NOT be incorporated unless a valid legal basis for doing so has been established.

The absence of an identified source MUST NOT be treated as proof that AI-generated code is free of licensing obligations.

• • •

## 15.7. Confidentiality and Sensitive Information

Developers MUST NOT submit passwords, authentication tokens, private keys, or other secret credentials to AI tools unless an explicitly authorized and appropriately secured mechanism requires such handling. Ordinary AI prompts, code-generation requests, and debugging sessions MUST NOT be used to transmit these secrets.

Before submitting source code, logs, configuration files, datasets, or other project information to an AI service, developers MUST verify that the disclosure is permitted by the project's confidentiality requirements and applicable policies.

Particular care MUST be taken with:

- Proprietary or confidential source code.
- Personal information and user-generated data.
- Production logs and database exports.
- Authentication material and security-sensitive configuration.
- Internal architecture documents and vulnerability reports.
- Third-party information subject to confidentiality obligations.

The fact that information is technically accessible to a developer MUST NOT automatically be interpreted as permission to disclose it to an external AI service.

Developers MUST consider the tool's data handling, retention, access, and confidentiality conditions before transmitting sensitive project material.

Where disclosure is not authorized, developers MUST use sanitized, synthetic, or otherwise appropriately transformed data, or refrain from submitting the information.

Secrets MUST NOT be embedded in AI-generated source code, test fixtures, documentation, or example configuration files. Appropriate placeholders or approved secret-management mechanisms MUST be used instead.

• • •

## 15.8. AI-Generated Tests and Documentation

AI MAY be used to generate, improve, review, and maintain tests and documentation. However, AI-generated tests and documentation MUST be independently reviewed before being accepted as part of the project.

AI-generated tests MUST be evaluated for whether they actually verify the intended requirements rather than merely reproducing assumptions or implementation details present in the generated code.

Where applicable, test review SHOULD consider:

- Normal operating conditions.
- Boundary conditions and edge cases.
- Invalid inputs and failure paths.
- Error propagation and resource cleanup.
- Memory safety and resource ownership.
- Regression risks introduced by changes.
- Relevant portability and compatibility requirements.

The fact that an AI-generated test passes MUST NOT, by itself, establish that the implementation is correct. Developers MUST evaluate whether the test is meaningful, sufficiently independent, and appropriate for the behavior being verified.

AI-generated documentation MUST be checked against the actual implementation, public interfaces, and authoritative project requirements.

Documentation MUST NOT describe nonexistent functionality, unsupported guarantees, incorrect ownership rules, or behavior that the implementation does not provide.

Developers MUST correct misleading or incomplete AI-generated tests and documentation before accepting them.

• • •

## 15.9. Compliance with This Guide

All AI-generated and AI-modified code MUST comply with this coding style guide and the applicable rules of the project.

No exception to a coding rule MUST be assumed merely because the code was generated or modified by an AI tool.

AI-generated code MUST comply with the project's requirements concerning, among other things:

- The ISO C11 language standard and permitted compiler behavior.
- Naming conventions and source-code organization.
- Declaration, initialization, and scope rules.
- Memory management, ownership, and resource lifetimes.
- Error handling and status-code conventions.
- Public interfaces and ABI stability.
- Portability and supported platform constraints.
- Compiler warnings, formatting, static analysis, and testing.
- Documentation and code review requirements.

Developers MUST review AI-generated output for compliance before integrating it into the project.

If an AI tool proposes an implementation that conflicts with this guide, the project's established rules MUST take precedence. The developer MUST correct the implementation or reject the proposal.

Project-specific AI instructions MUST NOT override the normative requirements of this coding style guide unless an explicit, authorized amendment to the applicable rules has been made.

For projects using AI-assisted development, the project MUST maintain the documentation files specified in this section:

- `ai_memory_bank.md`: Records relevant development progress, decisions, changes, and context needed to continue work consistently. Entries MUST include dates and SHOULD include times when necessary to distinguish significant events.
- `ai_project_goals.md`: Records the project's goals, development stages, completed objectives, outstanding objectives, and relevant blockers.
- `ai_coding_rules.md`: Provides AI-oriented instructions derived from this coding style guide and the project's additional requirements.

All three files MUST be maintained when AI-assisted development is used. They MUST reflect the current project state and MUST NOT knowingly contain obsolete instructions presented as current requirements.

If an official AI-specific version of this coding style guide is published, projects MUST use that official version as the basis for `ai_coding_rules.md`, together with any applicable project-specific rules.

The AI-oriented rules file MUST NOT contradict the normative requirements of the main coding style guide.

• • •

## 15.10. Prohibited AI Usage Patterns

The following practices are prohibited:

- Executing AI-generated commands or applying AI-generated changes without the required supervision and authorization.
- Accepting code that the responsible developer does not understand sufficiently to evaluate and maintain.
- Skipping required testing, code review, static analysis, or other verification because code was generated by AI.
- Treating AI-generated explanations, claims of verification, or test results as substitutes for independently established evidence.
- Ignoring or deliberately bypassing this coding style guide or the project's requirements because an AI tool recommends doing so.
- Submitting AI-generated code without evaluating its correctness, security, portability, and licensing implications as applicable.
- Concealing the AI origin of code that remains AI-generated under the project's code-marking requirements.
- Providing AI tools with unrestricted authority to make architectural decisions or independently control the project.
- Disclosing secrets or confidential information in violation of the requirements established in this section.
- Using AI-generated tests or documentation as a substitute for the developer's responsibility to verify the implementation and its behavior.

AI-generated code MUST be marked according to the project's AI content marking requirements. AI-generated content MUST NOT be deliberately misrepresented as entirely human-authored when it remains AI-generated under those requirements.

Developers MAY use AI tools extensively for assistance, automation, and productivity. However, such use MUST remain consistent with human responsibility, appropriate supervision, this coding style guide, and the project's objective of developing reliable software for the benefit of people.

___

## Notes

> **AI Usage Notice:** This document was written by artificial intelligence in accordance with the architecture, rules, and standards provided by the developer, and has been reviewed by a human.
