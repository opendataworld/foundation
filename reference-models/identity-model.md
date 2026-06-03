# OpenDataWorld Identity Model

OpenDataWorld treats identity as a first-class foundation concept.

Every important actor, asset, system, policy, workflow, service, dataset, and agent must be identifiable across time, systems, organizations, and governance contexts.

## Identity North Star

```text
Everything that can own, access, govern, produce, transform, publish, consume, decide, or act on data must have identity.
```

## Core Assertions

1. Identity enables accountability.
2. Identity enables trust.
3. Identity enables access control.
4. Identity enables provenance.
5. Identity enables auditability.
6. Identity must persist across lifecycle changes.
7. Identity must support aliases and external identifiers.
8. Identity must distinguish human, organization, system, asset, and agent identities.
9. Identity must be time-aware.
10. Identity must support verification where trust-sensitive.

## Identity Scope

```text
Identity
├── HumanIdentity
├── OrganizationIdentity
├── TeamIdentity
├── SystemIdentity
├── ApplicationIdentity
├── ServiceIdentity
├── AgentIdentity
├── AssetIdentity
├── DatasetIdentity
├── DataProductIdentity
├── APIIdentity
├── SchemaIdentity
├── PolicyIdentity
├── WorkflowIdentity
└── ExternalIdentity
```

## Identity Record

Every identity record should include:

```yaml
id: string
type: Identity
identityType: string
subject: string
canonicalId: string
aliases:
  - string
externalIds:
  - system: string
    value: string
    url: string
issuer: string
verificationStatus: string
trustLevel: string
lifecycleState: string
validFrom: datetime
validTo: datetime
createdAt: datetime
updatedAt: datetime
```

## Identifier Types

```text
Identifier
├── CanonicalIdentifier
├── LocalIdentifier
├── ExternalIdentifier
├── PersistentIdentifier
├── DecentralizedIdentifier
├── EmailIdentifier
├── UsernameIdentifier
├── URIIdentifier
├── DomainIdentifier
├── RegistryIdentifier
├── DatasetIdentifier
├── VersionIdentifier
└── ContentHashIdentifier
```

## Canonical Identifier

A canonical identifier is the primary governed identifier for an object inside OpenDataWorld.

### Rules

1. It must be stable.
2. It must not depend on display name.
3. It must survive renaming.
4. It must support lifecycle transitions.
5. It must be resolvable by the registry where applicable.

Example:

```text
odw:dataset:public-health-facilities
odw:policy:data-access-public-v1
odw:agent:metadata-enrichment-agent
```

## Identity Subject Types

### Human Identity

Represents a person.

Used for:

- Data owner
- Data steward
- Reviewer
- Approver
- Analyst
- Researcher
- Consumer
- Publisher
- Auditor

### Organization Identity

Represents an institution, company, government agency, nonprofit, community, research body, or other organization.

Used for:

- Ownership
- Publishing
- Licensing
- Contracting
- Governance
- Accountability

### Team Identity

Represents a group inside or across organizations.

Used for:

- Stewardship
- Platform operations
- Governance review
- Analytics ownership
- Support ownership

### System Identity

Represents a technical system that produces, stores, transforms, exposes, or consumes data.

Used for:

- Data sources
- Connectors
- Pipelines
- APIs
- Databases
- Applications
- Event systems

### Service Identity

Represents a platform or external service.

Used for:

- Registry service
- Catalog service
- Policy service
- Analytics service
- Agentic workflow service
- Search service

### Agent Identity

Represents an autonomous or semi-autonomous software actor.

An agent identity must declare:

```yaml
agentId: string
agentName: string
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
lifecycleState: string
```

### Asset Identity

Represents a governed asset.

Used for:

- Dataset
- Data product
- API
- Schema
- Model
- Report
- Dashboard
- Policy
- Workflow
- Knowledge asset

## Identity Relationships

```text
Identity represents Subject
Identity issuedBy Issuer
Identity verifiedBy Verifier
Identity belongsTo Organization
Identity memberOf Team
Identity owns Asset
Identity stewards DataAsset
Identity operates System
Identity publishes Dataset
Identity approves Decision
Identity executes Action
Identity accesses Resource
Identity supersedes Identity
Identity aliasedAs Identifier
```

## Verification Model

Identity verification establishes confidence that an identity represents the claimed subject.

### Verification States

```text
Unverified
SelfAsserted
EmailVerified
DomainVerified
OrganizationVerified
RegistryVerified
CredentialVerified
ManuallyVerified
Revoked
Expired
```

### Verification Record

```yaml
id: string
identity: string
verificationType: string
verifiedBy: string
verifiedAt: datetime
evidence:
  - string
status: string
expiresAt: datetime
```

## Trust and Identity

Identity is not the same as trust.

```text
Identity answers: who or what is this?
Trust answers: how much confidence should we place in it for this context?
```

Identity must feed trust scoring, but trust must remain contextual and evidence-backed.

## Lifecycle States

```text
Proposed
Active
Suspended
Deprecated
Merged
Split
Revoked
Archived
Deleted
```

## Alias and Merge Model

An identity may have aliases across systems.

### Alias Record

```yaml
id: string
canonicalIdentity: string
aliasType: string
aliasValue: string
sourceSystem: string
validFrom: datetime
validTo: datetime
confidence: number
provenance: object
```

### Merge Rules

1. Merging identities must preserve original identifiers.
2. Merge decisions must be auditable.
3. Merged identities must redirect to the canonical identity.
4. Conflicting evidence must be preserved.
5. Automated merges above risk threshold require human review.

## Identity and Access

Access decisions require identity.

```text
Subject Identity + Action + Resource Identity + Context + Policy → Access Decision
```

Every access record must preserve:

```yaml
subjectIdentity: string
resourceIdentity: string
action: string
purpose: string
policyVersion: string
decision: string
decidedAt: datetime
```

## Identity and Provenance

Provenance requires identity for:

- Creator
- Publisher
- Source
- Transformer
- Reviewer
- Approver
- Agent
- System
- Organization

## Identity and Agents

Agents must never act anonymously.

Every agent action must record:

```yaml
agentIdentity: string
operatorIdentity: string
action: string
resource: string
policyDecision: string
approvalReference: string
traceId: string
executedAt: datetime
```

## Identity and Assets

Data assets need identity because they are owned, governed, versioned, accessed, transformed, cited, published, and audited.

Every governed data asset identity must support:

- Stable ID
- Version IDs
- Source IDs
- External IDs
- Ownership relationship
- Stewardship relationship
- Provenance relationship
- Lineage relationship

## Minimum Viable Identity Baseline

For the first operational platform, support:

1. Canonical IDs for data assets
2. Canonical IDs for datasets
3. Canonical IDs for organizations
4. Canonical IDs for users
5. Canonical IDs for systems
6. Canonical IDs for agents
7. External identifiers
8. Ownership relationships
9. Stewardship relationships
10. Verification status
11. Lifecycle state
12. Access decision subject and resource identity

## Identity Validation Rules

1. Every governed object must have an `id`.
2. Every DataAsset must have a canonical identity.
3. Every owner must resolve to an identity.
4. Every steward must resolve to an identity.
5. Every agent must have an identity before acting.
6. Every access decision must reference subject and resource identities.
7. Every external identifier must declare source system.
8. Every verified identity must preserve verification evidence.
9. Every identity merge must be auditable.
10. Every revoked identity must not be used for new access grants.

## Status

Draft. Canonical after governance review.
