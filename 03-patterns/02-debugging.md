# Debugging Prompts

Debugging prompts are designed to help AI systems identify, explain, and fix problems in software.

A good debugging prompt does more than say **"fix my code."** It provides the AI with the code, expected behavior, actual behavior, error messages, environment, and relevant constraints.

---

## What Is a Debugging Prompt?

A weak debugging prompt:

```text
Fix this code. It doesn't work.
```

A stronger debugging prompt:

```text
LANGUAGE:
Python 3.12

TASK:
Find and fix the bug in the following function.

EXPECTED BEHAVIOR:
The function should return the total price.

ACTUAL BEHAVIOR:
It returns an incorrect value when quantity is greater than 1.

ERROR:
No exception is raised.

CODE:
[CODE]

REQUIREMENTS:
- Identify the root cause.
- Explain the bug.
- Provide the corrected code.
- Provide test cases.
```

The second prompt gives the AI enough information to investigate the problem systematically.

---

# The Debugging Information Model

A useful debugging prompt usually contains:

```text
Environment
     ↓
Expected Behavior
     ↓
Actual Behavior
     ↓
Error / Evidence
     ↓
Code
     ↓
Constraints
     ↓
Debugging Task
```

Each piece helps narrow down the problem.

---

# 1. Define the Environment

Software behavior can depend on the environment.

Include information such as:

```text
LANGUAGE:
Python 3.12

FRAMEWORK:
FastAPI 0.116

DATABASE:
PostgreSQL 17

OS:
Windows
```

You do not need to include irrelevant environment details.

Only provide information that can affect the problem.

---

# 2. Define Expected Behavior

Tell the AI what should happen.

```text
EXPECTED:
When the user submits a valid email,
the function should return True.
```

Without expected behavior, the AI may not know what "correct" means.

---

# 3. Define Actual Behavior

Explain what actually happens.

```text
ACTUAL:
The function returns False even when
the email is valid.
```

The difference between expected and actual behavior is often the key to debugging.

---

# Expected vs. Actual

A useful format is:

```text
EXPECTED:
User submits valid credentials → Login succeeds.

ACTUAL:
User submits valid credentials → Login fails.
```

This gives the AI a concrete failure condition.

---

# 4. Include the Exact Error

If an error exists, provide the exact message.

```text
ERROR:
TypeError: unsupported operand type(s) for +:
'int' and 'str'
```

Avoid vague descriptions such as:

```text
It gives some type error.
```

Exact errors provide better evidence.

---

# 5. Include the Stack Trace

For complicated problems:

```text
TRACEBACK:
[Paste the relevant traceback here]
```

A stack trace can reveal:

* Where the error occurred
* Which function called it
* Which line failed
* What type of exception occurred

---

# 6. Include Relevant Code

Provide the smallest amount of code that still reproduces the problem.

````text
CODE:
```python
def calculate_total(price, quantity):
    return price + quantity
````

````

If the issue depends on other functions, include those dependencies too.

---

# Minimal Reproducible Example

A minimal reproducible example, often called an **MRE**, is a small version of the problem that still demonstrates the bug.

Instead of providing:

```text
5000 lines of application code
````

provide:

```text
The smallest relevant section that reproduces the issue.
```

This can make debugging faster and more focused.

---

# 7. Explain How to Reproduce the Bug

Tell the AI how the problem occurs.

```text
STEPS TO REPRODUCE:

1. Start the application.
2. Open /login.
3. Enter a valid email.
4. Enter a valid password.
5. Click Login.
6. The page returns HTTP 500.
```

This is especially useful for application bugs.

---

# 8. Include Recent Changes

Sometimes the problem appeared after a recent change.

```text
RECENT CHANGE:
I upgraded the database library from version X
to version Y.
```

Or:

```text
The bug appeared immediately after changing
the authentication middleware.
```

This can provide an important debugging clue.

---

# Root-Cause Analysis

Do not only ask the AI to provide a patch.

Ask it to identify the root cause.

```text
TASK:
Find the root cause of the problem.

OUTPUT:
1. Root cause
2. Evidence
3. Fix
4. Prevention
```

The goal is to understand **why** the problem occurred, not just make the error disappear.

---

# Debugging Workflow

A structured debugging workflow can be:

```text
Observe
   ↓
Reproduce
   ↓
Collect Evidence
   ↓
Identify Root Cause
   ↓
Design Fix
   ↓
Implement Fix
   ↓
Test
   ↓
Verify
```

This is a useful mental model for AI-assisted debugging.

---

# Debugging Prompt Example

````text
ROLE:
Act as a senior Python developer.

LANGUAGE:
Python 3.12

TASK:
Debug the following function.

EXPECTED:
The function should return the average
of all numbers in the list.

ACTUAL:
It crashes when the list is empty.

ERROR:
ZeroDivisionError

CODE:
```python
def average(numbers):
    return sum(numbers) / len(numbers)
````

REQUIREMENTS:

1. Identify the root cause.
2. Explain why the error occurs.
3. Provide a corrected implementation.
4. Add tests for normal and empty input.

````

This gives the AI a clear debugging workflow.

---

# Debugging Without an Error Message

Not every bug produces an exception.

For example:

```text
EXPECTED:
The total should be 150.

ACTUAL:
The application displays 100.

ERROR:
None.
````

This is a **logic bug**, not necessarily a runtime error.

In these cases, expected and actual behavior become especially important.

---

# Logic Bug Prompt

```text
TASK:
Find the logic error.

EXPECTED:
10% discount should be applied to the total.

ACTUAL:
The discount appears to be calculated
using the original price instead of the subtotal.

CODE:
[CODE]

OUTPUT:
Explain the incorrect calculation and
provide the corrected implementation.
```

---

# Runtime Error Prompts

For runtime errors, include:

```text
ERROR:
[Exact error]

TRACEBACK:
[Traceback]

REPRODUCTION:
[Steps]

CODE:
[Relevant code]
```

Then ask:

```text
TASK:
Identify the root cause and provide a minimal fix.
```

---

# Compile-Time / Syntax Errors

For syntax or compilation errors:

```text
LANGUAGE:
Java

ERROR:
[Compiler output]

CODE:
[Code]

TASK:
Identify the syntax or compilation problem
and provide the corrected version.
```

The exact compiler output is valuable evidence.

---

# Dependency Problems

Sometimes the problem is caused by a package or dependency.

Include:

```text
DEPENDENCIES:
fastapi==0.116.1
pydantic==2.x
```

And:

```text
RECENT CHANGE:
The application worked before upgrading FastAPI.
```

Then ask the AI to investigate the compatibility issue.

Do not assume the dependency is the cause without evidence.

---

# Database Debugging

For database problems, include:

* Database system
* Schema
* Query
* Error
* Expected result
* Actual result

Example:

```text
DATABASE:
PostgreSQL

TABLE:
orders(id, customer_id, total, created_at)

QUERY:
SELECT customer_id, SUM(total)
FROM orders;

ERROR:
column "customer_id" must appear in the GROUP BY clause

TASK:
Explain the error and provide the corrected query.
```

---

# API Debugging

For API problems, include the request and response.

```text
METHOD:
POST

ENDPOINT:
/api/users

REQUEST:
{
  "name": "Test User",
  "email": "test@example.com"
}

EXPECTED:
HTTP 201 with created user.

ACTUAL:
HTTP 422.

RESPONSE:
[API response]

TASK:
Identify the likely cause and explain how to debug it.
```

---

# Frontend Debugging

Frontend bugs often need:

```text
FRAMEWORK:
React

BROWSER:
Chrome

EXPECTED:
The button should submit the form.

ACTUAL:
Clicking the button does nothing.

CONSOLE ERROR:
[Error]

CODE:
[Component]

TASK:
Identify the likely cause and provide a fix.
```

Screenshots can also be useful when the problem is visual.

---

# Debugging Prompts With Constraints

Sometimes you want to prevent unnecessary changes.

```text
CONSTRAINTS:
- Do not change the database schema.
- Do not add dependencies.
- Preserve the existing API.
- Modify only the affected function.
```

This limits the scope of the fix.

---

# Ask for Multiple Possible Causes

When the evidence is insufficient:

```text
TASK:
Identify the most likely causes of this problem.

OUTPUT:
For each possible cause provide:
1. Probability / confidence
2. Evidence
3. How to verify it
4. Potential fix
```

This is better than pretending there is one certain answer when the available evidence is incomplete.

---

# Hypothesis-Driven Debugging

A useful debugging pattern is:

```text
Observation
    ↓
Hypothesis
    ↓
Test
    ↓
Result
    ↓
Next hypothesis
```

Example:

```text
Observation:
API returns HTTP 500.

Hypothesis:
Database connection is failing.

Test:
Check database connectivity.

Result:
Database connection works.

Next hypothesis:
Unhandled application exception.
```

This turns debugging into an investigation rather than random code changes.

---

# Debugging With Logs

Logs can provide valuable evidence.

```text
LOGS:
[Relevant application logs]
```

Ask:

```text
Analyze these logs and identify
the most likely failure point.
```

Only include relevant logs when possible.

---

# Debugging With Test Failures

Test output can make an excellent debugging input.

```text
TEST:
test_calculate_total

EXPECTED:
150

ACTUAL:
100

FAILURE:
AssertionError: 100 != 150

CODE:
[CODE]
```

Then:

```text
TASK:
Identify why the test fails and fix the implementation.
```

---

# Debugging With Git Changes

When a bug appeared after a code change, a diff can be useful.

```text
RECENT CHANGE:
[Git diff]

PROBLEM:
The application started returning 500 errors
after this change.

TASK:
Analyze the diff and identify the most likely cause.
```

This is especially useful for regression debugging.

---

# Regression Debugging

A regression occurs when previously working functionality stops working after a change.

A useful prompt:

```text
TASK:
Investigate this regression.

BEFORE:
The feature worked correctly.

CHANGE:
[Recent code change]

AFTER:
The feature now fails.

REQUIREMENTS:
- Identify what changed.
- Determine how the change could cause the failure.
- Suggest the smallest safe fix.
- Suggest a regression test.
```

---

# Ask for a Minimal Fix

If you want to avoid unnecessary rewrites:

```text
CONSTRAINT:
Provide the smallest change that fixes
the root cause while preserving existing behavior.
```

This is useful for mature codebases.

---

# Ask for a Safer Fix

For important systems:

```text
REQUIREMENTS:
- Preserve backward compatibility.
- Avoid breaking existing API consumers.
- Add a regression test.
- Explain potential side effects.
```

The AI should not be encouraged to make broad changes without justification.

---

# Debugging and Verification

A fix is not complete merely because the code looks correct.

A stronger workflow is:

```text
Bug
 ↓
Diagnosis
 ↓
Fix
 ↓
Test
 ↓
Regression Test
 ↓
Verification
```

Ask the AI to explain how the fix should be verified.

---

# Before and After

## Weak

```text
My login isn't working. Fix it.
```

## Stronger

```text
PROJECT:
FastAPI application

TASK:
Debug the login endpoint.

EXPECTED:
Valid credentials should return HTTP 200
and an authentication token.

ACTUAL:
Valid credentials return HTTP 401.

RECENT CHANGE:
Authentication middleware was updated yesterday.

CODE:
[Relevant code]

LOGS:
[Relevant logs]

REQUIREMENTS:
1. Identify the likely root cause.
2. Explain the evidence.
3. Provide the smallest safe fix.
4. Create a regression test.
5. Explain how to verify the fix.
```

The second prompt provides a real debugging investigation framework.

---

# Common Debugging Prompt Mistakes

## 1. "Fix It" Without Context

The AI cannot reliably diagnose an unknown problem.

## 2. Missing Expected Behavior

Without knowing what should happen, the AI cannot clearly define success.

## 3. Missing Error Messages

Exact errors are valuable evidence.

## 4. Providing Too Much Irrelevant Code

Large amounts of unrelated code can obscure the actual issue.

## 5. Asking for a Rewrite Instead of a Diagnosis

A complete rewrite may hide the original problem.

## 6. No Reproduction Steps

The AI may not understand how the failure occurs.

## 7. No Verification

A proposed fix should be tested.

---

# Debugging Prompt Template

```text
# ROLE
Act as a senior [LANGUAGE / DOMAIN] developer.

# ENVIRONMENT
Language:
Framework:
Runtime:
Database:
OS:

# TASK
Debug the following problem.

# EXPECTED BEHAVIOR
[What should happen]

# ACTUAL BEHAVIOR
[What actually happens]

# ERROR
[Exact error message]

# TRACEBACK / LOGS
[Relevant evidence]

# REPRODUCTION STEPS
1. [Step 1]
2. [Step 2]
3. [Step 3]

# RECENT CHANGES
[Recent changes, if relevant]

# CODE
"""
[Relevant code]
"""

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]

# OUTPUT
1. Root cause
2. Evidence
3. Fix
4. Corrected code
5. Tests
6. Verification steps
```

---

# Debugging Checklist

Before sending a debugging prompt:

* [ ] Did I describe the expected behavior?
* [ ] Did I describe the actual behavior?
* [ ] Did I include the exact error?
* [ ] Did I include relevant logs or traceback?
* [ ] Did I provide reproduction steps?
* [ ] Did I include the relevant code?
* [ ] Did I specify the environment?
* [ ] Did I mention recent changes?
* [ ] Did I define constraints?
* [ ] Did I ask for the root cause?
* [ ] Did I request tests?
* [ ] Did I define how the fix should be verified?

---

# Key Takeaways

1. Debugging prompts should provide evidence, not just instructions.
2. Expected behavior and actual behavior are both important.
3. Exact errors and stack traces can significantly improve diagnosis.
4. A minimal reproducible example keeps debugging focused.
5. Ask for the root cause instead of only requesting a patch.
6. Use constraints when you need to limit changes.
7. Consider multiple hypotheses when the evidence is incomplete.
8. Validate fixes with tests and reproduction steps.
9. Regression tests help prevent the same bug from returning.
10. Effective debugging prompts turn AI from a simple code generator into a **structured debugging assistant**.

---

## Next

**`03-patterns/03-refactoring.md`**

This file will cover prompts for **refactoring, code cleanup, maintainability, performance improvements, and safe modernization**.
