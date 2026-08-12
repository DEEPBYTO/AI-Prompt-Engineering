# Classification Prompts

Classification prompts help AI assign information to predefined categories or labels.

They are useful for:

* Customer support
* Sentiment analysis
* Spam detection
* Content moderation
* Lead qualification
* Priority detection
* Document categorization
* Intent detection
* Business workflows
* Data organization

A good classification prompt defines **the categories, rules, boundaries, and output format** clearly.

---

# What Is Classification?

Classification means assigning an input to one or more predefined categories.

Example:

```text
Input:
"I cannot log into my account."

Category:
Account Access
```

Another example:

```text
Input:
"I love this product!"

Category:
Positive
```

The AI is not simply summarizing the input. It is **assigning a label according to defined rules**.

---

# Basic Classification Prompt

Weak:

```text
Classify this message.
```

Strong:

```text
TASK:
Classify the customer message.

CATEGORIES:
- Billing
- Technical Support
- Account Access
- Feature Request
- Other

RULE:
Choose the category that best represents
the customer's primary issue.

OUTPUT:
Return only the category name.
```

The second prompt defines exactly how classification should work.

---

# Classification Structure

A reusable structure:

```text
TASK:
[Classification task]

INPUT:
[Text / data]

CATEGORIES:
- [Category A]
- [Category B]
- [Category C]

RULES:
[Classification rules]

PRIORITY:
[How conflicts should be handled]

OUTPUT:
[Required format]

UNCERTAINTY:
[What to do when classification is unclear]
```

---

# Define Categories Clearly

Poor categories:

```text
Good
Bad
Other
```

Better:

```text
- Billing Issue
- Technical Issue
- Account Issue
- Product Feedback
- General Question
```

Categories should be:

* Clear
* Distinct
* Relevant
* Consistent
* Easy to identify

---

# Category Definitions

Definitions make classification more reliable.

```text
CATEGORIES:

Billing:
Questions involving payments, invoices, refunds,
or charges.

Technical:
Problems involving software functionality,
errors, crashes, or performance.

Account:
Login, password, registration, or account access.

Feature Request:
Requests for new functionality.

Other:
Anything that does not fit the categories above.
```

The AI now has a decision boundary for each label.

---

# Single-Label Classification

Use this when only one category is allowed.

```text
TASK:
Assign exactly one category.

CATEGORIES:
- Sales
- Support
- Billing
- Feedback

RULE:
Choose the category representing the primary
purpose of the message.

OUTPUT:
One category only.
```

Example:

```text
Input:
"Can you tell me how much your enterprise plan costs?"

Output:
Sales
```

---

# Multi-Label Classification

Sometimes an input belongs to multiple categories.

```text
TASK:
Assign all applicable categories.

CATEGORIES:
- Billing
- Technical
- Account
- Security
- Feature Request

RULE:
More than one category may be selected.

OUTPUT:
Return a JSON array of labels.
```

Example:

```text
Input:
"My account was hacked after I was charged twice."

Output:
["Account", "Security", "Billing"]
```

---

# Hierarchical Classification

Some classification systems contain levels.

```text
Technology
├── Software
│   ├── AI
│   ├── Web
│   └── Mobile
└── Hardware
    ├── Robotics
    └── Electronics
```

Prompt:

```text
TASK:
Classify the input using the category hierarchy.

OUTPUT:
Level 1 → Level 2 → Level 3
```

Example:

```text
AI chatbot

Technology → Software → AI
```

---

# Intent Classification

Intent classification identifies what the user wants.

Example categories:

```text
- Buy Product
- Cancel Order
- Track Order
- Request Refund
- Ask Question
- Contact Support
```

Prompt:

```text
TASK:
Identify the user's intent.

INPUT:
[Customer message]

OUTPUT:
Intent + confidence
```

---

# Sentiment Classification

Common categories:

```text
- Positive
- Neutral
- Negative
```

Prompt:

```text
TASK:
Classify the sentiment.

CATEGORIES:
Positive
Neutral
Negative

RULE:
Classify the emotional sentiment expressed
by the customer.

OUTPUT:
Sentiment + short explanation
```

Example:

```text
Input:
"The product works perfectly and I'm very happy."

Output:
Positive
```

---

# Sentiment With More Categories

For more detailed analysis:

```text
- Very Positive
- Positive
- Neutral
- Negative
- Very Negative
```

Do not create more categories unless the use case actually benefits from them.

---

# Urgency Classification

Useful for customer support.

```text
CATEGORIES:

Critical:
Immediate action required.

High:
Important issue requiring quick response.

Medium:
Normal priority.

Low:
Can be handled later.
```

Prompt:

```text
Classify the urgency of this request.

Consider:
- Business impact
- Number of affected users
- Security implications
- Time sensitivity

Output:
Priority + reason.
```

---

# Lead Classification

For sales:

```text
CATEGORIES:

Hot:
Strong buying intent and high potential value.

Warm:
Some buying intent but requires nurturing.

Cold:
Little immediate buying intent.
```

Prompt:

```text
TASK:
Classify this lead.

Consider:
- Buying intent
- Budget signals
- Timeline
- Business need
- Decision authority

OUTPUT:
Lead category + evidence.
```

---

# Spam Classification

```text
CATEGORIES:
- Spam
- Legitimate
- Unclear
```

Prompt:

```text
TASK:
Determine whether this message is spam.

RULES:
Consider:
- Suspicious links
- Repetitive promotional language
- Requests for sensitive information
- Misleading claims
- Unusual sender behavior

If evidence is insufficient:
Return Unclear.
```

Allowing **Unclear** is safer than forcing a binary decision.

---

# Content Classification

For organizing content:

```text
CATEGORIES:
- Education
- Business
- Technology
- Entertainment
- News
- Sports
- Other
```

Prompt:

```text
Classify the content into the most appropriate
category.

Use only the information provided.
```

---

# Document Classification

```text
TASK:
Classify each document.

CATEGORIES:
- Contract
- Invoice
- Resume
- Research Paper
- Technical Documentation
- Report
- Other
```

For each document:

```text
Document → Category
```

---

# Priority Classification

For project management:

```text
P0 = Critical
P1 = High
P2 = Medium
P3 = Low
```

Prompt:

```text
Classify each task according to priority.

P0:
Blocking or critical issue.

P1:
High business impact.

P2:
Important but not urgent.

P3:
Low impact or optional.

Return:
Task → Priority → Reason
```

---

# Risk Classification

```text
LOW
MEDIUM
HIGH
CRITICAL
```

Prompt:

```text
Classify each identified risk.

Consider:
- Probability
- Potential impact
- Detectability
- Time sensitivity

Return:
Risk → Classification → Reason
```

---

# Classification With Rules

Explicit rules can reduce inconsistent outputs.

```text
RULES:

1. If the issue involves unauthorized access,
classify as Security.

2. If the issue involves payment or billing,
classify as Billing.

3. If both apply, choose Security as primary.

4. If no category clearly applies,
return Other.
```

Rules are especially useful when categories overlap.

---

# Priority Rules

When multiple categories could apply:

```text
PRIORITY:

Security
↓
Account
↓
Billing
↓
Technical
↓
Feature Request
↓
Other
```

Prompt:

```text
If multiple categories apply,
use the highest-priority applicable category.
```

This creates deterministic behavior.

---

# Classification With Confidence

```text
OUTPUT:

Category:
[Category]

Confidence:
High / Medium / Low

Reason:
[Short explanation]
```

Example:

```text
Category: Billing
Confidence: High
Reason: The user is reporting an unexpected charge.
```

Confidence should reflect the clarity of the evidence.

---

# Classification With Uncertainty

A robust classifier should be allowed to say:

```text
Unknown
```

or:

```text
Unclear
```

Prompt:

```text
If none of the categories can be assigned
with reasonable confidence, return:

Unclear

Do not guess.
```

This is an important classification principle.

---

# Few-Shot Classification

Examples can teach the classification pattern.

```text
EXAMPLES:

Input:
"I was charged twice."

Category:
Billing

Input:
"I forgot my password."

Category:
Account

Input:
"The application keeps crashing."

Category:
Technical
```

Then:

```text
Now classify:

"I cannot access my account after changing my password."
```

Examples can be especially useful when category boundaries are difficult to explain with rules alone.

---

# Classification With JSON

For software workflows:

```text
TASK:
Classify the customer message.

OUTPUT EXACTLY:

{
  "category": "string",
  "confidence": "high|medium|low",
  "reason": "string"
}
```

Structured output makes AI results easier to process programmatically.

---

# Batch Classification

For multiple inputs:

```text
TASK:
Classify every item.

INPUTS:
1. [Text]
2. [Text]
3. [Text]
4. [Text]

OUTPUT:

1. Category
2. Category
3. Category
4. Category
```

For larger systems, structured JSON or CSV-style output can be preferable.

---

# Classification + Extraction

Sometimes classification alone is insufficient.

```text
TASK:
Analyze the customer message.

EXTRACT:
- Customer name
- Product
- Issue

CLASSIFY:
- Intent
- Priority
- Sentiment
```

Example output:

```text
Name: Ahmed
Product: Mobile App
Intent: Technical Support
Priority: High
Sentiment: Negative
```

This combines multiple AI tasks into one workflow.

---

# Classification + Routing

Classification can determine what happens next.

```text
Message
   ↓
Classification
   ↓
Routing
   ↓
Specialist
```

Example:

```text
Security → Security Team
Billing → Finance Team
Technical → Engineering Team
Sales → Sales Team
```

Prompt:

```text
Classify the request and determine
which department should receive it.
```

---

# Classification + Automation

A more advanced workflow:

```text
Customer Message
        ↓
Intent Classification
        ↓
Priority Classification
        ↓
Department Routing
        ↓
Automated Response
```

Example:

```text
Security + Critical
        ↓
Security Team
        ↓
Immediate escalation
```

This is a common AI automation pattern.

---

# Classification Consistency

For production systems, consistency matters.

Prompt:

```text
Use the category definitions exactly.

Do not change category names.

Do not create new categories.

If the input does not fit:
return Other.

Apply the same rules to every input.
```

This prevents category drift.

---

# Classification Evaluation

A classifier should be tested.

Create test examples:

```text
Input
Expected Category
AI Category
Correct?
```

Example:

```text
| Input | Expected | AI Output | Correct |
|------|----------|-----------|---------|
| Forgot password | Account | Account | Yes |
| Double charge | Billing | Billing | Yes |
| App crashes | Technical | Technical | Yes |
```

A classification system should be evaluated against known examples.

---

# Confusion Analysis

If the AI repeatedly confuses two categories:

```text
Billing
    ↕
Sales
```

The category definitions may be too similar.

Prompt:

```text
Analyze these classification errors.

Identify:
- Most common confusion
- Why the categories overlap
- Which rule is unclear
- How the category definitions should change
```

Improving the taxonomy can be more effective than simply making the prompt longer.

---

# Classification Taxonomy

A taxonomy defines how categories are organized.

Example:

```text
Customer Support
├── Account
│   ├── Login
│   └── Password
├── Billing
│   ├── Payment
│   └── Refund
└── Technical
    ├── Bug
    └── Performance
```

A well-designed taxonomy makes classification easier.

---

# Classification vs. Clustering

These are different.

### Classification

Categories are predefined.

```text
Input → Existing Category
```

### Clustering

The system discovers groups.

```text
Inputs
 ↓
Patterns
 ↓
Discovered Groups
```

If you already know the categories, use classification.

If you want AI to discover categories, consider clustering instead.

---

# Dynamic Category Discovery

Prompt:

```text
Analyze these customer messages.

Do not use predefined categories.

Instead:
1. Identify recurring themes.
2. Group similar messages.
3. Name each group.
4. Explain the defining characteristics.
5. Identify unusual messages.
```

This is useful when building a taxonomy from scratch.

---

# Classification Prompt for Customer Support

```text
# TASK
Classify the customer's request.

# CATEGORIES

Billing:
Payments, charges, invoices, refunds.

Account:
Login, registration, password, account access.

Technical:
Errors, crashes, bugs, performance.

Security:
Unauthorized access, suspicious activity,
compromised accounts.

Feature Request:
Requests for new functionality.

Other:
Anything that does not fit above.

# RULES

- Choose one primary category.
- Prioritize Security when unauthorized access
  is involved.
- Do not guess.
- Use Other when the evidence is insufficient.

# OUTPUT

Category:
[Category]

Confidence:
[High / Medium / Low]

Reason:
[One sentence]
```

---

# Classification Prompt for Content

```text
# TASK
Classify the following content.

# CATEGORIES
- Technology
- Business
- Education
- Science
- Entertainment
- News
- Sports
- Other

# RULE
Choose the category representing the
primary subject of the content.

# OUTPUT
Category + confidence.
```

---

# Classification Prompt for Business Leads

```text
# TASK
Classify this lead.

# CATEGORIES
HOT:
Strong buying intent and near-term opportunity.

WARM:
Potential customer but requires further engagement.

COLD:
Low current buying intent.

UNQUALIFIED:
Insufficient information.

# CONSIDER
- Buying intent
- Budget
- Timeline
- Need
- Decision authority

# OUTPUT
Category
Evidence
Confidence
```

---

# Classification Prompt for Bug Reports

```text
# TASK
Classify this bug report.

# CATEGORIES
- Critical
- High
- Medium
- Low

# CONSIDER
- Number of affected users
- Data loss
- Security impact
- System availability
- Workaround availability

# OUTPUT
Severity
Reason
Recommended escalation
```

---

# Classification Prompt Template

```text
# ROLE
Act as a classification system for [DOMAIN].

# TASK
Classify the input into the appropriate category.

# INPUT
[Input]

# CATEGORIES

## [Category A]
[Definition]

## [Category B]
[Definition]

## [Category C]
[Definition]

## Other
Use when no category clearly applies.

# RULES
- Follow category definitions.
- Choose the primary category.
- Do not invent categories.
- Do not guess when evidence is insufficient.
- Apply the same rules consistently.

# OUTPUT
Category: [Category]
Confidence: [High / Medium / Low]
Reason: [Short explanation]
```

---

# Classification Checklist

Before creating a classification prompt:

* [ ] Are categories clearly defined?
* [ ] Are categories sufficiently distinct?
* [ ] Is single-label or multi-label classification specified?
* [ ] Are overlapping categories handled?
* [ ] Is there an `Other` or `Unclear` option?
* [ ] Are priority rules defined?
* [ ] Are examples provided when useful?
* [ ] Is confidence required?
* [ ] Is the output format defined?
* [ ] Can the classification be evaluated against test examples?
* [ ] Are category names fixed?
* [ ] Are edge cases addressed?

---

# Key Takeaways

1. Classification assigns inputs to predefined categories.
2. Categories should have clear and distinct definitions.
3. Classification rules should explain how overlapping categories are handled.
4. Use single-label classification when one primary category is required.
5. Use multi-label classification when multiple categories can legitimately apply.
6. Confidence and `Unclear` options reduce forced guessing.
7. Examples can improve consistency for difficult classification tasks.
8. Structured outputs are useful when classification feeds software or automation.
9. Classification can be combined with extraction, routing, and automation.
10. Classification systems should be evaluated using known test examples.
11. Repeated classification errors may indicate a poorly designed taxonomy.
12. Good classification prompts turn AI into a **consistent labeling and decision-routing system**.

---

## End of `03-patterns`

The next major section should be:

**`04-advanced/01-prompt-chaining.md`**

This moves the repository from individual prompting patterns into **advanced prompt engineering and multi-step AI workflows**.
