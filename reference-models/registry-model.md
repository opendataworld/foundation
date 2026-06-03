# OpenDataWorld Registry Model

OpenDataWorld treats registries as governed systems of record for data and analytics solutions as a service.

A registry makes important things identifiable, discoverable, governable, versioned, auditable, and reusable.

## Registry North Star

```text
Every governed object should have a canonical registry record that explains what it is, who owns it, how it is governed, whether it can be trusted, and how it may be used.
```

## Core Assertion

```text
Catalogs help people find things.
Registries make things official.
Knowledge graphs connect things.
```

## Registry Scope

```text
Registry
├── Identity Registry
├── Organization Registry
├── Person and Team Registry
├── System Registry
├── Service Registry
├── Data Asset Registry
├── Dataset Registry
├── Data Product Registry
├── Data Source Registry
├── Schema Registry
├── Data Element Registry
├── API Registry
├── Policy Registry
├── Rule Registry
├── Trust Registry
├── Provenance Registry
├── Lineage Registry
├── Evidence Registry
├── Analytics Registry
├── Metrics Registry
├── Insight Registry
├── Decision Registry
├── Outcome Registry
├── Agent Registry
├── Tool Registry
└── Workflow Registry
```

## Registry Record

Every registry record should include:

```yaml
id: string
type: RegistryRecord
recordType: string
subject: string
subjectType: string
canonicalId: string
name: string
description: string
owner: string
steward: string
classification: object
lifecycleState: string
trust: string
provenance: string
lineage: string
policyRefs:
  - string
schemaRefs:
  - string
links:
  - string
version: string
createdAt: datetime
updatedAt: datetime
```

## Registry Card Pattern

A registry card is the human-readable and machine-readable summary of a governed object.

```text
Registry Record = canonical system record
Registry Card = consumable representation of the record
```

### Minimum Registry Card

```yaml
id: string
type: string
name: string
description: string
owner: string
steward: string
status: string
classification: object
trustLevel: string
qualityTier: string
accessLevel: string
license: string
version: string
lastUpdated: datetime
```

## Data Asset Registry

The Data Asset Registry stores canonical records for all data assets.

### Supported Record Types

```text
Dataset
DataProduct
DataSource
DataElement
DataTable
DataFile
DataStream
DataAPI
DataIndex
DataView
Report
Dashboard
KnowledgeGraph
MetadataRecord
```

### Data Asset Registry Required Fields

```yaml
id: string
canonicalId: string
assetType: string
name: string
description: string
owner: string
steward: string
source: string
schema: string
classification: object
accessPolicy: string
license: string
qualityProfile: string
trustAssessment: string
provenance: string
lineage: string
lifecycleState: string
version: string
```

## Dataset Registry

The Dataset Registry stores canonical dataset records, versions, distributions, schemas, provenance, quality, and publication status.

### Dataset Registry Required Fields

```yaml
id: string
datasetId: string
name: string
description: string
owner: string
steward: string
source: string
schema: string
distributions:
  - string
versions:
  - string
classification: object
license: string
accessLevel: string
qualityTier: string
trustLevel: string
publicationStatus: string
provenance: string
lineage: string
```

## Data Product Registry

The Data Product Registry stores reusable data products with owners, consumers, contracts, SLOs, APIs, and quality expectations.

### Data Product Registry Required Fields

```yaml
id: string
dataProductId: string
name: string
description: string
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
slo: object
qualityExpectations: object
accessPolicy: string
supportModel: string
changePolicy: string
lifecycleState: string
```

## Schema Registry

The Schema Registry stores schema definitions, versions, mappings, validation rules, and compatibility status.

### Schema Registry Required Fields

```yaml
id: string
schemaId: string
name: string
description: string
schemaType: string
version: string
status: string
owner: string
appliesTo:
  - string
contentHash: string
compatibility: string
validationRules:
  - string
```

## Policy Registry

The Policy Registry stores governed policy records and versions.

### Policy Registry Required Fields

```yaml
id: string
policyId: string
name: string
description: string
policyType: string
appliesTo:
  - string
rules:
  - string
effect: string
owner: string
approver: string
version: string
lifecycleState: string
effectiveFrom: datetime
effectiveTo: datetime
```

## Agent Registry

The Agent Registry stores governed agent records.

### Agent Registry Required Fields

```yaml
id: string
agentId: string
name: string
description: string
owner: string
operator: string
purpose: string
allowedActions:
  - string
allowedTools:
  - string
allowedDataClasses:
  - string
riskLevel: string
approvalRequirements:
  - string
trustAssessment: string
lifecycleState: string
```

## Trust Registry

The Trust Registry stores trust assessments and trust history.

### Trust Registry Required Fields

```yaml
id: string
trustAssessmentId: string
subject: string
subjectType: string
trustContext: string
trustScore: number
trustLevel: string
method: string
evidence:
  - string
calculatedAt: datetime
validUntil: datetime
reviewStatus: string
```

## Evidence Registry

The Evidence Registry stores records that support claims, decisions, trust assessments, quality results, and audits.

### Evidence Registry Required Fields

```yaml
id: string
evidenceId: string
evidenceType: string
source: string
claim: string
supports: string
collectedAt: datetime
collector: string
confidence: number
provenance: string
```

## Decision Registry

The Decision Registry stores decisions and their data, evidence, constraints, alternatives, outcomes, and review status.

### Decision Registry Required Fields

```yaml
id: string
decisionId: string
decisionType: string
madeBy: string
madeAt: datetime
basedOnDataAssets:
  - string
basedOnEvidence:
  - string
constraints:
  - string
alternatives:
  - string
selectedOption: string
confidence: number
outcome: string
reviewStatus: string
```

## Registry Lifecycle

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

## Registry Governance Rules

1. Every registry record must have an identifier.
2. Every registry record must have a type.
3. Every official record must have an owner.
4. Every data asset record must have classification.
5. Every published dataset record must have provenance.
6. Every sensitive data asset record must have an access policy.
7. Every registry record must preserve lifecycle state.
8. Every registry record must be versioned where changes affect governance, access, trust, or usage.
9. Every registry record used in a decision must be preserved with that decision context.
10. Every registry deletion must preserve auditability unless legally required otherwise.

## Registry Query Patterns

```text
Find all published datasets in Healthcare with Verified trust.
Find data products owned by Organization X.
Find sensitive assets without access policy.
Find schemas superseded in the last 90 days.
Find agents allowed to access Restricted data.
Find decisions based on Dataset version 1.2.
Find policies expiring this quarter.
Find all assets without steward assignment.
```

## Minimum Viable Registry Baseline

For the first operational platform, support:

1. Data Asset Registry
2. Dataset Registry
3. Data Source Registry
4. Schema Registry
5. Policy Registry
6. Identity Registry
7. Trust Registry
8. Provenance Registry
9. Lineage Registry
10. Decision Registry
11. Agent Registry
12. Audit-backed lifecycle changes

## Relationship to Other Foundation Models

```text
Identity Model defines persistent identity.
Trust Model defines confidence.
Provenance Model defines origin and custody.
Lineage Model defines flow and dependency.
Knowledge Graph Model connects records.
Registry Model makes records official, governed, versioned, and discoverable.
```

## Status

Draft. Canonical after governance review.
