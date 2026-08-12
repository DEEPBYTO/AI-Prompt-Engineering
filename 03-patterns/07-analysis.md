# Analysis Prompts

Analysis prompts are designed to help AI examine information, identify relationships, evaluate evidence, compare alternatives, uncover problems, and produce reasoned conclusions.

A good analysis prompt does not simply ask the AI to "analyze this." It defines **what should be examined, which criteria matter, what evidence should be used, and what the final decision or conclusion should address**.

---

# What Is an Analysis Prompt?

Weak:

```text
Analyze this business idea.
```

Stronger:

```text
TASK:
Analyze this SaaS business idea.

EVALUATE:
- Target customer
- Problem severity
- Existing alternatives
- Competitive advantage
- Revenue model
- Technical complexity
- Customer acquisition
- Major risks

OUTPUT:
1. Strengths
2. Weaknesses
3. Opportunities
4. Risks
5. Critical assumptions
6. Recommendation

Do not assume market demand without evidence.
```

The second prompt gives the AI an analytical framework.

---

# Analysis vs. Summarization

These tasks are different.

### Summarization

Answers:

> **What does the information say?**

```text
Source
 ↓
Important information
 ↓
Shorter representation
```

### Analysis

Answers:

> **What does the information mean, and what can we conclude from it?**

```text
Information
 ↓
Evidence
 ↓
Relationships
 ↓
Evaluation
 ↓
Conclusion
```

A strong prompt should make clear which task is required.

---

# The Analysis Framework

A general analytical workflow:

```text
Problem
   ↓
Context
   ↓
Evidence
   ↓
Factors
   ↓
Relationships
   ↓
Alternatives
   ↓
Tradeoffs
   ↓
Conclusion
   ↓
Action
```

This framework can be adapted to business, technology, research, strategy, and many other domains.

---

# Define the Analytical Question

Instead of:

```text
Analyze AI.
```

Ask:

```text
What are the main barriers preventing small
businesses from successfully adopting AI,
and which barriers are most significant?
```

A good analytical question has a clear target.

---

# Define the Objective

Tell the AI what the analysis is supposed to accomplish.

```text
OBJECTIVE:
Determine whether we should launch this product.
```

or:

```text
OBJECTIVE:
Identify the most likely cause of the performance problem.
```

or:

```text
OBJECTIVE:
Choose the most suitable technology for the project.
```

The objective determines what evidence matters.

---

# Define the Context

Context prevents incorrect assumptions.

```text
CONTEXT:
We are a small software team with three developers.

PROJECT:
A customer-support SaaS product.

CONSTRAINT:
Limited initial budget.

OBJECTIVE:
Determine the most practical technology stack.
```

The same technology may be appropriate for a large enterprise but unsuitable for a small team.

---

# Identify Variables

Complex problems often contain multiple variables.

For example:

```text
Business Success
├── Product
├── Market
├── Pricing
├── Distribution
├── Competition
└── Operations
```

Prompt:

```text
Identify the major variables that could
influence the outcome before performing
the analysis.
```

This helps avoid focusing on only one factor.

---

# Root-Cause Analysis

Root-cause analysis attempts to determine why a problem occurred.

Basic structure:

```text
Problem
 ↓
Symptoms
 ↓
Possible Causes
 ↓
Evidence
 ↓
Root Cause
 ↓
Corrective Action
```

Prompt:

```text
TASK:
Perform a root-cause analysis.

PROBLEM:
[Problem]

SYMPTOMS:
[Symptoms]

EVIDENCE:
[Evidence]

OUTPUT:
1. Possible causes
2. Evidence for each cause
3. Evidence against each cause
4. Most likely root cause
5. Recommended corrective action
6. Prevention strategy
```

---

# Five Whys

The Five Whys technique repeatedly asks why a problem occurred.

Example:

```text
Why did the server fail?
↓
Database connection failed.

Why did the connection fail?
↓
Connection pool was exhausted.

Why was the pool exhausted?
↓
Connections were not released.

Why were they not released?
↓
Error handling skipped cleanup.

Why did error handling skip cleanup?
↓
The resource lifecycle was incorrectly designed.
```

Prompt:

```text
Apply the Five Whys method to this problem.

Do not assume each answer is correct.
Identify where evidence is needed.
```

The important point is that "five" is not mandatory; stop when the underlying cause has been adequately identified.

---

# Fishbone-Style Analysis

For complex problems, group possible causes.

```text
Problem
├── People
├── Process
├── Technology
├── Data
├── Environment
└── Management
```

Prompt:

```text
Analyze this problem using categories such as:

- People
- Process
- Technology
- Data
- Environment
- Management

Identify possible causes under each category.
Then rank them by likelihood and impact.
```

---

# SWOT Analysis

SWOT examines:

```text
Strengths
Weaknesses
Opportunities
Threats
```

Prompt:

```text
Analyze this business using SWOT.

STRENGTHS:
Internal advantages

WEAKNESSES:
Internal limitations

OPPORTUNITIES:
External opportunities

THREATS:
External risks

For each item, explain the evidence or reasoning.
```

Do not treat SWOT as a substitute for detailed market research.

---

# PESTLE Analysis

PESTLE examines external factors:

```text
Political
Economic
Social
Technological
Legal
Environmental
```

Prompt:

```text
Perform a PESTLE analysis of this industry.

REGION:
[Region]

TIME PERIOD:
[Period]

For each category:
- Identify major factors.
- Explain potential impact.
- Distinguish current evidence from speculation.
```

---

# Comparative Analysis

To compare options:

```text
TASK:
Compare Option A and Option B.

CRITERIA:
- Cost
- Performance
- Reliability
- Scalability
- Complexity
- Security
- Maintenance

OUTPUT:
Comparison table followed by analysis.
```

The criteria should be relevant to the actual decision.

---

# Weighted Decision Analysis

Not all criteria have equal importance.

Example:

```text
Performance: 30%
Cost: 25%
Security: 25%
Maintenance: 20%
```

Prompt:

```text
Evaluate these options using weighted criteria.

CRITERIA:
Performance — 30%
Cost — 25%
Security — 25%
Maintenance — 20%

Score each option from 1–10.

Show:
1. Individual scores
2. Weighted scores
3. Total score
4. Sensitivity to changing the weights
5. Final recommendation
```

Weighted scoring makes assumptions explicit.

---

# Tradeoff Analysis

Many decisions have no perfect solution.

Prompt:

```text
Analyze the tradeoffs between these options.

For each option identify:

BENEFITS:
[Benefits]

COSTS:
[Costs]

RISKS:
[Risks]

WHAT WE GAIN:
[Advantages]

WHAT WE GIVE UP:
[Disadvantages]
```

The goal is to make tradeoffs visible.

---

# Cost-Benefit Analysis

```text
TASK:
Perform a cost-benefit analysis.

COSTS:
- Development
- Infrastructure
- Employees
- Maintenance
- Marketing

BENEFITS:
- Revenue
- Efficiency
- Customer value
- Strategic advantages

OUTPUT:
Compare expected costs and benefits.

Clearly identify assumptions.
```

Do not present uncertain estimates as guaranteed financial outcomes.

---

# Risk Analysis

A basic risk framework:

```text
Risk
 ↓
Probability
 ↓
Impact
 ↓
Exposure
 ↓
Mitigation
```

Prompt:

```text
TASK:
Analyze the risks of launching this product.

For each risk provide:
- Description
- Probability
- Impact
- Evidence
- Early warning signs
- Mitigation
- Contingency plan
```

---

# Risk Matrix

You can structure risks as:

```text
| Risk | Probability | Impact | Priority | Mitigation |
|------|-------------|--------|----------|------------|
```

A matrix makes large risk lists easier to prioritize.

---

# Scenario Analysis

When the future is uncertain:

```text
Best Case
   ↓
Expected Case
   ↓
Worst Case
```

Prompt:

```text
Create three scenarios for this business.

1. Optimistic
2. Base case
3. Pessimistic

For each:
- Assumptions
- Main drivers
- Risks
- Expected outcome
- Indicators to monitor
```

Scenarios are not predictions; they are structured possibilities.

---

# Sensitivity Analysis

Sensitivity analysis asks:

> What happens if an important assumption changes?

Example:

```text
Customer acquisition cost:
$20 → $30 → $40 → $50
```

Prompt:

```text
Perform a sensitivity analysis.

VARIABLE:
Customer acquisition cost

VALUES:
20, 30, 40, 50

Show how each value affects
the expected business outcome.
```

This helps identify assumptions that matter most.

---

# Assumption Analysis

Many conclusions depend on hidden assumptions.

Prompt:

```text
TASK:
Identify the assumptions behind this conclusion.

For each assumption:
- State it clearly.
- Explain why it matters.
- Identify supporting evidence.
- Explain what happens if it is wrong.
```

This is one of the most useful analysis techniques.

---

# Decision Analysis

For a decision:

```text
DECISION:
Should we choose Option A or Option B?

CONTEXT:
[Context]

GOALS:
[Goals]

CONSTRAINTS:
[Constraints]

CRITERIA:
[Criteria]

OPTIONS:
A
B

OUTPUT:
1. Evaluation
2. Tradeoffs
3. Risks
4. Recommendation
5. Conditions under which the recommendation changes
```

The final condition is important because recommendations can depend on assumptions.

---

# Decision Tree

Some decisions contain multiple paths.

```text
Decision
├── Option A
│   ├── Success
│   └── Failure
└── Option B
    ├── Success
    └── Failure
```

Prompt:

```text
Build a decision tree for this problem.

For each branch identify:
- Decision
- Possible outcome
- Probability if evidence supports it
- Impact
- Next decision
```

Do not invent probabilities when no evidence exists.

---

# Evidence-Based Analysis

Ask AI to distinguish evidence from inference.

```text
For every major conclusion, provide:

CLAIM:
[Conclusion]

EVIDENCE:
[Supporting evidence]

INFERENCE:
[Reasoning connecting evidence to conclusion]

CONFIDENCE:
[High / Medium / Low]

LIMITATION:
[Important limitation]
```

This makes the analytical chain easier to inspect.

---

# Analysis of Conflicting Evidence

```text
TASK:
Analyze these conflicting findings.

SOURCE A:
[Finding]

SOURCE B:
[Finding]

SOURCE C:
[Finding]

OUTPUT:
1. What each source claims
2. Why they may disagree
3. Methodological differences
4. Evidence strength
5. What can reasonably be concluded
```

Do not force agreement when the evidence does not support it.

---

# Causal Analysis

Causal questions require extra caution.

Weak:

```text
Does X cause Y?
```

Better:

```text
Evaluate whether the available evidence supports
a causal relationship between X and Y.

Consider:
- Temporal order
- Alternative explanations
- Confounding variables
- Experimental evidence
- Correlation vs. causation
```

Correlation alone is generally insufficient to establish causation.

---

# Scenario Planning

For strategic decisions:

```text
CURRENT STATE
     ↓
Key Drivers
     ↓
Uncertainties
     ↓
Possible Futures
     ↓
Strategic Responses
```

Prompt:

```text
Identify the two most important uncertainties
that could shape the future of this market.

Create four scenarios based on those uncertainties.

For each scenario:
- Description
- Drivers
- Risks
- Opportunities
- Recommended response
```

---

# Strategic Analysis

```text
TASK:
Analyze the strategic position of this company.

CONSIDER:
- Market position
- Competitive advantage
- Customer segments
- Distribution
- Technology
- Economics
- Threats
- Opportunities

OUTPUT:
Current position → Strategic options → Recommendation
```

---

# Product Analysis

```text
TASK:
Analyze this product idea.

EVALUATE:
- Customer problem
- User value
- Differentiation
- Usability
- Technical feasibility
- Business model
- Competition
- Risks
- Growth potential

OUTPUT:
Strengths → Weaknesses → Risks → Opportunities → Recommendation
```

---

# Technical Architecture Analysis

```text
TASK:
Analyze this software architecture.

CHECK:
- Scalability
- Reliability
- Security
- Performance
- Maintainability
- Coupling
- Complexity
- Failure points

OUTPUT:
1. Architecture summary
2. Strengths
3. Weaknesses
4. Bottlenecks
5. Risks
6. Recommended improvements
```

---

# Code Analysis

For code:

```text
TASK:
Analyze this codebase.

CHECK:
- Architecture
- Complexity
- Duplication
- Security
- Performance
- Maintainability
- Error handling
- Testing

OUTPUT:
Prioritized findings with severity and recommendations.
```

Analysis is different from refactoring: first understand the problems, then decide what should change.

---

# Root Cause vs. Symptom

A useful analytical distinction:

```text
Symptom:
Application is slow.

Possible causes:
- Database queries
- Network latency
- CPU usage
- Memory pressure
- Inefficient algorithm

Root cause:
The specific underlying issue supported by evidence.
```

Prompt:

```text
Separate:
1. Symptoms
2. Immediate causes
3. Contributing factors
4. Root cause
```

---

# Prioritization Analysis

When there are many problems:

```text
TASK:
Prioritize these issues.

CRITERIA:
- Impact
- Urgency
- Effort
- Risk
- Dependency

OUTPUT:
Priority ranking with explanation.
```

A common framework is:

```text
Priority Score =
Impact × Urgency ÷ Effort
```

If using a formula, define the scoring scale clearly.

---

# Pareto Analysis

Pareto-style analysis asks which causes account for the largest share of the problem.

Prompt:

```text
Analyze these problems and identify
which small number of causes appear to
account for the largest portion of the impact.

Do not assume a Pareto distribution exists;
use the available evidence.
```

---

# Five-Level Analysis

For complicated problems:

```text
LEVEL 1:
What happened?

LEVEL 2:
Why did it happen?

LEVEL 3:
What factors contributed?

LEVEL 4:
What assumptions or system weaknesses allowed it?

LEVEL 5:
What should change?
```

This moves from observation toward action.

---

# Analysis Output Structure

A strong general format:

```text
## Problem
[Definition]

## Context
[Relevant context]

## Evidence
[Evidence]

## Findings
[Major findings]

## Analysis
[Interpretation]

## Alternatives
[Options]

## Tradeoffs
[Tradeoffs]

## Risks
[Risks]

## Recommendation
[Recommendation]

## Uncertainty
[What remains unknown]

## Next Steps
[Actions]
```

---

# Analysis Prompt Template

```text
# ROLE
Act as a senior analyst specializing in [DOMAIN].

# OBJECTIVE
[What decision or problem should be addressed?]

# CONTEXT
[Relevant context]

# PROBLEM
[Problem]

# EVIDENCE
[Data / documents / information]

# OPTIONS
[Options, if applicable]

# CRITERIA
- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]

# REQUIREMENTS
- Separate facts from assumptions.
- Identify uncertainty.
- Consider alternative explanations.
- Do not invent missing evidence.
- Explain important conclusions.

# OUTPUT
1. Problem definition
2. Evidence
3. Findings
4. Analysis
5. Alternatives
6. Tradeoffs
7. Risks
8. Recommendation
9. Uncertainty
10. Next steps
```

---

# Before and After

## Weak

```text
Analyze this startup idea.
```

## Strong

```text
ROLE:
Act as a startup strategy analyst.

OBJECTIVE:
Determine whether this startup idea is
worth validating further.

IDEA:
[Description]

TARGET CUSTOMER:
[Customer]

PROBLEM:
[Problem]

ANALYZE:
- Problem severity
- Customer willingness to pay
- Existing alternatives
- Competitive landscape
- Differentiation
- Technical feasibility
- Acquisition difficulty
- Business model
- Major risks

CONSTRAINTS:
- Identify assumptions.
- Do not claim market demand without evidence.
- Separate evidence from speculation.

OUTPUT:
1. Key findings
2. Strongest assumptions
3. Risks
4. Opportunities
5. Validation experiments
6. Recommendation
```

The stronger version transforms an open-ended request into a structured analytical investigation.

---

# Analysis Checklist

Before sending an analysis prompt:

* [ ] Is the objective clear?
* [ ] Is the problem clearly defined?
* [ ] Is relevant context provided?
* [ ] Are important variables identified?
* [ ] Are evaluation criteria defined?
* [ ] Are constraints specified?
* [ ] Are assumptions identified?
* [ ] Are alternative explanations considered?
* [ ] Are tradeoffs examined?
* [ ] Is uncertainty acknowledged?
* [ ] Is the desired output defined?
* [ ] Does the recommendation depend on evidence?

---

# Key Takeaways

1. Analysis is about understanding relationships, causes, tradeoffs, and implications.
2. Define the analytical objective before asking for analysis.
3. Separate evidence, assumptions, inference, and conclusions.
4. Root-cause analysis should distinguish symptoms from underlying causes.
5. Comparative analysis requires explicit criteria.
6. Weighted decision analysis makes priorities visible.
7. Risk analysis should consider probability, impact, and mitigation.
8. Scenario and sensitivity analysis help handle uncertainty.
9. Do not force conclusions when evidence is insufficient.
10. Strong analysis prompts turn raw information into **structured reasoning and actionable decisions**.

---

## Next

**`03-patterns/08-decision-making.md`**

This file will focus specifically on **AI-assisted decision-making, option evaluation, scoring frameworks, tradeoffs, prioritization, recommendations, and decision criteria**.
