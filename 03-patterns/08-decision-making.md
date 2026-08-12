# Decision-Making Prompts

Decision-making prompts help AI evaluate options, identify tradeoffs, compare alternatives, assess risks, and support better decisions.

A good decision prompt should **not force the AI toward a predetermined answer**. Instead, it should define the goal, constraints, criteria, available options, and acceptable tradeoffs.

---

# What Is a Decision-Making Prompt?

Weak:

```text
Which programming language is best?
```

Better:

```text
I need to choose a programming language for a
small SaaS application.

Options:
- Python
- JavaScript
- Go

Criteria:
- Development speed
- Performance
- Ecosystem
- Hiring
- Maintenance

Recommend the most suitable option and explain
the tradeoffs.
```

The second prompt gives the AI enough context to make a useful comparison.

---

# The Decision-Making Framework

A general decision workflow is:

```text
Goal
 ↓
Context
 ↓
Constraints
 ↓
Options
 ↓
Criteria
 ↓
Evidence
 ↓
Tradeoffs
 ↓
Risks
 ↓
Decision
 ↓
Action
```

Each stage can be explicitly included in a prompt.

---

# Define the Decision

Start with a clear question.

Weak:

```text
Should I build an app?
```

Better:

```text
Should I build a mobile app for small businesses
or start with a web application?
```

Best:

```text
Given a limited development budget and a target
audience of small businesses, should we launch
our product as a web application first or build
native mobile applications?
```

Specific decisions produce better analysis.

---

# Define the Goal

The AI needs to know what success means.

```text
GOAL:
Minimize development cost while reaching customers
as quickly as possible.
```

Another example:

```text
GOAL:
Choose the architecture that provides the best
long-term scalability without unnecessary complexity.
```

Different goals can produce different decisions.

---

# Define Constraints

Real-world decisions always have constraints.

```text
CONSTRAINTS:
- Budget: $10,000
- Team: 3 developers
- Timeline: 3 months
- Target: First 1,000 users
```

Without constraints, AI may recommend solutions that are unrealistic.

---

# Define Options

Explicitly list the options when possible.

```text
OPTIONS:
A. Build internally
B. Hire an external agency
C. Use an existing SaaS platform
```

If you don't know the options:

```text
Identify the most realistic options before
evaluating them.
```

---

# Define Decision Criteria

Common criteria include:

* Cost
* Time
* Quality
* Performance
* Security
* Scalability
* Reliability
* Complexity
* Risk
* Customer value
* Revenue potential
* Maintainability

Example:

```text
CRITERIA:
Cost
Speed
Security
Scalability
Maintenance
```

Only include criteria that actually matter to the decision.

---

# Criteria Weighting

Some criteria matter more than others.

Example:

```text
Cost: 20%
Performance: 25%
Security: 30%
Scalability: 15%
Maintenance: 10%
```

Prompt:

```text
Score each option from 1–10.

Apply these weights:
Cost: 20%
Performance: 25%
Security: 30%
Scalability: 15%
Maintenance: 10%

Calculate the weighted total.
```

This makes the decision process more transparent.

---

# Weighted Decision Matrix

A useful structure:

```text
| Criteria | Weight | Option A | Option B | Option C |
|----------|--------|----------|----------|----------|
| Cost | 20% | 8 | 6 | 9 |
| Performance | 25% | 7 | 9 | 6 |
| Security | 30% | 8 | 8 | 7 |
| Scalability | 15% | 7 | 9 | 6 |
| Maintenance | 10% | 9 | 7 | 8 |
```

Then calculate the weighted score.

The important part is not the mathematical score itself; it is making the assumptions visible.

---

# Decision Matrix Prompt

```text
TASK:
Create a decision matrix for the following options.

OPTIONS:
A: [Option]
B: [Option]
C: [Option]

CRITERIA:
- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

WEIGHTS:
- Criterion 1: [%]
- Criterion 2: [%]
- Criterion 3: [%]

SCALE:
1 = Very poor
10 = Excellent

OUTPUT:
1. Decision matrix
2. Weighted scores
3. Strongest option
4. Weakest option
5. Key tradeoffs
6. Recommendation
```

---

# Decision Trees

Some decisions contain multiple possible outcomes.

```text
Choose Strategy
├── Strategy A
│   ├── Success
│   └── Failure
└── Strategy B
    ├── Success
    └── Failure
```

Prompt:

```text
Create a decision tree for this decision.

For every branch identify:
- Decision
- Possible outcome
- Consequence
- Risk
- Next decision
```

Do not invent probabilities unless they are supported by evidence.

---

# Decision Under Uncertainty

Sometimes the information is incomplete.

```text
TASK:
Help evaluate this decision under uncertainty.

Clearly separate:
- Known facts
- Assumptions
- Unknowns
- Risks
- Possible outcomes
```

This prevents false confidence.

---

# Expected Value

When probabilities are reasonably known, expected value can help.

```text
Expected Value =
Probability × Outcome
```

Example:

```text
Option A:
60% chance of $100,000 gain
40% chance of $20,000 loss
```

Prompt:

```text
Calculate the expected value of each option.

Show:
- Possible outcomes
- Probabilities
- Expected value
- Important assumptions
```

Expected value should not be treated as the only decision criterion.

---

# Risk-Adjusted Decision

A financially attractive option may also have much higher risk.

Prompt:

```text
Evaluate these options using:

1. Expected benefit
2. Probability of success
3. Downside risk
4. Required investment
5. Recovery options

Explain whether the higher potential return
justifies the additional risk.
```

---

# Best-Case / Base-Case / Worst-Case

Use scenarios when outcomes are uncertain.

```text
OPTION A

Best case:
[Outcome]

Base case:
[Outcome]

Worst case:
[Outcome]
```

Prompt:

```text
For each option, analyze:

BEST CASE
BASE CASE
WORST CASE

Then compare:
- Probability
- Impact
- Risk
- Reversibility
```

---

# Reversible vs. Irreversible Decisions

Not every decision deserves the same amount of analysis.

### Reversible

Example:

```text
Testing a new landing page.
```

You can change it later.

### Difficult to Reverse

Example:

```text
Signing a long-term infrastructure contract.
```

Prompt:

```text
Classify this decision as:

1. Easily reversible
2. Moderately reversible
3. Difficult to reverse

Adjust the decision process accordingly.
```

For reversible decisions, speed can matter more than perfect certainty.

---

# One-Way vs. Two-Way Doors

A useful decision framework:

```text
Two-way door:
Easy to reverse → Decide quickly.

One-way door:
Difficult to reverse → Analyze carefully.
```

Prompt:

```text
Determine whether this is a one-way or two-way
decision.

If reversible:
Prioritize speed and experimentation.

If difficult to reverse:
Prioritize evidence, risk analysis, and
scenario planning.
```

---

# Opportunity Cost

Choosing one option means giving up another.

Prompt:

```text
Analyze the opportunity cost of each option.

For every option identify:
- What we gain
- What we give up
- What alternative becomes unavailable
- Long-term consequences
```

This prevents decisions from being evaluated only by their direct benefits.

---

# Short-Term vs. Long-Term

Some options optimize the present while damaging future flexibility.

```text
Compare each option across:

SHORT TERM:
0–12 months

MEDIUM TERM:
1–3 years

LONG TERM:
3+ years
```

Then ask:

```text
Which option provides the best balance
between short-term execution and long-term value?
```

---

# Strategic Fit

An option may be good generally but wrong for your organization.

Prompt:

```text
Evaluate each option based on strategic fit.

Consider:
- Current capabilities
- Team skills
- Existing infrastructure
- Business model
- Customer base
- Long-term strategy
```

---

# Decision With Limited Information

When information is missing:

```text
TASK:
Identify the minimum additional information
needed to make this decision with greater confidence.

For each missing information item:
- Why it matters
- How to obtain it
- Estimated effort
- Expected impact on the decision
```

This turns uncertainty into a research plan.

---

# Value of Information

Sometimes the best next action is not choosing an option—it is gathering information.

Prompt:

```text
Before making the decision:

Identify the unknowns that could materially
change the recommendation.

Rank them by:
- Importance
- Cost to investigate
- Time required
- Expected reduction in uncertainty
```

This helps determine what should be researched first.

---

# Minimum Viable Decision

For fast-moving projects:

```text
TASK:
Determine the minimum information required
to make a reasonable decision.

Do not require perfect information.

Identify:
- Critical facts
- Useful but non-essential information
- Information that can be learned later
```

This prevents analysis paralysis.

---

# Avoid Analysis Paralysis

A useful prompt:

```text
We have limited time to make this decision.

Identify:
1. Decisions that require deep analysis
2. Decisions that can be made quickly
3. Unknowns that actually matter
4. Unknowns that do not materially affect the decision
```

The objective is not maximum analysis.

The objective is **sufficient analysis for the importance of the decision**.

---

# Decision With Multiple Stakeholders

Different people may have different priorities.

```text
STAKEHOLDERS:

CEO:
Growth

Engineering:
Reliability

Finance:
Cost

Customers:
Ease of use
```

Prompt:

```text
Evaluate the decision from each stakeholder's perspective.

Then identify:
- Areas of agreement
- Conflicts
- Tradeoffs
- Possible compromise
- Final recommendation
```

---

# Stakeholder Decision Matrix

```text
| Criteria | CEO | Engineering | Finance | Customer |
|----------|-----|-------------|---------|----------|
| Growth | High | Medium | High | Medium |
| Cost | Medium | Medium | High | Low |
| Reliability | High | High | Medium | High |
| Ease of Use | High | Medium | Medium | High |
```

This makes conflicting priorities explicit.

---

# Prioritization

Decision-making often involves deciding what to do first.

Prompt:

```text
Prioritize these initiatives.

Evaluate:
- Impact
- Urgency
- Effort
- Strategic importance
- Dependencies
- Risk

Output:
Priority ranking with justification.
```

---

# Impact vs. Effort

A simple framework:

```text
             HIGH IMPACT
                  ↑
                  |
   Quick Wins     |    Major Projects
                  |
------------------+----------------→ EFFORT
                  |
   Low Priority   |    Avoid / Reconsider
                  |
```

Prompt:

```text
Classify each initiative by:

Impact:
Low / Medium / High

Effort:
Low / Medium / High

Then recommend:
- Quick wins
- Strategic projects
- Low-priority items
- Items to reconsider
```

---

# Decision Recommendations

A recommendation should explain **why**.

Weak:

```text
Choose Option B.
```

Strong:

```text
RECOMMENDATION:
Choose Option B.

WHY:
- Better scalability
- Lower long-term maintenance
- Stronger security

TRADEOFF:
Higher initial implementation cost.

CONDITION:
If the budget is reduced below $X,
Option A becomes more practical.
```

This makes recommendations conditional rather than absolute.

---

# Challenge Your Own Recommendation

Ask AI to attack its conclusion.

```text
TASK:
After making your recommendation,
attempt to disprove it.

Identify:
- Strongest counterargument
- Weakest assumption
- Missing evidence
- Scenario where another option wins
```

This can expose weaknesses in the original analysis.

---

# Pre-Mortem Analysis

Imagine the decision failed.

```text
TASK:
Assume our chosen strategy failed completely.

Explain:
1. What probably went wrong?
2. Which assumptions failed?
3. What warning signs did we ignore?
4. What could we have done earlier?
5. How can we reduce these risks?
```

This is useful before major decisions.

---

# Post-Mortem Analysis

After a decision:

```text
TASK:
Analyze the outcome of our decision.

ORIGINAL DECISION:
[Decision]

EXPECTED OUTCOME:
[Expectation]

ACTUAL OUTCOME:
[Result]

ANALYZE:
- What went right?
- What went wrong?
- Which assumptions were correct?
- Which assumptions were wrong?
- What should we change next time?
```

This turns decisions into organizational learning.

---

# Decision Log

A structured decision log:

```text
DECISION:
[Decision]

DATE:
[Date]

OBJECTIVE:
[Goal]

OPTIONS:
[Options]

CRITERIA:
[Criteria]

ASSUMPTIONS:
[Assumptions]

EVIDENCE:
[Evidence]

DECISION:
[Chosen option]

REASON:
[Why]

RISKS:
[Risks]

REVIEW DATE:
[Date]
```

Decision logs help teams understand why decisions were made.

---

# Decision Prompt for Business

```text
ROLE:
Act as a business strategy advisor.

DECISION:
[Decision]

BUSINESS CONTEXT:
[Context]

GOAL:
[Goal]

OPTIONS:
A. [Option]
B. [Option]
C. [Option]

CONSTRAINTS:
- Budget
- Team
- Time
- Market

CRITERIA:
- Revenue potential
- Cost
- Risk
- Speed
- Strategic fit

REQUIREMENTS:
- Identify assumptions.
- Consider opportunity cost.
- Analyze downside risk.
- Identify missing information.
- Challenge the recommendation.

OUTPUT:
1. Decision summary
2. Comparison
3. Tradeoffs
4. Risks
5. Missing information
6. Recommendation
7. Conditions that would change the recommendation
```

---

# Technology Selection Prompt

```text
TASK:
Choose the most appropriate technology for this project.

PROJECT:
[Project]

OPTIONS:
[Options]

TEAM:
[Team skills]

CONSTRAINTS:
[Constraints]

CRITERIA:
- Performance
- Cost
- Security
- Scalability
- Developer experience
- Ecosystem
- Maintenance

OUTPUT:
Comparison table + weighted analysis + recommendation.
```

---

# Career Decision Prompt

```text
TASK:
Help evaluate these career paths.

OPTIONS:
A. [Path A]
B. [Path B]
C. [Path C]

PERSONAL GOALS:
[Goals]

CRITERIA:
- Income potential
- Learning
- Stability
- Growth
- Location
- Work-life balance

Do not decide based on one criterion alone.
Explain the tradeoffs.
```

---

# Product Decision Prompt

```text
TASK:
Determine which product feature should be developed first.

FEATURES:
A. [Feature]
B. [Feature]
C. [Feature]

EVALUATE:
- Customer value
- Revenue impact
- Development effort
- Strategic value
- Risk
- Dependencies

OUTPUT:
Priority ranking + reasoning + recommended sequence.
```

---

# Investment-Style Decision Framework

For general analytical evaluation:

```text
TASK:
Evaluate this opportunity.

ANALYZE:
- Potential upside
- Downside
- Key assumptions
- Risk factors
- Competitive environment
- Time horizon
- Liquidity / reversibility
- Alternative opportunities

CONSTRAINT:
Do not present uncertain outcomes as guaranteed returns.
```

---

# Decision Quality Checklist

Before making a recommendation, check:

```text
[ ] Is the goal clear?
[ ] Are the options defined?
[ ] Are the constraints known?
[ ] Are the criteria relevant?
[ ] Are criteria weighted appropriately?
[ ] Are assumptions explicit?
[ ] Is evidence available?
[ ] Are risks considered?
[ ] Is opportunity cost considered?
[ ] Is reversibility considered?
[ ] Are alternative outcomes considered?
[ ] Is uncertainty acknowledged?
[ ] Has the recommendation been challenged?
```

---

# Reusable Decision-Making Prompt

```text
# ROLE
Act as a decision-support analyst specializing in [DOMAIN].

# DECISION
[What decision needs to be made?]

# OBJECTIVE
[What are we trying to achieve?]

# CONTEXT
[Relevant background]

# OPTIONS
A. [Option A]
B. [Option B]
C. [Option C]

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]
- [Constraint 3]

# CRITERIA
- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

# WEIGHTS
[Optional weights]

# REQUIREMENTS
- Separate facts from assumptions.
- Identify missing information.
- Analyze tradeoffs.
- Consider opportunity cost.
- Evaluate risks.
- Consider reversibility.
- Challenge the recommendation.
- Do not invent evidence.

# OUTPUT
1. Decision definition
2. Options
3. Criteria
4. Decision matrix
5. Tradeoffs
6. Risks
7. Missing information
8. Recommendation
9. Counterargument
10. Conditions that would change the decision
11. Next action
```

---

# Key Takeaways

1. Good decision prompts define the **goal, options, constraints, and criteria**.
2. Weighted criteria make priorities explicit.
3. Decisions should consider both benefits and opportunity costs.
4. Risk and uncertainty should be visible.
5. Reversible decisions can usually be made faster.
6. Irreversible decisions deserve deeper analysis.
7. Missing information can become a research task.
8. Scenario and sensitivity analysis help with uncertain outcomes.
9. Recommendations should explain their assumptions and tradeoffs.
10. Challenge the recommendation before committing to it.
11. A good AI decision prompt does not simply ask **"What should I choose?"** — it creates a transparent process for determining **why** one option is preferable.

---

## Next

**`03-patterns/09-classification.md`**

This file will cover prompts for **categorizing information, assigning labels, detecting intent, sorting data, sentiment classification, priority classification, and building consistent classification rules**.
