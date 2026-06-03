# OpenDataWorld Operating Model

OpenDataWorld provides data and analytics solutions as a service for everyone.

This operating model defines how people, organizations, systems, services, and governed agents work together to create, govern, publish, consume, analyze, and improve data and analytics services.

## Operating Model North Star

```text
Right data, right context, right access, right governance, right insight, right decision, right outcome.
```

## Core Operating Flow

```text
Producer
  ↓
Source
  ↓
Registry
  ↓
Stewardship
  ↓
Governance
  ↓
Quality and Trust
  ↓
Catalog and Discovery
  ↓
Access
  ↓
Analytics
  ↓
Insight
  ↓
Decision
  ↓
Action
  ↓
Outcome
  ↓
Learning and Improvement
```

## Operating Principle

Data must move through a governed value chain.

```text
Data is produced.
Data is registered.
Data is described.
Data is classified.
Data is governed.
Data is validated.
Data is trusted.
Data is published.
Data is consumed.
Data is analyzed.
Data informs decisions.
Decisions create actions.
Actions create outcomes.
Outcomes create learning.
Learning improves data and services.
```

## Primary Roles

```text
Data Producer
Data Source Owner
Data Owner
Data Steward
Data Custodian
Data Product Owner
Analytics Product Owner
Platform Operator
Governance Officer
Compliance Officer
Security Officer
Privacy Officer
Publisher
Reviewer
Approver
Auditor
Data Consumer
Analyst
Researcher
Developer
Decision Maker
Outcome Owner
AI Agent
Automation System
Community Contributor
```

## Role Definitions

### Data Producer

Creates or supplies data.

Responsibilities:

- Provide data to the platform
- Declare source context
- Support provenance capture
- Document generation or collection method
- Notify downstream users of material changes

### Data Source Owner

Owns the source system, database, file, API, stream, or external source from which data originates.

Responsibilities:

- Maintain source reliability
- Define source access constraints
- Support extraction and integration
- Provide operational metadata
- Communicate source changes

### Data Owner

Accountable for a data asset.

Responsibilities:

- Approve ownership record
- Define business purpose
- Approve access rules
- Approve publication where required
- Ensure policy compliance
- Own risk and value realization

### Data Steward

Responsible for day-to-day data quality, metadata, classification, and lifecycle management.

Responsibilities:

- Maintain metadata
- Classify data assets
- Review quality issues
- Maintain glossary alignment
- Manage lifecycle state
- Support consumers

### Data Custodian

Responsible for technical operation, storage, security, backup, and availability.

Responsibilities:

- Operate storage and infrastructure
- Ensure technical controls
- Maintain backups
- Support recovery
- Monitor availability

### Data Product Owner

Owns a reusable data product.

Responsibilities:

- Define intended consumers
- Define use cases
- Define quality expectations
- Define SLOs
- Manage roadmap
- Manage feedback and improvements

### Analytics Product Owner

Owns a reusable analytics asset such as a dashboard, report, metric, benchmark, or model.

Responsibilities:

- Define analytical purpose
- Define input data assets
- Maintain metric definitions
- Document assumptions
- Review outputs
- Track usage and value

### Platform Operator

Operates the OpenDataWorld platform and shared services.

Responsibilities:

- Maintain runtime services
- Manage deployments
- Monitor service health
- Manage incidents
- Maintain observability
- Support integrations

### Governance Officer

Defines and oversees governance policies and controls.

Responsibilities:

- Define governance rules
- Review exceptions
- Monitor policy compliance
- Approve governance workflows
- Maintain operating standards

### Compliance Officer

Ensures alignment with applicable laws, regulations, contracts, and institutional obligations.

Responsibilities:

- Review regulated data use
- Validate compliance controls
- Support audits
- Review evidence
- Track obligations

### Security Officer

Ensures data and platform security.

Responsibilities:

- Define security controls
- Review sensitive access
- Monitor threats
- Manage security incidents
- Support access reviews

### Privacy Officer

Ensures responsible use of personal and sensitive data.

Responsibilities:

- Review privacy impact
- Ensure consent references
- Define privacy controls
- Review purpose limitation
- Support data subject rights

### Publisher

Publishes data or analytics assets to intended audiences.

Responsibilities:

- Prepare publication record
- Ensure metadata completeness
- Ensure license clarity
- Route publication review
- Manage updates and withdrawals

### Reviewer

Reviews a data asset, policy, publication, access request, decision, or workflow.

Responsibilities:

- Evaluate evidence
- Check completeness
- Identify risks
- Recommend approval, rejection, or changes

### Approver

Makes formal approval decisions.

Responsibilities:

- Approve or reject requests
- Record decision rationale
- Ensure authority to approve
- Own approval accountability

### Auditor

Independently examines records, controls, evidence, and actions.

Responsibilities:

- Review audit trails
- Verify compliance
- Check evidence quality
- Report findings
- Recommend remediation

### Data Consumer

Uses data for a legitimate purpose.

Responsibilities:

- Use data according to policy
- Respect license and usage terms
- Report issues
- Preserve attribution where required
- Avoid unauthorized redistribution

### Analyst

Uses data to produce analysis, reports, dashboards, metrics, or insights.

Responsibilities:

- Reference input data versions
- Document assumptions
- Maintain analytical definitions
- Communicate limitations
- Support decision traceability

### Researcher

Uses or publishes data for research.

Responsibilities:

- Preserve provenance
- Cite datasets
- Respect license and consent
- Support reproducibility
- Publish methodology where appropriate

### Developer

Builds applications, APIs, integrations, automations, or tools using governed data services.

Responsibilities:

- Use approved interfaces
- Respect access policies
- Preserve auditability
- Handle data securely
- Avoid hidden data dependencies

### Decision Maker

Uses data, analytics, insights, and evidence to make decisions.

Responsibilities:

- Reference supporting data and evidence
- Document assumptions and constraints
- Record rationale for important decisions
- Track outcomes where appropriate

### Outcome Owner

Accountable for the result produced by a decision, action, service, or program.

Responsibilities:

- Define success metrics
- Track outcomes
- Review impact
- Feed learning back into improvement

### AI Agent

A governed software actor that assists with data and analytics work.

Responsibilities:

- Operate under identity
- Use approved tools
- Respect policies
- Preserve provenance
- Emit audit records
- Escalate when required
- Never bypass human approval gates

## Accountability Model

Every important data asset must have clear accountability.

```text
Data Asset
├── Accountable: Data Owner
├── Responsible: Data Steward
├── Technical Custodian: Data Custodian
├── Governance Oversight: Governance Officer
├── Security Oversight: Security Officer
├── Privacy Oversight: Privacy Officer when applicable
├── Consumers: Data Consumers
└── Outcome Accountability: Outcome Owner where applicable
```

## RACI Model

| Activity | Owner | Steward | Custodian | Governance | Security | Consumer | Agent |
|---|---|---|---|---|---|---|---|
| Register data asset | A | R | C | C | C | I | C |
| Classify data asset | A | R | C | C | C | I | C |
| Approve access | A | C | I | R | C | I | N/A |
| Maintain metadata | A | R | C | C | I | C | C |
| Run quality checks | A | R | C | C | I | I | C |
| Publish dataset | A | R | C | R | C | I | C |
| Consume data | I | C | I | I | I | R | C |
| Execute agent workflow | A | C | C | R | C | I | R |
| Audit action | I | C | C | R | C | I | I |

Legend:

- R = Responsible
- A = Accountable
- C = Consulted
- I = Informed
- N/A = Not applicable

## Operating Governance Gates

### Gate 1: Registration Gate

Before a data asset enters the registry:

- Owner must be known
- Source must be known
- Asset type must be classified
- Initial lifecycle state must be assigned

### Gate 2: Classification Gate

Before broader discovery:

- Sensitivity must be classified
- Access level must be assigned
- Domain must be assigned
- License status must be known or marked pending

### Gate 3: Quality Gate

Before trusted use:

- Schema must be available or exception recorded
- Validation status must be known
- Quality tier must be assigned
- Known limitations must be documented

### Gate 4: Access Gate

Before access is granted:

- Subject identity must be known
- Purpose must be declared
- Policy must be evaluated
- Approval must be captured where required
- Audit record must be emitted

### Gate 5: Publication Gate

Before publication:

- Metadata completeness must pass threshold
- License must be clear
- Provenance must be recorded
- Sensitivity must not be Unknown
- Publication approver must be recorded

### Gate 6: Agentic Action Gate

Before an agent acts on data:

- Agent identity must be known
- Tool permission must be checked
- Data access policy must be evaluated
- Risk must be assessed
- Human approval must be obtained where required
- Audit event must be emitted

## Operating Loops

### Data Asset Lifecycle Loop

```text
Create → Register → Classify → Validate → Approve → Publish/Use → Monitor → Improve → Deprecate → Archive/Retire
```

### Data Product Lifecycle Loop

```text
Identify Need → Package Data → Define Consumer → Define SLO → Govern Access → Publish → Monitor Usage → Improve → Version → Retire
```

### Analytics Lifecycle Loop

```text
Define Question → Select Data → Define Metrics → Analyze → Explain → Review → Publish → Track Decisions → Measure Outcome → Improve
```

### Governance Lifecycle Loop

```text
Define Policy → Review → Approve → Enforce → Monitor → Audit → Learn → Update
```

### Decision Intelligence Loop

```text
Context → Data → Evidence → Alternatives → Decision → Action → Outcome → Learning
```

## Human and Agent Collaboration Model

Agents may assist, but humans remain accountable for high-impact decisions.

```text
Human defines objective.
Agent discovers and prepares context.
Policy engine evaluates permissions.
Agent proposes action.
Human approves where required.
System executes.
Audit records outcome.
Learning improves future operations.
```

## Minimum Viable Operating Model

For an initial operational platform, every data asset should support:

1. Owner assignment
2. Steward assignment
3. Source record
4. Metadata record
5. Classification
6. Schema reference or exception
7. Access level
8. License status
9. Provenance record
10. Quality tier
11. Lifecycle state
12. Audit trail

## Operating Metrics

### Data Coverage Metrics

- Number of registered data assets
- Percentage with owner
- Percentage with steward
- Percentage with schema
- Percentage with provenance
- Percentage with classification

### Governance Metrics

- Access request completion time
- Policy evaluation count
- Policy violation rate
- Exceptions opened and closed
- Audit completeness

### Quality Metrics

- Quality tier distribution
- Validation pass rate
- Freshness compliance
- Data issue resolution time

### Usage Metrics

- Search volume
- Dataset views
- Dataset downloads
- API calls
- Data product subscriptions
- Analytics product usage

### Value Metrics

- Reuse rate
- Decision records linked to data
- Outcomes measured
- Improvement actions completed
- Public or institutional impact

## Operating Model Boundaries

### Foundation Owns

- Vocabulary
- Ontology
- Taxonomy
- Meta model
- Reference operating model
- Governance model
- Schema definitions
- Validation principles

### Platform Owns

- Runtime services
- Registry
- Catalog
- Workflows
- APIs
- Integrations
- Audit implementation
- Policy execution
- Observability

### Solutions Own

- Use-case packaging
- Domain-specific workflows
- User experiences
- Domain configurations
- Implementation playbooks

## Status

Draft. Canonical after governance review.
