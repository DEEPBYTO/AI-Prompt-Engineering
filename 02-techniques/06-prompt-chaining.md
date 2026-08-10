# Prompt Chaining

Prompt chaining is a prompt engineering technique where multiple prompts are connected together so that the output of one prompt becomes the input, context, or starting point for another prompt.

Instead of asking an AI system to complete a complex workflow in one step, the workflow is divided into separate stages.

---

## What Is Prompt Chaining?

A simple prompt chain looks like:

```text
Prompt 1
   ↓
Output 1
   ↓
Prompt 2
   ↓
Output 2
   ↓
Prompt 3
   ↓
Final Output
```

For example:

```text
Prompt 1:
Generate a business idea.

        ↓

Prompt 2:
Analyze the business idea.

        ↓

Prompt 3:
Create an MVP plan.

        ↓

Prompt 4:
Create a launch strategy.
```

Each stage has a specific responsibility.

---

# Prompt Chaining vs. Task Decomposition

These concepts are related but not identical.

### Task Decomposition

Breaks a large task into smaller steps.

```text
1. Research
2. Analyze
3. Plan
4. Implement
```

### Prompt Chaining

Actually connects separate prompts or stages.

```text
Prompt 1 → Output 1 → Prompt 2 → Output 2
```

A task can be decomposed without necessarily using separate prompts.

Prompt chaining turns those stages into a connected workflow.

---

# Basic Prompt Chain

Consider this workflow:

```text
Goal:
Create a YouTube video.
```

Instead of one huge prompt:

```text
Create a complete YouTube video about AI.
```

Use:

```text
Prompt 1:
Identify the target audience and topic angle.

        ↓

Prompt 2:
Create an outline based on the audience and angle.

        ↓

Prompt 3:
Write the script based on the outline.

        ↓

Prompt 4:
Create a title, description, and thumbnail concepts.
```

Each stage receives information from the previous stage.

---

# Why Use Prompt Chaining?

Prompt chaining can help with:

* Complex workflows
* Large tasks
* Multi-stage analysis
* Content pipelines
* Software development
* Research workflows
* Data processing
* AI automation
* Quality control

It allows each stage to focus on a specific objective.

---

# Simple Example

Suppose we want to analyze customer feedback.

### Prompt 1 — Extract Issues

```text
Extract the main problems from this customer feedback:

[FEEDBACK]
```

Output:

```text
1. Slow application
2. Difficult navigation
3. Poor customer support
```

### Prompt 2 — Categorize

The extracted issues become input:

```text
Categorize these problems:

1. Slow application
2. Difficult navigation
3. Poor customer support
```

Output:

```text
Performance:
- Slow application

UX:
- Difficult navigation

Support:
- Poor customer support
```

### Prompt 3 — Recommend Solutions

```text
Suggest solutions for these categorized problems:

[PREVIOUS OUTPUT]
```

Output:

```text
Performance:
Improve backend performance.

UX:
Simplify navigation.

Support:
Reduce support response times.
```

The workflow is chained.

---

# Prompt Chain Architecture

A typical chain can look like:

```text
                 ┌──────────────┐
                 │   Input      │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │   Prompt 1   │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │   Output 1   │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │   Prompt 2   │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │   Output 2   │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │   Prompt 3   │
                 └──────┬───────┘
                        ↓
                 ┌──────────────┐
                 │ Final Output │
                 └──────────────┘
```

Each stage transforms information before passing it forward.

---

# Sequential Prompt Chaining

The most common type is sequential chaining.

```text
Research
   ↓
Summary
   ↓
Analysis
   ↓
Recommendation
```

Example:

```text
Prompt 1:
Summarize the research.

Prompt 2:
Analyze the summarized findings.

Prompt 3:
Identify the major implications.

Prompt 4:
Create recommendations based on the implications.
```

The output of each stage feeds the next stage.

---

# Conditional Prompt Chaining

Sometimes the next step depends on the previous result.

For example:

```text
Prompt 1:
Classify the customer request.

        ↓

If technical issue
        ↓
Prompt 2A:
Create technical support response.

If billing issue
        ↓
Prompt 2B:
Create billing support response.

If general question
        ↓
Prompt 2C:
Create general support response.
```

Conceptually:

```text
                 Classification
                       ↓
          ┌────────────┼────────────┐
          ↓            ↓            ↓
      Technical      Billing      General
          ↓            ↓            ↓
     Response       Response     Response
```

This pattern is useful in AI applications.

---

# Parallel Prompt Chains

Some workflows can process multiple parts independently.

For example, analyzing a product:

```text
                    Product
                       ↓
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
     Market         Technical      Business
     Analysis       Analysis       Analysis
        ↓              ↓              ↓
        └──────────────┼──────────────┘
                       ↓
                Final Evaluation
```

Each branch can use its own prompt.

---

# Prompt Chaining for Research

Research workflows can use multiple stages.

```text
Prompt 1:
Define the research question.

        ↓

Prompt 2:
Identify relevant information.

        ↓

Prompt 3:
Organize the findings.

        ↓

Prompt 4:
Compare different perspectives.

        ↓

Prompt 5:
Create the final report.
```

For serious research, the information should be supported by reliable sources and independently verified.

---

# Prompt Chaining for Content Creation

A content pipeline might look like:

```text
Topic
 ↓
Audience Analysis
 ↓
Ideas
 ↓
Outline
 ↓
Draft
 ↓
Editing
 ↓
Final Content
```

### Prompt 1

```text
Identify the target audience for a YouTube
video about AI productivity.
```

### Prompt 2

```text
Generate five video concepts for this audience.
```

### Prompt 3

```text
Create an outline for the selected concept.
```

### Prompt 4

```text
Write the script using the outline.
```

### Prompt 5

```text
Edit the script for clarity and engagement.
```

This is a content-generation chain.

---

# Prompt Chaining for Coding

Software development can also use chains.

```text
Requirements
     ↓
Architecture
     ↓
Database Design
     ↓
API Design
     ↓
Implementation
     ↓
Testing
     ↓
Review
```

Example:

### Stage 1

```text
Analyze these application requirements
and identify the core features.
```

### Stage 2

```text
Based on the identified features,
design the database schema.
```

### Stage 3

```text
Based on the database schema,
design the API endpoints.
```

### Stage 4

```text
Based on the API design,
generate the implementation.
```

### Stage 5

```text
Review the generated implementation
for bugs and security problems.
```

Each stage builds on the previous one.

---

# Prompt Chaining for Customer Support

A customer-support system might use:

```text
Customer Message
       ↓
Intent Detection
       ↓
Information Extraction
       ↓
Knowledge Retrieval
       ↓
Response Generation
       ↓
Response Review
       ↓
Customer
```

For example:

```text
Prompt 1:
Identify the customer's intent.

Prompt 2:
Extract relevant account or order information.

Prompt 3:
Use the available support information
to determine the appropriate solution.

Prompt 4:
Write a professional response.

Prompt 5:
Check the response for clarity and policy compliance.
```

This allows different stages to specialize in different tasks.

---

# Prompt Chaining for AI Applications

In a real application, prompt chaining can be implemented programmatically.

Conceptually:

```text
user_input = "Customer cannot log in"

result_1 = classify_intent(user_input)

result_2 = extract_information(user_input)

result_3 = generate_solution(result_1, result_2)

result_4 = create_response(result_3)
```

The exact implementation depends on the application and AI platform.

The important concept is:

```text
Output of one stage
        ↓
Input/context for another stage
```

---

# Benefits of Prompt Chaining

## 1. Smaller Tasks

Each prompt can focus on one objective.

## 2. Easier Debugging

If the final result is wrong, you can inspect individual stages.

## 3. Better Control

Developers can control each step independently.

## 4. Reusability

Individual prompts can be reused in different workflows.

## 5. Easier Evaluation

Each stage can have its own evaluation criteria.

## 6. Flexible Workflows

Branches and conditions can be introduced when needed.

---

# Limitations

Prompt chaining also introduces challenges.

## 1. More Complexity

A chain is more complicated than a single prompt.

## 2. More Latency

Multiple AI calls may take longer than one call.

```text
One prompt:
Input → AI → Output

Chain:
Input → AI → AI → AI → Output
```

## 3. More Cost

If each stage requires a separate model request, total usage can increase.

## 4. Error Propagation

An error in an early stage can affect every later stage.

```text
Bad Output 1
     ↓
Bad Input 2
     ↓
Bad Output 2
     ↓
Bad Final Result
```

This is one of the most important problems to consider.

## 5. State Management

Applications need to keep track of information between stages.

---

# Error Propagation

Suppose:

```text
Prompt 1:
Identify the customer issue.

Output:
"The customer is asking about billing."
```

But the actual issue was technical.

Then:

```text
Prompt 2:
Generate a billing solution.
```

The next stage receives incorrect information.

This creates:

```text
Incorrect Classification
        ↓
Incorrect Analysis
        ↓
Incorrect Recommendation
        ↓
Incorrect Response
```

Therefore, important intermediate outputs should be validated.

---

# Validation Between Steps

A stronger workflow can include validation:

```text
Prompt 1
   ↓
Output 1
   ↓
Validation
   ↓
Prompt 2
   ↓
Output 2
   ↓
Validation
   ↓
Final Output
```

For example:

```text
Step 1:
Extract customer information.

Step 2:
Check whether the extracted information
contains all required fields.

Step 3:
Only continue if validation succeeds.
```

This can improve reliability.

---

# Prompt Chaining vs. One Large Prompt

### One Large Prompt

```text
Research the market, analyze competitors,
design the product, create a business model,
make a launch plan, and write the final report.
```

### Prompt Chain

```text
Research
   ↓
Competitor Analysis
   ↓
Product Strategy
   ↓
Business Model
   ↓
Launch Plan
   ↓
Final Report
```

The chain provides more control over the workflow.

However, the single prompt may be preferable if the task is simple enough and the model can reliably complete it.

---

# When Should You Use Prompt Chaining?

Use prompt chaining when:

* The task has multiple stages.
* Different stages require different instructions.
* Intermediate results need to be inspected.
* The workflow has conditional branches.
* You need predictable transformations.
* Different stages have different evaluation criteria.
* You are building an AI-powered application.

Avoid it when a simple prompt can reliably solve the task.

---

# Designing a Good Prompt Chain

## Step 1 — Define the Final Goal

```text
What should the complete system produce?
```

## Step 2 — Identify Major Stages

```text
What transformations are required?
```

## Step 3 — Define Inputs and Outputs

For every stage:

```text
INPUT → PROMPT → OUTPUT
```

## Step 4 — Identify Dependencies

Determine which stages require previous outputs.

## Step 5 — Add Validation

Check important intermediate results.

## Step 6 — Test the Entire Chain

Use multiple realistic inputs.

---

# Example: Complete Business Analysis Chain

```text
INPUT:
Startup idea
```

### Chain

```text
Stage 1
Identify customer problem
        ↓
Stage 2
Define target market
        ↓
Stage 3
Analyze competition
        ↓
Stage 4
Evaluate business model
        ↓
Stage 5
Identify risks
        ↓
Stage 6
Recommend MVP
        ↓
Stage 7
Create final business assessment
```

Each stage has a clear purpose.

---

# Prompt Chain Template

A reusable design template:

```text
# FINAL GOAL
[Desired final result]

# STAGE 1
INPUT:
[Initial input]

TASK:
[Stage 1 task]

OUTPUT:
[Stage 1 output]

# STAGE 2
INPUT:
[Stage 1 output]

TASK:
[Stage 2 task]

OUTPUT:
[Stage 2 output]

# STAGE 3
INPUT:
[Stage 2 output]

TASK:
[Stage 3 task]

OUTPUT:
[Stage 3 output]

# FINAL STAGE
INPUT:
[Previous output]

TASK:
[Final task]

OUTPUT:
[Final result]
```

---

# Best Practices

### 1. Give Each Stage One Clear Responsibility

Avoid making every prompt responsible for everything.

### 2. Keep Intermediate Outputs Useful

Only pass information that the next stage actually needs.

### 3. Validate Important Outputs

Do not blindly trust every intermediate result.

### 4. Handle Errors

Define what should happen if a stage fails.

### 5. Minimize Unnecessary Calls

More prompts do not automatically mean better results.

### 6. Track Dependencies

Know which stage depends on which output.

### 7. Test Individual Stages

Debugging is easier when each stage can be tested separately.

---

# Common Mistakes

## Mistake 1: Creating a Chain for a Simple Task

```text
Prompt 1 → Prompt 2 → Prompt 3
```

for a task that one prompt can solve reliably.

## Mistake 2: Passing Everything Forward

Do not automatically pass every previous output into every stage.

## Mistake 3: No Validation

An early error can contaminate the entire chain.

## Mistake 4: Too Many Stages

Every stage introduces additional complexity, latency, and possible failure.

## Mistake 5: Poor Stage Definitions

Each stage should have a clear input, task, and output.

---

# Prompt Chaining Checklist

Before building a prompt chain:

* [ ] Is the overall task complex enough to justify a chain?
* [ ] Is the final goal clear?
* [ ] Are the stages logically separated?
* [ ] Does each stage have a clear responsibility?
* [ ] Is each input defined?
* [ ] Is each output defined?
* [ ] Are dependencies understood?
* [ ] Are important outputs validated?
* [ ] Is error handling considered?
* [ ] Are unnecessary AI calls avoided?
* [ ] Has the complete workflow been tested?

---

# Key Takeaways

1. Prompt chaining connects multiple prompts into a workflow.
2. The output of one stage can become the input or context for another.
3. Chaining is useful for complex, multi-stage tasks.
4. Chains can be sequential, conditional, parallel, or hierarchical.
5. Prompt chaining provides greater control and easier debugging.
6. Multiple AI calls can increase latency and cost.
7. Errors can propagate from one stage to later stages.
8. Important intermediate results should be validated.
9. Not every task requires prompt chaining.
10. A good prompt chain has a **clear goal, defined stages, controlled data flow, and validation**.

---

## Next

The next section is:

**`03-patterns/01-coding.md`**

This begins practical prompt patterns for real-world use cases, starting with **Coding Prompts**.
