# OpenDataWorld Graph Specification

This directory contains the canonical OpenDataWorld graph implementation contract.

The graph connects data, metadata, identity, trust, provenance, lineage, governance, analytics, decisions, outcomes, and agents.

## Graph Purpose

```text
Make data, context, governance, trust, lineage, analytics, decisions, and outcomes connected, queryable, explainable, validatable, and reusable.
```

## Graph Package

```text
graph/
├── README.md
├── node-types.yaml
├── edge-types.yaml
├── constraints.yaml
├── graph-validation-rules.yaml
└── example-health-dataset.graph.json

contexts/
└── opendataworld.context.jsonld
```

## What Each File Does

| File | Purpose |
|---|---|
| `node-types.yaml` | Defines allowed node types, required fields, inheritance, and allowed edges |
| `edge-types.yaml` | Defines allowed edge types, source/target compatibility, cardinality, temporal behavior, provenance, evidence, and audit requirements |
| `constraints.yaml` | Defines hard graph validity rules and lifecycle/publication/governance gates |
| `graph-validation-rules.yaml` | Defines validation phases, checks, severity model, and validation report shape |
| `example-health-dataset.graph.json` | Provides canonical example graph for documentation, testing, SDKs, and validators |
| `contexts/opendataworld.context.jsonld` | Provides semantic interoperability using JSON-LD and mappings to schema.org, DCAT, DCTerms, and PROV-O |

## Graph Layers

```text
Semantic Model
    ↓
Node Contract
    ↓
Edge Contract
    ↓
Constraint Contract
    ↓
Validation Contract
    ↓
Reference Example
    ↓
JSON-LD Context
```

## Required Graph Capabilities

A conforming implementation should support:

1. Node type validation
2. Edge type validation
3. Source and target compatibility validation
4. Required field validation
5. Required edge validation
6. Lifecycle gate validation
7. Publication gate validation
8. Governance gate validation
9. Trust evidence validation
10. Lineage temporal validation
11. Agent action validation
12. JSON-LD export or mapping

## Core Node Families

```text
Identity Nodes
├── Person
├── Organization
├── Team
├── System
└── Agent

Data Nodes
├── DataAsset
├── Dataset
├── DataProduct
├── DataSource
├── DataElement
└── Schema

Governance Nodes
├── Policy
├── Rule
├── AccessDecision
├── Approval
└── AuditEvent

Trust and Evidence Nodes
├── ProvenanceRecord
├── LineageRecord
├── TrustAssessment
└── Evidence

Analytics and Decision Nodes
├── Metric
├── Insight
├── Decision
├── Outcome
└── Workflow
```

## Core Edge Families

```text
Accountability
├── ownedBy
├── stewardedBy
├── operatedBy
└── approvedBy

Data Flow
├── sourcedFrom
├── derivedFrom
├── transformedInto
├── dependsOn
└── feeds

Governance
├── classifiedAs
├── governedBy
├── appliesTo
├── evaluatedBy
└── recordedBy

Trust and Evidence
├── hasProvenance
├── hasLineage
├── hasTrustAssessment
├── hasEvidence
└── basedOn

Analytics and Decisions
├── supports
├── informs
├── leadsTo
└── impacts
```

## Minimum Valid Published Dataset Graph

A published dataset must connect to:

```text
Dataset
├── ownedBy → Person | Team | Organization
├── stewardedBy → Person | Team
├── sourcedFrom → DataSource
├── conformsTo → Schema
├── classifiedAs → Classification
├── governedBy → Policy
├── hasProvenance → ProvenanceRecord
└── hasTrustAssessment → TrustAssessment
```

It must also include:

```text
license
accessPolicy
version
lifecycleState = Published
```

## Graph Completion Status

The OpenDataWorld graph is complete at the Foundation specification level.

```text
Conceptual model        ✓
Node contract           ✓
Edge contract           ✓
Constraint contract     ✓
Validation contract     ✓
Reference example       ✓
JSON-LD context         ✓
```

Runtime implementations may still add database-specific mappings such as SurrealDB, RDF, property graph, Cypher, Gremlin, SPARQL, or OpenAPI projections.

## Status

Draft. Canonical after governance review.
