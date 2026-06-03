# OpenDataWorld Registry Buckets and Namespaces

OpenDataWorld uses registries to make governed objects official, discoverable, versioned, accountable, and interoperable.

This document defines the canonical registry buckets and namespaces that separate foundation meaning, specifications, graph contracts, platform services, products, solutions, data assets, analytics assets, agents, legal rights, and brand assets.

## Core Principle

```text
Everything official must be registered in the right namespace.
Everything registered must have identity, owner, lifecycle, version, license, provenance, and governance context where applicable.
```

## Registry Bucket Map

```text
OpenDataWorld Registry
├── Foundation Registry
├── Specification Registry
├── Graph Registry
├── Schema Registry
├── Architecture Registry
├── Governance Registry
├── Platform Registry
├── Product Registry
├── Solution Registry
├── Data Registry
├── Analytics Registry
├── Agent Registry
├── Legal Registry
├── Brand Registry
└── Community Registry
```

## Namespace Map

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

## 1. Foundation Registry

Namespace:

```text
odw.foundation.*
```

Purpose:

Registers canonical foundation concepts and models.

Objects:

```text
GlossaryTerm
OntologyClass
TaxonomyClass
MetaModel
ReferenceModel
DecisionIntelligenceModel
NamespaceModel
```

Examples:

```text
odw.foundation.model.identity
odw.foundation.model.trust
odw.foundation.model.provenance
odw.foundation.model.lineage
odw.foundation.model.knowledgeGraph
odw.foundation.model.decisionIntelligence
```

## 2. Specification Registry

Namespace:

```text
odw.spec.*
```

Purpose:

Registers machine-readable contracts.

Objects:

```text
JSONSchema
YAMLContract
JSONLDContext
ValidationRule
APIContract
EventContract
GraphContract
```

Examples:

```text
odw.spec.schema.dataset
odw.spec.schema.policy
odw.spec.graph.nodeTypes
odw.spec.graph.edgeTypes
odw.spec.graph.constraints
odw.spec.context.opendataworld
```

## 3. Graph Registry

Namespace:

```text
odw.graph.*
```

Purpose:

Registers graph nodes, edge types, constraints, projections, example graphs, and mappings.

Objects:

```text
GraphNodeType
GraphEdgeType
GraphConstraint
GraphValidationRule
GraphExample
GraphProjection
GraphMapping
```

Examples:

```text
odw.graph.node.Dataset
odw.graph.edge.governedBy
odw.graph.constraint.PublishedDatasetMustBeComplete
odw.graph.example.healthDataset
```

## 4. Schema Registry

Namespace:

```text
odw.schema.*
```

Purpose:

Registers object schemas and versions.

Objects:

```text
DatasetSchema
DataProductSchema
PolicySchema
TrustAssessmentSchema
MetricSchema
InsightSchema
DecisionSchema
OutcomeSchema
AgentSchema
```

Examples:

```text
odw.schema.Dataset.v1
odw.schema.DataProduct.v1
odw.schema.Policy.v1
odw.schema.Decision.v1
```

## 5. Architecture Registry

Namespace:

```text
odw.architecture.*
```

Purpose:

Registers reference architectures and implementation guidance.

Objects:

```text
ReferencePlatformArchitecture
ReferenceDataArchitecture
ReferenceGovernanceArchitecture
ReferenceAnalyticsArchitecture
ReferenceAgentArchitecture
ReferenceDeploymentArchitecture
```

Examples:

```text
odw.architecture.platform.reference
odw.architecture.data.reference
odw.architecture.governance.reference
odw.architecture.analytics.reference
odw.architecture.agent.reference
```

## 6. Governance Registry

Namespace:

```text
odw.governance.*
```

Purpose:

Registers policies, controls, approvals, audit rules, risk rules, and compliance mappings.

Objects:

```text
Policy
Rule
Control
Approval
AccessDecision
AuditEvent
RiskAssessment
ComplianceObligation
Exception
```

Examples:

```text
odw.governance.policy.openDataAccess
odw.governance.control.publishedDatasetCompleteness
odw.governance.approval.publicationReview
odw.governance.audit.agentAction
```

## 7. Platform Registry

Namespace:

```text
odw.platform.*
```

Purpose:

Registers runtime services, APIs, stores, workflows, and operational capabilities.

Objects:

```text
Service
API
Database
Worker
Workflow
Connector
Queue
SearchIndex
GraphStore
PolicyEngine
RuntimeComponent
```

Examples:

```text
odw.platform.service.registry
odw.platform.service.catalog
odw.platform.service.governance
odw.platform.service.analytics
odw.platform.service.agent
```

## 8. Product Registry

Namespace:

```text
odw.product.*
```

Purpose:

Registers named product modules.

Objects:

```text
Product
ProductModule
ProductCapability
ProductPackage
ProductPlan
```

Examples:

```text
odw.product.registry
odw.product.catalog
odw.product.governance
odw.product.quality
odw.product.lineage
odw.product.knowledgeGraph
odw.product.analytics
odw.product.decisionIntelligence
odw.product.agenticWorkflows
```

## 9. Solution Registry

Namespace:

```text
odw.solution.*
```

Purpose:

Registers packaged solutions for domains and use cases.

Objects:

```text
Solution
SolutionPackage
UseCase
ImplementationPattern
ReferenceWorkflow
```

Examples:

```text
odw.solution.openDataPortal
odw.solution.publicDataExchange
odw.solution.enterpriseDataMarketplace
odw.solution.dataProductPlatform
odw.solution.governanceWorkbench
odw.solution.aiReadyDataFoundation
odw.solution.agenticDataOperations
```

## 10. Data Registry

Namespace:

```text
odw.data.*
```

Purpose:

Registers data assets, datasets, sources, elements, distributions, and data products.

Objects:

```text
DataAsset
Dataset
DataProduct
DataSource
DataElement
DataDistribution
MetadataRecord
QualityProfile
ProvenanceRecord
LineageRecord
```

Examples:

```text
odw.data.dataset.publicHealthFacilities
odw.data.product.healthcareAccess
odw.data.source.governmentPortal
odw.data.element.facilityId
```

## 11. Analytics Registry

Namespace:

```text
odw.analytics.*
```

Purpose:

Registers analytical assets, metrics, insights, decisions, outcomes, and value records.

Objects:

```text
Metric
KPI
Report
Dashboard
Benchmark
Forecast
Insight
Recommendation
Decision
Outcome
Value
Learning
ImprovementAction
```

Examples:

```text
odw.analytics.metric.facilityCoverageRate
odw.analytics.insight.facilityAccessGap
odw.analytics.decision.facilityPlanning
odw.analytics.outcome.planningReview
```

## 12. Agent Registry

Namespace:

```text
odw.agent.*
```

Purpose:

Registers governed agents, skills, tools, actions, approvals, evaluations, and trust assessments.

Objects:

```text
Agent
AgentIdentity
Skill
Tool
Action
Task
Plan
Memory
Evaluation
AgentTrustAssessment
AgentAuditEvent
```

Examples:

```text
odw.agent.discovery
odw.agent.metadataEnrichment
odw.agent.classification
odw.agent.analytics
odw.agent.governance
odw.agent.decisionSupport
```

## 13. Legal Registry

Namespace:

```text
odw.legal.*
```

Purpose:

Registers legal, IP, copyright, licensing, contributor, and usage rights records.

Objects:

```text
CopyrightRecord
LicenseRecord
NoticeRecord
ContributorAgreement
PatentPolicy
TrademarkPolicy
TermsOfUse
DataLicense
```

Examples:

```text
odw.legal.license.apache2
odw.legal.license.ccBy4
odw.legal.license.cc0
odw.legal.notice.foundation
odw.legal.copyright.contributors
```

## 14. Brand Registry

Namespace:

```text
odw.brand.*
```

Purpose:

Registers names, marks, taglines, logos, and brand usage rules.

Objects:

```text
BrandName
ProductName
SolutionName
Logo
Tagline
DomainName
BrandUsageRule
```

Examples:

```text
odw.brand.openDataWorld
odw.brand.foundation
odw.brand.platform
odw.brand.tagline.dataAnalyticsSolutionsForEveryone
```

## 15. Community Registry

Namespace:

```text
odw.community.*
```

Purpose:

Registers community governance, working groups, maintainers, contributors, and public participation models.

Objects:

```text
Contributor
Maintainer
WorkingGroup
GovernanceBody
CommunityPolicy
CodeOfConduct
ContributionGuide
```

Examples:

```text
odw.community.workingGroup.graph
odw.community.workingGroup.schemas
odw.community.maintainer.foundation
```

## Universal Registry Record

Every registry record should include:

```yaml
id: string
namespace: string
type: string
name: string
description: string
owner: string
steward: string
license: string
version: string
lifecycleState: string
createdAt: datetime
updatedAt: datetime
provenance: string
links:
  - string
```

## Required Namespace Fields

Every namespace should define:

```yaml
namespace: string
owner: string
purpose: string
allowedObjectTypes:
  - string
license: string
extensionPolicy: string
lifecycleState: string
version: string
```

## Registry Governance Rules

1. Every official object must be registered in exactly one primary namespace.
2. Cross-namespace references must use canonical IDs.
3. Foundation namespaces must not depend on product namespaces.
4. Product namespaces may depend on foundation, specification, graph, schema, and architecture namespaces.
5. Solution namespaces may depend on product and platform namespaces.
6. Legal and brand namespaces must be governed separately from technical namespaces.
7. Trade-secret or private implementation details must not be placed in open foundation registries.
8. Every registry record must declare license or rights status.
9. Every registry record must declare lifecycle state.
10. Every registry record must preserve provenance where applicable.

## Recommended Repository Buckets

```text
registry/
├── registry-buckets.md
├── foundation.registry.yaml
├── spec.registry.yaml
├── graph.registry.yaml
├── schema.registry.yaml
├── architecture.registry.yaml
├── governance.registry.yaml
├── product.registry.yaml
├── solution.registry.yaml
├── data.registry.yaml
├── analytics.registry.yaml
├── agent.registry.yaml
├── legal.registry.yaml
├── brand.registry.yaml
└── community.registry.yaml
```

## Status

Draft. Canonical after governance review.
