# Instructions in Prompt Engineering

Instructions are one of the most important components of a prompt. They tell an AI system **what actions to perform** and help turn a general request into a clearly defined task.

A good instruction should be clear, specific, actionable, and relevant to the desired outcome.

---

## What Are Instructions?

An instruction is a direct command or requirement given to an AI system.

### Simple instruction

```text
Explain machine learning.
```

### More specific instructions

```text
Explain machine learning to a beginner.

Define the concept first.
Give three real-world examples.
Explain the difference between machine learning
and traditional programming.
Finish with five key takeaways.
```

The second prompt provides several explicit instructions, making the expected task clearer.

---

## Why Instructions Matter

AI systems can interpret broad requests in many different ways.

Compare:

```text
Write about cybersecurity.
```

with:

```text
Explain cybersecurity to a beginner.

Cover:
1. What cybersecurity is
2. Three common cyber threats
3. Three practical protection methods

Use simple English and real-world examples.
Keep the answer under 600 words.
```

The second version gives the AI a clearer path to the desired result.

Good instructions can help improve:

* Relevance
* Consistency
* Structure
* Usability
* Task completion
* Output quality

However, instructions cannot guarantee that an AI response will always be correct.

---

# Characteristics of Good Instructions

## 1. Be Clear

Avoid instructions that can have multiple interpretations.

### Weak

```text
Make this better.
```

### Better

```text
Rewrite this paragraph to make it clearer and easier
for a general audience to understand.
```

The second instruction defines what "better" means.

---

## 2. Be Specific

Tell the AI exactly what you need when the task requires precision.

### Weak

```text
Write a marketing post.
```

### Specific

```text
Write a LinkedIn post announcing the launch of a
new AI productivity tool for small businesses.

Include:
- A strong opening
- Three key benefits
- A short call to action

Keep it under 150 words.
```

Specific instructions reduce unnecessary assumptions.

---

## 3. Use Actionable Verbs

Use verbs that describe the required action.

Useful verbs include:

```text
Explain
Summarize
Compare
Analyze
Classify
Extract
Generate
Rewrite
Translate
Evaluate
Identify
Organize
Transform
Create
```

### Example

Instead of:

```text
This article and its main points.
```

Use:

```text
Summarize this article and identify its five main points.
```

The second version clearly defines the action.

---

# 4. Break Complex Tasks Into Steps

Large tasks can be easier to handle when divided into smaller operations.

### General instruction

```text
Analyze this business idea.
```

### Decomposed instruction

```text
Analyze this business idea.

Follow these steps:

1. Identify the target customer.
2. Identify the problem being solved.
3. Explain the proposed solution.
4. Analyze the potential market.
5. Identify major risks.
6. Suggest three improvements.
7. Give a final recommendation.
```

Task decomposition makes the workflow easier to understand and evaluate.

---

# 5. Define the Desired Outcome

The AI should understand what a successful response looks like.

### Weak

```text
Help me learn Python.
```

### Better

```text
Create a 30-day beginner Python learning plan.

The learner should be able to write simple Python
programs by the end of the plan.

Include daily topics, exercises, and expected outcomes.
```

The desired outcome gives the task direction.

---

# 6. Specify the Audience

Instructions can change depending on who will receive the output.

### Example

```text
Explain blockchain to a high-school student.
```

Compared with:

```text
Explain blockchain to a software engineer
who understands distributed systems.
```

The topic is the same, but the expected depth is different.

---

# 7. Specify the Tone When Necessary

Tone can be part of the instruction.

Examples:

```text
Use a professional tone.
```

```text
Use a friendly and conversational tone.
```

```text
Use a concise technical tone.
```

```text
Write in a beginner-friendly style.
```

For tasks where tone does not matter, it can be omitted.

---

# 8. Define Length

If the response needs a specific size, say so.

Examples:

```text
Summarize this article in 100 words.
```

```text
Give me five bullet points.
```

```text
Write a 60-second video script.
```

```text
Keep the explanation under 800 words.
```

Avoid unrealistic precision when the task does not require it.

---

# 9. Define Output Structure

Tell the AI how the result should be organized.

### Example

```text
Analyze this startup idea.

Return the result using:

## Problem
## Target Market
## Solution
## Business Model
## Risks
## Recommendation
```

Another example:

```text
Return the result as:

| Feature | Benefit | Risk |
|---|---|---|
```

A defined structure makes outputs easier to read and reuse.

---

# 10. Separate Instructions From Input

For complex prompts, clearly distinguish what the AI should **do** from the information it should **process**.

### Example

```text
TASK:
Summarize the following customer feedback.

INSTRUCTIONS:
- Identify the main complaint.
- Identify the customer's positive feedback.
- Suggest one improvement.

INPUT:
"""
The application is useful, but the login process
is slow. I like the dashboard and its simple design.
"""
```

This separation makes the prompt easier to understand and modify.

---

# 11. Use Constraints When Necessary

Constraints define what the AI should or should not do.

### Example

```text
Explain quantum computing.

Requirements:
- Use simple English.
- Avoid advanced mathematics.
- Include two real-world examples.
- Keep the explanation under 500 words.
```

Constraints can control:

* Length
* Scope
* Language
* Format
* Complexity
* Number of examples
* Required sections

Do not add unnecessary constraints. Every constraint should serve a purpose.

---

# 12. Avoid Conflicting Instructions

Conflicting instructions can make a prompt harder to follow.

### Conflicting

```text
Write a very detailed explanation.

Keep the answer under 50 words.
```

These requirements may conflict depending on the topic.

### Better

```text
Provide a concise explanation of the main concepts.

Keep the answer under 150 words.
```

Instructions should work together rather than compete with each other.

---

# 13. Prioritize Important Requirements

When a prompt contains many requirements, organize them clearly.

### Example

```text
TASK:
Create a product description.

REQUIRED:
- Explain the main benefit.
- Mention the target customer.
- Include a call to action.

STYLE:
- Professional
- Concise

LIMIT:
- Maximum 150 words
```

This makes the requirements easier to identify.

---

# 14. Tell the AI What to Avoid

Sometimes specifying exclusions is useful.

### Example

```text
Explain artificial intelligence to a beginner.

Avoid:
- Unnecessary technical jargon
- Complex mathematical formulas
- Historical details unrelated to the explanation
```

Use negative constraints when they prevent a known problem.

---

# 15. Use Examples When Instructions Are Not Enough

Some output styles are difficult to describe.

Instead of explaining the desired style with many words, provide an example.

### Example

```text
Create short product descriptions.

Example:

Product:
Wireless Keyboard

Description:
A compact wireless keyboard designed for comfortable
typing at home, school, or work.

Now create a similar description for:
Wireless Mouse
```

Examples can communicate structure, style, length, and level of detail simultaneously.

---

# Instruction Patterns

Here are some reusable instruction patterns.

## Explain

```text
Explain [TOPIC] to [AUDIENCE].

Start with a simple definition.
Give [NUMBER] examples.
Finish with key takeaways.
```

## Summarize

```text
Summarize the following text.

Extract:
- Main idea
- Key arguments
- Important facts
- Final conclusion

Keep the summary under [NUMBER] words.
```

## Compare

```text
Compare [A] and [B].

Cover:
- Definition
- Advantages
- Disadvantages
- Main differences
- Best use cases

Return the result as a table.
```

## Analyze

```text
Analyze [INPUT].

Identify:
1. Strengths
2. Weaknesses
3. Opportunities
4. Risks

Finish with three recommendations.
```

## Rewrite

```text
Rewrite the following text.

Requirements:
- Preserve the original meaning.
- Improve clarity.
- Remove unnecessary repetition.
- Use a professional tone.
```

---

# Before and After

## Before

```text
Make a website plan.
```

## After

```text
Create a website development plan for a small
software startup.

Include:

1. Project goals
2. Target audience
3. Required pages
4. Core features
5. Technology options
6. Development phases
7. Testing
8. Launch plan

Return the result as a table with:
Phase | Tasks | Deliverables
```

The improved version clearly defines the task, scope, required information, and output structure.

---

# Instructions Should Not Be Unnecessarily Long

Longer does not automatically mean better.

### Overcomplicated

```text
Please carefully and thoroughly think about and consider
all possible aspects of this topic and then provide a
very comprehensive answer while making sure that you
explain everything in a detailed and understandable way...
```

### Better

```text
Analyze the topic from three perspectives:

1. Technical
2. Business
3. Practical

Use clear headings and provide one example for each.
```

The second version is shorter but more actionable.

---

# Instruction Refinement

A useful process for improving instructions is:

```text
Initial Instruction
       ↓
Test
       ↓
Review Output
       ↓
Identify Problem
       ↓
Add or Change Instruction
       ↓
Test Again
```

### Example

**Version 1**

```text
Write a YouTube script about AI.
```

**Problem:** Too broad.

**Version 2**

```text
Write a 5-minute YouTube script explaining
how generative AI works for beginners.
```

**Problem:** The structure is still undefined.

**Version 3**

```text
Write a 5-minute YouTube script explaining
how generative AI works for beginners.

Structure:
1. Hook
2. Simple explanation
3. Real-world example
4. Common misconception
5. Conclusion

Use conversational language.
```

The instruction becomes more useful through iteration.

---

# Instruction Checklist

Before using an instruction, ask:

* [ ] Is the requested action clear?
* [ ] Is the goal defined?
* [ ] Is the audience clear when necessary?
* [ ] Is enough context available?
* [ ] Are important requirements explicit?
* [ ] Are constraints necessary and realistic?
* [ ] Is the output structure clear?
* [ ] Are there conflicting requirements?
* [ ] Would an example improve clarity?
* [ ] Can the result be evaluated?

---

# Key Takeaways

1. Instructions tell the AI **what to do**.
2. Clear instructions reduce ambiguity.
3. Specific instructions are useful for complex tasks.
4. Actionable verbs make tasks easier to interpret.
5. Complex tasks can be divided into smaller steps.
6. Audience, tone, length, and format can be specified when relevant.
7. Constraints should be purposeful rather than excessive.
8. Conflicting instructions should be avoided.
9. Examples can communicate desired output patterns.
10. Good instructions should be **clear, actionable, relevant, and testable**.

---

## Next

Continue with:

**[Context](./04-context.md)**

Learn how context provides the background information an AI system needs to understand and complete a task effectively.
