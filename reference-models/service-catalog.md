# OpenDataWorld Service Catalog

OpenDataWorld provides data and analytics solutions as a service for everyone.

This service catalog defines the canonical services that make the platform consumable, governable, measurable, and extensible.

## Service Catalog Purpose

The service catalog translates capabilities into reusable services.

```text
Capability → Service → Product Module → Solution → Outcome
```

## Service Design Principles

1. Every service must be data-first.
2. Every service must be governable.
3. Every service must be observable.
4. Every service must be versioned.
5. Every service must expose metadata.
6. Every service must preserve provenance where applicable.
7. Every service must support audit where policy-relevant.
8. Every service must be usable by humans, systems, and governed agents.
9. Every service should prefer open standards and portable interfaces.
10. Every service must declare ownership, purpose, inputs, outputs, policies, and success metrics.

## Service Domains

```text
OpenDataWorld Services
├── Data Services
├── Metadata Services
├── Governance Services
├── Trust and Quality Services
├── Analytics Services
├── Insight Services
├── Knowledge Graph Services
├── Decision Intelligence Services
├── Publishing Services
├── Access Services
├── Integration Services
├── Agentic Data Services
├── Observability Services
└── Improvement Services
```

## 1. Data Services

Data Services provide governed access to datasets, data assets, data products, APIs, streams, and distributions.

### Dataset Service

Manages dataset registration, metadata, versions, distributions, schema references, ownership, quality, access, and publication state.

#### Inputs

- Dataset metadata
- Schema reference
- Source reference
- Owner and steward
- Classification
- License
- Access policy

#### Outputs

- Dataset card
- Dataset page
- Dataset version record
- Catalog entry
- Access endpoint reference

#### Metrics

- Registered datasets
- Published datasets
- Dataset metadata completeness
- Dataset reuse rate

### Data Asset Registry Service

Maintains canonical records for all governed data assets.

#### Supported Assets

- Dataset
- Data product
- Data source
- Data element
- Data API
- Data stream
- Data file
- Data view
- Data index
- Data report
- Dashboard
- Knowledge graph

### Data Product Service

Packages data assets into reusable data products with consumers, SLOs, access rules, documentation, and support expectations.

#### Outputs

- Data product card
- Consumer contract
- Quality expectations
- Change policy
- Usage metrics

### Data API Service

Exposes governed data assets through APIs.

#### Requirements

- API contract
- Access policy
- Rate limits
- Usage logging
- Versioning
- Schema reference

### Data Subscription Service

Allows consumers to subscribe to datasets, data products, updates, events, or alerts.

## 2. Metadata Services

Metadata Services describe data and make it understandable, discoverable, and governable.

### Metadata Registry Service

Stores descriptive, structural, technical, governance, operational, quality, and usage metadata.

### Schema Registry Service

Stores and versions schemas for datasets, APIs, streams, events, and metadata records.

### Data Dictionary Service

Defines data elements, fields, metrics, dimensions, allowed values, and semantic meanings.

### Glossary Mapping Service

Maps terms used in datasets and systems to canonical glossary and ontology terms.

### Classification Service

Assigns taxonomy values to data assets.

#### Classification Types

- Domain
- Data asset type
- Sensitivity
- Access level
- Quality tier
- License class
- Trust level
- Criticality
- Lifecycle state

## 3. Governance Services

Governance Services define and enforce rules around ownership, access, privacy, usage, retention, publication, audit, and lifecycle.

### Policy Registry Service

Stores governed policy records and versions.

### Policy Evaluation Service

Evaluates whether a subject may perform an action on a resource under context.

```text
Subject + Action + Resource + Context → Allow | Deny | RequireApproval | Escalate
```

### Access Request Service

Manages requests to access data assets.

### Approval Workflow Service

Routes governance decisions to authorized reviewers.

### Consent Reference Service

Links data processing and access to consent records where required.

### Retention Service

Defines how long data should be kept and when it should be archived, deleted, or reviewed.

### Audit Service

Records policy-relevant actions, access events, decisions, and changes.

## 4. Trust and Quality Services

Trust and Quality Services help users decide whether data is fit for use.

### Provenance Service

Records origin, source, creator, collection method, evidence, and change history.

### Lineage Service

Tracks how data moves, transforms, derives, and produces downstream assets.

### Quality Service

Runs and records quality checks.

#### Quality Dimensions

- Accuracy
- Completeness
- Consistency
- Timeliness
- Validity
- Uniqueness
- Reliability
- Usability

### Validation Service

Validates data, metadata, schemas, policies, and registry records.

### Trust Score Service

Calculates evidence-backed trust levels.

### Certification Service

Supports governed review and certification of data assets and data products.

## 5. Analytics Services

Analytics Services turn governed data into reusable analysis.

### Metrics Registry Service

Defines metrics, KPIs, formulas, dimensions, owners, and calculation logic.

### Dashboard Service

Creates and serves dashboards from governed data.

### Reporting Service

Creates recurring, governed, auditable reports.

### Benchmark Service

Compares datasets, entities, organizations, systems, or outcomes using defined metrics.

### Forecasting Service

Produces forecast outputs with assumptions, confidence, limitations, and data references.

### Analytical Model Service

Manages analytical models used for scoring, segmentation, prediction, or classification.

## 6. Insight Services

Insight Services convert analytics into understandable, evidence-backed narratives and recommendations.

### Insight Card Service

Produces structured insight cards.

#### Insight Card Fields

- Insight statement
- Data used
- Evidence
- Confidence
- Explanation
- Recommended action
- Limitations
- Owner
- Review status

### Explanation Service

Explains metrics, anomalies, trends, forecasts, and model outputs.

### Recommendation Service

Produces governed recommendations linked to evidence and constraints.

### Narrative Analytics Service

Generates human-readable summaries from analytical outputs.

## 7. Knowledge Graph Services

Knowledge Graph Services connect data, entities, relationships, policies, lineage, evidence, decisions, and outcomes.

### Entity Resolution Service

Identifies and links records that refer to the same entity.

### Relationship Service

Stores and governs relationships between entities, assets, policies, events, and decisions.

### Graph Query Service

Enables graph exploration and relationship queries.

### Semantic Search Service

Supports meaning-aware search across assets, entities, documents, policies, and insights.

### Context Retrieval Service

Provides governed context to humans, systems, and AI agents.

## 8. Decision Intelligence Services

Decision Intelligence Services connect data, analytics, evidence, assumptions, constraints, actions, outcomes, and learning.

### Decision Registry Service

Stores decision records.

### Evidence Registry Service

Stores evidence used for claims, decisions, validations, and audits.

### Assumption Registry Service

Tracks assumptions used in analysis and decision-making.

### Outcome Tracking Service

Tracks decision outcomes and impact.

### Decision Review Service

Supports review, approval, challenge, and learning from decisions.

## 9. Publishing Services

Publishing Services make data and analytics available to intended audiences under governance.

### Dataset Publishing Service

Publishes dataset pages, metadata, downloads, APIs, and version history.

### Open Data Portal Service

Publishes public data assets with metadata, license, provenance, and quality indicators.

### Analytics Publishing Service

Publishes dashboards, reports, benchmarks, insight cards, and explainers.

### Schema.org and JSON-LD Publishing Service

Publishes machine-readable metadata for discovery and interoperability.

### Publication Review Service

Manages review and approval before publication.

## 10. Access Services

Access Services ensure the right subject gets the right access for the right purpose under the right policy.

### Identity Integration Service

Connects users, organizations, systems, and agents to identity providers.

### Authorization Service

Controls permissions for data, APIs, workflows, and administrative functions.

### Purpose-Based Access Service

Evaluates intended use as part of access decisions.

### License Enforcement Service

Connects data access to license and terms of use.

### Access Revocation Service

Revokes access when policy, consent, risk, contract, or lifecycle changes.

## 11. Integration Services

Integration Services bring data and metadata into OpenDataWorld and expose outputs to external systems.

### Connector Service

Manages connectors to files, databases, APIs, SaaS systems, catalogs, and public portals.

### Ingestion Service

Loads data and metadata from sources.

### Web Crawl Service

Discovers and extracts public data and metadata from websites where permitted.

### API Contract Import Service

Imports OpenAPI and AsyncAPI specifications.

### Export Service

Exports metadata, catalog records, schemas, reports, and data products to external systems.

## 12. Agentic Data Services

Agentic Data Services allow governed agents to assist with data and analytics work.

### Data Discovery Agent Service

Finds relevant data assets based on user goals and policy.

### Metadata Enrichment Agent Service

Suggests descriptions, tags, glossary mappings, and classifications.

### Data Quality Agent Service

Detects quality issues and recommends remediation.

### Schema Mapping Agent Service

Maps schemas across systems and standards.

### Analytics Agent Service

Generates governed analysis from approved data assets.

### Publishing Agent Service

Prepares data and metadata for publication, subject to approval.

### Governance Agent Service

Recommends policies, access decisions, and risk controls, subject to human review.

### Agent Action Audit Service

Records every agent action on data, including policy decision, input, output, evidence, and approval status.

## 13. Observability Services

Observability Services monitor system, data, governance, quality, and service health.

### Data Health Monitor

Monitors freshness, quality, availability, and schema drift.

### Governance Monitor

Monitors policy decisions, access violations, exceptions, and audit completeness.

### Usage Monitor

Tracks search, access, downloads, API calls, subscriptions, dashboards, and reports.

### Cost Monitor

Tracks operational costs, compute usage, storage usage, and agent execution cost.

### Service Health Monitor

Tracks platform availability, latency, error rates, and reliability.

## 14. Improvement Services

Improvement Services support continuous improvement of data assets, services, policies, and platform maturity.

### Feedback Service

Captures feedback from users, stewards, consumers, agents, and systems.

### Issue Management Service

Tracks quality issues, governance issues, access issues, and metadata issues.

### Maturity Assessment Service

Assesses data, analytics, governance, and AI-readiness maturity.

### Roadmap Service

Prioritizes improvements based on value, risk, usage, and strategic goals.

## Service Record Template

Every service should have a service record.

```yaml
id: string
name: string
serviceDomain: string
description: string
owner: string
steward: string
users:
  - string
inputs:
  - string
outputs:
  - string
policies:
  - string
apis:
  - string
events:
  - string
metrics:
  - string
lifecycleState: string
version: string
```

## Minimum Viable Service Catalog

The first operational OpenDataWorld platform should provide:

1. Dataset Service
2. Data Asset Registry Service
3. Metadata Registry Service
4. Schema Registry Service
5. Classification Service
6. Policy Registry Service
7. Access Request Service
8. Provenance Service
9. Quality Service
10. Catalog Search Service
11. Dataset Publishing Service
12. Audit Service

## Service Governance Rules

1. Every service must have an owner.
2. Every service must define inputs and outputs.
3. Every service must declare policies it enforces or depends on.
4. Every service that changes data must emit events.
5. Every service that supports access must produce audit records.
6. Every service used by agents must define tool contracts and risk level.
7. Every service must define success metrics.
8. Every service must have lifecycle state and version.
9. Every public-facing service must define usage terms.
10. Every service must map back to one or more platform capabilities.

## Status

Draft. Canonical after governance review.
