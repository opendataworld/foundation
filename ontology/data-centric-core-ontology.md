# OpenDataWorld Data-Centric Core Ontology

OpenDataWorld Foundation is anchored on data.

This ontology defines data as the primary governed object. Agents, workflows, APIs, systems, policies, models, and decisions exist to create, describe, govern, protect, improve, publish, discover, use, or act upon data.

## Ontology North Star

Make data findable, trustworthy, interoperable, reusable, governable, traceable, and actionable.

## Core Assertion

```text
Data is the anchor.
Everything else is context, control, transformation, access, usage, evidence, or outcome around data.
```

## Data-Centric Concept Model

```text
Data
├── DataAsset
│   ├── Dataset
│   ├── DataProduct
│   ├── DataSource
│   ├── DataElement
│   ├── DataRecord
│   ├── DataTable
│   ├── DataFile
│   ├── DataStream
│   ├── DataIndex
│   └── DataView
├── DataDescription
│   ├── Metadata
│   ├── Schema
│   ├── Ontology
│   ├── Taxonomy
│   ├── Glossary
│   └── CatalogEntry
├── DataGovernance
│   ├── Policy
│   ├── AccessRule
│   ├── ConsentRule
│   ├── RetentionRule
│   ├── PrivacyRule
│   ├── SecurityRule
│   └── QualityRule
├── DataTrust
│   ├── Provenance
│   ├── Lineage
│   ├── QualityProfile
│   ├── ValidationResult
│   ├── Evidence
│   └── TrustScore
├── DataUsage
│   ├── Query
│   ├── APIAccess
│   ├── Publication
│   ├── Report
│   ├── Dashboard
│   ├── ModelTraining
│   ├── DecisionSupport
│   └── AgenticUse
└── DataOutcome
    ├── Insight
    ├── Decision
    ├── Action
    ├── Automation
    ├── Publication
    └── Impact
```

## Primary Entity: DataAsset

A DataAsset is any identifiable, governed object that contains, references, describes, produces, transforms, indexes, exposes, or represents data.

### Required Properties

- `id`
- `type`
- `name`
- `description`
- `owner`
- `steward`
- `createdAt`
- `updatedAt`
- `lifecycleState`
- `classification`
- `provenance`
- `accessPolicy`
- `license`
- `schema`
- `qualityProfile`
- `lineage`
- `version`

### Required Relationships

- `ownedBy` DataOwner
- `stewardedBy` DataSteward
- `sourcedFrom` DataSource
- `describedBy` Metadata
- `conformsTo` Schema
- `governedBy` Policy
- `classifiedAs` Classification
- `hasProvenance` Provenance
- `hasLineage` Lineage
- `hasQualityProfile` QualityProfile
- `licensedUnder` License
- `accessibleThrough` AccessChannel

## Dataset

A Dataset is a structured or semi-structured collection of data that is described, versioned, governed, and made available for use.

### Dataset Must Answer

- What data does it contain?
- Where did it come from?
- Who owns it?
- Who stewards it?
- What schema does it follow?
- What is its quality?
- What can it be used for?
- Who can access it?
- Under what license or usage terms?
- What changed between versions?
- What decisions or outcomes depend on it?

### Dataset Relationships

- `hasSchema` Schema
- `hasMetadata` Metadata
- `hasDistribution` Distribution
- `hasVersion` DatasetVersion
- `derivedFrom` DataAsset
- `usedBy` Actor
- `publishedIn` Catalog
- `supports` UseCase
- `feeds` DataProduct
- `evaluatedBy` QualityAssessment

## DataProduct

A DataProduct is a data asset packaged for reliable consumption with ownership, documentation, quality expectations, access model, and service-level expectations.

### DataProduct Required Relationships

- `contains` Dataset
- `ownedBy` DataProductOwner
- `stewardedBy` DataSteward
- `servedThrough` APIAsset
- `documentedBy` Documentation
- `governedBy` DataPolicy
- `monitoredBy` ObservabilitySystem
- `hasSLO` ServiceLevelObjective
- `hasConsumer` DataConsumer

## DataSource

A DataSource is the origin system, file, stream, API, database, sensor, application, or provider from which data is collected or referenced.

### DataSource Relationships

- `produces` DataAsset
- `ownedBy` Actor
- `operatedBy` System
- `connectedThrough` Connector
- `hasFreshnessExpectation` FreshnessRule
- `hasExtractionMethod` ExtractionMethod
- `hasReliabilityProfile` ReliabilityProfile

## DataElement

A DataElement is the smallest governed meaningful data unit.

Examples include a column, field, attribute, metric, dimension, feature, property, or JSON path.

### DataElement Required Properties

- `name`
- `definition`
- `dataType`
- `semanticType`
- `sensitivity`
- `allowedValues`
- `validationRules`
- `source`
- `owner`

## Metadata

Metadata is data about a data asset.

### Metadata Types

- Descriptive metadata
- Structural metadata
- Administrative metadata
- Technical metadata
- Governance metadata
- Quality metadata
- Usage metadata
- Provenance metadata
- Operational metadata

## Schema

A Schema formally defines the structure, fields, constraints, types, and validation rules for data or metadata.

### Schema Relationships

- `describes` DataAsset
- `defines` DataElement
- `validates` DataRecord
- `versionedAs` SchemaVersion
- `mappedTo` ExternalSchema
- `publishedIn` SchemaRegistry

## Provenance

Provenance records the origin and history of data.

### Provenance Must Capture

- Source
- Creator
- Collection method
- Creation time
- Transformation history
- Responsible actors
- Evidence
- License or usage terms
- Confidence

## Lineage

Lineage traces how data moves and changes over time.

### Lineage Relationships

- `sourceAsset` DataAsset
- `targetAsset` DataAsset
- `transformedBy` Transformation
- `executedBy` Actor
- `executedAt` Timestamp
- `producedVersion` Version
- `usedInput` DataAsset
- `producedOutput` DataAsset

## DataQuality

DataQuality measures whether data is fit for its intended use.

### Quality Dimensions

- Accuracy
- Completeness
- Consistency
- Timeliness
- Validity
- Uniqueness
- Reliability
- Availability
- Usability
- Explainability

## DataGovernance

DataGovernance defines how data is owned, accessed, protected, used, shared, published, retained, and retired.

### Governance Controls

- Ownership
- Stewardship
- Classification
- Access control
- Consent
- Privacy
- Security
- Retention
- Licensing
- Audit
- Approval
- Publication review
- Risk review

## DataAccess

DataAccess defines who or what may use data, for what purpose, under which conditions.

### Access Relationship

```text
Subject --requests--> Action --on--> DataAsset --under--> Policy --with--> Context
```

### Required Access Context

- Subject identity
- Purpose
- Role
- Organization
- Jurisdiction
- Data classification
- Consent status
- Policy decision
- Time
- Environment
- Risk score

## DataUsage

DataUsage records how data is consumed.

### Usage Types

- Search
- View
- Query
- Download
- API call
- Dashboard use
- Model training
- Model inference
- Report generation
- Publication
- Decision support
- Agentic action

## DataDecision

A DataDecision is a decision that depends on data.

### DataDecision Must Capture

- Decision maker
- Data used
- Data version
- Evidence
- Assumptions
- Policy constraints
- Confidence
- Outcome
- Review status

## Actors Around Data

Actors exist in relation to data.

### Actor Roles

- DataOwner
- DataSteward
- DataProducer
- DataConsumer
- DataPublisher
- DataReviewer
- DataCustodian
- DataProcessor
- DataController
- DataSubject
- Agent
- System
- Organization

## Agents Around Data

An Agent is a governed actor that may assist with data work.

### Agent Data Responsibilities

- Discover data
- Classify data
- Validate data
- Enrich metadata
- Map schemas
- Detect quality issues
- Generate documentation
- Recommend governance controls
- Support decisions
- Execute approved workflows

Agents are not the anchor. Data is the anchor. Agents must remain governed actors operating around data assets.

## Canonical Data Relationships

```text
DataAsset ownedBy Actor
DataAsset stewardedBy Actor
DataAsset sourcedFrom DataSource
DataAsset describedBy Metadata
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

## Lifecycle States

### DataAsset Lifecycle

- Draft
- Proposed
- Registered
- Validated
- Active
- Published
- Deprecated
- Archived
- Retired
- Deleted

### Dataset Version Lifecycle

- Created
- Validated
- Approved
- Published
- Superseded
- Revoked
- Archived

### Policy Lifecycle

- Draft
- Reviewed
- Approved
- Active
- Superseded
- Deprecated
- Retired

## Minimum Viable Data Asset Card

Every governed data asset must have a card.

```yaml
id: string
type: DataAsset
name: string
description: string
owner: string
steward: string
source: string
schema: string
classification: string
license: string
accessPolicy: string
qualityProfile: string
provenance: string
lineage: string
lifecycleState: string
version: string
createdAt: datetime
updatedAt: datetime
```

## Validation Rules

1. Every DataAsset must have an owner.
2. Every DataAsset must have provenance.
3. Every Dataset must have a schema or documented schema exception.
4. Every published Dataset must have a license or usage terms.
5. Every DataProduct must define intended consumers.
6. Every sensitive DataAsset must have an access policy.
7. Every transformation must produce lineage.
8. Every access event must be auditable.
9. Every agent action on data must be policy-evaluated.
10. Every decision using data must reference the data version used.

## Relationship to Glossary

The glossary defines the words. This ontology defines the data-centered structure behind those words.

## Status

Draft. Canonical after governance review.
