# OpenDataWorld Reference Analytics Architecture

OpenDataWorld provides data and analytics solutions as a service for everyone.

This reference analytics architecture defines how governed data becomes metrics, KPIs, reports, dashboards, insights, recommendations, decisions, outcomes, value, learning, and continuous improvement.

## Analytics Architecture North Star

```text
Move beyond dashboards: connect data to insight, decision, action, outcome, value, learning, and improvement.
```

## Core Analytics Flow

```text
Governed Data
    ↓
Metrics
    ↓
KPIs
    ↓
Analysis
    ↓
Reports and Dashboards
    ↓
Insights
    ↓
Recommendations
    ↓
Decisions
    ↓
Actions
    ↓
Outcomes
    ↓
Value
    ↓
Learning
    ↓
Improvement
```

## Architecture Principles

1. Analytics must be based on governed data.
2. Every analytical output must reference input data assets and versions.
3. Metrics must be defined, owned, versioned, and traceable.
4. Dashboards must not be treated as the final outcome.
5. Insights must be evidence-backed and explainable.
6. Decisions must preserve data, evidence, assumptions, constraints, and rationale.
7. Outcomes must be measured where possible.
8. Value realization must be connected to decisions and outcomes.
9. Analytics must disclose assumptions and limitations.
10. AI-generated or agent-assisted analytics must preserve provenance and review status.

## Analytics Layers

```text
Analytics Experience Layer
├── Analytics Portal
├── Dashboard Studio
├── Report Builder
├── Metrics Explorer
├── KPI Workspace
├── Benchmark Explorer
├── Insight Workspace
├── Decision Intelligence Workspace
└── Outcome Review Workspace

Analytics Services Layer
├── Metrics Registry Service
├── KPI Service
├── Report Service
├── Dashboard Service
├── Benchmark Service
├── Forecast Service
├── Insight Service
├── Recommendation Service
├── Decision Service
├── Outcome Tracking Service
└── Value Realization Service

Analytics Intelligence Layer
├── Metric Calculation Engine
├── Aggregation Engine
├── Statistical Analysis Engine
├── Forecasting Engine
├── Anomaly Detection Engine
├── Explanation Engine
├── Recommendation Engine
├── Decision Support Engine
└── Learning Engine

Analytics Records Layer
├── Metric Records
├── KPI Records
├── Report Records
├── Dashboard Records
├── Analysis Records
├── Insight Records
├── Recommendation Records
├── Decision Records
├── Outcome Records
├── Value Records
└── Learning Records
```

## Primary Analytics Objects

```text
Metric
KPI
Dimension
Measure
Calculation
Report
Dashboard
Benchmark
Forecast
Analysis
Insight
Recommendation
Decision
Action
Outcome
Impact
Value
Learning
```

## Metric Architecture

A Metric is a governed measurement definition.

### Metric Requirements

```yaml
id: string
name: string
definition: string
formula: string
owner: string
inputDataAssets:
  - string
dimensions:
  - string
unit: string
refreshCadence: string
version: string
lifecycleState: string
```

### Metric Governance Rules

1. Every metric must have an owner.
2. Every metric must define its formula or calculation method.
3. Every metric must reference input data assets.
4. Every metric must preserve version history.
5. Every metric used in a decision must preserve calculation context.

## KPI Architecture

A KPI is a metric tied to a goal, threshold, target, or performance expectation.

### KPI Requirements

```yaml
id: string
name: string
metric: string
target: string
thresholds: object
owner: string
businessObjective: string
reviewCadence: string
lifecycleState: string
```

## Report and Dashboard Architecture

Reports and dashboards are analytical presentation assets.

### Requirements

- Input data assets must be referenced.
- Metrics must be defined.
- Refresh cadence must be known.
- Owner must be assigned.
- Audience must be declared.
- Limitations must be disclosed.
- Data version or time window must be preserved.
- Publication status must be governed.

## Insight Architecture

An Insight is an evidence-backed interpretation of data or analysis.

### Insight Requirements

```yaml
id: string
statement: string
basedOn:
  - string
evidence:
  - string
confidence: number
explanation: string
limitations:
  - string
recommendedActions:
  - string
owner: string
reviewStatus: string
```

### Insight Rules

1. Insights must not be unsupported claims.
2. Insights must link to data, metric, analysis, or evidence.
3. Confidence must be stated for high-impact insights.
4. Limitations must be disclosed where known.
5. AI-generated insights must declare AI involvement and review status.

## Recommendation Architecture

A Recommendation is a suggested action derived from data, analytics, insights, policy, constraints, or objectives.

### Recommendation Requirements

```yaml
id: string
recommendation: string
basedOnInsights:
  - string
basedOnDataAssets:
  - string
constraints:
  - string
expectedOutcome: string
riskLevel: string
reviewStatus: string
```

## Decision Intelligence Architecture

Decision Intelligence connects data, insights, alternatives, constraints, choices, actions, and outcomes.

### Decision Flow

```text
Decision Context
    ↓
Relevant Data
    ↓
Evidence
    ↓
Metrics and Insights
    ↓
Alternatives
    ↓
Constraints
    ↓
Selected Option
    ↓
Action
    ↓
Outcome
    ↓
Learning
```

### Decision Record Requirements

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

## Outcome and Value Architecture

Outcomes connect analytics and decisions to measurable change.

### Outcome Requirements

```yaml
id: string
name: string
producedBy: string
measuredAt: datetime
metrics:
  - string
baseline: string
actual: string
impact: string
value: string
learning: string
```

### Value Types

```text
Public Value
Operational Value
Financial Value
Research Value
Social Value
Compliance Value
Risk Reduction
Time Savings
Quality Improvement
Decision Improvement
```

## Analytics Lineage

Analytics lineage connects outputs to inputs.

```text
Dataset
    ↓
Metric
    ↓
Dashboard
    ↓
Insight
    ↓
Decision
    ↓
Outcome
```

Every analytics output must preserve:

- Input data asset references
- Input data versions
- Calculation method
- Metric version
- Analysis timestamp
- Owner
- Review status

## Analytics Governance

Analytics governance ensures analytical outputs are reliable, explainable, and responsible.

### Governance Gates

```text
Metric Definition Gate
KPI Approval Gate
Dashboard Publication Gate
Insight Review Gate
Decision Support Gate
Outcome Review Gate
```

### Analytics Governance Rules

1. Every metric must have owner and definition.
2. Every published dashboard must reference governed data.
3. Every insight must be evidence-backed.
4. Every decision must reference data versions where data was used.
5. Every AI-assisted analytics output must declare AI involvement.
6. Every high-impact recommendation must be reviewed before action.
7. Every outcome should feed learning and improvement.

## Agentic Analytics

Agents may assist with analytics but must operate under governance.

### Allowed Agentic Analytics Tasks

- Suggest metrics
- Generate draft analysis
- Explain dashboard changes
- Detect anomalies
- Generate insight drafts
- Recommend next questions
- Prepare decision briefs
- Summarize outcomes

### Agentic Analytics Rules

1. Agents must use governed data.
2. Agents must preserve input data references.
3. Agents must disclose generated outputs.
4. Agents must not make high-impact decisions autonomously without approval.
5. Agent-generated insights must be reviewed where required.

## Minimum Viable Analytics Architecture

The first operational analytics platform should support:

1. Metrics registry
2. KPI records
3. Dashboard records
4. Report records
5. Input data references
6. Data version references
7. Insight cards
8. Decision records
9. Outcome records
10. Analytics lineage
11. Review status
12. Audit events

## Analytics Validation Rules

1. Every metric must have definition and owner.
2. Every KPI must reference a metric.
3. Every dashboard must reference input data or metrics.
4. Every insight must reference evidence or analysis.
5. Every decision must reference maker and time.
6. Every decision based on data must reference data versions.
7. Every outcome must link back to decision, action, or workflow where possible.
8. Every AI-generated analytics output must mark AI involvement.
9. Every published analytics asset must have lifecycle state.
10. Every high-impact analytics output must preserve review status.

## Relationship to Other Architectures

```text
Data Architecture provides governed data.
Governance Architecture controls policy, access, approval, and audit.
Knowledge Graph connects analytics to data, evidence, decisions, and outcomes.
Agent Architecture automates analytics assistance under governance.
Analytics Architecture realizes value from data.
```

## Status

Draft. Canonical after governance review.
