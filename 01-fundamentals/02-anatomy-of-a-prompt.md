# Anatomy of a Prompt

A well-designed prompt is made up of different components that help an AI system understand **what to do, why it should do it, what information it should use, and how the result should be presented**.

Not every prompt needs every component. Simple tasks may require only an instruction, while complex tasks may benefit from context, examples, constraints, and a specific output format.

---

## The Basic Anatomy

A useful prompt can be understood through these components:

```text
┌─────────────────────────┐
│        ROLE             │
├─────────────────────────┤
│        GOAL             │
├─────────────────────────┤
│      CONTEXT            │
├─────────────────────────┤
│     INSTRUCTIONS        │
├─────────────────────────┤
│      CONSTRAINTS        │
├─────────────────────────┤
│       EXAMPLES          │
├─────────────────────────┤
│    OUTPUT FORMAT        │
└─────────────────────────┘
```

These components can be combined depending on the task.

---

# 1. Role

A role gives the AI a perspective or professional context for the task.

### Example

```text
Act as a Python programming instructor.
```

Then provide the task:

```text
Act as a Python programming instructor.

Explain Python functions to a beginner.
```

The role can help establish the type of response you expect.

### Common Roles

```text
Act as a teacher.
Act as a software engineer.
Act as a marketing strategist.
Act as a research assistant.
Act as a technical writer.
Act as a business analyst.
```

### Important

A role is **optional**.

You should not add a role just to make a prompt longer. Use one when the perspective or expertise is useful for the task.

---

# 2. Goal

The goal describes the desired outcome.

A clear goal answers:

> What should the AI accomplish?

### Weak

```text
Python
```

### Better

```text
Explain Python to a beginner.
```

### More Specific

```text
Create a beginner-friendly introduction to Python
that explains what Python is, where it is used,
and why beginners might learn it.
```

A clear goal gives the AI a defined destination.

---

# 3. Context

Context provides information that helps the AI understand the situation.

Without sufficient context, an AI may have to make assumptions.

### Example

```text
I am a first-year computer science student
with no previous programming experience.
```

Combined with the task:

```text
I am a first-year computer science student
with no previous programming experience.

Explain object-oriented programming to me.
```

The AI now has information about the intended audience.

### Useful Context

Context may include:

* Audience
* Background
* Industry
* Existing knowledge
* Project information
* Available resources
* Previous decisions
* Business requirements
* Technical requirements

---

# 4. Instructions

Instructions tell the AI what actions to perform.

### Example

```text
Explain the concept.

Give three real-world examples.

Compare it with procedural programming.

Finish with five key takeaways.
```

Instructions should be clear and actionable.

### Weak Instruction

```text
Make it good.
```

### Better Instruction

```text
Use simple language, explain unfamiliar terms,
and provide practical examples.
```

---

# 5. Constraints

Constraints define boundaries for the response.

They can control:

* Length
* Language
* Audience
* Scope
* Tone
* Number of examples
* Topics to include
* Topics to avoid
* Technical requirements

### Example

```text
Keep the explanation under 500 words.

Use simple English.

Include exactly three examples.

Avoid advanced mathematical notation.
```

Constraints are particularly useful when the output needs to fit a specific requirement.

---

# 6. Examples

Examples show the AI what kind of output you want.

This is especially useful when the desired result is difficult to describe using instructions alone.

### Example

Suppose you want short product descriptions.

You could provide:

```text
Example:

Product: Wireless Keyboard

Description:
A compact wireless keyboard designed for comfortable
typing at home, school, or work.
```

Then:

```text
Create a similar description for:
Product: Wireless Mouse
```

Examples can communicate:

* Style
* Structure
* Length
* Formatting
* Level of detail
* Expected reasoning pattern

Providing examples is commonly known as **few-shot prompting** when examples are included in the prompt.

---

# 7. Input Data

The input is the information the AI needs to process.

For example:

```text
Analyze the following customer feedback:

"Your application is easy to use, but the login
process is too slow."
```

The quoted text is the input data.

For larger tasks, clearly separating instructions from input can make the prompt easier to understand.

### Example

```text
INSTRUCTIONS:
Identify the main customer complaint.

INPUT:
"Your application is easy to use, but the login
process is too slow."
```

---

# 8. Output Format

Output format defines how the AI should present its answer.

Without an output format, the AI may choose a structure you don't want.

### No Format

```text
Analyze this business idea.
```

### Defined Format

```text
Analyze this business idea.

Return the answer using:

1. Problem
2. Target Customer
3. Value Proposition
4. Revenue Model
5. Main Risks
6. Recommendation
```

You can also request structured formats such as:

### Table

```text
Return the result as:

| Feature | Benefit | Risk |
|---------|---------|------|
```

### JSON

```text
Return valid JSON with these fields:

{
  "summary": "",
  "strengths": [],
  "weaknesses": [],
  "recommendation": ""
}
```

### Bullet Points

```text
Return five bullet points.
```

---

# 9. Tone and Style

Tone defines how the response should sound.

Examples:

```text
Use a professional tone.
```

```text
Write in a friendly and conversational style.
```

```text
Use a concise technical style.
```

```text
Explain the topic in a beginner-friendly way.
```

Tone is useful for communication, marketing, writing, education, and many other tasks.

---

# 10. Audience

The same information may need to be explained differently depending on who will read it.

### Example

```text
Explain artificial intelligence to a 12-year-old.
```

versus:

```text
Explain artificial intelligence to a machine learning engineer.
```

The topic is the same, but the expected depth and terminology are different.

Always define the audience when it materially affects the answer.

---

# 11. Separators

Separators help distinguish different parts of a prompt.

Common separators include:

```text
---
```

```text
### 
```

```text
"""
```

or labeled sections:

```text
CONTEXT:
...

TASK:
...

INPUT:
...

OUTPUT:
...
```

### Example

```text
CONTEXT:
You are helping a small software startup.

TASK:
Analyze the following customer feedback.

INPUT:
"""
The application is useful, but the onboarding
process is confusing.
"""

OUTPUT:
Return:
- Main problem
- Possible cause
- Recommended solution
```

Separating sections makes complex prompts easier to read, modify, and maintain.

---

# 12. A Complete Prompt

Here is an example combining several components:

```text
ROLE:
Act as a senior Python instructor.

CONTEXT:
The learner is a beginner with no previous
programming experience.

GOAL:
Teach the learner the basics of Python functions.

INSTRUCTIONS:
1. Explain what a function is.
2. Explain parameters and return values.
3. Provide three simple examples.
4. Explain each example.

CONSTRAINTS:
- Use simple English.
- Avoid advanced terminology.
- Keep the explanation under 800 words.

OUTPUT FORMAT:
Use these sections:
1. Concept
2. Syntax
3. Examples
4. Common Mistakes
5. Key Takeaways
```

This prompt gives the AI a clear task, relevant context, specific instructions, boundaries, and an expected structure.

---

# Prompt Components Are Modular

You do not need to use every component in every prompt.

For example, a simple task might only need:

```text
Summarize this article in five bullet points.
```

A more complex task might need:

```text
Role
+ Context
+ Goal
+ Instructions
+ Constraints
+ Examples
+ Output Format
```

The principle is:

> **Use the components that improve clarity for the specific task.**

More instructions do not automatically mean a better prompt.

---

# A Reusable Prompt Framework

For complex tasks, this structure can be used as a starting point:

```text
ROLE:
[Who should the AI act as?]

CONTEXT:
[What background information does the AI need?]

GOAL:
[What should the AI accomplish?]

INPUT:
[What information should the AI process?]

INSTRUCTIONS:
[What should the AI do?]

CONSTRAINTS:
[What limitations or requirements should it follow?]

EXAMPLES:
[What examples demonstrate the desired result?]

OUTPUT FORMAT:
[How should the final answer be structured?]
```

You can remove any section that is unnecessary.

---

# Before and After

## Before

```text
Write a business plan.
```

## After

```text
ROLE:
Act as a startup business strategist.

CONTEXT:
The business is an online software service
targeting small businesses.

GOAL:
Create a concise business plan.

INSTRUCTIONS:
Cover the target market, value proposition,
business model, marketing strategy, and major risks.

CONSTRAINTS:
Use practical assumptions and keep the plan
under 1,000 words.

OUTPUT FORMAT:
Use clear headings and bullet points.
Finish with three recommended next steps.
```

The second prompt provides much more useful direction without requiring unnecessary complexity.

---

# Anatomy Checklist

Before using a complex prompt, ask:

* [ ] Is the goal clear?
* [ ] Is enough context provided?
* [ ] Are the instructions actionable?
* [ ] Are important constraints defined?
* [ ] Is the input clearly separated?
* [ ] Is an example useful?
* [ ] Is the audience defined?
* [ ] Is the tone appropriate?
* [ ] Is the output format clear?
* [ ] Can the result be evaluated?

You do not need every item. Choose the components that matter for the task.

---

# Key Takeaways

1. A prompt is more than just a question.
2. Clear goals help define the desired outcome.
3. Context reduces unnecessary assumptions.
4. Instructions tell the AI what to do.
5. Constraints define boundaries.
6. Examples can demonstrate the desired pattern.
7. Output formats make results easier to use.
8. Roles and audience can provide useful perspective.
9. Separators help organize complex prompts.
10. Good prompt engineering is about **clarity and purpose, not unnecessary length**.

---

## Next

Continue with:

**[Instructions](./03-instructions.md)**

Learn how to write clear, precise, and actionable instructions for AI systems.
