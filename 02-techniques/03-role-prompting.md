# Role Prompting

Role prompting is a technique where you assign an AI system a specific role, perspective, or area of expertise before giving it a task.

The purpose is to provide additional context about **how the AI should approach the task**, what type of expertise is relevant, and how the response should be communicated.

---

## What Is Role Prompting?

A basic role prompt might look like:

```text
Act as a Python programming instructor.
```

The task can then follow:

```text
Act as a Python programming instructor.

Explain Python functions to a beginner.
```

The role provides context about the expected perspective.

---

## Why Use Roles?

Different tasks require different perspectives.

For example:

```text
Act as a teacher.
Explain this topic to a beginner.
```

is different from:

```text
Act as a senior software engineer.
Review this code and identify potential problems.
```

The underlying AI model is the same, but the task context and expected approach are different.

Role prompting can help communicate:

* Relevant expertise
* Intended audience
* Communication style
* Professional perspective
* Task context
* Evaluation criteria

---

# Basic Structure

A simple role prompt can follow:

```text
ROLE:
[Define the relevant role]

TASK:
[Describe the task]

CONTEXT:
[Provide background information]

REQUIREMENTS:
[Define important requirements]

OUTPUT:
[Define the desired format]
```

### Example

```text
ROLE:
Act as a senior Python developer.

TASK:
Review the following Python code.

CONTEXT:
The code is part of a small web application.

REQUIREMENTS:
- Identify bugs.
- Identify potential performance issues.
- Suggest improvements.

OUTPUT:
Return:
1. Problems
2. Explanation
3. Recommended fixes
```

---

# Common Role Types

Roles should be chosen based on the task.

## Education

```text
Act as a patient programming instructor.
```

```text
Act as a mathematics tutor for beginners.
```

```text
Act as a university research advisor.
```

---

## Software Development

```text
Act as a senior software engineer.
```

```text
Act as a code reviewer.
```

```text
Act as a cybersecurity analyst.
```

```text
Act as a database engineer.
```

---

## Business

```text
Act as a business strategist.
```

```text
Act as a product manager.
```

```text
Act as a marketing consultant.
```

```text
Act as a startup advisor.
```

---

## Writing

```text
Act as a technical writer.
```

```text
Act as a professional editor.
```

```text
Act as a copywriter.
```

---

## Research

```text
Act as a research assistant.
```

```text
Act as a data analyst.
```

```text
Act as a scientific literature reviewer.
```

---

# Role + Task

A role by itself is usually not enough.

### Weak

```text
Act as a software engineer.
```

What should the AI actually do?

### Better

```text
Act as a software engineer.

Review the following API design and identify
potential reliability and scalability problems.
```

The role provides perspective, while the task defines the action.

---

# Role + Context

Adding context can make the role more relevant.

```text
ROLE:
Act as a senior product manager.

CONTEXT:
We are developing an AI-powered education
platform for university students.

TASK:
Identify the most important features for
the first version of the product.
```

Now the AI has:

* A role
* A situation
* A specific task

---

# Role + Audience

The role and audience can work together.

```text
ROLE:
Act as a programming instructor.

AUDIENCE:
Students with no previous programming experience.

TASK:
Explain variables in Python.
```

The role determines the perspective, while the audience helps determine the level of explanation.

---

# Role + Constraints

You can also define boundaries.

```text
ROLE:
Act as a cybersecurity educator.

TASK:
Explain phishing attacks.

CONSTRAINTS:
- Use simple English.
- Do not assume technical knowledge.
- Give three real-world examples.
- Keep the explanation under 500 words.
```

The role does not replace clear instructions or constraints.

---

# Role Prompting for Code Review

Role prompting is commonly useful for software development.

### Example

```text
ROLE:
Act as a senior Python code reviewer.

TASK:
Review the following code.

CHECK FOR:
- Bugs
- Security problems
- Performance issues
- Readability
- Maintainability

OUTPUT:
For each issue provide:
1. Problem
2. Why it matters
3. Suggested improvement
```

This creates a clear review framework.

---

# Role Prompting for Business Analysis

```text
ROLE:
Act as a startup business strategist.

CONTEXT:
We are evaluating a SaaS product for small businesses.

TASK:
Analyze the business idea.

EVALUATE:
- Target market
- Customer problem
- Competition
- Revenue model
- Risks
- Growth potential

OUTPUT:
Provide a structured business assessment
and finish with a recommendation.
```

The role provides a strategic perspective.

---

# Role Prompting for Education

```text
ROLE:
Act as a patient computer science teacher.

AUDIENCE:
A beginner who has never studied algorithms.

TASK:
Explain binary search.

REQUIREMENTS:
- Start with an intuitive explanation.
- Use a simple real-world analogy.
- Provide a small example.
- Explain the time complexity.
- Finish with three practice questions.
```

The role helps establish the expected teaching perspective.

---

# Role Prompting for Writing

```text
ROLE:
Act as a professional technical writer.

TASK:
Rewrite the following documentation.

REQUIREMENTS:
- Preserve the technical meaning.
- Improve clarity.
- Remove unnecessary repetition.
- Use concise language.
- Organize information with headings.
```

The role communicates the desired writing perspective.

---

# Role Prompting for Research

```text
ROLE:
Act as a research assistant.

TASK:
Analyze the following research topic.

REQUIREMENTS:
- Define the problem.
- Identify important research questions.
- Identify possible limitations.
- Suggest areas for further investigation.

OUTPUT:
Use structured headings and concise explanations.
```

For factual or high-stakes research, the role does not replace source verification.

---

# Role Prompting vs. Instructions

These concepts should not be confused.

### Role

Defines perspective:

```text
Act as a senior data analyst.
```

### Instruction

Defines action:

```text
Analyze this dataset and identify the main trends.
```

### Combined

```text
ROLE:
Act as a senior data analyst.

INSTRUCTION:
Analyze this dataset and identify the main trends.
```

A role tells the AI **how to approach the task**; an instruction tells it **what task to perform**.

---

# Role Prompting vs. Expertise Claims

A role prompt should be treated as a way to provide context, not as a guarantee that the AI actually possesses the credentials or real-world experience associated with that role.

For example:

```text
Act as a doctor.
```

does not make the AI a real doctor.

For important medical, legal, financial, scientific, or safety-related decisions, information should be appropriately verified and qualified professionals should be consulted when necessary.

---

# Choosing an Effective Role

A good role should be:

### Relevant

The role should match the task.

Good:

```text
Act as a database engineer.
Optimize this SQL query.
```

Less relevant:

```text
Act as a graphic designer.
Optimize this SQL query.
```

### Specific When Needed

Instead of:

```text
Act as an expert.
```

Use:

```text
Act as a senior backend engineer specializing
in Python APIs.
```

Specificity can provide more useful context.

### Not Excessive

Do not create complicated fictional backgrounds unless they actually help the task.

---

# Role Prompting Does Not Guarantee Better Results

Adding a role does not automatically improve every prompt.

Compare:

```text
Act as an expert.

Explain photosynthesis.
```

with:

```text
Explain photosynthesis to a beginner using
two real-world examples and simple language.
```

The second prompt may be more useful because it provides a clear task and audience.

A role is valuable when the **perspective itself matters**.

---

# Multiple Roles

For complex tasks, multiple perspectives can sometimes be useful.

For example:

```text
Analyze this product idea from three perspectives:

1. Product manager
2. Software engineer
3. Business strategist

For each perspective, identify:
- Opportunities
- Risks
- Recommendations
```

This is different from simply assigning one role.

Multiple perspectives can help expose different considerations, but they should be used purposefully.

---

# Role + Few-Shot Examples

Role prompting can be combined with few-shot prompting.

```text
ROLE:
Act as a professional technical writer.

TASK:
Rewrite technical explanations for beginners.

EXAMPLE:

Input:
"An API endpoint returns HTTP 404."

Output:
"The requested page or resource could not be found."

Now rewrite:

Input:
"The server returned HTTP 401."
```

The role establishes the perspective, while the example demonstrates the desired style.

---

# Role + Structured Output

Roles can also be combined with structured outputs.

```text
ROLE:
Act as a senior software engineer.

TASK:
Review this API design.

OUTPUT FORMAT:

{
  "strengths": [],
  "problems": [],
  "security_risks": [],
  "recommendations": []
}
```

The role and output format solve different problems.

---

# Before and After

## Before

```text
Review this business idea.
```

## Improved

```text
ROLE:
Act as a startup business strategist.

CONTEXT:
The product is an AI-powered study assistant
for university students.

TASK:
Evaluate the business idea.

ANALYZE:
- Customer problem
- Target market
- Competitive advantage
- Revenue model
- Main risks

OUTPUT:
Provide a structured assessment and finish
with three recommended next steps.
```

The improved prompt establishes a useful perspective while also providing the context and instructions necessary to perform the task.

---

# Common Mistakes

## Mistake 1: Using an Unrelated Role

```text
Act as a graphic designer.

Analyze this database schema.
```

The role does not match the task.

---

## Mistake 2: Giving Only a Role

```text
Act as an expert.
```

This does not define the task.

---

## Mistake 3: Assuming a Role Guarantees Accuracy

A role prompt does not guarantee expertise, factual correctness, or professional qualifications.

---

## Mistake 4: Using Unnecessary Roles

Not every prompt needs:

```text
Act as a world-class expert with decades
of experience...
```

If the task is simple, direct instructions may be enough.

---

## Mistake 5: Confusing Style With Expertise

A role can influence perspective and communication style, but it should not be treated as proof of real-world credentials.

---

# Role Prompting Checklist

Before using a role, ask:

* [ ] Is the role relevant to the task?
* [ ] Does the role provide useful perspective?
* [ ] Is the task clearly defined?
* [ ] Is relevant context included?
* [ ] Is the audience defined when necessary?
* [ ] Are important constraints included?
* [ ] Is the output format clear?
* [ ] Is the role unnecessarily exaggerated?
* [ ] Are important results independently verified?

---

# Key Takeaways

1. Role prompting assigns a perspective or role to an AI system.
2. A role can provide useful task context.
3. Roles work best when they are relevant to the task.
4. A role should be combined with clear instructions when necessary.
5. Audience, context, constraints, and output format remain important.
6. Role prompting does not guarantee expertise or factual accuracy.
7. Multiple roles can provide different perspectives when used purposefully.
8. Roles can be combined with other prompting techniques.
9. Simple tasks may not require role prompting.
10. The goal is not to make the prompt sound impressive; the goal is to provide **useful context for the task**.

---

## Next

Continue with:

**[Structured Prompting](./04-structured-prompting.md)**

Learn how to organize prompts into clear sections and define predictable input and output structures.
