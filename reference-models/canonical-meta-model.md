# OpenDataWorld Canonical Meta Model

The canonical meta model defines the structural foundation for all OpenDataWorld records, schemas, registries, catalogs, graphs, APIs, policies, and implementations.

This meta model is data-first. Data is the anchor. Every other object exists to describe, govern, protect, transform, publish, discover, use, validate, or act upon data.

## Purpose

The meta model provides a common inheritance structure for:

- Data assets
- Datasets
- Data products
- Data sources
- Schemas
- Metadata records
- Knowledge graph records
- Policies
- Relationships
- Events
- Actions
- Workflows
- Decisions
- Evidence
- Trust records
- Audit records
- Agents and tools that operate on data

## Foundational Assertion

```text
Every governed thing is identifiable.
Every identifiable thing has metadata.
Every metadata record must be traceable.
Every traceable object must have provenance.
Every data action must be governed.
```

## Root Model

```text
Thing
├── Entity
├── Asset
├── Relationship
├── Event
├── Action
├── Policy
├── Rule
├── Decision
├── Workflow
├── Evidence
├── Observation
├── Metric
├── Identity
├── Capability
├── Resource
├── Context
└── Contract
```

## Thing

`Thing` is the root abstraction for every identifiable object in OpenDataWorld.

### Required Fields

```yaml
id: string
type: string
name: string
description: string
createdAt: datetime
updatedAt: datetime
lifecycleState: string
version: string
```

### Recommended Fields

```yaml
canonicalId: string
aliases: array
labels: array
tags: array
externalIds: array
links: array
owner: string
steward: string
classification: object
provenance: object
trust: object
metadata: object
```

## Entity

An Entity is a uniquely identifiable person, organization, system, agent, place, concept, asset, or real-world object.

```text
Entity
├── Person
├── Organization
├── System
├── Agent
├── Place
├── Concept
└── Asset
```

### Entity Fields

```yaml
id: string
type: Entity
entityType: string
name: string
identity: Identity
relationships: array
lifecycleState: string
```

## Asset

An Asset is any identifiable thing with value, ownership, metadata, lifecycle, and governance.

```text
Asset
├── DataAsset
├── KnowledgeAsset
├── APIAsset
├── ModelAsset
├── PolicyAsset
├── WorkflowAsset
├── ReportAsset
├── DashboardAsset
├── DocumentationAsset
└── RegistryEntry
```

### Asset Required Fields

```yaml
id: string
type: Asset
assetType: string
name: string
description: string
owner: string
steward: string
classification: object
accessPolicy: string
lifecycleState: string
version: string
provenance: object
```

## DataAsset

A DataAsset is the primary anchor object in OpenDataWorld.

```text
DataAsset
├── Dataset
├── DataProduct
├── DataSource
├── DataElement
├── DataRecord
├── DataTable
├── DataFile
├── DataStream
├── DataAPI
├── DataIndex
├── DataView
└── MetadataRecord
```

### DataAsset Required Fields

```yaml
id: string
type: DataAsset
dataAssetType: string
name: string
description: string
owner: string
steward: string
source: string
schema: string
classification:
  domain: string
  sensitivity: string
  accessLevel: string
  qualityTier: string
  lifecycleState: string
license: string
accessPolicy: string
qualityProfile: string
provenance: string
lineage: string
version: string
createdAt: datetime
updatedAt: datetime
```

## Relationship

A Relationship is a meaningful connection between two or more Things.

### Relationship Fields

```yaml
id: string
type: Relationship
relationshipType: string
source: string
target: string
direction: string
context: object
provenance: object
confidence: number
validFrom: datetime
validTo: datetime
lifecycleState: string
```

### Canonical Data Relationships

```text
DataAsset ownedBy Actor
DataAsset stewardedBy Actor
DataAsset sourcedFrom DataSource
DataAsset describedBy MetadataRecord
DataAsset conformsTo Schema
DataAsset governedBy Policy
DataAsset classifiedAs Classification
DataAsset hasProvenance Provenance
DataAsset hasLineage Lineage
DataAsset hasQualityProfile QualityProfile
DataAsset licensedUnder License
DataAsset publishedIn Catalog
DataAsset accessibleThrough AccessChannel
DataAsset usedBy Actor
DataAsset supports UseCase
DataAsset produces Outcome
DataAsset derivedFrom DataAsset
DataAsset dependsOn DataAsset
Schema defines DataElement
Policy constrains DataAccess
Action operatesOn DataAsset
Decision basedOn DataAsset
Agent actsOn DataAsset under Policy
```

## Event

An Event is an append-only record that something happened.

### Event Fields

```yaml
id: string
type: Event
eventType: string
subject: string
action: string
object: string
occurredAt: datetime
actor: string
context: object
evidence: array
provenance: object
```

## Action

An Action is a deliberate operation performed by a subject on a resource.

### Action Fields

```yaml
id: string
type: Action
actionType: string
subject: string
resource: string
input: object
output: object
policyDecision: string
status: string
startedAt: datetime
completedAt: datetime
traceId: string
```

## Policy

A Policy defines what is allowed, denied, required, recommended, or escalated.

### Policy Fields

```yaml
id: string
type: Policy
policyType: string
name: string
description: string
appliesTo: array
rules: array
effect: string
owner: string
version: string
lifecycleState: string
validFrom: datetime
validTo: datetime
```

## Rule

A Rule is an executable or declarative condition within a policy.

```yaml
id: string
type: Rule
ruleType: string
condition: string
effect: string
severity: string
message: string
```

## Decision

A Decision is a selected judgment or course of action based on data, evidence, context, and constraints.

### Decision Fields

```yaml
id: string
type: Decision
decisionType: string
madeBy: string
madeAt: datetime
basedOnDataAssets: array
basedOnEvidence: array
context: object
constraints: array
alternatives: array
selectedOption: string
confidence: number
outcome: string
reviewStatus: string
```

## Workflow

A Workflow is a sequence or graph of actions, events, policies, tools, actors, and decisions that produces an outcome.

```yaml
id: string
type: Workflow
workflowType: string
name: string
description: string
steps: array
inputs: array
outputs: array
actors: array
policies: array
status: string
traceId: string
```

## Evidence

Evidence supports a claim, decision, classification, validation, score, or audit result.

```yaml
id: string
type: Evidence
evidenceType: string
source: string
claim: string
supports: string
collectedAt: datetime
confidence: number
provenance: object
```

## Observation

An Observation is a recorded measurement or fact about a thing at a time.

```yaml
id: string
type: Observation
observedThing: string
observedProperty: string
value: any
unit: string
observedAt: datetime
source: string
confidence: number
```

## Metric

A Metric is a defined measurement used to evaluate quality, performance, trust, risk, usage, or impact.

```yaml
id: string
type: Metric
metricType: string
name: string
definition: string
formula: string
unit: string
owner: string
```

## Identity

Identity represents a persistent subject or object across systems and time.

```yaml
id: string
type: Identity
identityType: string
subject: string
issuer: string
identifier: string
proof: object
status: string
validFrom: datetime
validTo: datetime
```

## Capability

A Capability is something an actor, system, agent, tool, or platform can do.

```yaml
id: string
type: Capability
name: string
description: string
capabilityType: string
provider: string
inputs: array
outputs: array
constraints: array
riskLevel: string
```

## Resource

A Resource is anything that can be accessed, governed, protected, referenced, or used.

```yaml
id: string
type: Resource
resourceType: string
uri: string
owner: string
accessPolicy: string
classification: object
```

## Context

Context is the set of relevant conditions required to interpret, decide, or act correctly.

```yaml
id: string
type: Context
subject: string
resource: string
action: string
purpose: string
time: datetime
environment: object
jurisdiction: string
risk: object
constraints: array
```

## Contract

A Contract defines commitments, rights, obligations, expectations, and constraints between parties.

```yaml
id: string
type: Contract
contractType: string
parties: array
subject: string
terms: array
validFrom: datetime
validTo: datetime
status: string
```

## Universal Required Fields

Every governed object should include:

```yaml
id: string
type: string
name: string
description: string
createdAt: datetime
updatedAt: datetime
createdBy: string
updatedBy: string
lifecycleState: string
version: string
```

## Universal Governance Fields

Every governed object should include where applicable:

```yaml
owner: string
steward: string
classification: object
accessPolicy: string
provenance: object
lineage: object
trust: object
audit: object
policyRefs: array
```

## Universal Lifecycle States

```text
Draft
Proposed
Registered
Validated
Approved
Active
Published
Deprecated
Superseded
Archived
Retired
Revoked
Deleted
```

## Meta Model Validation Rules

1. Every object must have an `id`.
2. Every object must have a `type`.
3. Every governed object must have a lifecycle state.
4. Every DataAsset must have an owner.
5. Every DataAsset must have provenance.
6. Every published DataAsset must have classification.
7. Every sensitive DataAsset must have an access policy.
8. Every schema-bearing asset must reference a schema version.
9. Every transformation must produce lineage.
10. Every decision based on data must reference the data asset version.
11. Every agent action on data must reference a policy decision.
12. Every relationship must preserve source, target, type, and provenance.
13. Every event must be append-only.
14. Every policy must be versioned.
15. Every trust score must be evidence-backed.

## Derivation Targets

This meta model should be used to derive:

- JSON Schema
- JSON-LD context
- SurrealDB schema
- Graph schema
- OpenAPI contracts
- Registry records
- Catalog records
- Validation rules
- Governance policies
- Search index mappings
- Agent tool contracts

## Status

Draft. Canonical after governance review.
