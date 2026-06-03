# OpenDataWorld Reference Platform Architecture

OpenDataWorld provides data and analytics solutions as a service for everyone.

This reference architecture defines how the Foundation models can be implemented as a platform that supports data registries, catalogs, governance, analytics, knowledge graphs, decision intelligence, and governed agentic workflows.

## Architecture North Star

```text
A platform that turns fragmented data into governed, trusted, discoverable, reusable, AI-ready data and analytics services.
```

## Architecture Principles

1. Data is the anchor.
2. Foundation models are the source of meaning.
3. Registries make objects official.
4. Catalogs make objects discoverable.
5. Knowledge graphs make objects connected.
6. Governance is built in, not added later.
7. Trust must be evidence-backed.
8. Current state is a projection over history.
9. Every meaningful action must be auditable.
10. Agents must operate under identity, policy, and approval.
11. Open standards and portable interfaces are preferred.
12. Platform capabilities must be modular, composable, and replaceable.

## Platform Layers

```text
Experience Layer
    ↓
Application Services Layer
    ↓
Intelligence and Governance Layer
    ↓
Data and Knowledge Layer
    ↓
Integration Layer
    ↓
Platform Operations Layer
    ↓
Infrastructure Layer
```

## 1. Experience Layer

The Experience Layer provides human and agent-facing interfaces.

```text
Experience Layer
├── Public Data Portal
├── Data Catalog UI
├── Registry UI
├── Data Product UI
├── Analytics UI
├── Insight UI
├── Governance Workbench
├── Steward Console
├── Admin Console
├── Developer Portal
├── API Explorer
├── Knowledge Graph Explorer
├── Lineage Explorer
├── Decision Intelligence Workspace
└── Agent Workspace
```

### Responsibilities

- Search and discovery
- Dataset and data product pages
- Metadata review
- Access requests
- Policy review
- Quality review
- Lineage exploration
- Analytics and insight consumption
- Decision records
- Agent workflow monitoring

## 2. Application Services Layer

The Application Services Layer implements product and solution capabilities.

```text
Application Services
├── Registry Service
├── Catalog Service
├── Dataset Service
├── Data Product Service
├── Metadata Service
├── Schema Registry Service
├── Data Dictionary Service
├── Publishing Service
├── Search Service
├── Access Request Service
├── Governance Workflow Service
├── Analytics Service
├── Metrics Service
├── Insight Service
├── Decision Service
├── Evidence Service
├── Agent Workflow Service
└── Notification Service
```

### Responsibilities

- Expose business capabilities
- Manage workflows
- Provide APIs
- Enforce validation
- Coordinate domain services
- Emit events
- Maintain audit trails

## 3. Intelligence and Governance Layer

This layer provides decisioning, policy, trust, lineage, graph, and AI-ready context.

```text
Intelligence and Governance
├── Policy Engine
├── Authorization Engine
├── Trust Engine
├── Quality Engine
├── Lineage Engine
├── Provenance Engine
├── Knowledge Graph Engine
├── Search and Ranking Engine
├── Recommendation Engine
├── Decision Engine
├── Rules Engine
├── Evaluation Engine
├── Agent Guardrail Engine
└── Human Approval Engine
```

### Responsibilities

- Evaluate policy
- Calculate trust
- Validate quality
- Build lineage
- Resolve entities
- Connect graph relationships
- Support semantic search
- Record decisions
- Govern agent actions
- Route human approvals

## 4. Data and Knowledge Layer

The Data and Knowledge Layer stores governed records, projections, files, graph edges, events, indexes, and audit history.

```text
Data and Knowledge Stores
├── Registry Store
├── Metadata Store
├── Graph Store
├── Search Index
├── Object Store
├── Event Store
├── Audit Store
├── Policy Store
├── Schema Store
├── Lineage Store
├── Provenance Store
├── Trust Store
├── Decision Store
├── Metrics Store
├── Analytics Store
└── Vector Index
```

### Storage Rules

1. Registry records must be versioned.
2. Events should be append-only where auditability matters.
3. Current state should be represented as projection.
4. Raw source data should preserve provenance where retained.
5. Graph edges must preserve evidence and temporal context.
6. Audit records must be protected from unauthorized modification.

## 5. Integration Layer

The Integration Layer connects OpenDataWorld to data sources, systems, APIs, catalogs, portals, and external platforms.

```text
Integration Layer
├── File Connectors
├── Database Connectors
├── API Connectors
├── SaaS Connectors
├── Stream Connectors
├── Web Crawl Connectors
├── Government Portal Connectors
├── Research Repository Connectors
├── OpenAPI Importer
├── AsyncAPI Importer
├── DCAT Importer and Exporter
├── Schema.org and JSON-LD Exporter
├── Webhook Gateway
├── Event Gateway
└── External Catalog Synchronizer
```

### Integration Rules

1. Every integration must have a source identity.
2. Every ingestion must produce provenance.
3. Every transformation must produce lineage.
4. Every external schema must be mapped to canonical schemas where applicable.
5. Every connector must declare permissions and risk level.

## 6. Platform Operations Layer

The Platform Operations Layer supports identity, observability, reliability, security, deployment, and runtime operations.

```text
Platform Operations
├── Identity Provider Integration
├── Access Control
├── Secrets Management
├── Configuration Management
├── Workflow Orchestration
├── Scheduler
├── Notification System
├── Observability
├── Logging
├── Metrics
├── Tracing
├── Alerting
├── Backup and Recovery
├── Cost Monitoring
├── Incident Management
└── Release Management
```

### Operational Requirements

- Multi-tenant ready
- Cloud-native ready
- Self-hostable
- Edge and air-gapped deployable where required
- Observable by default
- Secure by default
- Policy-governed by default
- Backup and recovery aware

## 7. Infrastructure Layer

The Infrastructure Layer provides compute, network, storage, security, and deployment substrates.

```text
Infrastructure
├── Compute
├── Containers
├── Kubernetes or Lightweight Cluster Runtime
├── Object Storage
├── Persistent Volumes
├── Network
├── Ingress
├── TLS
├── Secrets
├── Identity Infrastructure
├── Backup Storage
├── Monitoring Stack
└── Disaster Recovery Environment
```

## Core Platform Services

### Registry Platform

Provides canonical records for assets, identities, policies, schemas, evidence, trust, lineage, decisions, agents, and workflows.

### Catalog Platform

Provides discovery, search, browse, filters, pages, recommendations, and user-facing navigation.

### Governance Platform

Provides policies, access requests, approvals, audit, classification, retention, privacy, and compliance workflows.

### Knowledge Graph Platform

Provides graph records, relationships, lineage, impact analysis, root-cause analysis, semantic context, and connected discovery.

### Analytics Platform

Provides metrics, dashboards, reports, analytical models, benchmarking, forecasting, and explainable insight generation.

### Decision Intelligence Platform

Provides decision records, evidence, assumptions, alternatives, constraints, outcomes, and learning loops.

### Agentic Data Platform

Provides governed agents for discovery, classification, metadata enrichment, schema mapping, quality analysis, analytics, publishing, and governance support.

## Canonical Request Flow: Dataset Registration

```text
User or Connector submits dataset metadata
    ↓
Identity is checked
    ↓
Dataset schema is validated
    ↓
Dataset record is created in registry
    ↓
Classification is assigned
    ↓
Provenance is recorded
    ↓
Quality checks are scheduled
    ↓
Lineage links are created
    ↓
Trust assessment is calculated
    ↓
Catalog projection is updated
    ↓
Audit event is recorded
```

## Canonical Request Flow: Data Access

```text
Subject requests access
    ↓
Subject identity resolved
    ↓
Resource identity resolved
    ↓
Purpose and context captured
    ↓
Policy engine evaluates request
    ↓
Approval routed if required
    ↓
Access decision recorded
    ↓
Access grant or denial issued
    ↓
Audit event recorded
    ↓
Usage monitored
```

## Canonical Request Flow: Agentic Data Action

```text
Agent proposes action
    ↓
Agent identity resolved
    ↓
Tool permission checked
    ↓
Target data asset resolved
    ↓
Policy evaluated
    ↓
Risk evaluated
    ↓
Human approval requested if required
    ↓
Action executed
    ↓
Output validated
    ↓
Provenance and lineage recorded
    ↓
Audit event emitted
```

## Minimum Viable Platform Architecture

The first operational platform should include:

1. Registry Store
2. Dataset Service
3. Metadata Service
4. Schema Registry Service
5. Classification Service
6. Catalog UI
7. Search Service
8. Access Request Service
9. Policy Registry
10. Audit Store
11. Provenance Service
12. Quality Service
13. Lineage Service
14. Basic Knowledge Graph
15. Admin Console

## Non-Functional Requirements

### Security

- Identity-bound access
- Least privilege
- Policy-based authorization
- Secrets management
- Audit trails
- Data classification enforcement

### Reliability

- Backup and restore
- Health checks
- Retry-safe workflows
- Event durability
- Graceful degradation

### Observability

- Logs
- Metrics
- Traces
- Audit events
- Data health monitoring
- Policy monitoring

### Portability

- Open APIs
- JSON Schema
- JSON-LD
- Exportable registry records
- Portable metadata
- Infrastructure-agnostic deployment patterns

### Governance

- Versioned policies
- Approval workflows
- Lifecycle states
- Retention controls
- Evidence-backed decisions

## Architecture Boundaries

### Foundation Repository Defines

- Vocabulary
- Models
- Schemas
- Reference architecture
- Governance principles
- Validation rules

### Platform Repository Implements

- Runtime services
- APIs
- Databases
- UI
- Workflows
- Integrations
- Deployments

### Solution Repositories Configure

- Domain-specific schemas
- Taxonomies
- User journeys
- Dashboards
- Reports
- Connectors
- Policy packs

## Status

Draft. Canonical after governance review.
