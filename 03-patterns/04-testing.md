# Testing Prompts

Testing prompts help AI create, analyze, improve, and debug software tests.

AI can assist with:

* Unit tests
* Integration tests
* End-to-end tests
* Test cases
* Edge cases
* Regression tests
* Test coverage
* Mocking
* Test-driven development
* Test analysis

The goal is not simply to generate more tests. The goal is to create **useful tests that verify expected behavior and detect meaningful failures**.

---

# What Is a Testing Prompt?

A weak prompt:

```text
Write tests for this code.
```

A stronger prompt:

```text
LANGUAGE:
Python 3.12

FRAMEWORK:
pytest

TASK:
Create unit tests for the following function.

REQUIREMENTS:
- Test normal inputs.
- Test boundary values.
- Test invalid inputs.
- Test empty input.
- Test expected errors.

CODE:
[CODE]

OUTPUT:
Provide the complete test file and explain
what each test verifies.
```

The second prompt gives the AI a clear testing target.

---

# Why Use AI for Testing?

AI can help developers:

* Generate initial test cases
* Identify missing edge cases
* Create test data
* Explain failed tests
* Suggest regression tests
* Improve test coverage
* Convert requirements into tests
* Generate mocks
* Review existing tests

AI-generated tests should still be reviewed because a test can be syntactically correct while testing the wrong behavior.

---

# Types of Software Tests

Different tests serve different purposes.

```text
Unit Tests
   ↓
Test individual components

Integration Tests
   ↓
Test components working together

End-to-End Tests
   ↓
Test complete user workflows
```

A good testing strategy uses the appropriate level for each requirement.

---

# Unit Testing Prompts

Unit tests focus on small pieces of code such as:

* Functions
* Methods
* Classes
* Small modules

Example:

```text
TASK:
Create unit tests for this function.

FUNCTION:
calculate_total(price, quantity)

REQUIREMENTS:
- Test normal values.
- Test zero quantity.
- Test negative values.
- Test decimal prices.
- Test invalid input.

FRAMEWORK:
pytest
```

---

# Testing Normal Cases

Start with expected valid behavior.

```text
INPUT:
price = 100
quantity = 2

EXPECTED:
200
```

Prompt:

```text
Create a test that verifies the function
returns 200 for price=100 and quantity=2.
```

Normal cases establish the basic contract.

---

# Testing Edge Cases

Edge cases are inputs near the boundaries of expected behavior.

Examples:

```text
0
1
-1
empty string
empty list
very large number
maximum allowed value
minimum allowed value
```

Prompt:

```text
Identify important edge cases for this function.

For each edge case provide:
1. Input
2. Expected result
3. Reason it matters
```

This can reveal cases that ordinary tests miss.

---

# Testing Invalid Inputs

A strong test suite should verify how software handles invalid data.

Example:

```text
VALID:
"example@email.com"

INVALID:
"example"
""
None
```

Prompt:

```text
Create tests for valid and invalid email inputs.

Verify that:
- Valid emails are accepted.
- Invalid emails are rejected.
- Empty values are handled correctly.
```

---

# Testing Error Handling

Tests should verify expected failures.

Example:

```text
TASK:
Test division by zero.

EXPECTED:
The function raises ZeroDivisionError.
```

Or, for an application:

```text
EXPECTED:
Invalid input returns HTTP 400.
```

The test should verify the intended error behavior rather than merely checking that "something failed."

---

# Boundary Testing

Boundary values are especially important.

Suppose:

```text
Minimum age: 18
Maximum age: 65
```

Useful tests include:

```text
17 → Invalid
18 → Valid
19 → Valid
64 → Valid
65 → Valid
66 → Invalid
```

Prompt:

```text
Identify the boundary values for this requirement
and create tests for each boundary.
```

---

# Parameterized Tests

When the same logic needs many inputs, parameterized tests can reduce duplication.

Example concept:

```text
INPUT     EXPECTED
2         4
3         9
4         16
5         25
```

Prompt:

```text
Create parameterized pytest tests for these
input/output pairs.
```

This keeps test suites concise.

---

# Test Cases From Requirements

Requirements can be converted directly into test cases.

Requirement:

```text
Users must enter a valid email address.
```

Possible tests:

```text
Valid email → Accepted
Invalid email → Rejected
Empty email → Rejected
Missing email → Rejected
```

Prompt:

```text
Convert the following requirements into
a comprehensive test case list.

REQUIREMENTS:
[Requirements]
```

This is useful before implementation begins.

---

# Test-Driven Development

Test-Driven Development, or TDD, follows a cycle:

```text
Write Test
    ↓
Implement
    ↓
Run Test
    ↓
Refactor
    ↓
Repeat
```

Often summarized as:

```text
RED → GREEN → REFACTOR
```

### RED

Write a test that fails.

### GREEN

Implement enough functionality to pass it.

### REFACTOR

Improve the implementation while keeping tests passing.

---

# TDD Prompt

```text
TASK:
Implement this feature using TDD.

FEATURE:
Create a function that validates passwords.

PROCESS:
1. Define the expected behavior.
2. Write failing tests.
3. Implement the minimum required code.
4. Explain why the implementation passes.
5. Suggest refactoring opportunities.

FRAMEWORK:
pytest
```

---

# Testing From Examples

Examples can define expected behavior.

```text
INPUT:
"hello"

EXPECTED:
"HELLO"

INPUT:
"Python"

EXPECTED:
"PYTHON"

INPUT:
""

EXPECTED:
""
```

Prompt:

```text
Create tests from these examples.
Then identify additional edge cases.
```

This is especially useful when specifications are example-driven.

---

# Regression Testing

A regression test ensures that a previously fixed bug does not return.

Example:

```text
BUG:
Users could create duplicate accounts
with the same email.

FIX:
Duplicate email validation was added.

REGRESSION TEST:
Attempt to create two accounts
with the same email and verify that
the second request is rejected.
```

Prompt:

```text
Create a regression test for this bug fix.

BUG:
[Bug description]

FIX:
[Fix description]
```

---

# Integration Testing

Integration tests verify that multiple components work together.

Example:

```text
API
 ↓
Service
 ↓
Database
```

Prompt:

```text
TASK:
Create an integration test for the user registration flow.

VERIFY:
1. API accepts valid registration.
2. User is created in the database.
3. Response contains the expected data.
4. Duplicate registration is rejected.
```

Integration tests are useful when individual unit tests cannot verify the interaction between components.

---

# End-to-End Testing

End-to-end tests simulate complete user workflows.

Example:

```text
Open website
    ↓
Register
    ↓
Login
    ↓
Create item
    ↓
View item
    ↓
Logout
```

Prompt:

```text
Create an end-to-end test for this workflow.

USER JOURNEY:
1. Open login page.
2. Register a new account.
3. Log in.
4. Create a task.
5. Verify the task appears.
6. Log out.
```

---

# API Testing

API tests should verify:

* Status codes
* Response structure
* Validation
* Authentication
* Error handling
* Business rules

Example:

```text
METHOD:
POST

ENDPOINT:
/api/users

VALID REQUEST:
{
  "name": "Test User",
  "email": "test@example.com"
}

EXPECTED:
HTTP 201
```

Then test invalid requests:

```text
Missing name → HTTP 400
Invalid email → HTTP 400
Duplicate email → appropriate error
```

---

# Database Testing

Database-related tests can verify:

* Data insertion
* Updates
* Deletion
* Constraints
* Relationships
* Transactions
* Query results

Prompt:

```text
TASK:
Create integration tests for the orders repository.

TEST:
- Create order.
- Retrieve order.
- Update order.
- Delete order.
- Verify missing order behavior.
- Verify invalid foreign key behavior.
```

---

# Mocking

Mocks can isolate a unit from external dependencies.

For example:

```text
Application
    ↓
Payment API
```

During a unit test, you may mock the payment API.

Prompt:

```text
TASK:
Create unit tests for this payment service.

REQUIREMENTS:
- Mock the external payment API.
- Test successful payment.
- Test failed payment.
- Test timeout.
- Verify the API was called with correct parameters.
```

The goal is to test your code without relying on the real external service.

---

# Mocking Carefully

Too much mocking can make tests unrealistic.

Avoid:

```text
Mock everything.
```

Instead:

```text
Mock external dependencies where isolation
is necessary, while keeping important
integration behavior covered separately.
```

This creates a balance between unit and integration testing.

---

# Test Coverage

Coverage measures which parts of the code are exercised by tests.

A prompt can ask:

```text
Analyze the existing tests and identify
important code paths that are not covered.
```

Do not assume:

```text
100% coverage = 100% correctness
```

High coverage can still contain weak tests.

The quality of assertions and scenarios matters.

---

# Branch Coverage

Suppose code contains:

```text
if user_is_admin:
    ...
else:
    ...
```

A good test suite should exercise both branches when both are important.

Prompt:

```text
Identify all meaningful branches in this function
and suggest tests that exercise each one.
```

---

# Mutation Testing Concept

Mutation testing evaluates whether tests can detect intentional changes to the code.

Conceptually:

```text
Original Code
      ↓
Introduce Small Bug
      ↓
Run Tests
      ↓
Should Fail
```

If the tests still pass, the test suite may be too weak.

Prompt:

```text
Review these tests and identify small changes
to the implementation that should cause
the tests to fail.
```

This helps evaluate test effectiveness.

---

# Property-Based Testing

Instead of testing only specific examples, property-based testing checks general rules.

Example:

```text
For every valid positive number:
square(number) >= 0
```

Prompt:

```text
Identify useful properties for this function
and suggest property-based tests.
```

This can be valuable for algorithms and data transformations.

---

# Test Data Generation

AI can help generate representative test data.

Example:

```text
TASK:
Generate test data for a user registration system.

INCLUDE:
- Valid users
- Invalid emails
- Empty fields
- Duplicate users
- Long names
- Boundary values
```

Avoid using real sensitive personal information as test data.

---

# Testing Security

Security-related behavior can also be tested.

Examples include:

* Authentication failures
* Authorization checks
* Input validation
* Session expiration
* Access control
* Rate limiting

Prompt:

```text
Create tests for the authorization system.

VERIFY:
- Authorized users can access permitted resources.
- Unauthorized users are rejected.
- Users cannot access another user's private data.
- Missing authentication is rejected.
```

Security testing for important systems should be reviewed by qualified professionals.

---

# Testing Performance

Performance tests can verify behavior under expected load.

Prompt:

```text
TASK:
Design a performance test for the API.

TARGET:
500 requests per second.

MEASURE:
- Response time
- Error rate
- Throughput

OUTPUT:
Test strategy and example implementation.
```

Do not invent performance targets without a real requirement.

---

# Testing AI Systems

AI systems require different testing considerations.

Possible evaluation dimensions include:

* Accuracy
* Consistency
* Safety
* Format compliance
* Hallucination rate
* Instruction following
* Robustness

Example:

```text
TASK:
Evaluate an AI customer-support assistant.

TEST:
Provide 100 representative customer questions.

MEASURE:
- Correctness
- Relevance
- Policy compliance
- Response format
```

AI evaluation should use representative datasets and clearly defined criteria.

---

# Testing Prompts Themselves

Prompt engineering systems can also be tested.

Suppose a prompt should produce JSON.

Test:

```text
INPUT:
[Different representative inputs]

EXPECTED:
Valid JSON matching the required schema.
```

A prompt test suite might look like:

```text
Prompt
  ↓
Test Inputs
  ↓
AI Outputs
  ↓
Evaluator
  ↓
Pass / Fail
```

This is important when prompts are part of production software.

---

# Prompt Regression Testing

When a prompt is changed:

```text
Old Prompt
   ↓
Evaluation Dataset
   ↓
Baseline Results
```

Then:

```text
New Prompt
   ↓
Same Evaluation Dataset
   ↓
Compare Results
```

This helps determine whether the new prompt actually improved the system.

---

# Before and After

## Weak

```text
Write tests for my login system.
```

## Strong

```text
PROJECT:
FastAPI authentication system

TASK:
Create a test suite for login.

TEST:

1. Valid credentials
   Expected: HTTP 200 + token

2. Wrong password
   Expected: HTTP 401

3. Unknown user
   Expected: HTTP 401

4. Missing email
   Expected: validation error

5. Missing password
   Expected: validation error

6. Account disabled
   Expected: access denied

7. Repeated failed attempts
   Expected: rate-limit behavior

FRAMEWORK:
pytest

OUTPUT:
Provide the test structure and implementation.
```

The second prompt defines the behavior that should be verified.

---

# Testing Prompt Template

```text
# ROLE
Act as a senior QA engineer.

# PROJECT
[Project]

# LANGUAGE / STACK
[Technologies]

# TASK
Create or improve tests for:

[Feature / Code]

# EXPECTED BEHAVIOR
[Expected behavior]

# TEST TYPES
- Unit
- Integration
- End-to-end
- Regression

# TEST SCENARIOS
- [Scenario 1]
- [Scenario 2]
- [Scenario 3]

# EDGE CASES
- [Edge case 1]
- [Edge case 2]

# ERROR CASES
- [Error case 1]
- [Error case 2]

# CONSTRAINTS
[Testing constraints]

# OUTPUT
1. Test strategy
2. Test cases
3. Test implementation
4. Missing coverage
5. Verification instructions
```

---

# Testing Checklist

Before creating a testing prompt:

* [ ] Is the expected behavior defined?
* [ ] Are normal cases included?
* [ ] Are edge cases considered?
* [ ] Are invalid inputs tested?
* [ ] Are error conditions tested?
* [ ] Are important branches covered?
* [ ] Are regression cases included?
* [ ] Is the correct test level selected?
* [ ] Are external dependencies mocked appropriately?
* [ ] Are acceptance criteria measurable?
* [ ] Will the tests actually detect meaningful failures?

---

# Key Takeaways

1. Testing prompts should define expected behavior clearly.
2. Test normal cases, boundary cases, invalid inputs, and failures.
3. Unit, integration, and end-to-end tests serve different purposes.
4. Regression tests protect against previously fixed bugs returning.
5. Mock external dependencies when appropriate, but avoid excessive mocking.
6. High code coverage does not automatically mean high-quality testing.
7. Test cases should be based on requirements and real user behavior.
8. AI-generated tests must themselves be reviewed.
9. Prompts and AI systems can also be evaluated with structured test suites.
10. Good testing prompts focus on **behavior, evidence, coverage, and verification**.

---

## Next

**`03-patterns/05-research.md`**

This file will cover **research prompts, source analysis, evidence evaluation, fact-checking, synthesis, and structured research workflows**.
