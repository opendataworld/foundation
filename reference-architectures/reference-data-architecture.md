# OpenDataWorld Reference Data Architecture

OpenDataWorld is anchored on data and analytics solutions as a service for everyone.

This reference data architecture defines how data moves from sources into governed, trusted, reusable, discoverable, and consumable data assets and data products.

## Data Architecture North Star

```text
Turn fragmented data into governed, trusted, reusable, AI-ready data assets and data products.
```

## Core Data Flow

```text
Data Sources
    ↓
Ingestion
    ↓
Metadata Extraction
    ↓
Schema Detection and Registration
    ↓
Classification
    ↓
Provenance Capture
    ↓
Quality Validation
    ↓
Registry
    ↓
Governance and Access Control
    ↓
Catalog and Discovery
    ↓
Data Products and APIs
    ↓
Analytics, Decisions, Agents, and Consumers
```

## Architecture Layers

```text
Source Layer
├── Databases
├── Files
├── APIs
├── Streams
├── Web Sources
├── Government Portals
├── Research Repositories
├── SaaS Systems
├── Sensors
└── Manual Submissions

Ingestion Layer
├── Connectors
├── Batch Ingestion
├── Streaming Ingestion
├── File Upload
├── API Import
├── Web Crawl
├── Schema Extraction
└── Metadata Extraction

Governance Preparation Layer
├── Identity Resolution
├── Source Registration
├── Ownership Assignment
├── Stewardship Assignment
├── Classification
├── License Detection
├── Sensitivity Detection
└── Policy Mapping

Trust Preparation Layer
├── Provenance Capture
├── Lineage Capture
├── Quality Validation
├── Freshness Measurement
├── Evidence Capture
├── Trust Assessment
└── Issue Detection

Registry and Catalog Layer
├── Data Asset Registry
├── Dataset Registry
├── Data Source Registry
├── Schema Registry
├── Data Element Registry
├── Catalog Projection
├── Search Index
└── Knowledge Graph

Consumption Layer
├── Dataset Pages
├── Data Product Pages
├── APIs
├── Downloads
├── Subscriptions
├── Dashboards
├── Reports
├── Decision Workspaces
└── Agentic Workflows
```

## Primary Data Objects

```text
DataSource
DataAsset
Dataset
DatasetVersion
DataProduct
DataElement
Schema
Distribution
MetadataRecord
ProvenanceRecord
LineageRecord
QualityProfile
TrustAssessment
AccessPolicy
CatalogEntry
```

## Data Source Architecture

A DataSource is the origin or immediate provider of data.

### Data Source Types

```text
Database
DataWarehouse
DataLake
ObjectStorage
FileUpload
API
WebPage
WebCrawl
Stream
Sensor
Application
SaaSApplication
GovernmentPortal
ResearchRepository
PublicRegistry
ManualEntry
Survey
Form
Document
Spreadsheet
LogSystem
EventBus
ExternalProvider
```

### Data Source Requirements

Every source should define:

```yaml
id: string
name: string
sourceType: string
owner: string
operator: string
accessMethod: string
updateCadence: string
reliabilityProfile: string
license: string
classification: object
provenance: object
```

## Ingestion Architecture

Ingestion brings data and metadata into the platform.

### Ingestion Modes

```text
ManualUpload
BatchImport
APIImport
StreamingIngestion
ScheduledSync
WebCrawl
EventDrivenImport
AgentAssistedImport
```

### Ingestion Requirements

Every ingestion must produce:

- Source reference
- Ingestion event
- Provenance record
- Initial metadata record
- Schema detection result where applicable
- Classification result or pending classification state
- Audit record

## Metadata Architecture

Metadata makes data understandable, discoverable, governable, and reusable.

### Metadata Types

```text
Descriptive Metadata
Structural Metadata
Technical Metadata
Administrative Metadata
Governance Metadata
Quality Metadata
Operational Metadata
Usage Metadata
Provenance Metadata
Lineage Metadata
```

### Metadata Completeness Baseline

Every published dataset should include:

```yaml
name: string
description: string
owner: string
steward: string
source: string
schema: string
classification: object
license: string
accessLevel: string
qualityTier: string
provenance: string
lineage: string
freshness: string
version: string
```

## Schema Architecture

Schemas define structure and validation.

### Schema Flow

```text
Detect Schema
    ↓
Register Schema
    ↓
Validate Data
    ↓
Map to Canonical Model
    ↓
Version Schema
    ↓
Monitor Schema Drift
```

### Schema Requirements

- Every schema must have an owner.
- Every schema must have a version.
- Every schema must declare what it applies to.
- Schema changes must be classified as breaking or non-breaking.
- Schema mappings must preserve provenance.

## Classification Architecture

Classification supports discovery, access, policy, and governance.

### Required Classifications

- Domain
- DataAssetType
- DataSensitivity
- DataAccessLevel
- DataQualityTier
- DataLifecycleState
- DataLicenseClass
- DataTrustLevel
- DataCriticality where applicable

## Quality Architecture

Quality determines whether data is fit for purpose.

### Quality Dimensions

```text
Accuracy
Completeness
Consistency
Timeliness
Validity
Uniqueness
Reliability
Availability
Usability
Explainability
```

### Quality Flow

```text
Define Quality Rules
    ↓
Run Validation
    ↓
Record Results
    ↓
Assign Quality Tier
    ↓
Publish Known Issues
    ↓
Monitor Continuously
    ↓
Improve
```

## Data Product Architecture

A DataProduct packages data for reliable consumption.

### Data Product Flow

```text
Identify Consumer Need
    ↓
Select Data Assets
    ↓
Define Product Contract
    ↓
Define Quality Expectations
    ↓
Define Access Model
    ↓
Define Interfaces
    ↓
Publish Data Product Card
    ↓
Monitor Usage and Feedback
    ↓
Improve
```

### Data Product Requirements

```yaml
owner: string
steward: string
intendedConsumers:
  - string
useCases:
  - string
inputDataAssets:
  - string
interfaces:
  - string
qualityExpectations: object
slo: object
accessPolicy: string
supportModel: string
changePolicy: string
```

## Data Access Architecture

Data access must be identity-bound, policy-evaluated, auditable, and revocable.

### Access Flow

```text
Subject requests data
    ↓
Identity resolved
    ↓
Purpose captured
    ↓
Resource classification checked
    ↓
Policy evaluated
    ↓
Approval routed if required
    ↓
Access decision recorded
    ↓
Access granted or denied
    ↓
Usage monitored
```

## Data Publication Architecture

Publishing makes data available to intended audiences.

### Publication Requirements

Before publication:

- Metadata completeness must pass threshold.
- Sensitivity must not be Unknown.
- License must be clear.
- Provenance must exist.
- Quality tier must be known.
- Access policy must be defined.
- Publication approval must be recorded where required.

## AI-Ready Data Architecture

AI-ready data must be governed, traceable, and contextual.

### AI-Ready Requirements

- Source reference
- Data version
- Schema version
- Classification
- License
- Access policy
- Provenance
- Lineage
- Quality profile
- Trust assessment
- Usage constraints

## Minimum Viable Data Architecture

The first operational platform should support:

1. Source registration
2. Dataset registration
3. Metadata capture
4. Schema registration
5. Classification
6. Provenance record
7. Quality tier
8. Access policy
9. Catalog entry
10. Search indexing
11. Dataset publication
12. Data product card
13. Audit events

## Data Architecture Validation Rules

1. Every dataset must have an owner.
2. Every dataset must have a source.
3. Every published dataset must have provenance.
4. Every published dataset must have license or usage terms.
5. Every sensitive dataset must have access policy.
6. Every data product must define intended consumers.
7. Every transformation must produce lineage.
8. Every schema must be versioned.
9. Every access decision must be auditable.
10. Every AI-ready data context must preserve source and version.

## Status

Draft. Canonical after governance review.
