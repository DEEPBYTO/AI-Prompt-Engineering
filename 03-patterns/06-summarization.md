# Summarization Prompts

Summarization prompts are designed to help AI reduce large amounts of information into a shorter, clearer, and more useful form.

A good summary is not simply a shorter copy of the original text. It should preserve the **important information, meaning, context, and conclusions** while removing unnecessary detail.

---

# What Is a Summarization Prompt?

A weak prompt:

```text
Summarize this.
```

A stronger prompt:

```text
TASK:
Summarize the following article.

AUDIENCE:
A university student.

REQUIREMENTS:
- Identify the main argument.
- Extract the five most important points.
- Preserve important numbers and dates.
- Explain important technical terms.
- Do not add information that is not in the source.

OUTPUT:
1. One-paragraph summary
2. Five key points
3. Important facts
```

The second prompt defines what should be preserved and how the summary should be presented.

---

# The Core Summarization Principle

A useful summarization prompt answers three questions:

```text
WHAT?
What information should be extracted?

HOW MUCH?
How short should the summary be?

FOR WHOM?
Who will use the summary?
```

For example:

```text
WHAT:
Main arguments and evidence

HOW MUCH:
300 words

FOR WHOM:
Beginner reader
```

---

# Basic Summarization Structure

```text
TASK:
Summarize [CONTENT].

AUDIENCE:
[Audience]

LENGTH:
[Word count / number of points]

FOCUS:
- [Important aspect 1]
- [Important aspect 2]
- [Important aspect 3]

REQUIREMENTS:
- Preserve important facts.
- Preserve important context.
- Do not invent information.
- Clearly distinguish conclusions from opinions.

OUTPUT:
[Desired format]
```

---

# Summarizing an Article

```text
TASK:
Summarize this article.

REQUIREMENTS:
- State the main argument.
- Identify the supporting points.
- Mention important evidence.
- Identify the conclusion.
- Do not introduce outside information.

OUTPUT:
- 150-word summary
- 5 key points
- 3 important facts
```

This works better than simply saying:

```text
Summarize this article.
```

---

# Executive Summary

An executive summary is designed for someone who needs the important information quickly.

```text
TASK:
Create an executive summary of this report.

AUDIENCE:
Business leadership.

INCLUDE:
- Main findings
- Important numbers
- Major risks
- Opportunities
- Recommendations
- Key conclusion

LENGTH:
Approximately 300 words.
```

The focus should be on decision-relevant information.

---

# Academic Summaries

Academic material requires more precision.

```text
TASK:
Summarize this research paper.

INCLUDE:
1. Research question
2. Methodology
3. Dataset / sample
4. Main findings
5. Limitations
6. Conclusion

CONSTRAINT:
Do not exaggerate the findings.
Distinguish correlation from causation.
```

This prevents an academic summary from becoming merely a list of conclusions.

---

# Research Paper Abstract Prompt

```text
TASK:
Create a concise abstract-style summary.

INCLUDE:
- Problem
- Method
- Results
- Conclusion

LENGTH:
150–250 words.

CONSTRAINT:
Use only information contained in the paper.
```

---

# Book Summaries

Books are much larger than ordinary articles, so structure matters.

```text
TASK:
Summarize this book.

OUTPUT:

1. Overall thesis
2. Chapter-by-chapter summary
3. Main ideas
4. Important concepts
5. Key examples
6. Practical lessons
7. Final conclusion

AUDIENCE:
Beginner reader.
```

For a long book, summarize chapter-by-chapter first and then create an overall synthesis.

---

# Chapter Summaries

```text
TASK:
Summarize this chapter.

INCLUDE:
- Main idea
- Important concepts
- Supporting examples
- Important terminology
- Final conclusion

OUTPUT:
1. Short summary
2. Key points
3. Important terms
4. Questions for revision
```

This is particularly useful for students.

---

# Summarizing Technical Documentation

Technical documentation should preserve exact technical details.

```text
TASK:
Summarize this API documentation.

INCLUDE:
- Purpose
- Authentication
- Main endpoints
- Required parameters
- Response format
- Error behavior
- Important limitations

CONSTRAINT:
Do not simplify technical details to the point
where they become inaccurate.
```

For technical material, **accuracy is more important than extreme brevity**.

---

# Summarizing Code

AI can summarize code at different levels.

### High-Level

```text
TASK:
Explain what this code does in 5 bullet points.
```

### Detailed

```text
TASK:
Explain the code.

INCLUDE:
- Overall purpose
- Main functions
- Data flow
- External dependencies
- Important edge cases
```

### Architecture

```text
TASK:
Summarize the architecture represented by this code.

OUTPUT:
Components → Responsibilities → Dependencies → Data flow
```

---

# Summarizing Meeting Notes

```text
TASK:
Summarize these meeting notes.

OUTPUT:

## Key Decisions
- ...

## Action Items
- Task — Owner — Deadline

## Open Questions
- ...

## Important Discussion Points
- ...

Do not invent owners or deadlines that are not present.
```

This is much more useful than a generic paragraph.

---

# Summarizing Conversations

```text
TASK:
Summarize this conversation.

INCLUDE:
- Main topics
- Decisions
- Agreements
- Disagreements
- Action items
- Unresolved questions

Do not infer intentions that are not explicitly stated.
```

---

# Summarizing Long Documents

For large documents, use hierarchical summarization.

```text
Document
   ↓
Sections
   ↓
Section Summaries
   ↓
Combined Summary
   ↓
Final Executive Summary
```

Prompt:

```text
FIRST:
Summarize each section separately.

THEN:
Combine the section summaries.

FINALLY:
Create a concise overall summary.
```

This can help preserve important details from long material.

---

# Hierarchical Summarization

A useful workflow:

```text
LEVEL 1:
Extract key information from each section.

LEVEL 2:
Summarize each section.

LEVEL 3:
Identify themes across sections.

LEVEL 4:
Create final summary.
```

This is especially useful for:

* Books
* Reports
* Research papers
* Legal documents
* Technical documentation

---

# Extractive vs. Abstractive Summarization

## Extractive

Selects important information from the original.

```text
Original
 ↓
Important sentences
 ↓
Summary
```

Prompt:

```text
Create an extractive summary using
only sentences from the original text.
```

## Abstractive

Rewrites the important ideas in new wording.

```text
Original
 ↓
Understand meaning
 ↓
Rewrite key ideas
 ↓
Summary
```

Prompt:

```text
Create an abstractive summary while
preserving the original meaning.
```

---

# Summary With Key Quotes

If exact wording matters:

```text
TASK:
Summarize the document and identify
up to 5 short quotations that support
the main points.

For each quote:
- Quote
- Context
- Why it matters
```

Use quotations sparingly and preserve their context.

---

# Summary With Important Numbers

For business and research documents, numbers can be critical.

```text
TASK:
Summarize this report.

IMPORTANT:
Preserve:
- Percentages
- Revenue figures
- Dates
- Quantities
- Growth rates
- Statistical results
```

A summary that removes critical numbers may become misleading.

---

# Summary With Definitions

Technical or educational text may contain unfamiliar terminology.

```text
TASK:
Summarize this technical document.

For each important technical term:
- Term
- Simple definition
- Role in the document
```

This makes the summary easier for beginners.

---

# Beginner-Friendly Summarization

```text
AUDIENCE:
Complete beginner.

REQUIREMENTS:
- Use simple language.
- Explain necessary technical terms.
- Avoid unnecessary jargon.
- Use examples where helpful.
```

The underlying information should remain accurate even when the language is simplified.

---

# Expert-Level Summarization

```text
AUDIENCE:
Senior software engineers.

REQUIREMENTS:
- Preserve technical terminology.
- Focus on architecture and implementation details.
- Remove basic explanations.
- Highlight tradeoffs and limitations.
```

The same source can require completely different summaries for different audiences.

---

# Summary by Audience

### Student

```text
Focus:
Definitions + concepts + examples
```

### Executive

```text
Focus:
Decisions + risks + opportunities + numbers
```

### Engineer

```text
Focus:
Implementation + architecture + constraints
```

### Researcher

```text
Focus:
Methodology + evidence + limitations
```

Audience should influence what information gets priority.

---

# Summary by Length

You can control the desired compression.

### One Sentence

```text
Summarize this in exactly one sentence.
```

### 5 Bullets

```text
Summarize this in exactly five bullet points.
```

### 100 Words

```text
Summarize this in approximately 100 words.
```

### Detailed

```text
Create a detailed summary while removing
repetition and minor details.
```

---

# Progressive Summarization

Instead of creating one final summary immediately:

```text
Full Document
      ↓
Detailed Summary
      ↓
Short Summary
      ↓
One-Sentence Summary
```

Prompt:

```text
Create three levels of summary:

LEVEL 1:
Detailed summary

LEVEL 2:
150-word summary

LEVEL 3:
One-sentence summary
```

This is useful when you need multiple formats.

---

# Summarizing With a Focus

A generic summary may not answer your actual question.

Instead:

```text
TASK:
Summarize this report with a focus on
cybersecurity risks.

IGNORE:
Unrelated financial details unless
they affect cybersecurity.
```

This produces a targeted summary.

---

# Compare Summary to Source

For high-accuracy tasks:

```text
TASK:
Create a summary and then verify it
against the original.

CHECK:
- Missing important facts
- Incorrect claims
- Changed numbers
- Lost context
- Unsupported conclusions
```

This adds a verification stage.

---

# Summary With Evidence

```text
TASK:
Summarize the document.

For every major finding, identify
the section or passage that supports it.
```

This creates a traceable summary.

---

# Avoiding Hallucinations in Summaries

A common problem is adding information that was not present in the source.

Use:

```text
CONSTRAINT:
Use only information contained in the provided text.

If the document does not provide an answer,
write:
"Not specified in the source."
```

This is particularly useful for factual documents.

---

# Handling Ambiguous Text

If the source is unclear:

```text
CONSTRAINT:
Do not resolve ambiguity by guessing.

Identify ambiguous statements and explain
what the source clearly establishes.
```

This preserves uncertainty instead of inventing certainty.

---

# Summarizing Multiple Documents

When several documents cover the same subject:

```text
DOCUMENT A
      +
DOCUMENT B
      +
DOCUMENT C
      ↓
Cross-Document Analysis
      ↓
Unified Summary
```

Prompt:

```text
TASK:
Synthesize these three documents.

INCLUDE:
- Common findings
- Differences
- Contradictions
- Unique information
- Overall conclusion

Do not assume that conflicting claims
are automatically resolved.
```

---

# Multi-Document Comparison

A useful structure:

```text
| Topic | Document A | Document B | Document C |
|------|------------|------------|------------|
| Claim 1 | ... | ... | ... |
| Claim 2 | ... | ... | ... |
```

This makes disagreements easier to identify.

---

# News Summary Prompt

For news articles:

```text
TASK:
Summarize this news article.

OUTPUT:
1. What happened?
2. Who is involved?
3. When did it happen?
4. Where did it happen?
5. Why does it matter?
6. What remains uncertain?

Do not add information that is not in the article.
```

The final question helps distinguish known facts from unresolved information.

---

# Legal or Policy Document Summaries

For important legal or policy material:

```text
TASK:
Summarize this policy document.

INCLUDE:
- Scope
- Main requirements
- Responsibilities
- Exceptions
- Deadlines
- Penalties / consequences
- Important definitions

CONSTRAINT:
Do not present the summary as a substitute
for professional legal advice.
```

Exact wording may matter significantly in these documents.

---

# Summarizing Data Reports

```text
TASK:
Summarize this data report.

INCLUDE:
- Major trends
- Important figures
- Changes over time
- Significant differences
- Anomalies
- Limitations

CONSTRAINT:
Do not infer causation unless supported by
the report.
```

---

# Summarizing Presentations

```text
TASK:
Summarize these presentation slides.

OUTPUT:
1. Main objective
2. Key messages
3. Important data
4. Major conclusions
5. Recommended actions
```

If speaker notes are available, they may contain context missing from the slides.

---

# Summarizing Emails

```text
TASK:
Summarize this email thread.

OUTPUT:
- Main issue
- Decisions
- Requests
- Action items
- Deadlines
- Unresolved questions
```

Do not infer deadlines if none were stated.

---

# Summarization With Action Items

For practical documents:

```text
TASK:
Summarize the document.

OUTPUT:

SUMMARY:
[Short summary]

DECISIONS:
[List]

ACTION ITEMS:
Task | Owner | Deadline

RISKS:
[List]

OPEN QUESTIONS:
[List]
```

This converts information into an actionable format.

---

# Before and After

## Weak

```text
Summarize this report.
```

## Strong

```text
TASK:
Summarize this business report.

AUDIENCE:
Company leadership.

FOCUS:
- Revenue performance
- Customer growth
- Major risks
- Market opportunities

PRESERVE:
- Important percentages
- Financial figures
- Dates
- Major conclusions

OUTPUT:
1. 150-word executive summary
2. 5 key findings
3. 3 risks
4. 3 opportunities
5. Important numbers
6. Unresolved questions

CONSTRAINT:
Use only information from the report.
Do not invent missing information.
```

The second prompt produces a much more useful result because the AI knows exactly what matters.

---

# Summarization Prompt Template

```text
# ROLE
Act as a professional summarization assistant.

# SOURCE
[Document / Article / Report]

# AUDIENCE
[Audience]

# PURPOSE
[Why the summary is needed]

# FOCUS
- [Important topic 1]
- [Important topic 2]
- [Important topic 3]

# LENGTH
[Word count / bullet count]

# PRESERVE
- Important facts
- Numbers
- Dates
- Conclusions
- Important context

# EXCLUDE
- Repetition
- Minor details
- Irrelevant information

# ACCURACY REQUIREMENTS
- Use only information from the source.
- Do not invent facts.
- Preserve uncertainty.
- Do not change the meaning.

# OUTPUT
[Desired structure]
```

---

# Summarization Checklist

Before sending a summarization prompt:

* [ ] Is the source clear?
* [ ] Is the audience defined?
* [ ] Is the purpose defined?
* [ ] Is the desired length specified?
* [ ] Is the focus specified?
* [ ] Are important numbers preserved?
* [ ] Are important dates preserved?
* [ ] Are conclusions preserved?
* [ ] Is outside information prohibited when necessary?
* [ ] Is uncertainty preserved?
* [ ] Is the output format defined?

---

# Key Takeaways

1. Good summaries preserve important meaning rather than simply reducing word count.
2. Define the audience and purpose before summarizing.
3. Specify the desired length and format.
4. Preserve important numbers, dates, evidence, and conclusions.
5. Use focused summaries when only certain information matters.
6. Hierarchical summarization works well for large documents.
7. Multi-document summaries should identify both agreement and disagreement.
8. Do not allow the AI to invent information missing from the source.
9. Technical and legal summaries require extra precision.
10. A strong summarization prompt controls **what to preserve, what to remove, how much to compress, and how the result should be presented**.

---

## Next

**`03-patterns/07-analysis.md`**

This file will cover prompts for **deep analysis, reasoning frameworks, root-cause analysis, comparisons, tradeoffs, decision-making, and turning information into actionable conclusions**.
