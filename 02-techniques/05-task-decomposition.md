# Task Decomposition

Task decomposition is a prompt engineering technique that breaks a complex task into smaller, clearly defined steps.

Instead of asking an AI system to solve a large problem all at once, you divide the problem into manageable parts and define what should happen at each stage.

---

## What Is Task Decomposition?

A complex request might look like:

```text
Create a complete business plan for my startup.
```

This combines many different tasks:

* Understanding the business
* Identifying customers
* Researching the market
* Analyzing competitors
* Defining the product
* Creating a business model
* Estimating costs
* Identifying risks
* Planning growth

A decomposed version makes those steps explicit.

```text
1. Define the customer problem.
2. Identify the target market.
3. Analyze competitors.
4. Define the product.
5. Develop the business model.
6. Identify risks.
7. Create a launch strategy.
8. Summarize the final plan.
```

The complex problem becomes a sequence of smaller tasks.

---

# Why Decompose Tasks?

Complex tasks often contain multiple objectives.

Without decomposition, an AI may:

* Skip important steps
* Mix different objectives
* Produce an incomplete answer
* Focus too much on one part
* Make assumptions
* Produce inconsistent results

Task decomposition provides a clearer workflow.

---

# Basic Structure

A decomposed prompt can use:

```text
TASK:
[Main objective]

STEPS:
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Step 4]

FINAL OUTPUT:
[Desired final result]
```

### Example

```text
TASK:
Evaluate this startup idea.

STEPS:
1. Identify the target customer.
2. Identify the problem being solved.
3. Analyze the proposed solution.
4. Identify competitors.
5. Evaluate the business model.
6. Identify major risks.
7. Recommend improvements.

FINAL OUTPUT:
Provide a structured evaluation with a final recommendation.
```

---

# Simple vs. Complex Tasks

Not every task needs decomposition.

### Simple

```text
Translate this sentence into Urdu.
```

No decomposition is necessary.

### Complex

```text
Develop a complete go-to-market strategy for a new SaaS product.
```

This may benefit from several stages.

A useful principle:

> **Use decomposition when the task contains multiple meaningful sub-tasks.**

---

# Step-by-Step Decomposition

A complex problem can be broken down progressively.

For example:

```text
Build an AI startup.
```

This is too broad.

### Step 1 — Define the problem

```text
Identify a specific problem that AI could solve.
```

### Step 2 — Define the customer

```text
Identify who experiences this problem.
```

### Step 3 — Design the solution

```text
Propose an AI-powered solution.
```

### Step 4 — Evaluate the market

```text
Analyze the potential market and competitors.
```

### Step 5 — Define the business model

```text
Suggest possible revenue models.
```

### Step 6 — Plan execution

```text
Create an MVP development and launch plan.
```

The original broad idea becomes a sequence of actionable tasks.

---

# Sequential Decomposition

In sequential decomposition, each step logically follows the previous one.

```text
Research
   ↓
Analysis
   ↓
Solution
   ↓
Implementation
   ↓
Evaluation
```

Example:

```text
1. Analyze the customer problem.
2. Based on that problem, define product requirements.
3. Based on the requirements, design the MVP.
4. Create an implementation plan.
5. Define success metrics.
```

This is useful when later steps depend on earlier findings.

---

# Parallel Decomposition

Some tasks can be divided into independent areas.

For example:

```text
Analyze this startup from:

1. Technical perspective
2. Business perspective
3. Marketing perspective
4. Financial perspective
```

These areas can be analyzed independently before combining the results.

Conceptually:

```text
              ┌─ Technical
              │
Main Task ────┼─ Business
              │
              ├─ Marketing
              │
              └─ Financial
                    ↓
              Final Analysis
```

---

# Hierarchical Decomposition

Large tasks can contain smaller sub-tasks.

Example:

```text
Build an e-commerce platform
```

can become:

```text
1. Product System
   1.1 Product listings
   1.2 Search
   1.3 Categories

2. Customer System
   2.1 Registration
   2.2 Login
   2.3 Profiles

3. Order System
   3.1 Cart
   3.2 Checkout
   3.3 Order tracking

4. Payment System
   4.1 Payment processing
   4.2 Payment confirmation
   4.3 Refund handling
```

This is hierarchical decomposition.

---

# Decomposition for Coding

Task decomposition is particularly useful for software development.

Instead of:

```text
Build me a complete web application.
```

Use:

```text
PROJECT:
Build a task management web application.

STEPS:

1. Define the application requirements.
2. Design the database schema.
3. Design the API endpoints.
4. Implement authentication.
5. Implement task management.
6. Add validation and error handling.
7. Create the frontend.
8. Connect frontend and backend.
9. Add tests.
10. Prepare deployment instructions.
```

This creates a development roadmap rather than one huge instruction.

---

# Decomposition for Research

Research tasks often contain multiple stages.

```text
TASK:
Research the impact of AI on education.

STEPS:

1. Define the research question.
2. Identify major applications of AI in education.
3. Identify potential benefits.
4. Identify risks and limitations.
5. Compare different viewpoints.
6. Identify gaps in existing research.
7. Summarize the findings.
```

For real research, each stage should use appropriate sources and verification.

---

# Decomposition for Content Creation

A content task can also be divided.

Instead of:

```text
Create a YouTube video about AI.
```

Use:

```text
TASK:
Create a YouTube video about AI for beginners.

STEPS:

1. Identify the target audience.
2. Define the main educational objective.
3. Create a strong hook.
4. Build the video outline.
5. Write the script.
6. Add examples.
7. Create a conclusion.
8. Suggest a title and thumbnail concept.
```

Each stage has a distinct purpose.

---

# Decomposition for Business Analysis

```text
TASK:
Evaluate a new SaaS business idea.

STEPS:

1. Identify the customer.
2. Define the customer problem.
3. Evaluate the proposed solution.
4. Analyze the competitive landscape.
5. Evaluate possible revenue models.
6. Identify operational challenges.
7. Identify major risks.
8. Suggest an MVP.
9. Create a launch strategy.
10. Provide a final recommendation.
```

This makes it easier to ensure that important areas are not forgotten.

---

# Step Dependencies

Not all steps are independent.

Consider:

```text
Identify Customer
       ↓
Understand Problem
       ↓
Design Solution
       ↓
Define Product
```

The later steps depend on earlier decisions.

A good decomposition should reflect these dependencies.

---

# Avoiding Unnecessary Decomposition

Breaking every task into many tiny steps can make prompts unnecessarily complicated.

### Over-decomposed

```text
1. Open the document.
2. Read the first sentence.
3. Read the second sentence.
4. Read the third sentence.
5. Think about the topic.
...
```

This usually adds unnecessary complexity.

### Better

```text
1. Read the document.
2. Identify the main arguments.
3. Summarize the conclusions.
```

Decompose at the level that actually improves clarity.

---

# Decomposition and Output

A task can be decomposed internally but still require a concise final answer.

For example:

```text
TASK:
Evaluate this startup.

STEPS:
1. Analyze the customer.
2. Analyze the market.
3. Analyze the product.
4. Analyze the business model.
5. Analyze the risks.

FINAL OUTPUT:
Provide a concise summary of the most important findings.
```

The process can be detailed while the final result remains focused.

---

# Example: Before and After

## Before

```text
Create a complete marketing strategy for my business.
```

## After

```text
BUSINESS:
Online clothing store

TARGET MARKET:
Young adults

TASK:
Create a marketing strategy.

STEPS:

1. Define the target customer.
2. Identify customer needs.
3. Define the brand positioning.
4. Suggest marketing channels.
5. Create a content strategy.
6. Suggest promotional campaigns.
7. Define key performance indicators.
8. Create a 30-day launch plan.

FINAL OUTPUT:
Present the strategy using clear headings and tables.
```

The second version makes the scope much clearer.

---

# Task Decomposition With Other Techniques

Task decomposition works well with other prompt engineering techniques.

## With Role Prompting

```text
ROLE:
Act as a senior product manager.

TASK:
Plan an MVP.

STEPS:
1. Identify user problems.
2. Define requirements.
3. Prioritize features.
4. Create the MVP roadmap.
```

## With Few-Shot Prompting

Examples can demonstrate how each stage should be performed.

## With Structured Prompting

The entire workflow can be organized into labeled sections.

## With Output Constraints

The final response can be limited to specific formats.

---

# Multi-Stage Prompting

For very complex projects, it may be better to use multiple prompts instead of one enormous prompt.

For example:

```text
Prompt 1
Research
   ↓
Prompt 2
Analysis
   ↓
Prompt 3
Planning
   ↓
Prompt 4
Implementation
   ↓
Prompt 5
Evaluation
```

This approach can make each stage easier to inspect and correct.

---

# Example: AI Product Development

A complete AI product project might be decomposed into:

```text
PHASE 1 — Problem
Identify the customer problem.

PHASE 2 — Research
Analyze existing solutions.

PHASE 3 — Product
Define the product requirements.

PHASE 4 — AI
Determine where AI provides value.

PHASE 5 — Engineering
Define the technical architecture.

PHASE 6 — MVP
Prioritize the minimum required features.

PHASE 7 — Testing
Define tests and evaluation criteria.

PHASE 8 — Launch
Create the deployment and launch plan.
```

This approach can turn a vague objective into an actionable roadmap.

---

# Decomposition and Verification

One advantage of decomposition is that individual steps can be checked separately.

For example:

```text
Research
   ↓
Verify Research
   ↓
Analysis
   ↓
Verify Analysis
   ↓
Final Recommendation
```

Instead of only checking the final answer, important intermediate results can also be reviewed.

This is especially useful for:

* Research
* Data analysis
* Software development
* Business planning
* Complex decision support

---

# Common Mistakes

## Mistake 1: Decomposing Too Little

```text
Build a complete company strategy.
```

This may be too broad.

## Mistake 2: Decomposing Too Much

Breaking a simple task into dozens of steps creates unnecessary complexity.

## Mistake 3: Ignoring Dependencies

Some steps depend on earlier decisions.

## Mistake 4: No Final Objective

The steps should ultimately lead toward a clear outcome.

## Mistake 5: Mixing Different Objectives

Keep unrelated tasks separated when possible.

---

# Task Decomposition Checklist

Before decomposing a task, ask:

* [ ] Is the task actually complex?
* [ ] What are the major sub-tasks?
* [ ] Which steps depend on others?
* [ ] Which steps can happen independently?
* [ ] Are any steps unnecessary?
* [ ] Does each step contribute to the main objective?
* [ ] Should the process be sequential or parallel?
* [ ] Should the task use multiple prompts?
* [ ] How will each stage be evaluated?
* [ ] What should the final output contain?

---

# Key Takeaways

1. Task decomposition breaks complex problems into smaller tasks.
2. It can improve clarity and reduce overlooked requirements.
3. Sequential decomposition works well when steps depend on one another.
4. Parallel decomposition works when multiple areas can be analyzed independently.
5. Hierarchical decomposition can organize large projects into sub-tasks.
6. Avoid decomposing simple tasks unnecessarily.
7. Complex workflows may benefit from multiple prompts.
8. Intermediate results can be evaluated before continuing.
9. Task decomposition works well with structured prompting and role prompting.
10. The goal is to turn a **complex objective into a clear, manageable workflow**.

---

## Next

Continue with:

**[Prompt Chaining](./06-prompt-chaining.md)**

Learn how multiple prompts can be connected so that the output of one stage becomes the input for the next stage.
