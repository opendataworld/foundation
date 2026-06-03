# OpenDataWorld Reference Agent Architecture

OpenDataWorld supports governed agents that assist with data and analytics solutions as a service.

This reference agent architecture defines how agents discover, understand, govern, validate, analyze, publish, and act on data under identity, policy, trust, provenance, lineage, human approval, and audit.

## Agent Architecture North Star

```text
Agents may accelerate data and analytics work, but they must never bypass identity, governance, trust, provenance, lineage, approval, or audit.
```

## Core Agent Flow

```text
Objective
    ↓
Context Retrieval
    ↓
Policy Evaluation
    ↓
Tool Permission Check
    ↓
Data Access Check
    ↓
Plan
    ↓
Human Approval where required
    ↓
Action
    ↓
Validation
    ↓
Provenance and Lineage
    ↓
Audit
    ↓
Evaluation
    ↓
Learning
```

## Agent Architecture Principles

1. Every agent must have identity.
2. Every agent must have an owner and operator.
3. Every agent must have a declared purpose.
4. Every agent action on data must be policy-evaluated.
5. Every agent tool use must be permissioned.
6. Every agent output must preserve provenance.
7. Every agent transformation must produce lineage.
8. Every high-impact action must support human approval.
9. Every agent action must be auditable.
10. Every agent must be evaluated and trust-scored over time.

## Agent Layers

```text
Agent Experience Layer
├── Agent Workspace
├── Agent Review Inbox
├── Agent Action Monitor
├── Agent Configuration UI
├── Tool Permission UI
├── Approval Console
└── Agent Audit Explorer

Agent Orchestration Layer
├── Agent Runtime
├── Planner
├── Task Router
├── Workflow Orchestrator
├── Handoff Manager
├── Memory Manager
├── Context Manager
└── Evaluation Manager

Agent Governance Layer
├── Agent Identity Service
├── Policy Evaluation Service
├── Tool Permission Service
├── Data Access Service
├── Risk Assessment Service
├── Human Approval Service
├── Guardrail Service
├── Trust Assessment Service
└── Audit Service

Agent Capability Layer
├── Data Discovery Agent
├── Metadata Enrichment Agent
├── Classification Agent
├── Schema Mapping Agent
├── Quality Agent
├── Lineage Agent
├── Analytics Agent
├── Insight Agent
├── Publishing Agent
├── Governance Agent
└── Decision Support Agent

Agent Knowledge Layer
├── Registry Context
├── Catalog Context
├── Knowledge Graph Context
├── Policy Context
├── Provenance Context
├── Lineage Context
├── Trust Context
├── Analytics Context
└── Decision Context
```

## Primary Agent Objects

```text
Agent
AgentIdentity
Objective
Task
Plan
Instruction
Tool
Skill
Capability
Memory
Context
PolicyDecision
Approval
Action
Observation
Output
Evaluation
TrustAssessment
AuditEvent
```

## Agent Identity

Every agent must have a canonical identity.

### Required Fields

```yaml
id: string
name: string
owner: string
operator: string
purpose: string
riskLevel: string
allowedActions:
  - string
allowedTools:
  - string
allowedDataClasses:
  - string
approvalRequirements:
  - string
lifecycleState: string
```

## Agent Types

```text
DiscoveryAgent
MetadataAgent
ClassificationAgent
SchemaMappingAgent
QualityAgent
LineageAgent
AnalyticsAgent
InsightAgent
PublishingAgent
GovernanceAgent
DecisionSupportAgent
AuditAgent
```

## Agent Capabilities

### Data Discovery Agent

Finds relevant data assets based on user goals, taxonomy, metadata, trust, and policy.

### Metadata Enrichment Agent

Suggests descriptions, tags, glossary mappings, ownership hints, and missing metadata.

### Classification Agent

Suggests domain, sensitivity, access level, quality tier, license class, and lifecycle classification.

### Schema Mapping Agent

Maps source schemas to canonical schemas and identifies schema drift.

### Quality Agent

Runs or recommends quality checks, detects anomalies, and creates quality issues.

### Lineage Agent

Suggests lineage edges based on transformations, usage, pipelines, and analytics dependencies.

### Analytics Agent

Creates draft metrics, analyses, dashboards, forecasts, and analytical summaries from governed data.

### Insight Agent

Creates draft insight cards with evidence, confidence, explanation, and limitations.

### Publishing Agent

Prepares data and metadata for publication subject to policy and approval.

### Governance Agent

Recommends policies, controls, reviews, access decisions, and risk mitigations.

### Decision Support Agent

Prepares decision briefs using data, evidence, insights, assumptions, constraints, and alternatives.

## Agent Tool Model

Tools are governed capabilities that agents may invoke.

### Tool Requirements

```yaml
id: string
name: string
description: string
provider: string
inputSchema: string
outputSchema: string
allowedAgentTypes:
  - string
riskLevel: string
policies:
  - string
auditRequired: boolean
approvalRequired: boolean
```

## Agent Action Model

Every agent action must be recorded.

```yaml
id: string
agentIdentity: string
actionType: string
objective: string
resource: string
tool: string
input: object
output: object
policyDecision: string
approvalReference: string
startedAt: datetime
completedAt: datetime
status: string
traceId: string
```

## Agent Governance Gates

### Gate 1: Identity Gate

Before an agent acts:

- Agent identity must exist.
- Owner must be known.
- Operator must be known.
- Purpose must be declared.
- Lifecycle state must allow action.

### Gate 2: Policy Gate

Before an agent accesses or modifies data:

- Subject identity must be resolved.
- Resource identity must be resolved.
- Purpose must be captured.
- Policy must be evaluated.
- Policy version must be recorded.

### Gate 3: Tool Gate

Before an agent invokes a tool:

- Tool identity must be known.
- Tool must be allowed for the agent type.
- Tool risk level must be evaluated.
- Tool input and output schemas must be known.

### Gate 4: Approval Gate

Before high-impact or sensitive action:

- Approval requirement must be checked.
- Authorized human approval must be captured where required.
- Approval rationale and conditions must be recorded.

### Gate 5: Validation Gate

After action:

- Output must be validated.
- Data changes must pass schema and quality checks where applicable.
- Metadata changes must be reviewable.
- Publication outputs must pass publication gates.

### Gate 6: Audit Gate

Every agent action must emit an audit event with actor, action, resource, context, result, and trace ID.

## Agent Memory and Context

Agent memory must be governed.

### Context Sources

```text
Registry
Catalog
Knowledge Graph
Data Asset Metadata
Policies
Provenance
Lineage
Trust Assessments
Analytics Records
Decision Records
User Instructions
```

### Memory Rules

1. Memory must not bypass policy.
2. Sensitive context must respect access controls.
3. Memory used for decisions must be traceable.
4. Generated memory must be marked as generated or inferred.
5. Stale memory must not override current registry or policy state.

## Agent Trust

Agent trust is contextual and temporal.

### Trust Signals

- Identity verification
- Owner and operator clarity
- Tool permission compliance
- Policy compliance history
- Audit completeness
- Evaluation results
- Failure rate
- Human override rate
- Escalation behavior
- Output quality
- Incident history

## Agent Evaluation

Agents must be evaluated continuously.

### Evaluation Dimensions

```text
Correctness
Completeness
Policy Compliance
Data Safety
Output Quality
Traceability
Explainability
Human Review Acceptance
Failure Recovery
Cost Efficiency
```

## Agent Handoff

Agents may hand off tasks to other agents, humans, or systems.

### Handoff Requirements

```yaml
from: string
to: string
task: string
context: string
reason: string
constraints:
  - string
policyDecision: string
createdAt: datetime
status: string
```

## Human-Agent Collaboration Model

```text
Human defines objective.
Agent retrieves governed context.
Policy engine evaluates scope.
Agent drafts plan or output.
Human reviews where required.
Agent executes approved action.
System validates output.
Audit records the full trace.
Evaluation updates agent trust.
```

## Minimum Viable Agent Architecture

The first operational platform should support:

1. Agent registry
2. Agent identity
3. Owner and operator fields
4. Purpose declaration
5. Allowed actions and tools
6. Policy evaluation before data access
7. Human approval gate
8. Tool invocation audit
9. Output validation
10. Provenance capture
11. Lineage capture for transformations
12. Agent trust assessment
13. Evaluation records

## Agent Validation Rules

1. Every agent must have identity.
2. Every agent must have owner and operator.
3. Every agent must declare purpose.
4. Every agent must be governed by policy.
5. Every tool use must be permissioned.
6. Every data access must be policy-evaluated.
7. Every sensitive data action must be audited.
8. Every high-impact action must support human approval.
9. Every agent output must preserve provenance.
10. Every transformation must produce lineage.
11. Every agent action must have trace ID.
12. Every agent must be evaluated over time.

## Relationship to Other Architectures

```text
Data Architecture defines governed data assets.
Governance Architecture defines policy, access, approval, and audit.
Analytics Architecture defines metrics, insights, decisions, and outcomes.
Knowledge Graph provides connected context.
Registry Model provides official records.
Agent Architecture provides governed automation around all of them.
```

## Status

Draft. Canonical after governance review.
