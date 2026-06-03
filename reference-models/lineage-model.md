# OpenDataWorld Lineage Model

OpenDataWorld treats lineage as a first-class foundation concept.

Lineage explains how data moves, transforms, derives, depends on, feeds, and impacts downstream assets, analytics, decisions, actions, and outcomes.

## Lineage North Star

```text
Every important data output must be traceable back to its inputs, transformations, actors, tools, policies, versions, and time.
```

## Provenance vs Lineage

```text
Provenance answers: where did it come from and who handled it?
Lineage answers: how did it flow, transform, derive, and impact downstream use?
```

Both are required for trust, auditability, reproducibility, governance, and decision intelligence.

## Core Assertions

1. Lineage must connect inputs to outputs.
2. Lineage must preserve versions.
3. Lineage must be temporal.
4. Lineage must reference transformations.
5. Lineage must reference actors, systems, tools, and agents.
6. Lineage must connect data to analytics, insights, decisions, and outcomes.
7. Lineage must support impact analysis.
8. Lineage must support root-cause analysis.
9. Lineage must support reproducibility.
10. Lineage must be queryable as a graph.

## Lineage Scope

```text
Lineage
├── Source Lineage
├── Dataset Lineage
├── Field Lineage
├── Schema Lineage
├── Transformation Lineage
├── Pipeline Lineage
├── API Lineage
├── Analytics Lineage
├── Model Lineage
├── Insight Lineage
├── Decision Lineage
├── Policy Lineage
├── Agent Action Lineage
└── Outcome Lineage
```

## Lineage Record

Every lineage record should include:

```yaml
id: string
type: LineageRecord
lineageType: string
sourceAsset: string
sourceVersion: string
targetAsset: string
targetVersion: string
relationshipType: string
transformation: string
executedBy: string
executedAt: datetime
tool: string
system: string
agent: string
policyDecision: string
inputTimeRange: object
outputTimeRange: object
evidence:
  - string
confidence: number
version: string
```

## Lineage Relationship Types

```text
sourcedFrom
derivedFrom
transformedInto
aggregatedInto
filteredInto
joinedInto
enrichedInto
validatedInto
publishedAs
indexedAs
servedThrough
usedBy
feeds
trains
scores
explains
supportsDecision
producesInsight
producesOutcome
dependsOn
supersedes
```

## Lineage Granularity

Lineage may exist at multiple levels.

```text
System-level lineage
Dataset-level lineage
Table-level lineage
Column-level lineage
Record-level lineage
Metric-level lineage
Model-feature lineage
Decision-level lineage
Outcome-level lineage
```

## Dataset Lineage

Dataset lineage connects datasets to sources, transformations, versions, and downstream assets.

Example:

```text
Raw Facility CSV
  → cleaned by Validation Pipeline
  → standardized as Health Facility Dataset v1.0
  → published as Public Health Facilities Data Product
  → used by Healthcare Access Dashboard
  → supports Facility Planning Decision
```

## Field Lineage

Field lineage tracks how individual data elements are derived.

```yaml
sourceField: string
sourceAsset: string
targetField: string
targetAsset: string
transformationLogic: string
validationRules:
  - string
confidence: number
```

## Schema Lineage

Schema lineage tracks schema evolution and mappings.

```yaml
sourceSchema: string
sourceSchemaVersion: string
targetSchema: string
targetSchemaVersion: string
mappingRules:
  - string
breakingChange: boolean
migrationRequired: boolean
```

## Transformation Lineage

Transformation lineage records the logic and execution that produced an output.

```yaml
transformationId: string
transformationType: string
inputAssets:
  - string
outputAssets:
  - string
logic: string
parameters: object
executedBy: string
executedAt: datetime
runtime: string
status: string
```

## Analytics Lineage

Analytics lineage connects analytical outputs to input data, metrics, assumptions, and methods.

```yaml
analyticsAsset: string
inputDataAssets:
  - id: string
    version: string
metrics:
  - string
assumptions:
  - string
method: string
refreshedAt: datetime
owner: string
```

## Decision Lineage

Decision lineage connects decisions to data, analytics, insights, evidence, constraints, and outcomes.

```yaml
decision: string
dataAssets:
  - id: string
    version: string
analyticsAssets:
  - string
insights:
  - string
evidence:
  - string
constraints:
  - string
outcome: string
madeAt: datetime
```

## Agent Action Lineage

Agent action lineage records agent involvement in data workflows.

```yaml
agentIdentity: string
action: string
inputAssets:
  - string
outputAssets:
  - string
tools:
  - string
policyDecision: string
approvalReference: string
traceId: string
executedAt: datetime
```

## Impact Analysis

Lineage must support downstream impact questions.

Examples:

```text
If this source changes, which datasets are affected?
If this schema field is removed, which dashboards break?
If this dataset is revoked, which decisions must be reviewed?
If this quality issue appears, which reports are impacted?
If this policy changes, which access grants should be re-evaluated?
```

## Root-Cause Analysis

Lineage must support upstream root-cause questions.

Examples:

```text
Why did this dashboard value change?
Which source created this incorrect metric?
Which transformation introduced duplicate records?
Which data version was used in this decision?
Which agent generated this metadata?
```

## Lineage Graph

Lineage should be represented as a graph.

```text
Node = DataAsset | Transformation | System | Agent | Policy | Analytics | Decision | Outcome
Edge = Lineage relationship with time, version, evidence, and confidence
```

## Minimum Viable Lineage Baseline

For the first operational platform, support:

1. Dataset source lineage
2. Dataset version lineage
3. Transformation input and output lineage
4. Schema version references
5. Analytics input references
6. Decision data references
7. Agent action lineage
8. Temporal lineage timestamps
9. Evidence references
10. Impact analysis queries

## Lineage Validation Rules

1. Every transformed output must reference input assets.
2. Every lineage edge must define source and target.
3. Every lineage edge must define relationship type.
4. Every lineage edge should preserve source and target versions where available.
5. Every lineage edge must have a timestamp or validity period.
6. Every analytics asset must reference input data assets.
7. Every decision using data must reference data versions.
8. Every agent-produced output must reference agent identity and action trace.
9. Every published data product should expose upstream lineage summary.
10. Every lineage record used for audit must preserve evidence.

## Status

Draft. Canonical after governance review.
