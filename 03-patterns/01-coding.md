# Coding Prompts

Coding prompts are prompts designed to help AI systems perform software development tasks such as writing code, debugging, refactoring, explaining code, designing APIs, generating tests, and reviewing implementations.

A strong coding prompt gives the AI enough information to understand the **goal, environment, constraints, and expected result**.

---

## What Is a Coding Prompt?

A basic coding prompt might be:

```text
Write Python code for a calculator.
```

A more useful version provides additional context:

```text
LANGUAGE:
Python 3

TASK:
Create a command-line calculator.

REQUIREMENTS:
- Support addition, subtraction, multiplication, and division.
- Handle invalid input.
- Prevent division by zero.

OUTPUT:
Provide the complete Python program with a short explanation.
```

The second prompt gives the AI a much clearer target.

---

# What Should a Coding Prompt Include?

A useful coding prompt may include:

* Programming language
* Framework or library
* Project context
* Task
* Existing code
* Requirements
* Constraints
* Expected behavior
* Error handling
* Input/output examples
* Testing requirements
* Output format

Not every coding task needs all of these.

---

# Basic Coding Prompt Structure

```text
LANGUAGE:
[Programming language]

ENVIRONMENT:
[Framework / runtime / version]

CONTEXT:
[Project information]

TASK:
[What needs to be built or changed]

REQUIREMENTS:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

CONSTRAINTS:
- [Constraint 1]
- [Constraint 2]

INPUT:
[Existing code or data]

EXPECTED OUTPUT:
[Expected behavior or format]
```

---

# Example: Generate Code

```text
LANGUAGE:
Python 3

TASK:
Create a function that checks whether a number
is prime.

REQUIREMENTS:
- Accept an integer.
- Return True for prime numbers.
- Return False otherwise.
- Handle numbers less than 2.

OUTPUT:
Provide the function and three example calls.
```

This is more precise than simply asking:

```text
Make a prime number function.
```

---

# Specify the Environment

Code depends heavily on its environment.

Compare:

```text
Create a web application.
```

with:

```text
Create a web application using:

Frontend:
HTML, CSS, JavaScript

Backend:
Python + FastAPI

Database:
PostgreSQL

Authentication:
JWT
```

The second prompt gives the AI important technical context.

---

# Specify Versions When Important

Libraries and frameworks change over time.

For example:

```text
Use Python 3.12 and FastAPI.
```

or:

```text
Use React with TypeScript.
```

When a specific version matters, include it explicitly.

---

# Include Existing Code

When asking AI to modify code, provide the relevant code.

````text
TASK:
Fix the bug in this Python function.

CODE:
```python
def divide(a, b):
    return a / b
````

PROBLEM:
The application crashes when b is zero.

REQUIREMENTS:

* Prevent division by zero.
* Keep the function simple.
* Explain the change.

````

Providing the actual code is usually much more useful than describing it vaguely.

---

# Code Generation

AI can help generate:

- Functions
- Classes
- Components
- APIs
- Scripts
- Database queries
- Configuration
- Tests
- Documentation

Example:

```text
TASK:
Create a REST API endpoint for retrieving a user.

STACK:
Python
FastAPI
PostgreSQL

REQUIREMENTS:
- Accept a user ID.
- Return user information.
- Return a suitable error when the user does not exist.
- Validate the ID.

OUTPUT:
Provide the endpoint implementation and explain the main components.
````

---

# Debugging Prompts

Debugging prompts should clearly describe the problem.

Weak:

```text
This code doesn't work. Fix it.
```

Better:

````text
TASK:
Debug the following Python code.

EXPECTED BEHAVIOR:
The function should return the sum of all numbers.

ACTUAL BEHAVIOR:
It returns only the first number.

CODE:
```python
def total(numbers):
    return numbers[0]
````

REQUIREMENTS:

* Identify the bug.
* Explain why it occurs.
* Provide the corrected code.

````

The more useful information you provide, the easier it is to diagnose the problem.

---

# Error Messages

When debugging, include the exact error message when available.

```text
ERROR:
TypeError: unsupported operand type(s) for +: 'int' and 'str'
````

Avoid replacing an exact error with a vague description such as:

```text
It gives some type error.
```

Exact information gives the AI more useful context.

---

# Stack Traces

For complex debugging tasks, include the relevant stack trace.

```text
TRACEBACK:
[Paste relevant traceback here]
```

Also provide:

* Environment
* Runtime version
* Relevant dependencies
* Expected behavior
* Actual behavior

---

# Refactoring Prompts

Refactoring means improving code structure without changing its intended behavior.

Example:

```text
TASK:
Refactor the following Python code.

GOAL:
Improve readability and maintainability.

CONSTRAINTS:
- Preserve existing behavior.
- Do not introduce external dependencies.
- Keep the public function names unchanged.

CODE:
[CODE]
```

This gives the AI a clear definition of what "improve" means.

---

# Code Review Prompts

A code review prompt can define exactly what should be inspected.

```text
ROLE:
Act as a senior software engineer.

TASK:
Review the following code.

CHECK FOR:
- Bugs
- Security issues
- Performance problems
- Error handling
- Maintainability
- Readability

OUTPUT:
For each issue provide:

1. Severity
2. Problem
3. Explanation
4. Recommended fix
```

This creates a repeatable review process.

---

# Security Review Prompts

Security analysis should be specific.

```text
TASK:
Review this web application's authentication code.

CHECK FOR:
- Authentication weaknesses
- Authorization problems
- Input validation issues
- Sensitive information exposure
- Session management problems
- Common web security risks

OUTPUT:
Rank findings by severity and explain each issue.
```

AI-generated security advice should still be reviewed by qualified security professionals for important systems.

---

# Testing Prompts

AI can generate test cases when the expected behavior is clearly defined.

```text
TASK:
Create unit tests for this Python function.

REQUIREMENTS:
- Test normal inputs.
- Test empty input.
- Test invalid input.
- Test boundary cases.
- Test error handling.

FRAMEWORK:
pytest

CODE:
[CODE]

OUTPUT:
Provide the test file and explain the test categories.
```

---

# Test-Driven Prompting

You can define expected behavior before requesting implementation.

```text
TASK:
Implement a password validation function.

EXPECTED BEHAVIOR:

Input:
"abc"

Expected:
False

Input:
"StrongPassword123!"

Expected:
True

Input:
""

Expected:
False

IMPLEMENTATION:
Write a Python function that satisfies these cases.
```

This gives the AI concrete behavioral targets.

---

# Input and Output Examples

Examples are particularly useful for functions and APIs.

```text
FUNCTION:
format_username(name)

INPUT:
"Abdul Sami"

OUTPUT:
"abdul-sami"
```

Then:

```text
Create the function according to the example above.
```

Multiple examples can clarify edge cases.

---

# API Prompts

When generating APIs, specify:

* HTTP method
* Endpoint
* Request format
* Response format
* Authentication
* Validation
* Error behavior

Example:

```text
TASK:
Design a REST API endpoint.

METHOD:
POST

ENDPOINT:
/api/users

REQUEST:
{
  "name": "Example User",
  "email": "user@example.com"
}

REQUIREMENTS:
- Validate email.
- Require name.
- Return an appropriate error for invalid input.
- Return the created user.

OUTPUT:
Provide:
1. API design
2. Example request
3. Example response
4. Error responses
```

---

# Database Prompts

Database tasks benefit from schema context.

```text
DATABASE:
PostgreSQL

TABLE:
users

COLUMNS:
id
name
email
created_at

TASK:
Write a SQL query that returns users
created in the last 30 days.

REQUIREMENTS:
- Sort newest first.
- Return id, name, and email.
```

The schema removes ambiguity.

---

# Frontend Prompts

For frontend development, specify:

```text
FRAMEWORK:
React

LANGUAGE:
TypeScript

TASK:
Create a responsive login form.

REQUIREMENTS:
- Email field
- Password field
- Submit button
- Validation
- Loading state
- Error message
- Mobile-friendly layout
```

If modifying an existing component, include the relevant code.

---

# Full-Stack Prompts

Large applications should usually be broken into stages.

```text
PROJECT:
Task management application

STACK:
Frontend: React + TypeScript
Backend: FastAPI
Database: PostgreSQL

PHASE 1:
Define requirements.

PHASE 2:
Design database schema.

PHASE 3:
Design API.

PHASE 4:
Implement backend.

PHASE 5:
Implement frontend.

PHASE 6:
Add tests.

PHASE 7:
Review security and performance.
```

This combines coding prompts with task decomposition and prompt chaining.

---

# Code + Explanation

If you need both code and explanation, say so.

```text
OUTPUT:
1. Complete code
2. Explanation of the main logic
3. Example usage
4. Possible improvements
```

Otherwise, the AI may focus mostly on one of these.

---

# Ask for Minimal Changes

When fixing existing code, define the scope.

```text
TASK:
Fix the authentication bug.

CONSTRAINTS:
- Change only the authentication logic.
- Do not modify the database schema.
- Do not change the API response format.
- Preserve existing functionality.
```

This reduces unnecessary changes.

---

# Ask for a Diff

For existing projects, a diff-style response can be useful.

```text
OUTPUT:
Show only the changes required to fix the issue,
followed by a short explanation.
```

This can make code review easier.

---

# Coding Prompt With Constraints

Example:

```text
LANGUAGE:
Python 3.12

TASK:
Create a CSV processing script.

REQUIREMENTS:
- Read a CSV file.
- Validate required columns.
- Remove duplicate records.
- Save the cleaned data.

CONSTRAINTS:
- Use only the Python standard library.
- Do not load the entire file into memory.
- Handle malformed rows safely.

OUTPUT:
Provide the complete script and usage instructions.
```

Constraints can be important when technical requirements are strict.

---

# Coding Prompt With Acceptance Criteria

Acceptance criteria define when the task is considered complete.

```text
TASK:
Create a user registration function.

ACCEPTANCE CRITERIA:
- Valid email is accepted.
- Invalid email is rejected.
- Duplicate email is rejected.
- Password must meet the defined requirements.
- Errors return clear messages.
- Existing users remain unaffected.
```

This gives the AI measurable goals.

---

# Coding Prompt With Edge Cases

Good coding prompts consider unusual inputs.

```text
TASK:
Create a function that calculates an average.

EDGE CASES:
- Empty list
- One value
- Negative numbers
- Very large numbers
- Invalid input
```

Edge cases can reveal problems that normal examples do not.

---

# Coding Prompt With Performance Requirements

When performance matters, state the expected constraint.

```text
TASK:
Find duplicate values in a list.

CONSTRAINT:
The solution should be approximately O(n)
time complexity.
```

Do not request a performance target unless it is actually relevant.

---

# Coding Prompt With Documentation

You can request documentation alongside code.

```text
OUTPUT:
Provide:

1. Implementation
2. Function documentation
3. Usage example
4. Test cases
5. Known limitations
```

---

# Prompt for Explaining Existing Code

```text
TASK:
Explain the following code.

AUDIENCE:
A beginner Python developer.

REQUIREMENTS:
- Explain the overall purpose first.
- Explain each major section.
- Identify important functions.
- Explain the data flow.
- Give a simple example.

CODE:
[CODE]
```

This is useful for learning unfamiliar projects.

---

# Prompt for Learning Programming

```text
ROLE:
Act as a programming instructor.

TOPIC:
Python classes

AUDIENCE:
Beginner

TASK:
Teach the topic.

STRUCTURE:
1. Simple explanation
2. Basic syntax
3. Example
4. Common mistakes
5. Practice exercises
6. Mini project
```

This combines coding with educational prompting.

---

# Before and After

## Weak

```text
Build a login system.
```

## Better

```text
TASK:
Build a user authentication system.

STACK:
Python + FastAPI + PostgreSQL

REQUIREMENTS:
- User registration
- Login
- Password hashing
- Authentication tokens
- Input validation
- Error handling

SECURITY:
Do not store plaintext passwords.

OUTPUT:
1. Architecture
2. Database schema
3. API design
4. Implementation
5. Testing strategy
```

The second prompt gives the AI a much clearer specification.

---

# Common Coding Prompt Mistakes

## 1. No Technology Stack

```text
Build an API.
```

Which language and framework?

---

## 2. No Existing Code

When fixing a bug, provide the relevant code.

---

## 3. No Expected Behavior

Explain what the software should do.

---

## 4. Vague Requirements

"Make it better" is difficult to evaluate.

Define what better means.

---

## 5. Too Many Requirements at Once

For large projects, decompose the work.

---

## 6. No Error Handling Requirements

Important software should define expected failure behavior.

---

## 7. No Acceptance Criteria

Define how success will be measured.

---

## 8. Blindly Trusting Generated Code

AI-generated code should be:

* Reviewed
* Tested
* Run in an appropriate environment
* Checked for security problems
* Validated against requirements

---

# Reusable Coding Prompt Template

```text
# PROJECT
[Project name]

# LANGUAGE
[Language]

# FRAMEWORK / STACK
[Technologies]

# CONTEXT
[Relevant project information]

# TASK
[Specific coding task]

# EXISTING CODE
"""
[Code]
"""

# REQUIREMENTS
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]

# EDGE CASES
- [Edge case 1]
- [Edge case 2]

# ACCEPTANCE CRITERIA
- [Criterion 1]
- [Criterion 2]

# OUTPUT
[Expected response format]
```

---

# Coding Prompt Checklist

Before sending a coding prompt:

* [ ] Is the task specific?
* [ ] Is the programming language defined?
* [ ] Is the framework or environment specified?
* [ ] Is relevant existing code included?
* [ ] Are requirements clear?
* [ ] Are constraints defined?
* [ ] Are edge cases considered?
* [ ] Is expected behavior clear?
* [ ] Are acceptance criteria defined?
* [ ] Is the desired output format specified?
* [ ] Will the generated code be tested and reviewed?

---

# Key Takeaways

1. Good coding prompts provide technical context and clear requirements.
2. Specify the language and framework when they matter.
3. Include existing code when requesting debugging or modifications.
4. Provide exact error messages when debugging.
5. Define expected behavior and acceptance criteria.
6. Include edge cases for important functionality.
7. Use constraints to control implementation decisions.
8. Break large software projects into smaller stages.
9. Generated code should always be reviewed and tested.
10. The best coding prompt is not necessarily the longest one; it is the one that provides the **right technical context and measurable requirements**.

---

## Next

**`03-patterns/02-debugging.md`**

This file will focus specifically on building effective prompts for **debugging, error analysis, root-cause investigation, and code repair**.
