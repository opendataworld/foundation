# OpenDataWorld Temporal Model

OpenDataWorld treats time as a first-class foundation concept.

Data, metadata, ownership, access, policy, quality, trust, lineage, relationships, decisions, and outcomes change over time. The platform must preserve these changes rather than overwrite them without trace.

## Temporal North Star

```text
Current state is a projection.
History is first-class.
Every meaningful change must be traceable across time.
```

## Core Assertions

1. Everything important is temporal.
2. Current state is not the whole truth.
3. History must be queryable.
4. Events must be append-only where auditability matters.
5. Versions must be immutable once published or used for decisions.
6. Policy decisions must reference the policy version active at decision time.
7. Data decisions must reference the data version used at decision time.
8. Trust and quality are time-bound.
9. Relationships may be valid only during a time window.
10. Reproducibility requires temporal context.

## Temporal Concepts

```text
Temporal Model
├── Time
├── Event
├── State
├── StateChange
├── Version
├── Snapshot
├── Projection
├── Timeline
├── ValidityPeriod
├── EffectivePeriod
├── ObservationTime
├── TransactionTime
├── DecisionTime
├── PublicationTime
├── AccessTime
└── RetentionPeriod
```

## Time Types

### Event Time

The time when something actually happened.

Example:

```text
A dataset was collected at 2026-01-01T10:00:00Z.
```

### Transaction Time

The time when the platform recorded something.

Example:

```text
The dataset record was registered at 2026-01-02T08:00:00Z.
```

### Effective Time

The time from which a policy, classification, ownership, or rule becomes effective.

Example:

```text
The new access policy is effective from 2026-02-01.
```

### Valid Time

The period during which a statement, relationship, policy, or record is considered true in the modeled world.

Example:

```text
Person A was steward of Dataset X from 2025-01-01 to 2025-12-31.
```

### Decision Time

The time when a decision was made.

Decision records must preserve the data, evidence, policy, trust score, and context available at decision time.

### Publication Time

The time when a data asset, dataset, insight, report, dashboard, schema, or policy was published.

### Access Time

The time when a subject accessed or attempted to access a resource.

## State and Events

OpenDataWorld distinguishes state from events.

```text
Event = something happened
State = current known condition
Projection = computed state from event history
```

### Example

```text
Events:
- DatasetRegistered
- DatasetClassified
- DatasetValidated
- DatasetPublished

Projection:
- Dataset lifecycleState = Published
```

## Event Model

Every meaningful change should emit an event.

### Event Required Fields

```yaml
id: string
type: Event
eventType: string
subject: string
action: string
object: string
occurredAt: datetime
recordedAt: datetime
actor: string
context: object
previousState: object
newState: object
policyDecision: string
evidence: array
traceId: string
```

## Canonical Event Types

```text
DataAssetRegistered
DataAssetClassified
DataAssetOwnerAssigned
DataAssetStewardAssigned
DataAssetSchemaLinked
DataAssetValidated
DataAssetQualityScored
DataAssetPublished
DataAssetDeprecated
DataAssetArchived
DataAssetRetired
DatasetVersionCreated
DatasetVersionPublished
DatasetAccessRequested
DatasetAccessApproved
DatasetAccessDenied
DatasetAccessRevoked
DatasetAccessed
PolicyCreated
PolicyReviewed
PolicyApproved
PolicyActivated
PolicySuperseded
PolicyRetired
SchemaCreated
SchemaVersionPublished
LineageEdgeCreated
ProvenanceRecorded
TrustScoreCalculated
DecisionRecorded
OutcomeRecorded
AgentActionRequested
AgentActionApproved
AgentActionExecuted
AgentActionDenied
```

## Version Model

A Version is a specific immutable state of an object at a point in its lifecycle.

### Version Required Fields

```yaml
id: string
versionOf: string
version: string
createdAt: datetime
createdBy: string
changeType: string
changeSummary: string
previousVersion: string
status: string
contentHash: string
```

## Versioning Rules

1. Published versions must be immutable.
2. Any data used in a decision must preserve its version reference.
3. Any schema used to validate data must preserve schema version.
4. Any policy used in an access decision must preserve policy version.
5. Any model used for analytics or scoring must preserve model version.
6. Superseded versions must remain queryable where audit or reproducibility requires it.
7. Deletion must not destroy audit history unless legally required and explicitly governed.

## Snapshot Model

A Snapshot captures the full known state of an object at a point in time.

### Snapshot Required Fields

```yaml
id: string
snapshotOf: string
snapshotAt: datetime
createdAt: datetime
createdBy: string
state: object
sourceEvents:
  - string
contentHash: string
```

## Projection Model

A Projection is a computed view derived from events, snapshots, and current records.

Examples:

```text
Current Dataset Card
Current Access Policy
Current Trust Score
Current Owner
Current Classification
Current Published Catalog Entry
```

Projection records must never pretend to be full historical truth.

## Timeline Model

A Timeline is the ordered history of events, versions, states, and decisions for an object.

### Timeline Query Examples

```text
Show all changes to Dataset X.
Show policy active on 2026-01-15.
Show who owned Data Product Y in Q1 2025.
Show trust score history for Dataset Z.
Show access decisions for User A on Dataset B.
Show lineage of Dataset C at model training time.
```

## Temporal Relationship Model

Relationships can change over time and must support validity periods.

### Temporal Relationship Fields

```yaml
id: string
type: Relationship
relationshipType: string
source: string
target: string
validFrom: datetime
validTo: datetime
effectiveFrom: datetime
effectiveTo: datetime
recordedAt: datetime
provenance: object
confidence: number
lifecycleState: string
```

## Temporal Governance

Governance is temporal because policies, approvals, consent, access, classifications, and risk change.

### Required Temporal Governance Records

- Policy version history
- Approval history
- Access grant history
- Access revocation history
- Consent reference history
- Classification history
- Ownership history
- Stewardship history
- Retention history
- Exception history

## Temporal Access Model

Every access decision must preserve:

```yaml
subject: string
action: string
resource: string
resourceVersion: string
policy: string
policyVersion: string
context: object
decision: string
decidedAt: datetime
decisionReason: string
expiresAt: datetime
```

## Temporal Trust Model

Trust is not permanent.

A trust score must always be associated with time, evidence, and context.

```yaml
trustScore: number
trustLevel: string
calculatedAt: datetime
validUntil: datetime
evidence:
  - string
method: string
```

## Temporal Quality Model

Quality can degrade or improve over time.

Quality records must preserve:

```yaml
qualityTier: string
qualityScore: number
measuredAt: datetime
qualityRules:
  - string
validationResults:
  - string
knownIssues:
  - string
```

## Temporal Lineage Model

Lineage must answer not only what depends on what, but when.

```yaml
sourceAsset: string
sourceVersion: string
targetAsset: string
targetVersion: string
transformation: string
executedAt: datetime
executedBy: string
inputTimeRange: object
outputTimeRange: object
```

## Temporal Decision Model

A decision must preserve the temporal context under which it was made.

```yaml
decisionId: string
madeAt: datetime
madeBy: string
dataAssets:
  - id: string
    version: string
    accessedAt: datetime
policies:
  - id: string
    version: string
    effectiveAt: datetime
evidence:
  - string
context: object
selectedOption: string
outcome: string
```

## Retention and Deletion

OpenDataWorld must distinguish between deletion of active access and preservation of governed history.

### Retention Rules

1. Audit records should be retained according to policy and law.
2. Published data versions should remain discoverable unless withdrawn under governance.
3. Sensitive or personal data deletion must respect legal, privacy, and consent obligations.
4. Deletion events must be recorded unless prohibited by law.
5. Tombstones should be used where records are removed but references must remain explainable.

## Temporal Validation Rules

1. Every event must have `occurredAt` and `recordedAt`.
2. Every version must reference what it versions.
3. Every published version must be immutable.
4. Every relationship with time-bounded truth must define `validFrom` and optionally `validTo`.
5. Every access decision must record policy version.
6. Every decision based on data must record data version.
7. Every trust score must record calculation time and evidence.
8. Every quality score must record measurement time.
9. Every lineage edge must preserve source and target versions where available.
10. Every projection must be traceable to source events or snapshots.

## Minimum Viable Temporal Baseline

For the first operational platform, support:

1. Created and updated timestamps
2. Lifecycle state changes
3. Dataset versions
4. Schema versions
5. Policy versions
6. Access decision history
7. Audit events
8. Publication history
9. Ownership history
10. Lineage timestamps

## Status

Draft. Canonical after governance review.
