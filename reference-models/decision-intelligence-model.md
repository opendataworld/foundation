# OpenDataWorld Decision Intelligence Model

OpenDataWorld treats decision intelligence as the value-realization layer of data and analytics solutions as a service.

Decision intelligence connects governed data, trust, analytics, insights, evidence, assumptions, constraints, alternatives, decisions, actions, outcomes, value, learning, and improvement.

## Decision Intelligence North Star

```text
Every important decision should be traceable to the data, evidence, assumptions, constraints, trust, and context that shaped it — and to the outcome and value it produced.
```

## Core Value Chain

```text
Data
    ↓
Trust
    ↓
Metric
    ↓
Insight
    ↓
Recommendation
    ↓
Decision
    ↓
Action
    ↓
Outcome
    ↓
Value
    ↓
Learning
    ↓
Improvement
```

## Core Assertions

1. Data alone does not create value.
2. Analytics alone does not create value.
3. Value is realized when data improves decisions, actions, outcomes, learning, and future behavior.
4. Every important decision should preserve evidence and context.
5. Every decision should reference the data versions used.
6. Every insight should disclose evidence, confidence, assumptions, and limitations.
7. Every outcome should link back to the decision, action, workflow, service, or program that produced it.
8. Every value claim should be evidence-backed or clearly marked as estimated.
9. Every learning should feed improvement.
10. Agents may assist decision intelligence, but high-impact decisions must preserve human accountability.

## Decision Intelligence Objects

```text
DecisionIntelligence
├── DecisionContext
├── DataInput
├── TrustAssessment
├── Metric
├── Insight
├── Recommendation
├── Evidence
├── Assumption
├── Constraint
├── Alternative
├── Decision
├── Action
├── Outcome
├── Value
├── Learning
└── ImprovementAction
```

## Decision Context

Decision context defines the situation in which a decision is made.

```yaml
id: string
decisionPurpose: string
scope: string
stakeholders:
  - string
constraints:
  - string
availableData:
  - string
policies:
  - string
riskLevel: string
timeHorizon: string
jurisdiction: string
```

## Data Input

Every decision that uses data must preserve data references.

```yaml
dataAsset: string
version: string
accessedAt: datetime
trustAssessment: string
qualityProfile: string
limitations:
  - string
```

## Insight to Decision Bridge

An insight should not automatically become a decision.

```text
Insight
    ↓
Interpretation
    ↓
Recommendation
    ↓
Review
    ↓
Decision
```

## Decision Record

A decision record preserves how and why a decision was made.

```yaml
id: string
decisionType: string
madeBy: string
madeAt: datetime
basedOnDataAssets:
  - id: string
    version: string
basedOnEvidence:
  - string
assumptions:
  - string
constraints:
  - string
alternatives:
  - string
selectedOption: string
confidence: number
rationale: string
outcome: string
reviewStatus: string
```

## Alternative Model

Alternatives make decision reasoning explicit.

```yaml
option: string
expectedOutcome: string
benefits:
  - string
risks:
  - string
constraints:
  - string
cost: string
confidence: number
```

## Action Model

Actions operationalize decisions.

```yaml
actionId: string
decision: string
actor: string
actionType: string
target: string
startedAt: datetime
completedAt: datetime
status: string
policyDecision: string
auditEvent: string
```

## Outcome Model

Outcomes evaluate what happened after action.

```yaml
id: string
producedBy: string
measuredAt: datetime
metrics:
  - string
baseline: object
actual: object
impact: string
value: string
learning:
  - string
```

## Value Model

Value explains why an outcome matters.

```text
Value
├── Public Value
├── Operational Value
├── Financial Value
├── Research Value
├── Social Value
├── Compliance Value
├── Risk Reduction
├── Time Savings
├── Quality Improvement
└── Decision Improvement
```

## Learning Model

Learning captures what should change after observing outcomes.

```yaml
learningId: string
sourceOutcome: string
lesson: string
confidence: number
recommendedImprovement: string
owner: string
status: string
```

## Improvement Loop

Decision intelligence is incomplete without improvement.

```text
Outcome observed
    ↓
Learning captured
    ↓
Improvement action proposed
    ↓
Owner assigned
    ↓
Policy, data, metric, model, workflow, or service updated
    ↓
Future decisions improve
```

## Decision Governance

Decision intelligence must be governed.

### Governance Requirements

- Decision maker identity
- Data version references
- Evidence references
- Policy references
- Assumption disclosure
- Constraint disclosure
- Alternative consideration
- Rationale capture
- Review status
- Outcome tracking where applicable

## Agentic Decision Support

Agents may assist decision intelligence by:

- Finding relevant data
- Summarizing evidence
- Explaining metrics
- Drafting insight cards
- Comparing alternatives
- Preparing decision briefs
- Tracking outcomes
- Suggesting improvements

Agents must not autonomously make high-impact decisions unless explicitly governed, approved, and auditable.

## Minimum Viable Decision Intelligence Baseline

The first operational platform should support:

1. Decision records
2. Data version references
3. Evidence references
4. Assumptions
5. Constraints
6. Alternatives
7. Selected option
8. Rationale
9. Outcome link
10. Review status
11. Learning notes
12. Improvement actions

## Validation Rules

1. Every decision must have a decision maker.
2. Every decision must have a timestamp.
3. Every decision must have a selected option.
4. Every data-informed decision must reference data versions.
5. Every evidence-backed decision must preserve evidence references.
6. Every approved decision must have reviewer or approval context.
7. Every outcome must link back to decision, action, workflow, service, or program where possible.
8. Every value claim must be evidence-backed or marked as estimated.
9. Every learning should reference an outcome.
10. Every agent-assisted decision artifact must disclose agent involvement.

## Relationship to Foundation Schemas

```text
Dataset schema defines data inputs.
TrustAssessment schema defines confidence context.
Metric schema defines measurement.
Insight schema defines interpretation.
Decision schema defines choice and rationale.
Outcome schema defines result and value.
Agent schema defines governed automation support.
```

## Status

Draft. Canonical after governance review.
