# OpenDataWorld Data Modeling Model

Data modeling is the discipline of representing data, meaning, relationships, constraints, governance, and usage in a structured form.

OpenDataWorld treats data modeling as a foundation capability, not a database-only activity.

## Core Position

```text
Data modeling defines how reality, institutions, systems, events, decisions, and knowledge are represented as governed data.
```

## North Star

Create models that make data understandable, trustworthy, interoperable, governable, reusable, traceable, and actionable.

## Data Modeling Layers

OpenDataWorld uses a multi-layer modeling approach:

```text
Conceptual Model
    ↓
Semantic Model
    ↓
Logical Model
    ↓
Physical Model
    ↓
Operational Model
    ↓
Governance Model
    ↓
AI-Ready Context Model
```

## 1. Conceptual Data Model

The conceptual model defines the business meaning of data without implementation details.

### Purpose

- Define core concepts
- Align stakeholders
- Clarify scope
- Establish shared vocabulary
- Avoid premature technical decisions

### Typical Objects

- Entity
- Data Asset
- Dataset
- Data Product
- Data Source
- Data Element
- Policy
- Actor
- Event
- Decision
- Outcome

### Example

```text
Organization owns Dataset
Dataset contains DataElement
Dataset is governedBy Policy
Dataset supports Decision
Decision produces Outcome
```

## 2. Semantic Data Model

The semantic model defines meaning, relationships, and context.

### Purpose

- Preserve meaning across systems
- Enable knowledge graph representation
- Support search and reasoning
- Align with schema.org, JSON-LD, DCAT, and domain vocabularies

### Semantic Modeling Rules

1. Every entity should have a stable identifier.
2. Every relationship should have a type.
3. Every relationship should preserve provenance.
4. Every term should map to glossary or ontology definitions.
5. External vocabularies should be reused where they fit.

### Example

```text
Dataset --about--> SubjectArea
Dataset --publishedBy--> Organization
Dataset --derivedFrom--> DataSource
Dataset --conformsTo--> Schema
Dataset --licensedUnder--> License
```

## 3. Logical Data Model

The logical model defines entities, attributes, constraints, and relationships independent of a specific database.

### Purpose

- Define fields and constraints
- Normalize relationships
- Define identifiers
- Establish validation rules
- Support multiple implementations

### Example Entity

```yaml
Dataset:
  id: string
  name: string
  description: string
  owner: Organization
  steward: Person | Team
  schema: Schema
  classification: Classification
  provenance: Provenance
  lineage: Lineage
  lifecycleState: LifecycleState
```

## 4. Physical Data Model

The physical model defines how the logical model is implemented in a specific database, graph store, document store, index, or file format.

### Possible Targets

- Relational database
- Document database
- Graph database
- Search index
- Object storage
- Event store
- Vector index
- Data warehouse
- Data lakehouse

### Physical Modeling Rule

Physical implementation must not become the canonical truth. It is a projection of the canonical model.

```text
Canonical model is source of meaning.
Physical model is source of execution.
```

## 5. Operational Data Model

The operational model defines how data changes over time.

### Purpose

- Track lifecycle
- Support event sourcing
- Preserve audit history
- Manage state transitions
- Enable replay and recovery

### Required Operational Concepts

- Event
- Action
- Command
- State
- Version
- Snapshot
- Audit record
- Lineage edge
- Policy decision

### Rule

Current state is a projection from history.

## 6. Governance Data Model

The governance model defines ownership, access, classification, privacy, retention, quality, trust, and compliance.

### Required Governance Fields

```yaml
owner: string
steward: string
classification: object
accessPolicy: string
license: string
retentionPolicy: string
privacyPolicy: string
qualityProfile: string
trustProfile: string
audit: object
```

### Governance Modeling Rules

1. Every important data asset must have an owner.
2. Every sensitive asset must have an access policy.
3. Every published asset must have a license or usage terms.
4. Every transformation must produce lineage.
5. Every policy-relevant action must be auditable.
6. Every agent action on data must reference policy evaluation.

## 7. AI-Ready Context Model

The AI-ready context model defines how data is prepared for AI systems, agents, retrieval, reasoning, and decision support.

### Purpose

- Provide trusted context to AI systems
- Prevent ungoverned data use
- Preserve provenance
- Enable explainability
- Support agentic workflows

### Required AI Context Fields

```yaml
sourceAsset: string
dataVersion: string
schemaVersion: string
license: string
classification: string
usagePolicy: string
provenance: string
qualityProfile: string
trustScore: string
retrievalContext: object
```

### AI Modeling Rules

1. AI context must reference source data.
2. AI-generated outputs must preserve provenance.
3. Generated metadata must be marked as generated or assisted.
4. Agent actions must be identity-bound and policy-evaluated.
5. AI-ready does not mean governance-free.

## Core Modeling Objects

```text
DataModel
├── ConceptualModel
├── SemanticModel
├── LogicalModel
├── PhysicalModel
├── OperationalModel
├── GovernanceModel
└── AIContextModel
```

## Canonical Data Modeling Flow

```text
1. Define purpose
2. Define scope
3. Define stakeholders
4. Define glossary terms
5. Define entities
6. Define relationships
7. Define attributes
8. Define identifiers
9. Define lifecycle
10. Define classification
11. Define governance controls
12. Define quality rules
13. Define lineage
14. Define access rules
15. Define schemas
16. Define examples
17. Define validation rules
18. Define implementation projections
19. Define monitoring
20. Define change governance
```

## Data Modeling Unit: Data Element

A DataElement is the smallest governed meaningful unit of data.

### Required Fields

```yaml
id: string
name: string
definition: string
dataType: string
semanticType: string
sensitivity: string
source: string
owner: string
allowedValues: array
validationRules: array
qualityRules: array
```

## Data Modeling Unit: Entity

An Entity represents something identifiable.

### Required Modeling Questions

- What is it?
- How is it uniquely identified?
- What attributes describe it?
- What relationships does it have?
- What lifecycle does it follow?
- Who owns it?
- What policies apply?
- What evidence supports it?

## Data Modeling Unit: Relationship

A Relationship connects two or more things.

### Required Fields

```yaml
source: string
target: string
relationshipType: string
direction: string
cardinality: string
validFrom: datetime
validTo: datetime
provenance: object
confidence: number
```

## Relationship Cardinality

```text
OneToOne
OneToMany
ManyToOne
ManyToMany
Temporal
Conditional
Derived
Inferred
```

## Data Model Quality Criteria

A good data model is:

- Understandable
- Stable
- Versioned
- Extensible
- Governed
- Validatable
- Traceable
- Interoperable
- Implementation-neutral
- Standards-aligned
- AI-ready
- Human-reviewable

## Anti-Patterns

Avoid:

- Database-first modeling without meaning
- Unnamed relationships
- Unowned datasets
- Hidden business rules
- Unclassified sensitive data
- Overwriting history
- Mixing current state with historical truth
- Treating generated data as verified truth
- Using implementation IDs as canonical identities
- Creating schemas without examples
- Creating data products without consumers
- Publishing data without license and provenance

## Data Model Review Checklist

Before a data model becomes canonical, verify:

- Does every entity have a definition?
- Does every entity have an identifier?
- Does every data asset have an owner?
- Does every relationship have a type?
- Does every important field have a definition?
- Are sensitivity and access classifications present?
- Are lifecycle states defined?
- Are provenance and lineage represented?
- Are validation rules defined?
- Are examples included?
- Are external standards mapped where possible?
- Are implementation projections clearly separated from the canonical model?

## Data Model Artifact Types

```text
Glossary
Ontology
Taxonomy
Conceptual Model
Semantic Model
Logical Model
Physical Model
JSON Schema
JSON-LD Context
Graph Model
API Contract
Registry Card
Example Record
Validation Rule
Migration Rule
```

## Relationship to Foundation Artifacts

```text
Glossary defines terms.
Ontology defines concepts and relationships.
Taxonomy defines classification values.
Meta Model defines structure.
Data Modeling defines modeling discipline.
Schemas define executable validation.
JSON-LD Context defines semantic interoperability.
Graph Model defines relationship execution.
```

## Status

Draft. Canonical after governance review.
