# OpenDataWorld Provenance Model

OpenDataWorld treats provenance as a first-class foundation concept.

Provenance explains the origin, history, custody, transformation, review, publication, and evidence behind data and analytics assets.

## Provenance North Star

```text
Every trusted data asset must be able to explain where it came from, how it changed, who handled it, and what evidence supports it.
```

## Core Assertions

1. Provenance is required for trust.
2. Provenance is required for accountability.
3. Provenance is required for reproducibility.
4. Provenance is required for responsible AI use.
5. Provenance must be temporal.
6. Provenance must reference identities.
7. Provenance must preserve evidence.
8. Provenance must survive publication, transformation, and reuse.
9. Provenance must distinguish source, creator, collector, transformer, reviewer, approver, publisher, and consumer.
10. Provenance must be queryable.

## Provenance Scope

```text
Provenance
├── Origin
├── Source
├── Creator
├── Collector
├── Publisher
├── Transformer
├── Reviewer
├── Approver
├── Evidence
├── Method
├── Tool
├── System
├── Agent
├── ChainOfCustody
├── TransformationHistory
├── PublicationHistory
└── UsageHistory
```

## Provenance Record

Every provenance record should include:

```yaml
id: string
type: ProvenanceRecord
subject: string
subjectType: string
origin: string
source: string
creator: string
collector: string
publisher: string
method: string
tools:
  - string
systems:
  - string
agents:
  - string
evidence:
  - string
createdAt: datetime
collectedAt: datetime
recordedAt: datetime
validFrom: datetime
validTo: datetime
confidence: number
limitations:
  - string
version: string
```

## Provenance Actors

```text
Creator
Collector
Provider
SourceOwner
Transformer
Reviewer
Approver
Publisher
Consumer
Agent
System
Organization
```

## Origin

Origin identifies where a data asset first came from.

Examples:

```text
Government portal
Research repository
Enterprise database
Sensor network
Manual survey
Web crawl
Application log
Public registry
Third-party provider
Generated synthetic source
```

## Source

A source is the immediate place from which data was collected or referenced.

A source must preserve:

```yaml
sourceId: string
sourceType: string
sourceName: string
sourceOwner: string
sourceUri: string
accessedAt: datetime
sourceVersion: string
reliabilityProfile: string
```

## Collection Method

Collection method explains how data was obtained.

```text
ManualEntry
FileUpload
APIExtraction
DatabaseQuery
WebCrawl
SensorCollection
SurveyCollection
StreamCapture
BatchImport
Generated
Derived
ThirdPartyTransfer
```

## Transformation Provenance

Every transformation must preserve input, operation, actor, tool, output, and time.

```yaml
transformationId: string
inputAssets:
  - id: string
    version: string
outputAssets:
  - id: string
    version: string
transformationType: string
method: string
tool: string
system: string
agent: string
executedBy: string
executedAt: datetime
parameters: object
qualityChecks:
  - string
```

## Chain of Custody

Chain of custody records who or what handled an asset over time.

```yaml
custodyEventId: string
asset: string
handler: string
handlerType: string
action: string
startedAt: datetime
endedAt: datetime
evidence:
  - string
policyDecision: string
```

## Evidence

Evidence supports provenance claims.

Examples:

```text
Source URL
API response hash
File checksum
Upload receipt
Database query log
Approval record
Publication record
Digital signature
Credential
Audit event
Review note
```

## Provenance and AI

AI-generated, AI-assisted, or agent-transformed data must be clearly marked.

Required fields:

```yaml
aiInvolvement: string
agentIdentity: string
modelIdentity: string
promptOrInstructionRef: string
humanReviewStatus: string
sourceDataRefs:
  - string
```

Allowed AI involvement values:

```text
None
Assisted
Generated
Transformed
Summarized
Classified
Enriched
Validated
Reviewed
```

## Provenance and Publication

Published data must preserve:

- Publisher identity
- Publication time
- Publication version
- License
- Review status
- Approval record
- Source reference
- Withdrawal history where applicable

## Provenance Validation Rules

1. Every published dataset must have provenance.
2. Every transformed asset must reference input and output assets.
3. Every provenance record must reference at least one identity or source.
4. Every AI-assisted output must declare AI involvement.
5. Every provenance record must include recorded time.
6. Every evidence-backed claim must reference evidence.
7. Every high-trust asset must have source and method documented.
8. Every provenance record used in a decision must be preserved with the decision record.
9. Every chain-of-custody event must be temporal.
10. Every provenance limitation must be disclosed where known.

## Minimum Viable Provenance Baseline

For the first operational platform, support:

1. Source record
2. Creator or publisher identity
3. Collection method
4. Recorded timestamp
5. Evidence link
6. Transformation input/output references
7. AI involvement flag
8. License reference
9. Publication record
10. Confidence and limitations

## Status

Draft. Canonical after governance review.
