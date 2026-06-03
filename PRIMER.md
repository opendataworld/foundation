# OpenDataWorld Primer

OpenDataWorld is a foundation for delivering **data and analytics solutions as a service for everyone**.

It exists to help people, organizations, governments, researchers, enterprises, communities, systems, and governed agents discover, understand, trust, govern, analyze, publish, and act on data.

## One-Line Definition

```text
OpenDataWorld turns fragmented data into governed, trusted, reusable, AI-ready data and analytics services.
```

## Core Anchor

```text
Data is the anchor.
Everything else exists to describe, govern, protect, improve, publish, discover, use, analyze, or act upon data.
```

## Why OpenDataWorld Exists

Most institutions have data, but they do not have a shared way to answer basic questions:

- What data exists?
- Who owns it?
- Where did it come from?
- Can we trust it?
- What does it mean?
- Who can access it?
- What policy governs it?
- What changed over time?
- Which analytics depend on it?
- Which decisions used it?
- What outcomes did it create?
- Can an AI agent use it safely?

OpenDataWorld creates the shared foundation needed to answer these questions consistently.

## The Big Idea

OpenDataWorld connects the full value chain:

```text
Data
  ↓
Analytics
  ↓
Insight
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

Most data platforms stop at cataloging or dashboards.

OpenDataWorld continues to decisions, outcomes, value, and learning.

## What This Repository Is

This repository is the **Foundation**.

The Foundation is not the full runtime platform. It is the canonical source of truth for the language, models, rules, and architectures that every OpenDataWorld implementation should follow.

```text
Foundation = meaning, models, schemas, governance, architecture
Platform   = software implementation of the foundation
Products   = reusable platform modules
Solutions  = packaged use cases for real-world problems
```

## Foundation vs Platform vs Product vs Solution

| Concept | Meaning | Example |
|---|---|---|
| Foundation | Canonical language, models, schemas, and governance | Ontology, taxonomy, registry model |
| Platform | Runtime implementation of the foundation | Registry, catalog, graph, governance services |
| Product | Named reusable module | OpenDataWorld Catalog, OpenDataWorld Governance |
| Solution | Packaged answer to a user or institutional problem | Open Data Portal, Enterprise Data Marketplace |
| Service | Reusable capability exposed by the platform | Dataset Service, Policy Service, Trust Service |

## What OpenDataWorld Provides

OpenDataWorld defines the foundation for:

- Data as a service
- Analytics as a service
- Metadata as a service
- Governance as a service
- Quality as a service
- Trust as a service
- Knowledge graph as a service
- Decision intelligence as a service
- Agentic data workflow as a service

## The Four Operating Planes

OpenDataWorld can be understood through four planes.

```text
Data Plane
Governance Plane
Analytics Plane
Agent Plane
```

### Data Plane

The Data Plane manages data assets.

It covers:

- Sources
- Ingestion
- Metadata
- Schemas
- Classification
- Quality
- Provenance
- Lineage
- Registry
- Catalog
- Data products

### Governance Plane

The Governance Plane controls access, policy, compliance, audit, risk, and accountability.

It covers:

- Identity
- Ownership
- Stewardship
- Classification
- Policy
- Access
- Approval
- Audit
- Retention
- Compliance
- Trust

### Analytics Plane

The Analytics Plane turns governed data into insight, decisions, and value.

It covers:

- Metrics
- KPIs
- Reports
- Dashboards
- Benchmarks
- Forecasts
- Insight cards
- Recommendations
- Decisions
- Outcomes
- Value realization

### Agent Plane

The Agent Plane allows governed agents to assist with data and analytics work.

It covers:

- Data discovery agents
- Metadata enrichment agents
- Quality agents
- Schema mapping agents
- Analytics agents
- Publishing agents
- Governance agents
- Policy-evaluated actions
- Human approval gates
- Audit and replay

## The Canonical Backbone

OpenDataWorld is built on a connected backbone:

```text
Glossary
  ↓
Ontology
  ↓
Taxonomy
  ↓
Meta Model
  ↓
Identity
  ↓
Trust
  ↓
Provenance
  ↓
Lineage
  ↓
Temporal Model
  ↓
Knowledge Graph
  ↓
Registry
  ↓
Reference Architecture
```

## What Each Foundation Artifact Means

### Glossary

Defines the shared vocabulary.

Example terms:

- Data Asset
- Dataset
- Data Product
- Policy
- Provenance
- Lineage
- Trust
- Decision

### Ontology

Defines the concepts and relationships.

Example:

```text
Dataset conformsTo Schema
Dataset governedBy Policy
Dataset hasProvenance ProvenanceRecord
Dataset supports Decision
```

### Taxonomy

Defines controlled classification values.

Example:

```text
Sensitivity = Public | Internal | Confidential | Restricted | Secret
Quality Tier = Bronze | Silver | Gold | Platinum | Certified
```

### Meta Model

Defines the structural root for all objects.

Example:

```text
Thing
├── Entity
├── Asset
├── Relationship
├── Event
├── Policy
├── Decision
└── Workflow
```

### Identity Model

Defines how people, organizations, systems, agents, datasets, policies, and services are identified.

Identity answers:

```text
Who or what is this?
```

### Trust Model

Defines whether something is reliable for a specific purpose.

Trust answers:

```text
Can we use this safely for this context?
```

### Provenance Model

Defines origin and custody.

Provenance answers:

```text
Where did this come from and who handled it?
```

### Lineage Model

Defines flow and dependency.

Lineage answers:

```text
How did this data move, transform, and affect downstream assets?
```

### Temporal Model

Defines time, events, versions, snapshots, projections, and history.

Temporal model answers:

```text
When was this true?
What version was used?
What changed?
```

### Knowledge Graph Model

Connects everything.

The graph answers:

```text
How is everything related and why does it matter?
```

### Registry Model

Makes objects official.

The registry answers:

```text
What is the canonical governed record?
```

## Catalog vs Registry vs Knowledge Graph

These are different but connected.

```text
Catalog        = helps people find things
Registry       = makes things official and governed
KnowledgeGraph = connects things and explains relationships
```

Example:

```text
Dataset appears in Catalog
Dataset is official in Registry
Dataset relationships live in Knowledge Graph
```

## Data Asset Card

Every important data asset should have a card.

```yaml
id: string
type: DataAsset
name: string
description: string
owner: string
steward: string
source: string
schema: string
classification: object
license: string
accessPolicy: string
qualityProfile: string
trustAssessment: string
provenance: string
lineage: string
lifecycleState: string
version: string
createdAt: datetime
updatedAt: datetime
```

## Minimum Viable OpenDataWorld Platform

A first implementation should support:

1. Register data assets
2. Register datasets
3. Assign owner and steward
4. Capture metadata
5. Register schemas
6. Classify sensitivity and domain
7. Capture provenance
8. Track lineage
9. Assess quality and trust
10. Publish catalog pages
11. Search datasets
12. Request access
13. Evaluate policy
14. Record audit events
15. Connect records in a knowledge graph

## Primary Solutions

OpenDataWorld can power:

- Open Data Portal
- Public Data Exchange
- Enterprise Data Marketplace
- Dataset Catalog
- Data Asset Registry
- Data Product Platform
- Governance Workbench
- Quality and Trust Hub
- Knowledge Graph Explorer
- Analytics Portal
- Decision Intelligence Workspace
- Research Data Repository
- AI-Ready Data Foundation
- Agentic Data Operations Platform

## Primary Products

The platform can be packaged as:

- OpenDataWorld Registry
- OpenDataWorld Catalog
- OpenDataWorld Governance
- OpenDataWorld Quality
- OpenDataWorld Lineage
- OpenDataWorld Knowledge Graph
- OpenDataWorld Publishing
- OpenDataWorld Analytics
- OpenDataWorld Insights
- OpenDataWorld Decision Intelligence
- OpenDataWorld Agentic Data Workflows

## How to Read This Repository

Start here:

1. `PRIMER.md`
2. `README.md`
3. `docs/data-analytics-solutions-as-a-service.md`
4. `docs/product-solutions-platform.md`
5. `glossary.md`
6. `ontology/data-centric-core-ontology.md`
7. `taxonomy/canonical-data-taxonomy.md`
8. `reference-models/canonical-meta-model.md`
9. `reference-models/data-modeling-model.md`
10. `reference-models/identity-model.md`
11. `reference-models/trust-model.md`
12. `reference-models/provenance-model.md`
13. `reference-models/lineage-model.md`
14. `reference-models/temporal-model.md`
15. `reference-models/knowledge-graph-model.md`
16. `reference-models/registry-model.md`
17. `reference-architectures/reference-platform-architecture.md`
18. `reference-architectures/reference-data-architecture.md`
19. `reference-architectures/reference-governance-architecture.md`

## Builder Reading Path

For builders implementing the platform:

```text
Primer
  ↓
Meta Model
  ↓
Schemas
  ↓
Registry Model
  ↓
Knowledge Graph Model
  ↓
Reference Platform Architecture
  ↓
Reference Data Architecture
  ↓
Reference Governance Architecture
```

## Governance Reading Path

For governance, compliance, and data stewardship teams:

```text
Primer
  ↓
Operating Model
  ↓
Governance Architecture
  ↓
Identity Model
  ↓
Trust Model
  ↓
Provenance Model
  ↓
Lineage Model
  ↓
Registry Model
```

## Analytics Reading Path

For analytics and decision intelligence teams:

```text
Primer
  ↓
Data & Analytics Solutions as a Service
  ↓
Capability Map
  ↓
Service Catalog
  ↓
Data Architecture
  ↓
Knowledge Graph Model
  ↓
Decision and Outcome Models
```

## Agent Reading Path

For agent and AI workflow builders:

```text
Primer
  ↓
Identity Model
  ↓
Trust Model
  ↓
Governance Architecture
  ↓
Knowledge Graph Model
  ↓
Service Catalog
  ↓
Agentic Data Services
```

## Important Design Rules

1. Data is the anchor.
2. Everything important must have identity.
3. Everything governed must have ownership.
4. Everything published must have provenance.
5. Everything transformed must have lineage.
6. Everything sensitive must have policy.
7. Everything trusted must have evidence.
8. Everything temporal must preserve history.
9. Everything agentic must be policy-evaluated.
10. Everything decision-relevant must be auditable.

## What Is Not Complete Yet

The Foundation is strong but still evolving.

Missing or incomplete areas include:

- Full graph implementation schema
- Node and edge YAML specifications
- JSON-LD context
- RDF/OWL alignment
- Complete JSON Schema inheritance chain
- Reference analytics architecture
- Reference agent architecture
- Deployment architecture
- Validation test fixtures
- Example seed graph
- Example dataset registry records

## Status

Draft. Canonical after governance review.

## Canonical Tagline

```text
Data and analytics solutions as a service for everyone.
```
