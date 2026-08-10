# Structured Prompting

Structured prompting is a technique for organizing a prompt into clear sections so that the AI can distinguish between the task, context, input, requirements, constraints, and expected output.

Instead of writing one large paragraph, structured prompts use labels, headings, lists, and defined formats.

---

## What Is Structured Prompting?

A simple prompt might look like:

```text
Analyze this business idea and tell me if it is good.
```

A structured version separates the important components:

```text
ROLE:
Act as a startup business strategist.

CONTEXT:
We are building an AI-powered education platform
for university students.

TASK:
Evaluate the business idea.

ANALYZE:
- Target market
- Customer problem
- Competition
- Revenue model
- Risks

OUTPUT:
1. Opportunity
2. Strengths
3. Weaknesses
4. Risks
5. Recommendation
```

The second prompt is easier to understand, modify, and reuse.

---

# Why Structure Matters

A structured prompt can help:

* Separate instructions from input
* Reduce ambiguity
* Make requirements easier to identify
* Improve consistency
* Simplify prompt maintenance
* Make prompts reusable
* Make outputs easier to evaluate

Structure is especially useful for complex tasks.

---

# Basic Prompt Structure

A general structure is:

```text
ROLE:
[Optional role]

CONTEXT:
[Background information]

TASK:
[What the AI should do]

INPUT:
[Information to process]

REQUIREMENTS:
[Important requirements]

CONSTRAINTS:
[Limitations]

OUTPUT FORMAT:
[Expected response structure]
```

Not every prompt needs every section.

Use only the sections that add value.

---

# Section 1: Role

The role defines a useful perspective when necessary.

```text
ROLE:
Act as a senior software engineer.
```

For simple tasks, this can be omitted.

---

# Section 2: Context

Context explains the situation.

```text
CONTEXT:
The application is a web-based learning platform
for university students.
```

This helps the AI understand the environment in which the task exists.

---

# Section 3: Task

The task defines the main action.

```text
TASK:
Identify the most important features for the
first version of the application.
```

The task should be clear and actionable.

---

# Section 4: Input

Input is the information the AI needs to process.

```text
INPUT:
"""
The application allows students to create
study schedules, track assignments, and
receive AI-generated explanations.
"""
```

For large inputs, clear delimiters can make the boundary obvious.

---

# Section 5: Requirements

Requirements describe important things that must be included.

```text
REQUIREMENTS:
- Identify essential features.
- Explain why each feature matters.
- Consider the target audience.
- Prioritize features for an MVP.
```

---

# Section 6: Constraints

Constraints define limits.

```text
CONSTRAINTS:
- Keep the analysis under 800 words.
- Avoid unnecessary technical terminology.
- Focus only on the first version.
```

Constraints should be relevant and realistic.

---

# Section 7: Output Format

The output format defines how the result should be organized.

```text
OUTPUT FORMAT:

| Feature | Priority | Reason |
|---|---|---|
```

Or:

```text
OUTPUT FORMAT:
1. Executive Summary
2. Key Findings
3. Risks
4. Recommendations
```

---

# Delimiters

Delimiters help separate different parts of a prompt.

Common delimiters include:

```text
"""
Text
"""
```

```text
<text>
Text
</text>
```

```text
---
Text
---
```

```text
### INPUT
Text
```

The specific delimiter is usually less important than using it consistently and clearly.

---

# Example: Text Analysis

A structured analysis prompt:

```text
TASK:
Analyze the following customer feedback.

CONTEXT:
The product is a mobile banking application.

INPUT:
"""
The application is easy to use, but transfers
sometimes fail and customer support takes too
long to respond.
"""

ANALYZE:
- Positive feedback
- Main complaints
- Potential product problems
- Suggested improvements

OUTPUT:
Use the following structure:

## Positive Feedback
## Problems
## Recommendations
```

This is much easier to maintain than one long paragraph.

---

# Structured Prompting for Coding

Structured prompts are especially useful for programming tasks.

```text
ROLE:
Act as a senior Python developer.

PROJECT:
Customer management application.

TECHNOLOGY:
Python + FastAPI + PostgreSQL.

TASK:
Create an API endpoint for retrieving customer data.

REQUIREMENTS:
- Accept a customer ID.
- Validate the ID.
- Return customer information.
- Handle missing customers.

OUTPUT:
Provide:
1. Python code
2. Explanation
3. Example request
4. Example response
```

The model can clearly distinguish the project details from the actual coding task.

---

# Structured Prompting for Research

```text
ROLE:
Act as a research assistant.

TOPIC:
Artificial intelligence in education.

TASK:
Create a research overview.

COVER:
- Current applications
- Benefits
- Risks
- Limitations
- Future research areas

REQUIREMENTS:
- Distinguish established findings from speculation.
- Identify areas requiring further research.

OUTPUT:
Use clear headings and concise explanations.
```

For serious research, structured prompting should be combined with reliable sources and verification.

---

# Structured Prompting for Business

```text
ROLE:
Act as a business strategist.

BUSINESS:
AI-powered customer support platform.

TARGET MARKET:
Small and medium-sized businesses.

CURRENT STAGE:
Early development.

TASK:
Evaluate the business opportunity.

ANALYZE:
- Customer problem
- Market
- Competition
- Business model
- Risks
- Growth opportunities

OUTPUT:
Return:

1. Opportunity
2. Strengths
3. Weaknesses
4. Risks
5. Recommendations
```

---

# Structured Prompting for Content Creation

```text
ROLE:
Act as a professional content strategist.

PLATFORM:
YouTube

TOPIC:
Artificial intelligence for students

AUDIENCE:
University students

TASK:
Create five video ideas.

REQUIREMENTS:
- Each idea must solve a specific problem.
- Include a strong hook.
- Avoid misleading clickbait.

OUTPUT:

| # | Title | Hook | Target Problem |
|---|---|---|---|
```

---

# Structured Prompting for Data Extraction

```text
TASK:
Extract information from the provided text.

INPUT:
"""
TechNova was founded in 2022 by Ahmed Khan.
The company develops AI software for businesses.
"""

EXTRACT:
- Company
- Founder
- Year Founded
- Industry

OUTPUT FORMAT:
{
  "company": "",
  "founder": "",
  "year_founded": "",
  "industry": ""
}
```

The structure makes both the extraction task and expected output clear.

---

# Structured Output

Structured prompting can be used to produce predictable responses.

For example:

```text
Return:

## Summary
...

## Key Findings
...

## Risks
...

## Recommendations
...
```

Or:

```text
{
  "summary": "",
  "findings": [],
  "risks": [],
  "recommendations": []
}
```

Structured output is particularly useful when AI responses are consumed by software.

---

# Structured Prompting in AI Applications

Structured prompts are common in real AI systems.

An application might construct a prompt like:

```text
SYSTEM:
[Application rules]

USER PROFILE:
[User information]

CONTEXT:
[Relevant information]

TASK:
[Current request]

OUTPUT FORMAT:
[Expected structure]
```

The application can dynamically insert information into each section.

Conceptually:

```text
Application Data
       ↓
Prompt Template
       ↓
AI Model
       ↓
Structured Response
       ↓
Application
```

This is an important concept when building AI-powered software.

---

# Prompt Templates

Structured prompts are easy to turn into reusable templates.

Example:

```text
ROLE:
[ROLE]

CONTEXT:
[CONTEXT]

TASK:
[TASK]

INPUT:
[INPUT]

REQUIREMENTS:
[REQUIREMENTS]

OUTPUT FORMAT:
[OUTPUT FORMAT]
```

Different users or applications can fill in the variables without redesigning the entire prompt.

---

# Optional vs. Required Sections

Not every prompt needs every section.

### Simple task

```text
TASK:
Translate the following text into Urdu.

INPUT:
[TEXT]
```

### Complex task

```text
ROLE:
[ROLE]

CONTEXT:
[CONTEXT]

TASK:
[TASK]

INPUT:
[INPUT]

REQUIREMENTS:
[REQUIREMENTS]

CONSTRAINTS:
[CONSTRAINTS]

OUTPUT FORMAT:
[FORMAT]
```

Use structure according to task complexity.

---

# Structured Prompting vs. Long Prompts

A structured prompt does not have to be long.

### Long but poorly organized

```text
I want you to analyze this startup and think about
the customers and competition and tell me what
features we should build first and also explain
the risks and maybe give some business advice...
```

### Structured and concise

```text
TASK:
Prioritize MVP features for this startup.

CONTEXT:
AI study platform for university students.

ANALYZE:
- Customer needs
- Competitive features
- Development effort
- Business value

OUTPUT:
Rank the top five features and explain each.
```

The second prompt is clearer despite containing fewer words.

---

# Structured Prompting vs. Unstructured Prompting

| Unstructured                    | Structured                 |
| ------------------------------- | -------------------------- |
| Large paragraph                 | Clear sections             |
| Harder to modify                | Easy to modify             |
| Requirements may be hidden      | Requirements are visible   |
| Input boundaries may be unclear | Input is clearly separated |
| Harder to reuse                 | Easy to template           |
| Output may vary                 | Output can be standardized |

Structured prompting is particularly useful when prompts are reused or maintained over time.

---

# Common Mistakes

## 1. Over-Structuring Simple Tasks

A simple translation request does not need seven sections.

```text
TASK:
Translate into Urdu.

INPUT:
[TEXT]
```

is enough.

---

## 2. Mixing Instructions and Input

Avoid unclear boundaries:

```text
Summarize this and remember that it is a
business article and here is the article...
```

Instead:

```text
TASK:
Summarize the article.

CONTEXT:
The article discusses business strategy.

INPUT:
"""
[ARTICLE]
"""
```

---

## 3. Unclear Output Requirements

If a specific structure matters, explicitly define it.

---

## 4. Redundant Sections

Do not repeat the same information in:

```text
CONTEXT
REQUIREMENTS
TASK
```

Each section should have a purpose.

---

## 5. Excessive Constraints

Too many unnecessary requirements can make the prompt difficult to maintain.

---

# Best Practices

### 1. Start With the Task

Make the primary action easy to identify.

### 2. Separate Context From Instructions

This prevents background information from being confused with commands.

### 3. Clearly Mark Input

Use labels or delimiters.

### 4. Define Important Requirements

Do not rely on assumptions for critical requirements.

### 5. Specify Output When Necessary

Especially when consistency matters.

### 6. Keep the Structure Proportional

Simple task → simple structure.

Complex task → detailed structure.

### 7. Make Templates Reusable

Use placeholders for changing information.

---

# Structured Prompt Template

A general-purpose template:

```text
# ROLE
[Optional role]

# CONTEXT
[Relevant background]

# OBJECTIVE
[Desired outcome]

# TASK
[Specific action]

# INPUT
"""
[Input data]
"""

# REQUIREMENTS
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]

# OUTPUT FORMAT
[Desired structure]
```

This template can be adapted for many different AI tasks.

---

# Before and After

## Before

```text
Analyze my website and tell me what is wrong
and how I can improve it.
```

## After

```text
ROLE:
Act as a senior UX designer.

CONTEXT:
The website is for a software company.

TASK:
Review the website content provided below.

ANALYZE:
- Navigation
- Content clarity
- User experience
- Calls to action
- Mobile usability

INPUT:
"""
[WEBSITE CONTENT]
"""

OUTPUT:
For each issue provide:
1. Problem
2. Why it matters
3. Recommended improvement

Finish with the five highest-priority changes.
```

The structured version makes the analysis more consistent and actionable.

---

# Structured Prompting Checklist

Before using a structured prompt:

* [ ] Is the task clearly defined?
* [ ] Is relevant context separated?
* [ ] Is the input clearly marked?
* [ ] Are requirements explicit?
* [ ] Are constraints necessary?
* [ ] Is the output format defined when needed?
* [ ] Are sections logically organized?
* [ ] Is unnecessary repetition removed?
* [ ] Can the prompt be reused as a template?
* [ ] Is the structure proportional to task complexity?

---

# Key Takeaways

1. Structured prompting organizes prompts into clear sections.
2. Structure makes complex prompts easier to understand and maintain.
3. Common sections include role, context, task, input, requirements, constraints, and output format.
4. Delimiters can separate input from instructions.
5. Structured prompts are useful for AI applications and reusable templates.
6. Structured output can make AI responses easier to process.
7. Simple tasks do not require complicated structures.
8. Good structure reduces ambiguity without adding unnecessary complexity.
9. Structured prompting works well with other techniques such as role prompting and few-shot prompting.
10. The goal is **clarity, consistency, and reusability**.

---

## Next

Continue with:

**[Task Decomposition](./05-task-decomposition.md)**

Learn how to break complex AI tasks into smaller, manageable steps.
