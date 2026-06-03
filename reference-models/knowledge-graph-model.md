# OpenDataWorld Knowledge Graph Model

OpenDataWorld treats the knowledge graph as the connected intelligence layer for data and analytics solutions as a service.

The knowledge graph connects data assets, entities, identities, metadata, schemas, policies, provenance, lineage, trust, analytics, insights, decisions, actions, outcomes, and agents.

## Knowledge Graph North Star

```text
Make data, context, governance, trust, lineage, analytics, decisions, and outcomes connected, queryable, explainable, and reusable.
```

## Core Assertion

```text
A catalog tells you what exists.
A registry tells you what is governed.
A knowledge graph tells you how everything is connected and why it matters.
```

## Graph Scope

```text
KnowledgeGraph
├── Entity Layer
├── Identity Layer
├── Asset Layer
├── Metadata Layer
├── Schema Layer
├── Taxonomy Layer
├── Governance Layer
├── Policy Layer
├── Provenance Layer
├── Lineage Layer
├── Trust Layer
├── Analytics Layer
├── Insight Layer
├── Decision Layer
├── Outcome Layer
├── Service Layer
└── Agent Layer
```

## Primary Node Types

```text
Person
Organization
Team
System
Application
Service
Agent

DataAsset
Dataset
DataProduct
DataSource
DataElement
Schema
API
Report
Dashboard
Metric
Model
KnowledgeAsset

GlossaryTerm
OntologyClass
TaxonomyClass
Classification

Policy
Rule
AccessDecision
Approval
AuditEvent

ProvenanceRecord
LineageRecord
TrustAssessment
Evidence
Observation

Insight
Decision
Action
Workflow
Outcome
Impact
```

## Primary Edge Types

```text
owns
stewards
operates
publishes
creates
collects
transforms
reviews
approves
accesses
uses
subscribesTo

sourcedFrom
derivedFrom
transformedInto
dependsOn
feeds
servedThrough
publishedAs
indexedAs

classifiedAs
conformsTo
describedBy
definedBy
mappedTo

 governedBy
constrainedBy
evaluatedBy
allowedBy
deniedBy
requiresApprovalFrom

hasProvenance
hasLineage
hasTrustAssessment
hasEvidence
hasQualityProfile

supports
produces
explains
measures
informs
leadsTo
impacts

executedBy
actedOn
approvedBy
reviewedBy
recordedBy
```

## Node Record

Every graph node should include:

```yaml
id: string
type: string
name: string
description: string
canonicalId: string
labels:
  - string
classification: object
lifecycleState: string
createdAt: datetime
updatedAt: datetime
version: string
provenance: string
trust: string
```

## Edge Record

Every graph edge should include:

```yaml
id: string
type: string
source: string
target: string
relationshipType: string
direction: string
validFrom: datetime
validTo: datetime
recordedAt: datetime
provenance: string
evidence:
  - string
confidence: number
lifecycleState: string
```

## Data Asset Graph

The data asset graph connects data assets to ownership, schemas, governance, trust, and usage.

```text
Organization owns Dataset
Person stewards Dataset
Dataset conformsTo Schema
Dataset classifiedAs Classification
Dataset governedBy Policy
Dataset hasProvenance ProvenanceRecord
Dataset hasLineage LineageRecord
Dataset hasTrustAssessment TrustAssessment
Dataset usedBy DataConsumer
Dataset supports Decision
```

## Governance Graph

The governance graph connects data assets, policies, rules, decisions, approvals, and audit events.

```text
Policy appliesTo DataAsset
Rule belongsTo Policy
AccessDecision evaluatedBy Policy
AccessDecision appliesTo Dataset
Approval approves AccessDecision
AuditEvent records Action
Action operatesOn DataAsset
```

## Lineage Graph

The lineage graph connects sources, transformations, outputs, analytics, decisions, and outcomes.

```text
DataSource produces DatasetA
DatasetA transformedInto DatasetB
DatasetB feeds Dashboard
Dashboard produces Insight
Insight informs Decision
Decision leadsTo Action
Action produces Outcome
```

## Trust Graph

The trust graph connects trust assessments to evidence, provenance, lineage, quality, certification, and review.

```text
TrustAssessment assesses Dataset
TrustAssessment basedOn Evidence
TrustAssessment considers QualityProfile
TrustAssessment considers ProvenanceRecord
TrustAssessment considers LineageRecord
TrustAssessment reviewedBy Reviewer
```

## Decision Graph

The decision graph connects data, analytics, evidence, assumptions, constraints, actions, outcomes, and learning.

```text
Decision basedOn Dataset
Decision basedOn Insight
Decision constrainedBy Policy
Decision supportedBy Evidence
Decision selected Action
Action produced Outcome
Outcome generated Learning
Learning improves DataProduct
```

## Agent Graph

The agent graph connects agents to identities, owners, tools, actions, policies, data assets, approvals, and audit records.

```text
Agent hasIdentity AgentIdentity
Agent operatedBy Organization
Agent allowedToUse Tool
Agent requested Action
Action operatesOn DataAsset
Action evaluatedBy Policy
Action approvedBy Human
Action recordedBy AuditEvent
Action produced OutputAsset
```

## Knowledge Graph Query Patterns

### Discovery Queries

```text
Find datasets about healthcare in India with Gold quality tier.
Find data products derived from government portals.
Find dashboards using a specific dataset.
Find datasets with public access and verified trust.
```

### Governance Queries

```text
Which sensitive datasets have no steward?
Which published datasets have unknown license?
Which access decisions used Policy version 2.1?
Which assets are governed by expired policies?
```

### Lineage Queries

```text
What downstream assets depend on this dataset?
Which source produced this metric?
Which model used this dataset version?
Which decisions used data affected by this quality issue?
```

### Trust Queries

```text
Why is this dataset trusted?
What evidence supports this trust score?
Which assets have revoked trust?
Which certified datasets lack recent quality checks?
```

### Agent Queries

```text
Which agents accessed restricted data?
Which agent generated this metadata?
Which agent actions required human approval?
Which outputs were produced by agentic workflows?
```

## Graph Validation Rules

1. Every node must have an identifier.
2. Every edge must have source, target, and relationship type.
3. Every governed edge must preserve provenance.
4. Every trust edge must reference evidence or declare missing evidence.
5. Every lineage edge must be temporal.
6. Every policy edge must reference policy version where applicable.
7. Every agent action edge must reference agent identity.
8. Every decision edge must preserve data and evidence references.
9. Every published data asset should connect to owner, steward, license, provenance, quality, and access policy.
10. Every graph projection must be reproducible from source records, events, or snapshots.

## Minimum Viable Knowledge Graph Baseline

For the first operational platform, support:

1. Dataset nodes
2. Data source nodes
3. Organization nodes
4. Person or team steward nodes
5. Schema nodes
6. Policy nodes
7. Provenance nodes
8. Lineage edges
9. Classification nodes
10. Trust assessment nodes
11. Access decision nodes
12. Basic graph queries for discovery, governance, lineage, and trust

## Relationship to Other Foundation Models

```text
Glossary defines terms.
Ontology defines concepts.
Taxonomy defines classification.
Meta Model defines structure.
Identity Model defines who or what exists persistently.
Temporal Model defines when things are true.
Trust Model defines confidence.
Provenance Model defines origin and custody.
Lineage Model defines data flow and dependency.
Knowledge Graph Model connects all of them.
```

## Status

Draft. Canonical after governance review.
