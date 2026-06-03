# OpenDataWorld Namespace and Bucket Model

OpenDataWorld should be organized into clear buckets and namespaces so concepts, artifacts, schemas, graph objects, services, products, legal rights, and implementation assets do not get mixed.

## Purpose

This model defines how OpenDataWorld Foundation artifacts should be separated, named, governed, licensed, and extended.

## Core Principle

```text
Separate meaning, specification, implementation, operation, product, solution, and legal ownership into explicit namespaces.
```

## Top-Level Buckets

```text
OpenDataWorld
├── Foundation Bucket
├── Specification Bucket
├── Graph Bucket
├── Schema Bucket
├── Architecture Bucket
├── Governance Bucket
├── Platform Bucket
├── Product Bucket
├── Solution Bucket
├── Data Bucket
├── Analytics Bucket
├── Agent Bucket
├── Legal and IP Bucket
├── Brand Bucket
└── Community Bucket
```

## Canonical Namespaces

```text
odw.foundation.*
odw.spec.*
odw.graph.*
odw.schema.*
odw.architecture.*
odw.governance.*
odw.platform.*
odw.product.*
odw.solution.*
odw.data.*
odw.analytics.*
odw.agent.*
odw.legal.*
odw.brand.*
odw.community.*
```

## 1. Foundation Namespace

Namespace:

```text
odw.foundation.*
```

Purpose:

The canonical meaning layer.

Contains:

```text
Glossary
Ontology
Taxonomy
Meta Model
Data Modeling Model
Identity Model
Temporal Model
Trust Model
Provenance Model
Lineage Model
Registry Model
Knowledge Graph Model
Decision Intelligence Model
Namespace Model
```

Repository locations:

```text
glossary.md
ontology/
taxonomy/
reference-models/
```

Recommended license:

```text
CC-BY-4.0 for documentation and models
Apache-2.0 for machine-readable specifications
```

## 2. Specification Namespace

Namespace:

```text
odw.spec.*
```

Purpose:

Machine-readable canonical contracts.

Contains:

```text
JSON Schemas
YAML Contracts
JSON-LD Contexts
Validation Rules
Graph Contracts
API Contracts
Event Contracts
```

Repository locations:

```text
schemas/
graph/
contexts/
reference-apis/
reference-events/
validators/
```

Recommended license:

```text
Apache-2.0
```

## 3. Graph Namespace

Namespace:

```text
odw.graph.*
```

Purpose:

Graph nodes, edges, constraints, validation, and semantic interoperability.

Contains:

```text
Node Types
Edge Types
Constraints
Validation Rules
Example Graphs
JSON-LD Contexts
Graph Projections
Graph Mappings
```

Repository locations:

```text
graph/
contexts/
```

Example IDs:

```text
odw.graph.node.Dataset
odw.graph.edge.governedBy
odw.graph.constraint.PublishedDatasetMustBeComplete
```

## 4. Schema Namespace

Namespace:

```text
odw.schema.*
```

Purpose:

Object validation and portable implementation contracts.

Contains:

```text
Dataset Schema
Data Product Schema
Policy Schema
Trust Assessment Schema
Metric Schema
Insight Schema
Decision Schema
Outcome Schema
Agent Schema
```

Repository location:

```text
schemas/
```

Example IDs:

```text
odw.schema.Dataset
odw.schema.Policy
odw.schema.Decision
```

## 5. Architecture Namespace

Namespace:

```text
odw.architecture.*
```

Purpose:

Reference architecture and system design guidance.

Contains:

```text
Reference Platform Architecture
Reference Data Architecture
Reference Governance Architecture
Reference Analytics Architecture
Reference Agent Architecture
Reference Deployment Architecture
```

Repository location:

```text
reference-architectures/
```

## 6. Governance Namespace

Namespace:

```text
odw.governance.*
```

Purpose:

Policies, controls, gates, decisions, approvals, audit, risk, and compliance.

Contains:

```text
Governance Policies
Control Catalog
Approval Rules
Audit Rules
Risk Rules
Compliance Mappings
Publication Gates
Agent Action Gates
```

Potential repository locations:

```text
governance/
controls/
policies/
```

## 7. Platform Namespace

Namespace:

```text
odw.platform.*
```

Purpose:

Runtime implementation concerns.

Contains:

```text
Services
APIs
Databases
Workers
Queues
Search
Graph Store
Registry Store
Policy Engine
Observability
Deployment
```

This namespace belongs mostly to implementation repositories, not the Foundation repository.

Example:

```text
odw.platform.registry
odw.platform.catalog
odw.platform.governance
odw.platform.graph
odw.platform.analytics
odw.platform.agent
```

## 8. Product Namespace

Namespace:

```text
odw.product.*
```

Purpose:

Named reusable modules that can be packaged, sold, deployed, documented, and supported.

Products:

```text
odw.product.registry
odw.product.catalog
odw.product.governance
odw.product.quality
odw.product.lineage
odw.product.knowledgeGraph
odw.product.analytics
odw.product.insights
odw.product.decisionIntelligence
odw.product.agenticWorkflows
```

## 9. Solution Namespace

Namespace:

```text
odw.solution.*
```

Purpose:

Packaged use cases for real user or institutional problems.

Solutions:

```text
odw.solution.openDataPortal
odw.solution.publicDataExchange
odw.solution.enterpriseDataMarketplace
odw.solution.datasetCatalog
odw.solution.dataProductPlatform
odw.solution.governanceWorkbench
odw.solution.qualityTrustHub
odw.solution.knowledgeGraphExplorer
odw.solution.analyticsPortal
odw.solution.decisionIntelligenceWorkspace
odw.solution.researchDataRepository
odw.solution.aiReadyDataFoundation
odw.solution.agenticDataOperations
```

## 10. Data Namespace

Namespace:

```text
odw.data.*
```

Purpose:

Data assets, datasets, data products, sources, data elements, distributions, and metadata records.

Examples:

```text
odw.data.dataset.publicHealthFacilities
odw.data.product.healthcareAccess
odw.data.source.governmentPortal
odw.data.element.facilityId
```

## 11. Analytics Namespace

Namespace:

```text
odw.analytics.*
```

Purpose:

Metrics, KPIs, dashboards, reports, insights, recommendations, decisions, outcomes, and value realization.

Examples:

```text
odw.analytics.metric.facilityCoverageRate
odw.analytics.insight.facilityAccessGap
odw.analytics.decision.facilityPlanning
odw.analytics.outcome.planningReview
```

## 12. Agent Namespace

Namespace:

```text
odw.agent.*
```

Purpose:

Agent identities, agent types, tools, skills, actions, evaluations, approvals, and audit traces.

Examples:

```text
odw.agent.discovery
odw.agent.metadataEnrichment
odw.agent.classification
odw.agent.analytics
odw.agent.governance
odw.agent.decisionSupport
```

## 13. Legal and IP Namespace

Namespace:

```text
odw.legal.*
```

Purpose:

Copyright, licensing, notices, contributor rights, patent policy, trademark policy, and usage terms.

Contains:

```text
LICENSE
NOTICE
COPYRIGHT.md
TRADEMARKS.md
PATENTS.md
CONTRIBUTING.md
CLA.md
DCO.md
```

Recommended separation:

```text
Code and machine-readable specifications → Apache-2.0
Documentation and models → CC-BY-4.0
Example data → CC0 or CC-BY-4.0
Brand and logos → Trademark policy
Private methods and playbooks → Trade secret, not published
```

## 14. Brand Namespace

Namespace:

```text
odw.brand.*
```

Purpose:

Names, marks, visual identity, taglines, logos, and brand usage.

Examples:

```text
OpenDataWorld
OpenDataWorld Foundation
OpenDataWorld Platform
OpenDataWorld Registry
OpenDataWorld Catalog
Data and Analytics Solutions as a Service for Everyone
```

## 15. Community Namespace

Namespace:

```text
odw.community.*
```

Purpose:

Community participation, contribution, governance, code of conduct, working groups, and public collaboration.

Contains:

```text
CODE_OF_CONDUCT.md
CONTRIBUTING.md
GOVERNANCE.md
working-groups/
community/
```

## Repository Bucket Layout

Recommended Foundation repository layout:

```text
/
├── README.md
├── PRIMER.md
├── LICENSE
├── NOTICE
├── COPYRIGHT.md
├── TRADEMARKS.md
├── docs/
├── ontology/
├── taxonomy/
├── reference-models/
├── reference-architectures/
├── schemas/
├── graph/
├── contexts/
├── governance/
├── controls/
├── policies/
├── examples/
├── validators/
├── reference-apis/
├── reference-events/
├── community/
└── brand/
```

## IP and Licensing Buckets

```text
Copyrighted Open Content
├── Docs
├── Primers
├── Models
├── Architectures
└── Diagrams

Copyrighted Open Source Specifications
├── JSON Schemas
├── YAML Contracts
├── JSON-LD Contexts
├── Validators
└── Code

Trademarked Brand Assets
├── Names
├── Logos
├── Product Names
└── Taglines

Potential Trade Secret Assets
├── Scoring Weights
├── Enterprise Playbooks
├── Private Benchmark Methods
├── Pricing Models
└── Customer-Specific Configurations
```

## Naming Rules

1. Use `odw.*` as the canonical namespace prefix.
2. Use lowercase kebab-case for file paths.
3. Use PascalCase for schema titles and object types.
4. Use camelCase for JSON fields.
5. Use stable IDs for governed objects.
6. Do not mix product names with foundational model names.
7. Do not place private trade-secret material in open foundation repositories.
8. Every namespace should declare owner, license, lifecycle state, and extension rules.

## Extension Rules

Domain or implementation namespaces may extend Foundation namespaces.

Examples:

```text
odw.healthcare.*
odw.education.*
odw.climate.*
odw.publicSector.*
odw.enterprise.*
odw.research.*
```

Extension requirements:

1. Must map back to canonical OpenDataWorld concepts.
2. Must declare namespace owner.
3. Must declare license.
4. Must declare version.
5. Must not redefine canonical terms without explicit mapping.
6. Must preserve provenance and lineage where applicable.

## Status

Draft. Canonical after governance review.
