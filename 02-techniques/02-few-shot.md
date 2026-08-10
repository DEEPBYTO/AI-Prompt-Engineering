# Few-Shot Prompting

Few-shot prompting is a prompt engineering technique where one or more examples are provided to an AI model to demonstrate the desired task, pattern, format, or style.

Instead of relying only on instructions, the model can learn from the examples included in the prompt.

---

## What Is Few-Shot Prompting?

A few-shot prompt typically contains:

```text id="j7x4rp"
Instructions
+
Examples
+
New Input
```

For example:

```text id="q9f4sa"
Classify each customer review as Positive or Negative.

Example 1:
Review: "The application is excellent."
Classification: Positive

Example 2:
Review: "The application crashes frequently."
Classification: Negative

Now classify:
Review: "The design is good, but the application is slow."
```

The examples demonstrate how the task should be performed.

---

# Why Is It Called "Few-Shot"?

The word **shot** refers to an example provided to the model.

```text
Zero-shot → 0 examples
One-shot  → 1 example
Few-shot  → A small number of examples
```

Few-shot prompting does not require a large dataset. A small number of carefully selected examples can sometimes be enough to demonstrate the desired pattern.

---

# Basic Structure

A simple few-shot prompt can follow this structure:

```text id="p9e1v7"
TASK:
[Describe the task]

EXAMPLE 1:
Input: [Example input]
Output: [Expected output]

EXAMPLE 2:
Input: [Example input]
Output: [Expected output]

NEW INPUT:
[Actual input]

OUTPUT:
[Expected result]
```

The examples should demonstrate the behavior you want the model to reproduce.

---

# Example: Classification

Suppose we want to classify customer feedback.

### Without Examples

```text id="j9mt1d"
Classify this review as Positive, Negative,
or Neutral:

"The product is useful but the interface is confusing."
```

The model must infer the classification rules.

### With Examples

```text id="a4c7q0"
Classify customer reviews as Positive, Negative, or Neutral.

Example 1:
Review: "The product is excellent and easy to use."
Classification: Positive

Example 2:
Review: "The application crashes every day."
Classification: Negative

Example 3:
Review: "The product works, but it needs more features."
Classification: Neutral

Now classify:
Review: "The application is useful, but the interface is confusing."
```

The examples provide a reference pattern.

---

# Example: Output Formatting

Few-shot prompting can teach a specific output format.

```text id="q7v2nh"
Convert product information into a short product description.

Example 1:

Product:
Wireless Keyboard

Description:
A compact wireless keyboard designed for
comfortable typing at home or work.

Example 2:

Product:
USB-C Hub

Description:
A versatile USB-C hub that expands connectivity
with multiple ports for modern devices.

Now create a description for:

Product:
Wireless Mouse
```

The model can infer the desired length and style from the examples.

---

# Example: Data Extraction

Few-shot prompting can demonstrate which information should be extracted.

```text id="z2w0pd"
Extract the company name and industry.

Example 1:
Input:
"TechNova develops cloud software for small businesses."

Output:
Company: TechNova
Industry: Cloud Software

Example 2:
Input:
"GreenFarm produces organic agricultural products."

Output:
Company: GreenFarm
Industry: Agriculture

Now process:

Input:
"SkyLabs develops AI-powered tools for education."
```

Expected pattern:

```text id="4j78r9"
Company: SkyLabs
Industry: AI / Education
```

---

# Example: Writing Style

Examples can communicate writing style more effectively than abstract instructions.

```text id="9g3b7p"
Write short professional product announcements.

Example:

Product:
AI Analytics Platform

Announcement:
Introducing a smarter way to understand your
business data. Our AI Analytics Platform helps
teams turn complex data into actionable insights.

Now write an announcement for:

Product:
AI Customer Support Platform
```

The example demonstrates:

* Tone
* Length
* Structure
* Level of detail
* Style

---

# Example: Classification With Rules

Few-shot examples can also demonstrate subtle distinctions.

```text id="u2z8ek"
Classify the message as:
Urgent, Normal, or Informational.

Example 1:
Message: "The production server is down."
Classification: Urgent

Example 2:
Message: "Can we schedule a meeting next week?"
Classification: Normal

Example 3:
Message: "The office will be closed tomorrow."
Classification: Informational

Now classify:
Message: "The payment system has stopped processing transactions."
```

The examples establish a pattern for how urgency is determined.

---

# Few-Shot Prompting vs. Zero-Shot Prompting

## Zero-Shot

No examples:

```text id="f7h1d3"
Classify this review as Positive or Negative:

"The product is easy to use."
```

## Few-Shot

Examples are included:

```text id="9z3p0b"
Example:
"The product is excellent." → Positive

Example:
"The product is unusable." → Negative

Now classify:
"The product is easy to use."
```

### Main Difference

```text
Zero-Shot
Instruction → Task

Few-Shot
Instruction → Examples → Task
```

---

# When Should You Use Few-Shot Prompting?

Few-shot prompting is especially useful when:

* The task has a specific pattern.
* Output formatting is difficult to describe.
* The classification rules are subtle.
* You need a consistent writing style.
* The desired behavior is unusual.
* A simple instruction produces inconsistent results.
* Examples communicate the requirement better than words.

Common applications include:

* Classification
* Information extraction
* Formatting
* Data transformation
* Writing style
* Content generation
* Structured outputs
* Text labeling

---

# Advantages

## 1. Demonstrates the Desired Pattern

Examples show the model exactly what successful input/output pairs look like.

## 2. Improves Consistency

When examples are well designed, outputs can become more consistent with the demonstrated pattern.

## 3. Handles Complex Instructions

Some tasks are difficult to describe precisely with instructions alone.

## 4. Controls Style

Examples can communicate tone, structure, vocabulary, and formatting.

## 5. Useful for Specialized Tasks

Few-shot prompting can help when the desired behavior is domain-specific.

---

# Limitations

Few-shot prompting also has limitations.

## 1. Uses More Context

Examples increase the amount of information included in the prompt.

## 2. Example Quality Matters

Poor examples can teach the wrong pattern.

## 3. Inconsistent Examples Can Cause Problems

If examples contradict each other, the intended behavior becomes unclear.

## 4. Too Many Examples Can Be Unnecessary

Adding examples does not automatically improve the prompt.

## 5. Examples May Bias the Output

The model can reproduce patterns from examples that were not intended.

---

# How to Choose Good Examples

Example selection is one of the most important parts of few-shot prompting.

## 1. Make Examples Relevant

Choose examples that are similar to the actual task.

Bad:

```text id="9d2lkh"
Example:
A completely unrelated task.
```

Better:

```text id="c3r2m1"
Example:
A task using the same input and output structure
as the target problem.
```

---

## 2. Make Examples Clear

Each example should have an obvious relationship between input and output.

```text id="k8x5i4"
Input:
Customer says the application is too slow.

Output:
Problem: Performance
```

---

## 3. Demonstrate Important Edge Cases

If a task contains unusual cases, examples can show how they should be handled.

For example:

```text id="x9e0pr"
Example:
Input: "The product works well, but delivery was late."

Output:
Product: Positive
Delivery: Negative
```

This demonstrates that different aspects can receive different classifications.

---

## 4. Keep Examples Consistent

Use the same output structure across examples.

### Good

```text id="w7p6q2"
Input: ...
Output: Category: A

Input: ...
Output: Category: B
```

### Poor

```text id="g0d4a1"
Input: ...
Output: A

Input: ...
Output: The category is B because...
```

Inconsistent formats can make the intended pattern less clear.

---

# Example Ordering

The order of examples can sometimes matter.

A useful approach is to arrange examples from:

```text id="4d6p3v"
Simple
  ↓
Moderate
  ↓
Complex
```

This creates a progressively richer demonstration of the task.

However, example ordering should be tested rather than assumed to always produce better results.

---

# Example Diversity

Examples should be representative rather than identical.

Suppose you are building a sentiment classifier.

Instead of:

```text id="g1n8w5"
"This product is excellent." → Positive
"This product is amazing." → Positive
"This product is great." → Positive
```

A more useful set may cover different cases:

```text id="m0v6ak"
"The product is excellent." → Positive

"The application crashes constantly." → Negative

"The product works, but the interface needs improvement." → Neutral
```

This demonstrates the boundaries between categories.

---

# Few-Shot Prompt Template

A reusable template:

```text id="9h3n1x"
TASK:
[Describe the task]

RULES:
[Important instructions]

EXAMPLE 1:
Input:
[Example input]

Output:
[Expected output]

EXAMPLE 2:
Input:
[Example input]

Output:
[Expected output]

EXAMPLE 3:
Input:
[Example input]

Output:
[Expected output]

NEW INPUT:
[Actual input]

OUTPUT:
Follow the demonstrated pattern.
```

You do not always need three examples. Use the smallest number that clearly demonstrates the required behavior.

---

# Before and After

## Before

```text id="q5c8f4"
Extract information from this text.

"John works at TechNova as a software engineer."
```

The expected extraction format is unclear.

## After

```text id="h4d9s2"
Extract the person's name, company, and job title.

Example 1:

Input:
"Sarah works at GreenTech as a data analyst."

Output:
Name: Sarah
Company: GreenTech
Job Title: Data Analyst

Example 2:

Input:
"Ali is a product manager at SoftLabs."

Output:
Name: Ali
Company: SoftLabs
Job Title: Product Manager

Now process:

Input:
"John works at TechNova as a software engineer."
```

The examples demonstrate the exact output structure.

---

# Few-Shot Prompting for Coding

Few-shot prompting can also demonstrate coding conventions.

```text id="q3c8ye"
Convert natural-language requirements into Python
function signatures.

Example:

Requirement:
Calculate the average of a list of numbers.

Output:
def calculate_average(numbers):
    pass

Example:

Requirement:
Check whether a string is a palindrome.

Output:
def is_palindrome(text):
    pass

Now create a function signature for:

Requirement:
Find the largest number in a list.
```

The model can infer the desired coding style and format.

---

# Few-Shot Prompting for Business

Examples can establish a consistent business-writing format.

```text id="3v5x7p"
Create concise business value propositions.

Example:

Product:
Project Management Software

Value Proposition:
Help small teams organize projects,
track deadlines, and collaborate efficiently.

Example:

Product:
Accounting Software

Value Proposition:
Help small businesses manage finances,
invoices, and expenses from one platform.

Now create a value proposition for:

Product:
AI Customer Support Software
```

---

# Common Mistakes

## Mistake 1: Poor Examples

If the examples are incorrect, the model may learn the wrong behavior.

## Mistake 2: Inconsistent Formatting

Keep input/output structure consistent.

## Mistake 3: Too Many Examples

Use enough examples to demonstrate the pattern, but avoid unnecessary repetition.

## Mistake 4: Unrepresentative Examples

Examples should resemble real inputs.

## Mistake 5: Hidden Rules

If an important rule is not obvious from the examples, state it explicitly.

---

# Few-Shot Evaluation

Few-shot prompts should be tested using multiple inputs.

For example:

```text id="h8m1yc"
Example Set
     ↓
Test Input 1
Test Input 2
Test Input 3
Test Input 4
Test Input 5
     ↓
Compare Results
     ↓
Identify Failures
     ↓
Improve Examples
```

Do not evaluate a few-shot prompt using only one successful example.

---

# Few-Shot Checklist

Before using a few-shot prompt:

* [ ] Are the examples relevant?
* [ ] Are the examples correct?
* [ ] Is the input/output relationship clear?
* [ ] Are examples consistently formatted?
* [ ] Do examples cover important cases?
* [ ] Are the examples representative?
* [ ] Are there unnecessary examples?
* [ ] Are hidden rules explicitly explained?
* [ ] Has the prompt been tested with new inputs?

---

# Key Takeaways

1. Few-shot prompting provides examples to demonstrate desired behavior.
2. Examples can communicate patterns that are difficult to describe with instructions alone.
3. Good examples should be relevant, accurate, clear, and consistent.
4. Few-shot prompting is useful for classification, formatting, extraction, and style control.
5. More examples do not automatically mean better results.
6. Diverse examples can demonstrate important distinctions.
7. Poor examples can produce poor or biased results.
8. Few-shot prompting uses more context than zero-shot prompting.
9. The best number of examples depends on the task.
10. Few-shot prompts should be tested with new inputs, not just the provided examples.

---

## Next

Continue with:

**[Role Prompting](./03-role-prompting.md)**

Learn how assigning a role or perspective can help define the expected expertise, communication style, and task context.
