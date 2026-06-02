# OpenDataWorld Canonical Data Taxonomy

This taxonomy defines canonical classification values for OpenDataWorld data assets.

The taxonomy is data-first. Every dataset, data product, source, schema, API, model, report, index, workflow, and agentic data action should be classified using controlled values where applicable.

## Purpose

The taxonomy makes data assets easier to discover, govern, compare, route, protect, evaluate, publish, and reuse.

## Taxonomy Principles

1. Data is the anchor.
2. Classification must support governance and discovery.
3. Taxonomy values must be stable, versioned, and auditable.
4. Open standards should be preferred where suitable.
5. Domain-specific taxonomies may extend this canonical taxonomy.
6. Sensitive data must never be left unclassified.
7. Classification should be machine-readable and human-understandable.

## Top-Level Classification Dimensions

```text
DataAsset
├── Domain
├── DataAssetType
├── DataSourceType
├── DataFormat
├── DataStructure
├── DataSensitivity
├── DataAccessLevel
├── DataQualityTier
├── DataLifecycleState
├── DataFreshnessClass
├── DataUsageClass
├── DataLicenseClass
├── DataTrustLevel
├── DataCriticality
├── GeographicScope
├── TemporalScope
├── GovernanceScope
└── PublicationStatus
```

## Domain

```text
Government
Healthcare
Finance
Education
Agriculture
Climate
Energy
Transportation
Retail
Manufacturing
Telecommunications
Media
Research
Legal
RealEstate
Employment
PublicSafety
Environment
SocialImpact
Technology
General
```

## DataAssetType

```text
Dataset
DataProduct
DataSource
DataElement
DataRecord
DataTable
DataFile
DataStream
DataAPI
DataIndex
DataView
DataCatalog
DataSchema
DataModel
DataReport
DataDashboard
DataNotebook
DataPipeline
KnowledgeGraph
Ontology
Taxonomy
Glossary
MetadataRecord
```

## DataSourceType

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

## DataFormat

```text
JSON
JSONLD
CSV
TSV
XML
YAML
Parquet
Avro
ORC
SQL
RDF
Turtle
GeoJSON
Shapefile
PDF
HTML
Markdown
PlainText
Image
Audio
Video
Binary
Other
```

## DataStructure

```text
Structured
SemiStructured
Unstructured
Graph
TimeSeries
Geospatial
Vector
Multimodal
EventBased
Hierarchical
Relational
```

## DataSensitivity

```text
Public
Open
Internal
Confidential
Restricted
Secret
PersonalData
SensitivePersonalData
FinancialData
HealthData
GovernmentRestrictedData
ChildData
LocationData
BiometricData
CredentialData
Unknown
```

`Unknown` is allowed only during ingestion and must be resolved before publication or broad access.

## DataAccessLevel

```text
OpenAccess
PublicReadOnly
RegisteredUserAccess
OrganizationInternal
RoleRestricted
PurposeRestricted
ConsentRequired
ApprovalRequired
ContractRequired
RegulatedAccess
AdminOnly
NoAccess
```

## DataQualityTier

```text
Unassessed
Bronze
Silver
Gold
Platinum
Certified
```

## DataLifecycleState

```text
Draft
Proposed
Registered
Ingested
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

## DataFreshnessClass

```text
Realtime
NearRealtime
Hourly
Daily
Weekly
Monthly
Quarterly
Annual
Historical
Static
Unknown
```

## DataUsageClass

```text
Discovery
Research
Reporting
Dashboarding
Analytics
OperationalUse
DecisionSupport
ModelTraining
ModelInference
Automation
Publication
RegulatoryReporting
Audit
Benchmarking
Testing
Archival
```

## DataLicenseClass

```text
OpenLicense
PublicDomain
CreativeCommons
GovernmentOpenDataLicense
Proprietary
InternalUseOnly
ContractRestricted
ResearchOnly
NonCommercial
ConsentBound
Regulated
Unknown
```

## DataTrustLevel

```text
Unknown
Low
Medium
High
Verified
Certified
Revoked
```

## DataCriticality

```text
Low
Medium
High
MissionCritical
SafetyCritical
FinanciallyCritical
LegallyCritical
NationallyCritical
```

## GeographicScope

```text
Global
Region
Country
State
District
City
Locality
Address
Coordinates
NotApplicable
```

## TemporalScope

```text
PointInTime
TimeRange
HistoricalSeries
Forecast
RealtimeWindow
Snapshot
VersionedHistory
NotApplicable
```

## GovernanceScope

```text
Individual
Team
Department
Organization
MultiOrganization
Public
Community
Jurisdiction
RegulatedSector
Global
```

## PublicationStatus

```text
NotPublished
DraftPublication
UnderReview
ApprovedForPublication
Published
Updated
Withdrawn
Archived
Removed
```

## Required Classification by Asset Type

### Dataset

- Domain
- DataAssetType
- DataFormat
- DataStructure
- DataSensitivity
- DataAccessLevel
- DataQualityTier
- DataLifecycleState
- DataFreshnessClass
- DataLicenseClass
- DataTrustLevel

### DataProduct

- Domain
- DataAssetType
- DataSensitivity
- DataAccessLevel
- DataQualityTier
- DataCriticality
- DataUsageClass
- DataTrustLevel
- DataLifecycleState

### DataSource

- Domain
- DataSourceType
- DataSensitivity
- DataAccessLevel
- DataFreshnessClass
- DataTrustLevel
- GovernanceScope

## Governance Rules

1. Every registered data asset must have a DataAssetType.
2. Every published data asset must have a DataSensitivity value other than Unknown.
3. Every published dataset must have a DataLicenseClass value other than Unknown.
4. Every sensitive data asset must have a DataAccessLevel that is not OpenAccess.
5. Every mission-critical data product must have at least Gold quality tier.
6. Every agentic use of data must declare DataUsageClass.
7. Every data product must declare DataCriticality.
8. Every data asset with PersonalData or SensitivePersonalData must have consent and privacy policy references where required.
9. Every public asset must have a publication status.
10. Every taxonomy extension must define ownership, version, and mapping to the canonical taxonomy.

## Example Classification Card

```yaml
id: odwf:dataset:example-public-health-facilities
type: Dataset
name: Public Health Facilities Registry
domain: Healthcare
dataAssetType: Dataset
dataSourceType: GovernmentPortal
dataFormat: CSV
dataStructure: Structured
dataSensitivity: Public
dataAccessLevel: OpenAccess
dataQualityTier: Silver
dataLifecycleState: Published
dataFreshnessClass: Monthly
dataUsageClass:
  - Discovery
  - Analytics
  - DecisionSupport
dataLicenseClass: GovernmentOpenDataLicense
dataTrustLevel: Verified
dataCriticality: High
geographicScope: Country
temporalScope: Snapshot
governanceScope: Public
publicationStatus: Published
```

## Status

Draft. Canonical after governance review.
