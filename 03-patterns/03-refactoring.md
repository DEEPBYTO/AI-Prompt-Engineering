# Refactoring Prompts

Refactoring prompts help AI improve existing code without changing its intended behavior.

The goal of refactoring is not simply to make code shorter. Good refactoring can improve:

* Readability
* Maintainability
* Structure
* Performance
* Testability
* Reusability
* Consistency

A good refactoring prompt clearly defines **what should change and what must remain unchanged**.

---

## What Is Refactoring?

Refactoring is the process of improving the internal structure of existing code while preserving its intended external behavior.

For example:

```text
Before:
Large function
    ↓
Mixed responsibilities
    ↓
Difficult to test
```

After:

```text
Main function
    ↓
Small focused functions
    ↓
Easier testing
```

The important principle is:

> **Improve the implementation without unintentionally changing the required behavior.**

---

# Basic Refactoring Prompt

A weak prompt:

```text
Make this code better.
```

A stronger prompt:

```text
TASK:
Refactor the following Python code.

GOALS:
- Improve readability.
- Reduce duplication.
- Separate responsibilities.
- Improve maintainability.

CONSTRAINTS:
- Preserve existing behavior.
- Do not change the public API.
- Do not add external dependencies.

CODE:
[CODE]

OUTPUT:
1. Refactored code
2. Summary of changes
3. Explanation of why each change was made
```

The second prompt provides measurable goals.

---

# Refactoring vs. Rewriting

These are not the same.

### Refactoring

```text
Existing code
     ↓
Improved internal structure
     ↓
Same intended behavior
```

### Rewriting

```text
Existing system
     ↓
New implementation
     ↓
Potentially different architecture
```

If you need to preserve existing behavior, explicitly say so.

---

# Why Use AI for Refactoring?

AI can help identify:

* Repeated code
* Large functions
* Poor naming
* Unnecessary complexity
* Duplicate logic
* Poor organization
* Missing abstractions
* Difficult-to-test code
* Outdated patterns

However, generated refactoring should still be reviewed and tested.

---

# Define the Refactoring Goal

"Refactor" can mean many things.

Be specific.

### Readability

```text
Improve variable names and simplify complex expressions.
```

### Maintainability

```text
Separate unrelated responsibilities into smaller functions.
```

### Performance

```text
Identify unnecessary repeated computations.
```

### Testability

```text
Separate external dependencies from business logic.
```

The AI can produce very different changes depending on the goal.

---

# Refactoring for Readability

Example:

```text
TASK:
Refactor this code for readability.

REQUIREMENTS:
- Use descriptive variable names.
- Break complex expressions into meaningful steps.
- Keep the same behavior.
- Do not change the public API.
```

This gives the AI a narrow target.

---

# Refactoring Large Functions

Large functions often perform multiple responsibilities.

Instead of:

```text
process_order()
    ├── validate user
    ├── calculate price
    ├── process payment
    ├── update database
    └── send email
```

A refactor might separate them:

```text
process_order()
    ↓
validate_user()
calculate_price()
process_payment()
save_order()
send_confirmation()
```

A prompt could be:

```text
Identify the responsibilities inside this function
and split them into smaller, logically focused functions.
```

---

# Refactoring Duplicate Code

Duplicate logic can increase maintenance costs.

A prompt:

```text
TASK:
Find duplicated logic in this code.

GOAL:
Reduce duplication while preserving behavior.

CONSTRAINTS:
- Do not over-engineer.
- Keep the public API unchanged.
- Explain the abstraction you introduce.
```

The important part is avoiding unnecessary abstraction.

---

# Refactoring Naming

Poor names:

```python
x = 10
y = 20
z = x * y
```

Better names:

```python
price = 10
quantity = 20
total = price * quantity
```

Prompt:

```text
Review the variable, function, and class names.
Suggest clearer names without changing behavior.
```

For large codebases, naming changes should be made consistently.

---

# Refactoring Nested Logic

Deep nesting can make code difficult to understand.

Example:

```text
if user:
    if account:
        if active:
            if permission:
                perform_action()
```

A refactoring prompt can ask:

```text
Reduce unnecessary nesting while preserving
the existing logic and behavior.
```

Possible approaches include:

* Guard clauses
* Early returns
* Extracted functions
* Simplified conditions

---

# Refactoring Conditional Logic

Complex conditions can be difficult to read.

Prompt:

```text
Simplify the conditional logic in this function.

Requirements:
- Preserve all existing cases.
- Do not remove validation.
- Explain any changed conditions.
- Add tests for important branches.
```

This encourages the AI to preserve behavior.

---

# Refactoring Classes

Classes can become difficult to maintain when they contain too many responsibilities.

Prompt:

```text
TASK:
Review this class for responsibility overload.

CHECK FOR:
- Too many responsibilities
- Tight coupling
- Difficult-to-test methods
- Duplicate logic

GOAL:
Suggest a cleaner class structure.

CONSTRAINT:
Do not introduce unnecessary design patterns.
```

The phrase **"do not introduce unnecessary design patterns"** is useful because AI can sometimes over-engineer simple code.

---

# Refactoring Architecture

For larger systems, refactoring can involve architecture.

Example:

```text
Current:

Controller
   ↓
Business Logic
   ↓
Database
```

A more structured system might separate:

```text
Controller
   ↓
Service Layer
   ↓
Repository
   ↓
Database
```

But architectural refactoring should only be requested when there is a real reason for the additional structure.

---

# Safe Refactoring

A safe refactoring prompt can include:

```text
SAFETY REQUIREMENTS:
- Preserve public APIs.
- Preserve database behavior.
- Preserve error behavior unless explicitly requested.
- Do not remove existing validation.
- Maintain backward compatibility.
- Add or update tests.
```

This is particularly useful for production code.

---

# Refactoring With Tests

Tests provide an important safety net.

A strong workflow is:

```text
Existing Code
     ↓
Existing Tests
     ↓
Refactor
     ↓
Run Tests
     ↓
Fix Regressions
     ↓
Review
```

Prompt:

```text
Before refactoring:
1. Analyze the existing tests.
2. Identify behavior that must be preserved.
3. Refactor the implementation.
4. Update tests only when necessary.
5. Explain any changed test behavior.
```

---

# Refactoring Without Tests

If tests do not exist, ask AI to identify important behaviors first.

```text
TASK:
Refactor this code.

FIRST:
Identify the important behaviors that should remain unchanged.

THEN:
Suggest tests that would verify those behaviors.

FINALLY:
Provide the refactored implementation.
```

This is safer than blindly modifying untested code.

---

# Performance Refactoring

Performance refactoring should include evidence when possible.

Weak:

```text
Make this faster.
```

Better:

```text
TASK:
Analyze this function for performance problems.

CONTEXT:
It processes approximately 1 million records.

CURRENT:
Execution takes approximately 45 seconds.

GOAL:
Identify realistic performance improvements.

CONSTRAINTS:
- Preserve behavior.
- Avoid unnecessary dependencies.
- Explain the expected complexity improvement.
```

Performance optimization should be based on actual bottlenecks rather than assumptions.

---

# Complexity Refactoring

You can ask AI to analyze algorithmic complexity.

```text
TASK:
Analyze the time and space complexity of this function.

THEN:
Identify opportunities to reduce unnecessary complexity.

OUTPUT:
1. Current complexity
2. Bottleneck
3. Proposed improvement
4. New complexity
5. Refactored code
```

This creates a more technical refactoring process.

---

# Refactoring for Testability

Code tightly coupled to external systems can be difficult to test.

For example:

```text
Business Logic
      ↓
Direct API Call
      ↓
External Service
```

A refactoring might introduce a boundary:

```text
Business Logic
      ↓
Interface / Service
      ↓
External API
```

Prompt:

```text
Refactor this code to improve testability.

GOALS:
- Separate business logic from external API calls.
- Make dependencies injectable.
- Preserve existing behavior.
- Avoid unnecessary architectural complexity.
```

---

# Refactoring for Reusability

If logic is repeated across multiple parts of a project:

```text
Module A
   ↓
Duplicate Logic

Module B
   ↓
Duplicate Logic

Module C
   ↓
Duplicate Logic
```

You may be able to create a reusable function or module.

Prompt:

```text
Identify logic that can safely be reused across
these modules.

Create a reusable abstraction only when it
reduces duplication without increasing complexity.
```

---

# Refactoring Legacy Code

Legacy code often requires extra caution.

A useful prompt:

```text
PROJECT:
Legacy Python application

TASK:
Identify safe refactoring opportunities.

PRIORITIES:
1. Preserve behavior.
2. Reduce technical debt.
3. Improve readability.
4. Improve testability.

CONSTRAINTS:
- No major rewrite.
- No framework migration.
- No breaking API changes.

OUTPUT:
Rank proposed refactoring opportunities
from lowest risk to highest risk.
```

This encourages incremental improvement.

---

# Incremental Refactoring

Large refactors are risky.

Instead:

```text
Step 1
Improve naming
   ↓
Step 2
Extract functions
   ↓
Step 3
Remove duplication
   ↓
Step 4
Improve tests
   ↓
Step 5
Review architecture
```

This makes each change easier to review and revert.

---

# Refactoring With Git

For a codebase under version control, you can ask AI to keep changes focused.

```text
TASK:
Prepare a focused refactoring.

REQUIREMENTS:
- Keep the change limited to the target module.
- Do not modify unrelated files.
- Preserve behavior.
- Explain every major change.
- Identify possible regression risks.
```

Small commits are generally easier to review than huge mixed changes.

---

# Code Review After Refactoring

After refactoring, use a separate review prompt.

```text
TASK:
Review this refactored code.

CHECK:
- Behavior preservation
- Bugs
- Complexity
- Readability
- Performance
- Security
- Test coverage
- Unnecessary abstractions

OUTPUT:
List findings by severity.
```

Separating refactoring from review can provide an additional quality check.

---

# Before and After Example

## Before

```python
def process_user(user):
    if user:
        if user["active"]:
            name = user["name"]
            email = user["email"]
            message = "Welcome " + name
            send_email(email, message)
            return True
    return False
```

A refactoring prompt:

```text
Refactor this function for readability.

Requirements:
- Preserve behavior.
- Use early returns where appropriate.
- Keep the function simple.
- Do not introduce unnecessary abstractions.
- Provide tests for active and inactive users.
```

Possible improved structure:

```python
def process_user(user):
    if not user or not user["active"]:
        return False

    send_email(
        user["email"],
        f"Welcome {user['name']}"
    )

    return True
```

The important point is not the exact code; it is the preservation of intended behavior.

---

# Refactoring Prompt With Acceptance Criteria

```text
TASK:
Refactor the payment processing module.

GOALS:
- Reduce duplicated validation.
- Improve readability.
- Separate business logic from external API calls.

ACCEPTANCE CRITERIA:
- Existing tests continue to pass.
- Public API remains unchanged.
- Payment behavior remains unchanged.
- No new external dependencies.
- Code is easier to test.
```

Acceptance criteria make the result measurable.

---

# Ask AI to Explain Tradeoffs

Refactoring often involves tradeoffs.

Ask:

```text
For each proposed refactoring, explain:

1. Benefit
2. Risk
3. Complexity impact
4. Maintenance impact
5. Whether you recommend implementing it
```

This is better than automatically accepting every suggested improvement.

---

# Avoid Over-Engineering

One of the most important refactoring principles:

> **More abstraction does not automatically mean better code.**

Avoid prompts that encourage unnecessary complexity.

Instead of:

```text
Apply every possible software design pattern.
```

Use:

```text
Improve the design only where it provides
a clear maintainability or testability benefit.
Prefer the simplest appropriate solution.
```

---

# Refactoring Checklist

Before asking AI to refactor:

* [ ] Is the goal clearly defined?
* [ ] Is existing behavior supposed to remain unchanged?
* [ ] Are public APIs protected?
* [ ] Are relevant tests available?
* [ ] Are constraints specified?
* [ ] Is the scope limited?
* [ ] Is performance actually a problem?
* [ ] Are unnecessary abstractions prohibited?
* [ ] Are acceptance criteria defined?
* [ ] Will the result be reviewed and tested?

---

# Reusable Refactoring Prompt

```text
# ROLE
Act as a senior software engineer.

# PROJECT
[Project description]

# LANGUAGE / STACK
[Technologies]

# TASK
Refactor the following code.

# GOALS
- [Goal 1]
- [Goal 2]
- [Goal 3]

# MUST PRESERVE
- Existing behavior
- Public APIs
- Required validation
- Backward compatibility

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]

# CODE
"""
[Code]
"""

# TESTS
[Existing tests, if available]

# ACCEPTANCE CRITERIA
- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

# OUTPUT
1. Refactored code
2. Changes made
3. Reasoning behind major changes
4. Risks
5. Tests
6. Verification steps
```

---

# Key Takeaways

1. Refactoring improves internal code structure while preserving intended behavior.
2. Define the specific reason for refactoring.
3. Distinguish refactoring from rewriting.
4. Protect public APIs and important behavior.
5. Use tests as a safety net.
6. Prefer incremental refactoring for large systems.
7. Performance refactoring should be based on actual bottlenecks.
8. Avoid unnecessary abstractions and over-engineering.
9. Ask AI to explain tradeoffs and regression risks.
10. A good refactoring prompt clearly defines **goals, constraints, preserved behavior, and acceptance criteria**.

---

## Next

**`03-patterns/04-testing.md`**

This file will cover AI prompts for **unit tests, integration tests, test cases, edge cases, test coverage, and test-driven development**.
