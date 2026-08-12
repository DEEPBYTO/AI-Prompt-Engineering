# Research Prompts

Research prompts are designed to help AI systems investigate topics, analyze information, compare sources, identify evidence, and produce structured conclusions.

A good research prompt does not simply ask:

```text
Research AI.
```

It defines:

* Research question
* Scope
* Context
* Sources
* Time period
* Evaluation criteria
* Output format
* Uncertainty requirements

---

# What Is a Research Prompt?

A research prompt gives an AI system a structured task for investigating a subject.

Weak:

```text
Tell me about electric vehicles.
```

Stronger:

```text
RESEARCH QUESTION:
How have electric vehicle battery costs changed since 2015?

SCOPE:
Global passenger vehicles.

TIME PERIOD:
2015–2026.

REQUIREMENTS:
- Identify major cost trends.
- Explain the main factors behind the changes.
- Distinguish estimates from measured data.
- Cite reliable sources.

OUTPUT:
Provide a timeline, key findings, and sources.
```

The second prompt defines what the research should actually investigate.

---

# Research Prompt Structure

A reusable structure is:

```text
ROLE:
[Research role]

QUESTION:
[Main research question]

CONTEXT:
[Why the research is needed]

SCOPE:
[What is included]

EXCLUSIONS:
[What should not be covered]

TIME PERIOD:
[Relevant dates]

SOURCES:
[Preferred source types]

CRITERIA:
[How information should be evaluated]

OUTPUT:
[Required format]

UNCERTAINTY:
[How uncertain or conflicting evidence should be handled]
```

---

# Define the Research Question

A good research question should be specific.

Weak:

```text
What is AI?
```

Better:

```text
How are generative AI tools changing software
development workflows for small development teams?
```

Even better:

```text
What measurable effects have generative AI coding
tools had on software development productivity
between 2023 and 2026, according to empirical studies?
```

The more precise the question, the more focused the research.

---

# Open-Ended vs. Focused Research

## Open-Ended

```text
Explore the major applications of robotics in agriculture.
```

Useful for discovering a topic.

## Focused

```text
Compare autonomous agricultural robots used for
weeding in commercial farms.

Compare:
- Navigation
- Sensors
- Operating environment
- Cost
- Limitations
- Commercial availability
```

Useful for decision-making.

---

# Define Scope

Without a scope, research can become unnecessarily broad.

Example:

```text
SCOPE:
Focus on commercially available AI coding tools.

EXCLUDE:
Academic prototypes that are not publicly usable.
```

Scope keeps the research relevant.

---

# Define Exclusions

Explicit exclusions can be useful.

```text
EXCLUDE:
- Historical developments before 2020
- Unrelated AI applications
- Purely speculative technologies
```

This prevents the research from drifting away from the question.

---

# Define the Time Period

Many research questions are time-sensitive.

Example:

```text
TIME PERIOD:
January 2024 – August 2026
```

Or:

```text
Use the most recent available information
and clearly identify publication dates.
```

For current topics, the research should distinguish recent information from historical background.

---

# Source Requirements

Not all sources have equal reliability.

You can specify:

```text
SOURCE PRIORITY:

1. Official government sources
2. Academic papers
3. Official company documentation
4. Reputable industry reports
5. Established news organizations
6. Expert analysis
7. Community discussions
```

The appropriate hierarchy depends on the subject.

---

# Primary vs. Secondary Sources

### Primary Sources

Examples:

* Government datasets
* Official filings
* Academic research
* Company documentation
* Original datasets
* Official announcements

### Secondary Sources

Examples:

* News articles
* Reviews
* Industry analysis
* Commentary

A strong research prompt can ask the AI to prioritize primary sources.

```text
PRIORITY:
Use primary sources whenever possible.
Use secondary sources to provide context.
```

---

# Source Verification

Do not treat every source as equally trustworthy.

Prompt:

```text
For every major claim:

1. Identify the source.
2. Determine whether it is primary or secondary.
3. Evaluate its credibility.
4. Check whether the source actually supports the claim.
```

This reduces unsupported conclusions.

---

# Fact-Checking Prompts

A useful fact-checking prompt:

```text
TASK:
Fact-check the following claims.

For each claim provide:

CLAIM:
[Claim]

VERDICT:
Supported / Partially Supported / Unsupported / Unclear

EVIDENCE:
[Evidence]

SOURCE:
[Source]

EXPLANATION:
[Reasoning]
```

This creates a consistent verification structure.

---

# Do Not Force a Verdict

Sometimes available evidence is insufficient.

A good research prompt allows:

```text
VERDICT:
Insufficient evidence
```

rather than forcing the AI to choose:

```text
True
```

or:

```text
False
```

Uncertainty is part of good research.

---

# Research With Conflicting Sources

Different sources can disagree.

Prompt:

```text
If credible sources disagree:

1. Identify the disagreement.
2. Summarize each position.
3. Explain why the sources differ.
4. Evaluate the evidence.
5. Do not hide the disagreement.
6. State what can and cannot be concluded.
```

This is especially important for complex or rapidly changing topics.

---

# Research Synthesis

Research is more than collecting links.

A synthesis prompt:

```text
TASK:
Synthesize the available research.

DO NOT:
Simply summarize each source separately.

INSTEAD:
- Identify common findings.
- Identify disagreements.
- Identify important trends.
- Compare methodologies.
- Identify evidence gaps.
- Produce an overall conclusion.
```

This turns source collection into analysis.

---

# Research Comparison

For comparing technologies:

```text
TASK:
Compare [Technology A] and [Technology B].

CRITERIA:
- Performance
- Cost
- Reliability
- Scalability
- Ease of implementation
- Security
- Limitations

SOURCE REQUIREMENT:
Use reliable and recent sources.

OUTPUT:
Comparison table followed by analysis.
```

Define the comparison criteria before collecting information.

---

# Competitive Research

For businesses:

```text
TASK:
Analyze the competitive landscape for
AI-powered customer support software.

RESEARCH:
- Major competitors
- Product positioning
- Target customers
- Pricing models
- Key features
- Differentiators
- Market gaps

TIME:
Use current information.

OUTPUT:
Competitive landscape + opportunity analysis.
```

The goal should be defined before collecting competitor information.

---

# Market Research

Market research prompts should clearly define:

```text
MARKET:
[Industry]

GEOGRAPHY:
[Country / Region / Global]

TIME PERIOD:
[Period]

SEGMENT:
[Customer segment]

QUESTIONS:
- Market size
- Growth
- Major players
- Customer behavior
- Trends
- Risks
- Opportunities
```

Avoid vague requests such as:

```text
Research the market.
```

---

# Academic Research Prompts

Academic research requires additional care.

```text
TASK:
Research the relationship between sleep
and learning performance.

SOURCE PRIORITY:
- Peer-reviewed studies
- Meta-analyses
- Systematic reviews

REQUIREMENTS:
- Identify study methodology.
- Distinguish correlation from causation.
- Identify limitations.
- Report conflicting findings.
```

This encourages evidence-based analysis.

---

# Research Paper Analysis

When analyzing a paper:

```text
TASK:
Analyze this research paper.

OUTPUT:
1. Research question
2. Hypothesis
3. Methodology
4. Dataset / sample
5. Main findings
6. Limitations
7. Statistical evidence
8. Practical implications
9. Questions for further research
```

The AI should distinguish what the paper actually demonstrated from what it merely suggests.

---

# Research Methodology Analysis

Ask:

```text
Evaluate the methodology.

CHECK:
- Sample size
- Sampling method
- Controls
- Measurement methods
- Possible bias
- Confounding variables
- Reproducibility
- Statistical methods
```

This helps assess the strength of evidence.

---

# Research From Data

If research involves datasets:

```text
DATASET:
[Dataset description]

QUESTIONS:
- What patterns are visible?
- What trends exist?
- Are there anomalies?
- What correlations appear?
- What conclusions are supported?

CONSTRAINT:
Do not infer causation from correlation alone.
```

This distinction is essential.

---

# Research vs. Opinion

A good research prompt can explicitly separate them.

```text
OUTPUT:

FACTS:
Evidence directly supported by sources.

INTERPRETATION:
Reasonable conclusions based on the evidence.

OPINION:
Subjective judgments.

UNCERTAINTY:
Claims that cannot currently be established.
```

This makes the final result easier to evaluate.

---

# Research With Multiple Perspectives

For controversial or disputed subjects:

```text
TASK:
Analyze the topic from multiple credible perspectives.

REQUIREMENTS:
- Present the strongest evidence for each position.
- Identify areas of agreement.
- Identify areas of disagreement.
- Avoid caricaturing either position.
- Separate evidence from interpretation.
```

The objective is balanced analysis rather than artificial "both sides" symmetry.

---

# Research Timeline Prompt

For historical or technological development:

```text
TASK:
Create a timeline of the development of
generative AI.

INCLUDE:
- Major developments
- Dates
- Organizations
- Important technologies
- Significance of each development

SOURCE REQUIREMENT:
Verify important dates using reliable sources.
```

---

# Research Trend Analysis

```text
TASK:
Identify major trends in robotics from 2020–2026.

FOR EACH TREND:
- What changed?
- Why did it change?
- Evidence
- Major organizations
- Current state
- Likely near-term direction

DISTINGUISH:
Observed trends from speculation.
```

This distinction is critical.

---

# Research Forecasting

Forecasting should explicitly separate evidence from prediction.

```text
TASK:
Assess the likely development of AI coding tools
over the next three years.

SEPARATE:
1. Current evidence
2. Industry signals
3. Reasonable projections
4. High-uncertainty scenarios

Do not present predictions as established facts.
```

---

# Research Questions Before Research

For complicated topics, ask the AI to develop research questions first.

```text
TASK:
I want to research [TOPIC].

FIRST:
Identify the 10 most important questions
that should be answered.

THEN:
Group them into logical categories.

DO NOT:
Perform the research yet.
```

This is useful for large investigations.

---

# Research Plan

A research plan can look like:

```text
Topic
 ↓
Research Questions
 ↓
Source Strategy
 ↓
Evidence Collection
 ↓
Source Evaluation
 ↓
Analysis
 ↓
Synthesis
 ↓
Conclusion
 ↓
Evidence Gaps
```

This creates a repeatable research workflow.

---

# Deep Research Prompt

```text
ROLE:
Act as a research analyst.

QUESTION:
[Main research question]

CONTEXT:
[Why this research matters]

SCOPE:
[Scope]

TIME PERIOD:
[Period]

SOURCE PRIORITY:
1. Primary sources
2. Peer-reviewed research
3. Official documentation
4. Reputable secondary sources

REQUIREMENTS:
- Verify important claims.
- Identify conflicting evidence.
- Distinguish facts from interpretation.
- Report uncertainty.
- Do not invent sources.

OUTPUT:
1. Executive summary
2. Research findings
3. Evidence
4. Conflicting evidence
5. Analysis
6. Limitations
7. Conclusion
8. Sources
```

---

# Research Prompt for Business Decisions

```text
ROLE:
Act as a business research analyst.

DECISION:
Should we build [PRODUCT]?

RESEARCH:
- Target customers
- Existing solutions
- Competitors
- Pricing
- Market demand
- Differentiation
- Technical barriers
- Regulatory considerations
- Major risks

OUTPUT:
1. Market overview
2. Competitive analysis
3. Opportunity
4. Risks
5. Unanswered questions
6. Recommendation
```

A recommendation should be based on the evidence gathered, not predetermined.

---

# Research Prompt for Technology Selection

```text
TASK:
Determine which technology is most suitable
for [PROJECT].

OPTIONS:
A
B
C

CRITERIA:
- Performance
- Cost
- Scalability
- Developer experience
- Ecosystem
- Security
- Long-term maintenance

WEIGHTING:
Performance: 30%
Cost: 20%
Scalability: 20%
Security: 15%
Maintenance: 15%

OUTPUT:
Weighted comparison and recommendation.
```

Explicit weights make decision-making more transparent.

---

# Research Output Formats

You can specify the final format.

### Executive Summary

```text
5 key findings
3 risks
3 opportunities
Final conclusion
```

### Research Report

```text
Introduction
Methodology
Findings
Analysis
Limitations
Conclusion
Sources
```

### Comparison

```text
Criteria | Option A | Option B | Option C
```

### Timeline

```text
Date → Event → Significance
```

### Evidence Matrix

```text
Claim | Evidence | Source | Confidence
```

The output format should match the purpose of the research.

---

# Evidence Matrix

An evidence matrix is useful for complex research.

```text
| Claim | Evidence | Source | Source Type | Confidence |
|------|----------|--------|-------------|------------|
| A    | ...      | ...    | Primary     | High       |
| B    | ...      | ...    | Secondary   | Medium     |
```

This makes the reasoning behind conclusions more transparent.

---

# Confidence Levels

You can ask AI to classify confidence.

```text
HIGH:
Strong evidence from multiple reliable sources.

MEDIUM:
Reasonable evidence but limitations exist.

LOW:
Limited, indirect, or conflicting evidence.

UNKNOWN:
Insufficient evidence.
```

Confidence should reflect evidence quality rather than AI certainty.

---

# Common Research Prompt Mistakes

## 1. Asking a Huge Question

```text
Research everything about technology.
```

Too broad.

---

## 2. No Time Period

Current information can become outdated quickly.

---

## 3. No Source Requirements

Low-quality sources may dominate the results.

---

## 4. Treating All Sources Equally

A primary dataset and an anonymous blog do not carry the same evidentiary weight.

---

## 5. Asking for a Predetermined Conclusion

Avoid:

```text
Prove that this technology is the best.
```

Instead:

```text
Evaluate whether this technology is the best
according to defined criteria.
```

---

## 6. Ignoring Conflicting Evidence

Good research should acknowledge credible disagreement.

---

## 7. Confusing Correlation With Causation

A relationship between two variables does not automatically prove one caused the other.

---

## 8. Accepting Unsupported Claims

Important claims should be traceable to evidence.

---

# Research Quality Checklist

Before sending a research prompt:

* [ ] Is the research question specific?
* [ ] Is the scope defined?
* [ ] Is the time period defined?
* [ ] Are source priorities specified?
* [ ] Are primary sources preferred when appropriate?
* [ ] Are conflicting sources considered?
* [ ] Is uncertainty allowed?
* [ ] Are facts separated from interpretation?
* [ ] Is the output format defined?
* [ ] Are important claims expected to be verified?
* [ ] Are evidence gaps identified?

---

# Reusable Research Prompt

```text
# ROLE
Act as a research analyst specializing in [DOMAIN].

# RESEARCH QUESTION
[Question]

# CONTEXT
[Why this research is needed]

# SCOPE
[What should be investigated]

# EXCLUSIONS
[What should not be included]

# TIME PERIOD
[Relevant period]

# SOURCE PRIORITY
1. [Source type]
2. [Source type]
3. [Source type]

# RESEARCH REQUIREMENTS
- Verify important claims.
- Distinguish facts from interpretation.
- Identify conflicting evidence.
- Report uncertainty.
- Do not invent sources or evidence.

# EVALUATION CRITERIA
[Criteria]

# OUTPUT
1. Executive summary
2. Findings
3. Evidence
4. Analysis
5. Conflicting evidence
6. Limitations
7. Conclusion
8. Sources
```

---

# Key Takeaways

1. A research prompt should define a clear question.
2. Scope prevents research from becoming unnecessarily broad.
3. Time periods matter for changing subjects.
4. Primary sources should usually receive higher priority when available.
5. Source quality matters as much as the number of sources.
6. Good research acknowledges conflicting evidence.
7. Uncertainty should be reported rather than hidden.
8. Separate facts, interpretation, and opinion.
9. Do not force a predetermined conclusion.
10. Strong research prompts turn AI into a **structured research and analysis assistant** rather than simply a text generator.

---

## Next

**`03-patterns/06-summarization.md`**

This file will cover prompts for **summarizing articles, books, documents, research papers, meetings, long text, and extracting key information without losing important context**.
