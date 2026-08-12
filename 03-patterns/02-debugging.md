# Debugging Prompts

Debugging prompts are designed to help AI systems identify, explain, and fix problems in software.

A strong debugging prompt does not simply say **“fix this code.”** It provides enough information for the AI to understand the expected behavior, actual behavior, environment, error, and relevant code.

---

## What Is a Debugging Prompt?

A basic debugging prompt:

```text
Fix this code.
```

provides almost no useful context.

A stronger prompt:

```text
LANGUAGE:
Python 3.12

EXPECTED BEHAVIOR:
The function should calculate the average of a list.

ACTUAL BEHAVIOR:
The program crashes when the list is empty.

ERROR:
ZeroDivisionError

CODE:
[CODE]

TASK:
Identify the root cause and provide a safe fix.
```

The second prompt gives the AI a much better debugging target.

---

# The Debugging Information Model

A useful debugging prompt can contain:

```text
ENVIRONMENT
     ↓
EXPECTED BEHAVIOR
     ↓
ACTUAL BEHAVIOR
     ↓
ERROR
     ↓
CODE
     ↓
REPRODUCTION STEPS
     ↓
TASK
     ↓
CONSTRAINTS
```

Not every debugging problem requires every section.

---

# 1. Environment

Software behavior can depend on the environment.

Include relevant information such as:

```text
LANGUAGE:
Python 3.12

FRAMEWORK:
FastAPI

OS:
Windows 11

DATABASE:
PostgreSQL 16
```

For frontend problems:

```text
FRAMEWORK:
React

LANGUAGE:
TypeScript

BROWSER:
Chrome
```

Only include information that can affect the problem.

---

# 2. Expected Behavior

Explain what should happen.

```text
EXPECTED:
When a user submits the form with valid
information, the account should be created.
```

This gives the AI a target to compare against.

---

# 3. Actual Behavior

Explain what is happening instead.

```text
ACTUAL:
The form submits successfully, but the user
is not added to the database.
```

The difference between expected and actual behavior is often the key to debugging.

---

# 4. Error Message

If an error exists, include the exact message.

```text
ERROR:
TypeError: Cannot read properties of undefined
```

Avoid paraphrasing errors when the original message is available.

---

# 5. Stack Trace

For runtime errors, include the relevant traceback.

```text
TRACEBACK:
[PASTE TRACEBACK HERE]
```

A stack trace can identify:

* Error type
* File
* Line number
* Call sequence
* Failure location

---

# 6. Relevant Code

Include the smallest useful section of code.

````text
CODE:
```python
def calculate_average(values):
    return sum(values) / len(values)
````

````

If the problem depends on another function, include that too.

Avoid dumping an entire large repository unless necessary.

---

# 7. Reproduction Steps

Explain how to reproduce the problem.

```text
REPRODUCTION:

1. Start the application.
2. Open the login page.
3. Enter an invalid email.
4. Click "Login".
5. The application crashes.
````

Reproduction steps are especially useful for application bugs.

---

# 8. Task

Tell the AI what you want it to do.

```text
TASK:
Identify the root cause, explain the problem,
and provide a minimal fix.
```

---

# 9. Constraints

Define what should not change.

```text
CONSTRAINTS:
- Do not change the database schema.
- Do not add external dependencies.
- Preserve the existing API response format.
- Make the smallest practical change.
```

This prevents unnecessary modifications.

---

# Root Cause Analysis

A good debugging prompt should encourage the AI to identify the **root cause**, not only the visible symptom.

For example:

```text
TASK:
Do not only suggest a workaround.

Identify:
1. The root cause
2. Why it occurs
3. Why the current implementation fails
4. The smallest reliable fix
```

This produces a more useful debugging process.

---

# Symptom vs. Root Cause

Consider:

```text
Symptom:
The login button does nothing.
```

Possible causes:

* JavaScript event handler failure
* Validation preventing submission
* API request failing
* Authentication endpoint returning an error
* Network configuration problem
* Frontend state issue

The visible symptom is not necessarily the actual problem.

---

# Debugging Workflow

A useful debugging workflow is:

```text
Problem
   ↓
Reproduce
   ↓
Collect Evidence
   ↓
Identify Possible Causes
   ↓
Test Hypotheses
   ↓
Identify Root Cause
   ↓
Implement Fix
   ↓
Test Fix
```

Prompting can guide the AI through this process.

---

# Root-Cause Debugging Prompt

```text
ROLE:
Act as a senior software debugging engineer.

TASK:
Investigate the following issue.

EXPECTED:
[Expected behavior]

ACTUAL:
[Actual behavior]

ERROR:
[Exact error]

ENVIRONMENT:
[Environment]

CODE:
[Relevant code]

REQUIREMENTS:
1. Identify the root cause.
2. Explain why it occurs.
3. Explain why the current implementation fails.
4. Provide the smallest reliable fix.
5. Provide a test that confirms the fix.

Do not rewrite unrelated parts of the code.
```

---

# Minimal Reproduction

A minimal reproduction contains only the code and conditions necessary to reproduce the problem.

For example:

````text
TASK:
Debug this minimal reproduction.

CODE:
```python
items = [1, 2, 3]

for i in range(len(items) + 1):
    print(items[i])
````

ERROR:
IndexError

EXPECTED:
Print every item exactly once.

````

A small reproducible example can make debugging much easier.

---

# Debugging With Logs

Logs can provide important evidence.

```text
LOGS:
2026-08-12 18:02:41 INFO Starting server
2026-08-12 18:02:45 INFO Login request received
2026-08-12 18:02:45 ERROR Database connection failed
````

Prompt:

```text
TASK:
Analyze these logs.

Identify:
- First meaningful failure
- Possible root cause
- Secondary errors
- Recommended investigation steps
```

The first visible error is not always the root cause, so chronological analysis matters.

---

# Debugging API Problems

A useful API debugging prompt:

```text
STACK:
FastAPI + PostgreSQL

EXPECTED:
POST /api/users should create a new user.

ACTUAL:
The endpoint returns HTTP 500.

REQUEST:
{
  "name": "Test User",
  "email": "test@example.com"
}

RESPONSE:
{
  "detail": "Internal Server Error"
}

SERVER LOG:
[LOGS]

CODE:
[ENDPOINT CODE]

TASK:
Identify the likely root cause and propose a fix.
```

---

# HTTP Debugging

For web APIs, include:

* HTTP method
* URL path
* Request headers when relevant
* Request body
* Status code
* Response body
* Server logs
* Expected response

Example:

```text
METHOD:
POST

ENDPOINT:
/api/login

STATUS:
401

EXPECTED:
200

REQUEST:
[REQUEST]

RESPONSE:
[RESPONSE]
```

---

# Database Debugging

Database problems should include the relevant schema and query.

```text
DATABASE:
PostgreSQL

TABLE:
users

QUERY:
SELECT * FROM users WHERE email = ?

ERROR:
column "email" does not exist

SCHEMA:
[SCHEMA]

TASK:
Identify why the query fails and provide the corrected query.
```

---

# Frontend Debugging

For frontend issues, include:

```text
FRAMEWORK:
React + TypeScript

EXPECTED:
Clicking the button should submit the form.

ACTUAL:
Nothing happens.

CONSOLE ERROR:
[ERROR]

COMPONENT:
[CODE]

TASK:
Identify the cause and provide the minimal fix.
```

Browser console errors can be particularly valuable.

---

# Authentication Debugging

Authentication issues should be described carefully.

```text
SYSTEM:
React frontend + FastAPI backend

EXPECTED:
A successful login should store the authentication
token and redirect the user to the dashboard.

ACTUAL:
Login succeeds, but the user is immediately redirected
back to the login page.

EVIDENCE:
[Console logs]
[Network response]
[Relevant code]

TASK:
Trace the authentication flow and identify where
the state is being lost.
```

This focuses the investigation on the complete flow rather than one line of code.

---

# Performance Debugging

Performance problems require measurements where possible.

Weak:

```text
The application is slow.
```

Better:

```text
PROBLEM:
The dashboard takes approximately 4 seconds to load.

EXPECTED:
The dashboard should load in under 1 second.

OBSERVED:
- API request: 3.2 seconds
- Database query: 2.8 seconds
- Frontend rendering: 0.2 seconds

TASK:
Analyze the measurements and identify the most likely
performance bottleneck.
```

Measurements are more useful than vague descriptions.

---

# Memory and Resource Problems

For memory leaks or resource exhaustion, include:

```text
ENVIRONMENT:
[Environment]

OBSERVATION:
Memory usage increases continuously during operation.

STARTING MEMORY:
300 MB

AFTER 30 MINUTES:
1.2 GB

STEPS:
[Reproduction steps]

CODE:
[Relevant code]

TASK:
Identify possible resource leaks and suggest
a method to verify each hypothesis.
```

---

# Debugging With Hypotheses

Instead of asking the AI to immediately choose one explanation:

```text
TASK:
Generate the three most likely causes.

For each cause provide:
- Evidence supporting it
- Evidence against it
- How to test it
```

This encourages systematic investigation.

---

# Evidence-Based Debugging

A useful debugging prompt can explicitly require evidence.

```text
TASK:
Analyze the issue using only the information provided.

For each proposed cause:
1. Identify supporting evidence.
2. Identify missing evidence.
3. Explain how to verify it.

Clearly distinguish:
- Confirmed facts
- Strong possibilities
- Speculation
```

This helps prevent unsupported conclusions.

---

# Debugging With Multiple Stages

Complex debugging can use a prompt chain.

```text
Stage 1:
Collect facts
      ↓
Stage 2:
Generate hypotheses
      ↓
Stage 3:
Rank hypotheses
      ↓
Stage 4:
Design tests
      ↓
Stage 5:
Identify root cause
      ↓
Stage 6:
Implement fix
      ↓
Stage 7:
Verify fix
```

This combines debugging with prompt chaining.

---

# Fix-Only vs. Explain-and-Fix

Sometimes you only need a patch:

```text
TASK:
Fix the bug and return the corrected code.
```

Other times, explanation is important:

```text
TASK:
1. Identify the bug.
2. Explain the root cause.
3. Show the corrected code.
4. Explain why the fix works.
5. Provide a regression test.
```

Choose the output based on your goal.

---

# Minimal Fix Prompt

For production code, unnecessary changes can create additional risk.

```text
TASK:
Fix only the identified bug.

CONSTRAINTS:
- Preserve existing architecture.
- Do not rename public functions.
- Do not change unrelated files.
- Do not introduce dependencies.
- Keep the patch as small as practical.
```

This encourages focused changes.

---

# Regression Testing

After fixing a bug, test that it does not return.

```text
TASK:
After proposing the fix, create a regression test
that fails with the original implementation and
passes with the corrected implementation.
```

This is an important software engineering practice.

---

# Before and After

## Weak

```text
My website login is broken. Fix it.
```

## Strong

```text
ROLE:
Act as a senior full-stack debugging engineer.

STACK:
React + TypeScript + FastAPI

EXPECTED:
Users can log in with valid credentials and
reach the dashboard.

ACTUAL:
The login request returns HTTP 200, but the
frontend redirects back to the login page.

BROWSER CONSOLE:
[ERROR]

NETWORK RESPONSE:
[RESPONSE]

FRONTEND CODE:
[CODE]

BACKEND CODE:
[CODE]

TASK:
1. Trace the authentication flow.
2. Identify the most likely root cause.
3. Explain the evidence.
4. Provide the minimal fix.
5. Create a regression test.

CONSTRAINT:
Do not modify unrelated functionality.
```

The second prompt provides enough information for systematic investigation.

---

# Debugging Prompt Template

```text
# ROLE
Act as a senior software debugging engineer.

# ENVIRONMENT
[Language / framework / runtime / OS]

# EXPECTED BEHAVIOR
[What should happen]

# ACTUAL BEHAVIOR
[What happens instead]

# ERROR
[Exact error message]

# REPRODUCTION STEPS
1. [Step 1]
2. [Step 2]
3. [Step 3]

# LOGS
[Relevant logs]

# CODE
"""
[Relevant code]
"""

# TASK
1. Identify the root cause.
2. Explain the evidence.
3. Provide the smallest reliable fix.
4. Provide a regression test.

# CONSTRAINTS
- [Constraint]

# OUTPUT
[Desired response format]
```

---

# Common Debugging Prompt Mistakes

## 1. Saying Only "Fix It"

The AI does not know what "it" means.

## 2. Omitting Expected Behavior

Without a target, the AI may not know what success looks like.

## 3. Hiding the Exact Error

Use the original error message whenever possible.

## 4. Providing Too Much Irrelevant Code

More information is not always better.

## 5. Asking for a Complete Rewrite

A rewrite may introduce new bugs when a small fix is sufficient.

## 6. No Reproduction Steps

Without reproduction, diagnosis becomes harder.

## 7. No Verification

A proposed fix should be tested.

## 8. Treating the First Hypothesis as Fact

A plausible explanation is not necessarily the root cause.

---

# Best Practices

### 1. Describe Expected vs. Actual

This is one of the most useful debugging patterns.

### 2. Provide Exact Evidence

Include errors, logs, stack traces, and measurements.

### 3. Ask for Root Cause

Do not stop at a workaround.

### 4. Limit the Scope

Request minimal changes when appropriate.

### 5. Ask for Tests

A fix without verification is incomplete.

### 6. Separate Facts From Hypotheses

This reduces overconfident diagnosis.

### 7. Reproduce Before Fixing

A reproducible problem is easier to investigate.

### 8. Verify After Fixing

Confirm that the original problem is resolved and that existing behavior remains intact.

---

# Debugging Checklist

Before sending a debugging prompt:

* [ ] Is the expected behavior clear?
* [ ] Is the actual behavior clear?
* [ ] Is the exact error included?
* [ ] Are relevant logs included?
* [ ] Are reproduction steps provided?
* [ ] Is the environment specified?
* [ ] Is the relevant code included?
* [ ] Are constraints defined?
* [ ] Is root-cause analysis requested?
* [ ] Is verification requested?
* [ ] Is a regression test requested when appropriate?

---

# Key Takeaways

1. Debugging prompts should provide evidence, not just symptoms.
2. Expected and actual behavior should be clearly separated.
3. Exact errors and logs are more useful than vague descriptions.
4. Relevant code and reproduction steps improve diagnosis.
5. Ask for the root cause rather than only a workaround.
6. Use constraints when you need a minimal or focused fix.
7. Separate confirmed facts from hypotheses.
8. Complex debugging can be divided into multiple stages.
9. Always verify important fixes.
10. A strong debugging prompt turns **“something is broken”** into a structured investigation.
