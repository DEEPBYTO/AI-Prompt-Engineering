# Zero-Shot Prompting

Zero-shot prompting is one of the simplest prompt engineering techniques. It means asking an AI model to perform a task **without providing examples of the desired output**.

The model receives the task and instructions directly and attempts to complete it based on its existing capabilities and understanding.

---

## What Is Zero-Shot Prompting?

A zero-shot prompt provides:

```text
Task
+
Instructions
+
Optional Context
```

but **no examples demonstrating the expected answer**.

### Example

```text
Translate the following sentence into Spanish:

"Artificial intelligence is changing the way we work."
```

No example translation is provided. The AI must perform the task directly.

---

## Why Is It Called "Zero-Shot"?

The term "shot" refers to an example provided to the model.

Therefore:

```text
Zero-shot → 0 examples
One-shot  → 1 example
Few-shot  → Multiple examples
```

Zero-shot prompting relies on the model's existing ability to understand the task from instructions alone.

---

# Basic Structure

A simple zero-shot prompt can follow this structure:

```text
TASK:
[Describe what the AI should do]

INPUT:
[Information to process]

REQUIREMENTS:
[Important constraints]

OUTPUT:
[Desired format]
```

### Example

```text
TASK:
Summarize the following article.

REQUIREMENTS:
- Identify the main idea.
- Include the three most important points.
- Keep the summary under 150 words.

OUTPUT:
Use bullet points.

ARTICLE:
"""
[Article text]
"""
```

There are no examples of summaries in the prompt, so this is zero-shot prompting.

---

# Simple Examples

## Classification

```text
Classify the following review as Positive,
Negative, or Neutral:

"The product is easy to use and works perfectly."
```

## Summarization

```text
Summarize the following article in five bullet points:

[ARTICLE]
```

## Translation

```text
Translate the following text into Urdu:

[TEXT]
```

## Extraction

```text
Extract all company names from the following text:

[TEXT]
```

## Rewriting

```text
Rewrite the following paragraph in a professional tone:

[TEXT]
```

## Coding

```text
Write a Python function that checks whether
a number is prime.
```

All of these can be zero-shot prompts because no examples are provided.

---

# Zero-Shot vs. Simple Questions

A simple question can also be a zero-shot prompt.

For example:

```text
What is machine learning?
```

The model receives the task without an example.

However, prompt engineering allows us to make the zero-shot instruction more precise:

```text
Explain machine learning to a beginner.

Requirements:
- Start with a simple definition.
- Use two real-world examples.
- Explain supervised and unsupervised learning.
- Avoid advanced mathematics.
- Finish with five key takeaways.
```

This remains zero-shot because **no examples of the expected output were provided**.

---

# When to Use Zero-Shot Prompting

Zero-shot prompting is useful when:

* The task is straightforward.
* The desired output is easy to describe.
* No specific example is required.
* You want a quick result.
* The model already understands the task well.
* You are testing an initial prompt.

Common applications include:

* Summarization
* Translation
* Classification
* Basic coding
* Information extraction
* Rewriting
* Brainstorming
* General explanations

---

# Advantages

## 1. Simple

Zero-shot prompts are usually easy to write.

```text
Summarize this article in five bullet points.
```

There is no need to create examples.

## 2. Fast

You can define a task and receive an output immediately.

## 3. Flexible

The same prompt can often be used with many different inputs.

## 4. Lower Prompt Complexity

You do not need to include additional example data.

## 5. Good Starting Point

Zero-shot prompting is often the first version of a prompt before testing more advanced approaches.

---

# Limitations

Zero-shot prompting is not ideal for every task.

## 1. Ambiguous Tasks

If the task is unclear, the AI may interpret it differently than expected.

```text
Analyze this.
```

Analyze what?

The instruction needs more context.

---

## 2. Specific Output Styles

If you need a very particular style or structure, instructions alone may not communicate it perfectly.

For example:

```text
Write product descriptions in exactly this style.
```

An example may work better than a verbal description.

---

## 3. Complex Tasks

Multi-step tasks may require additional structure, examples, or decomposition.

---

## 4. Specialized Formats

If the AI needs to produce an unusual or strict format, examples can help demonstrate the expected pattern.

---

# Improving a Zero-Shot Prompt

A weak zero-shot prompt:

```text
Write about AI.
```

### Step 1 — Define the goal

```text
Explain artificial intelligence.
```

### Step 2 — Define the audience

```text
Explain artificial intelligence to a beginner.
```

### Step 3 — Add requirements

```text
Explain artificial intelligence to a beginner.

Cover:
- What AI is
- How AI systems learn
- Three real-world applications
```

### Step 4 — Define output

```text
Explain artificial intelligence to a beginner.

Cover:
- What AI is
- How AI systems learn
- Three real-world applications

Use simple English and clear headings.
Keep the answer under 600 words.
```

It is still zero-shot because **we have not provided an example output**.

---

# Zero-Shot Prompt Template

Use this reusable template:

```text
TASK:
[What should the AI do?]

CONTEXT:
[Relevant background information]

INPUT:
[Information to process]

REQUIREMENTS:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

CONSTRAINTS:
- [Length]
- [Tone]
- [Other limitation]

OUTPUT FORMAT:
[Describe the desired structure]
```

### Example

```text
TASK:
Analyze the following business idea.

CONTEXT:
The business is an online education platform
for university students.

INPUT:
[BUSINESS IDEA]

REQUIREMENTS:
- Identify the target customer.
- Identify the main problem.
- Evaluate the proposed solution.
- Identify major risks.

CONSTRAINTS:
Keep the analysis concise.

OUTPUT FORMAT:
Use these sections:
1. Opportunity
2. Strengths
3. Weaknesses
4. Risks
5. Recommendation
```

---

# Zero-Shot Prompting in Practice

A practical workflow is:

```text
Create Prompt
     ↓
Run Prompt
     ↓
Review Output
     ↓
Identify Problems
     ↓
Improve Instructions
     ↓
Run Again
```

If the result is already reliable, zero-shot prompting may be sufficient.

If the output remains inconsistent, consider techniques such as **few-shot prompting** or **structured prompting**.

---

# Zero-Shot vs. Few-Shot

The key difference is examples.

### Zero-Shot

```text
Classify the following customer review
as Positive, Negative, or Neutral:

"The product is excellent."
```

No examples are provided.

### Few-Shot

```text
Example 1:
Review: "The product is excellent."
Classification: Positive

Example 2:
Review: "The application crashes frequently."
Classification: Negative

Now classify:

Review: "The design is good but the application
is sometimes slow."
```

Examples demonstrate the expected behavior.

---

# Important Principle

Zero-shot prompting does **not** mean writing a short prompt.

A zero-shot prompt can be very detailed:

```text
ROLE
+
CONTEXT
+
TASK
+
INSTRUCTIONS
+
CONSTRAINTS
+
OUTPUT FORMAT
```

As long as it contains **zero examples**, it remains zero-shot.

---

# Best Practices

### 1. Define the task clearly

Avoid vague instructions.

### 2. Provide relevant context

Give the model information needed to understand the situation.

### 3. Specify important requirements

Make critical expectations explicit.

### 4. Define the output format

Especially for structured tasks.

### 5. Test the prompt

Do not assume the first version will work perfectly.

### 6. Add examples only when needed

If instructions are sufficient, zero-shot may be simpler and more efficient.

---

# Common Mistakes

## Mistake 1: Being Too Vague

```text
Analyze this.
```

### Better

```text
Analyze this business idea and identify
its target market, strengths, weaknesses,
and major risks.
```

---

## Mistake 2: Missing Context

```text
Create a strategy.
```

### Better

```text
Create a marketing strategy for a new
mobile productivity application targeting
university students.
```

---

## Mistake 3: No Output Format

If the result needs a specific structure, define it.

```text
Return the analysis using:
Problem
Solution
Market
Risks
Recommendation
```

---

# Zero-Shot Checklist

Before using a zero-shot prompt, check:

* [ ] Is the task clear?
* [ ] Is the goal specific?
* [ ] Is relevant context included?
* [ ] Is the input clearly identified?
* [ ] Are important requirements defined?
* [ ] Are unnecessary constraints avoided?
* [ ] Is the output format clear?
* [ ] Are examples actually unnecessary?
* [ ] Can the output be evaluated?

---

# Key Takeaways

1. Zero-shot prompting uses **no examples**.
2. The AI performs the task using instructions and context.
3. Zero-shot is useful for straightforward and well-defined tasks.
4. A zero-shot prompt can still be detailed and structured.
5. Clear instructions are more important than unnecessary prompt length.
6. Zero-shot prompting is often a good starting point.
7. Complex or highly specific tasks may benefit from examples.
8. Prompt quality should be tested and refined.
9. Zero-shot and few-shot prompting differ primarily in whether examples are provided.
10. If instructions alone produce reliable results, zero-shot prompting may be the simplest approach.

---

## Next

Continue with:

**[Few-Shot Prompting](./02-few-shot.md)**

Learn how examples can guide an AI model toward a specific pattern, format, or behavior.
