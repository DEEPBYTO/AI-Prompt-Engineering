# Context in Prompt Engineering

Context is the background information provided to an AI system so it can better understand a task, situation, audience, or input.

A clear instruction tells the AI **what to do**.
Context helps explain **what the AI needs to know before doing it**.

Good context can reduce ambiguity, improve relevance, and help the AI produce an output that better matches the actual situation.

---

## What Is Context?

Context is any relevant information that helps the AI understand the task.

For example:

```text
Explain Python.
```

This gives very little context.

A contextual version might be:

```text
I am a first-year computer science student
with no previous programming experience.

Explain Python to me.
```

The AI now knows something about the learner's background.

---

## Why Does Context Matter?

The same instruction can produce very different results depending on the context.

Consider:

```text
Write an email about the project.
```

The AI does not know:

* Which project
* Who the recipient is
* What happened
* What the purpose of the email is
* What action is expected

Now add context:

```text
I am managing a software development project.

The project is two weeks behind schedule because
the backend integration took longer than expected.

The client is a business customer who expects
a professional and transparent update.

Write an email explaining the delay and proposing
a revised completion date.
```

The AI now has enough background to create a much more relevant response.

---

# Types of Context

Context can come in many forms.

## 1. User Context

Information about the person requesting the task.

Examples:

```text
I am a beginner in Python.
```

```text
I am a university student.
```

```text
I have three years of marketing experience.
```

User context helps determine the appropriate level of detail.

---

## 2. Audience Context

Information about who will receive or read the output.

Example:

```text
The presentation is for high-school students.
```

or:

```text
The report will be presented to senior business executives.
```

The same subject may require different language, depth, and examples depending on the audience.

---

## 3. Task Context

Information about what is currently happening.

Example:

```text
We are preparing to launch a new mobile application
next month and need a marketing plan.
```

This gives the AI a reason and situation for the task.

---

## 4. Business Context

Business-related information can make AI-generated content more relevant.

Example:

```text
Our company develops accounting software
for small businesses.

Our primary customers are businesses with
fewer than 50 employees.
```

Then:

```text
Create five marketing ideas for our product.
```

The AI can now create ideas based on the provided business context.

---

## 5. Technical Context

Technical tasks often require technical background.

Example:

```text
The application uses Python, FastAPI, PostgreSQL,
and Docker.

The API is returning a 500 error when users
upload large files.
```

Then:

```text
Help diagnose the problem.
```

Without the technical context, the AI may provide generic advice.

---

## 6. Historical Context

Previous events or decisions can affect the current task.

Example:

```text
We previously tried solution A, but it caused
database performance problems.

We are now evaluating solution B.
```

This helps the AI avoid repeating previously identified problems.

---

## 7. Input Context

Sometimes the actual information being processed is the context.

Example:

```text
Analyze the following customer feedback:

"""
The application is easy to use, but the dashboard
loads slowly and the mobile version is difficult
to navigate.
"""
```

The feedback provides the information needed for analysis.

---

# Relevant vs. Irrelevant Context

More context does not automatically mean better results.

The goal is to provide **relevant context**.

### Too Little

```text
Create a marketing plan.
```

### Useful

```text
We are launching a productivity application
for university students.

The product helps students organize assignments,
deadlines, and study schedules.

Our initial target market is students aged 18–24.
```

### Too Much

Adding unrelated information can make a prompt harder to manage:

```text
We are launching an application.

The founder likes blue.

The office has 14 chairs.

The company was registered on a Tuesday.

The founder's favorite food is pizza.

The product helps students organize assignments.
```

Most of this information is irrelevant to the marketing task.

### Principle

> **Provide enough context to understand the task, but avoid unnecessary information.**

---

# Context and Assumptions

When important context is missing, AI systems may make assumptions.

For example:

```text
Write a business proposal.
```

The AI does not know:

* The industry
* The customer
* The service
* The pricing
* The objective
* The proposal format

Instead of expecting the AI to guess, provide the relevant information.

```text
We provide website development services
to small local businesses.

Our target customers are businesses that
do not currently have a professional website.

Create a proposal offering website design,
development, hosting, and ongoing support.
```

The additional context makes the task much clearer.

---

# Context Windows and Large Inputs

Modern AI systems can process large amounts of information, but that does not mean every piece of information should be included.

For large documents, useful techniques include:

* Providing only relevant sections
* Summarizing background information
* Organizing information into sections
* Clearly labeling important details
* Separating instructions from source material
* Referencing specific parts of the input

### Example

```text
BACKGROUND:
[Relevant project information]

CURRENT PROBLEM:
[Specific issue]

SOURCE DATA:
"""
[Relevant data]
"""

TASK:
Analyze the problem and suggest three solutions.
```

This structure helps keep the task organized.

---

# Context Should Be Structured

For complex tasks, labels can make context easier to understand.

Example:

```text
PROJECT:
AI-powered education platform

TARGET USERS:
University students

CURRENT STAGE:
Early development

MAIN PROBLEM:
Low user retention

GOAL:
Identify possible reasons for user drop-off

TASK:
Analyze the information and suggest five
ways to improve retention.
```

Structured context is easier to read, update, and reuse.

---

# Context vs. Instructions

These two concepts are related but different.

### Context

Provides information:

```text
The target customers are university students.
```

### Instruction

Defines an action:

```text
Create a marketing strategy for these customers.
```

A complete prompt might combine both:

```text
CONTEXT:
The product is an AI study assistant designed
for university students.

INSTRUCTION:
Create a marketing strategy for the product.
```

A useful rule:

> **Context describes the situation. Instructions describe the action.**

---

# Context vs. Input

Context and input can sometimes overlap, but they serve different purposes.

### Context

Background information:

```text
The company sells project management software
to small businesses.
```

### Input

Information to process:

```text
Customer feedback:
"The reporting dashboard is difficult to use."
```

### Combined

```text
CONTEXT:
The company sells project management software
to small businesses.

INPUT:
"The reporting dashboard is difficult to use."

TASK:
Identify the customer's main problem and
suggest three improvements.
```

This separation becomes especially useful for analysis tasks.

---

# Context Injection

Context can be dynamically added to a prompt depending on the situation.

For example, a customer-support system might use:

```text
CUSTOMER:
[Customer name]

PRODUCT:
[Product name]

ORDER STATUS:
[Order information]

CUSTOMER MESSAGE:
[Customer's message]

TASK:
Write a helpful response.
```

The same prompt template can then be reused for many customers.

This is useful when building:

* Chatbots
* AI assistants
* Automation systems
* Customer-support tools
* AI applications
* Internal business tools

---

# Context in AI Applications

Context is particularly important when AI is integrated into software.

A simple AI application might receive:

```text
User question
+
User preferences
+
Relevant database information
+
Previous conversation
+
System instructions
```

The application can combine these elements before sending the request to the AI model.

Conceptually:

```text
User Request
      +
Relevant Context
      +
Instructions
      ↓
   AI Model
      ↓
   Response
```

The quality of the context provided to the model can strongly affect the usefulness of the response.

---

# Context Management

When working with large or complex tasks, context should be managed carefully.

Useful practices include:

### 1. Keep it relevant

Remove information that does not affect the task.

### 2. Organize it

Use headings and labels.

### 3. Prioritize important information

Put critical information where it is easy to identify.

### 4. Keep instructions separate

Clearly distinguish instructions from source material.

### 5. Update outdated information

Old context can lead to inappropriate recommendations.

### 6. Avoid unnecessary repetition

Repeating the same information can make prompts harder to maintain.

---

# Example: Improving Context

## Weak

```text
Help me with my startup.
```

## Better

```text
I am building a SaaS product for small businesses.

The product helps businesses manage customer
requests and support tickets.

We are currently in the early development stage
and have not launched publicly.

Help me identify the most important features
for the first version.
```

## Even More Structured

```text
BUSINESS:
SaaS customer-support platform

TARGET USERS:
Small businesses

PRODUCT:
Customer requests and support-ticket management

STAGE:
Pre-launch / early development

CURRENT GOAL:
Define the first version of the product

TASK:
Identify the most important MVP features.

OUTPUT:
Return:
1. Essential features
2. Optional features
3. Features to postpone
4. Reasoning for each recommendation
```

The final version gives the AI a structured understanding of the situation.

---

# Context Checklist

Before sending a complex prompt, ask:

* [ ] Does the AI know the situation?
* [ ] Does it know who the output is for?
* [ ] Does it have the relevant background information?
* [ ] Is important input data included?
* [ ] Is irrelevant information removed?
* [ ] Is the context organized?
* [ ] Are outdated assumptions removed?
* [ ] Are instructions separated from context?
* [ ] Is the context sufficient for the task?

---

# Key Takeaways

1. Context provides the background needed to understand a task.
2. Good context reduces unnecessary assumptions.
3. Relevant context is more valuable than excessive context.
4. Context can describe the user, audience, business, project, or technical environment.
5. Context and instructions serve different purposes.
6. Structured context is easier to manage and reuse.
7. Large inputs should be organized and filtered for relevance.
8. Context is especially important in AI applications and automation.
9. Dynamic context allows the same prompt template to work across different situations.
10. Effective prompt engineering uses **relevant, structured, and purposeful context**.

---

## Next

Continue with:

**[01-techniques](../02-techniques/)**

The next section introduces practical prompt engineering techniques, starting with **Zero-Shot Prompting**.
