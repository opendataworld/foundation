# OpenDataWorld Trust Model

OpenDataWorld treats trust as a first-class foundation concept.

Trust determines whether data, sources, systems, agents, analytics, policies, relationships, and decisions are fit for a specific purpose under a specific context.

## Trust North Star

```text
Trust must be contextual, temporal, evidence-backed, explainable, versioned, and auditable.
```

## Core Assertion

```text
Identity is not trust.
Verification is not trust.
Popularity is not trust.
Trust is earned through evidence, governance, provenance, quality, behavior, and context.
```

## Trust Scope

```text
Trust
├── Identity Trust
├── Data Trust
├── Dataset Trust
├── Data Product Trust
├── Source Trust
├── Organization Trust
├── System Trust
├── Agent Trust
├── Model Trust
├── Analytics Trust
├── Insight Trust
├── Decision Trust
├── Evidence Trust
├── Policy Trust
├── Relationship Trust
└── Service Trust
```

## Trust Inputs

Trust should be derived from multiple signals.

```text
Identity
+ Verification
+ Provenance
+ Lineage
+ Data Quality
+ Freshness
+ Completeness
+ Usage History
+ Certification
+ Evidence
+ Audit History
+ Policy Compliance
+ Source Reliability
+ Human Review
+ Outcome Feedback
= Contextual Trust
```

## Trust Record

Every trust assessment should produce a trust record.

```yaml
id: string
type: TrustAssessment
subject: string
subjectType: string
trustContext: string
trustScore: number
trustLevel: string
calculatedAt: datetime
validUntil: datetime
method: string
inputs:
  - string
evidence:
  - string
limitations:
  - string
explanation: string
reviewStatus: string
version: string
```

## Trust Levels

```text
Unknown
Low
Medium
High
Verified
Certified
Revoked
```

### Trust Level Meaning

- `Unknown`: No reliable assessment exists.
- `Low`: Evidence is weak, incomplete, stale, or contradictory.
- `Medium`: Some evidence supports use, but limitations remain.
- `High`: Strong evidence supports use in defined contexts.
- `Verified`: Identity, provenance, quality, and governance checks passed.
- `Certified`: Formal review or certification completed.
- `Revoked`: Trust has been withdrawn due to risk, invalidation, policy, or evidence.

## Contextual Trust

Trust must be evaluated for a purpose.

Example:

```text
A dataset may be trusted for exploratory analysis but not for regulatory reporting.
```

### Trust Context Examples

```text
Public discovery
Research use
Operational reporting
Regulatory reporting
Model training
Decision support
Financial decision
Safety-critical decision
Automated action
Publication
```

## Temporal Trust

Trust changes over time.

A trust score must always record:

```yaml
calculatedAt: datetime
validUntil: datetime
sourceVersions:
  - string
policyVersions:
  - string
evidenceVersions:
  - string
```

## Data Trust

Data trust evaluates whether a data asset is fit for use.

### Data Trust Signals

- Owner exists
- Steward exists
- Source known
- Provenance recorded
- Schema exists
- Quality profile exists
- Lineage exists
- Sensitivity classified
- License clear
- Access policy defined
- Freshness acceptable
- Usage history available
- Issues known and disclosed
- Certification status known

## Source Trust

Source trust evaluates the reliability of a data source.

### Source Trust Signals

- Source identity verified
- Source owner known
- Collection method documented
- Update cadence known
- Historical reliability
- Error rate
- Completeness rate
- Governance maturity
- External reputation where applicable
- Incident history

## Agent Trust

Agent trust evaluates whether an agent is safe and reliable for a specific action on data.

### Agent Trust Signals

- Agent identity exists
- Owner and operator known
- Purpose defined
- Tool permissions defined
- Allowed data classes defined
- Evaluation history
- Audit history
- Policy compliance history
- Human approval behavior
- Failure rate
- Escalation behavior
- Risk level

### Agent Trust Rule

An agent must never receive higher trust than the weakest critical dependency required for its action.

## Analytics Trust

Analytics trust evaluates whether an analytical output is reliable and explainable.

### Analytics Trust Signals

- Input data versions known
- Metrics defined
- Assumptions documented
- Calculation method recorded
- Refresh cadence known
- Limitations disclosed
- Validation performed
- Reviewer known
- Outcome feedback available

## Decision Trust

Decision trust evaluates whether a decision was made using appropriate data, evidence, policy, and review.

### Decision Trust Signals

- Decision maker identified
- Data versions referenced
- Evidence referenced
- Alternatives considered
- Constraints documented
- Policy context recorded
- Confidence stated
- Human approval captured where required
- Outcome tracked

## Evidence Trust

Evidence trust evaluates whether evidence can support a claim, score, validation, decision, or audit.

### Evidence Trust Signals

- Source known
- Collected time known
- Collector known
- Method documented
- Integrity preserved
- Version preserved
- Bias or limitation disclosed
- Confidence assigned

## Relationship Trust

Relationship trust evaluates whether a graph relationship is reliable.

### Relationship Trust Signals

- Source identity known
- Target identity known
- Relationship type defined
- Provenance recorded
- Evidence linked
- Confidence score assigned
- Validity period known
- Human reviewed where high impact

## Trust Score Dimensions

A trust score may be composed from weighted dimensions.

```text
Identity Verification
Provenance Completeness
Lineage Completeness
Quality Score
Freshness Score
Policy Compliance
Evidence Strength
Certification Status
Usage Reliability
Issue History
Human Review
```

## Example Trust Formula

This is a reference formula, not a mandatory implementation.

```text
Trust Score =
  0.15 Identity Verification
+ 0.15 Provenance Completeness
+ 0.15 Quality Score
+ 0.10 Lineage Completeness
+ 0.10 Freshness Score
+ 0.10 Policy Compliance
+ 0.10 Evidence Strength
+ 0.05 Certification Status
+ 0.05 Usage Reliability
+ 0.05 Human Review
```

Weights should vary by trust context.

## Trust Decisions

Trust assessments may produce actions.

```text
Allow Use
Allow With Warning
Require Review
Require Approval
Restrict Use
Quarantine
Revoke Trust
Escalate
```

## Trust Governance

Trust models must be governed.

### Governance Rules

1. Trust formulas must be versioned.
2. Trust inputs must be explainable.
3. Trust scores must preserve evidence.
4. Trust scores must be recalculated when critical evidence changes.
5. Trust revocation must be auditable.
6. Trust certification must require authorized approval.
7. Trust must be context-specific.
8. Trust must not be inferred from identity alone.
9. Trust must not be permanent.
10. Trust must disclose limitations.

## Minimum Viable Trust Baseline

For the first operational platform, support:

1. Trust level per data asset
2. Trust score per dataset
3. Provenance completeness signal
4. Quality tier signal
5. Owner and steward signal
6. Source known signal
7. License known signal
8. Access policy known signal
9. Trust calculation timestamp
10. Trust explanation text
11. Trust evidence references
12. Trust review status

## Trust Validation Rules

1. Every trust assessment must reference a subject.
2. Every trust assessment must define context.
3. Every trust score must have calculation time.
4. Every trust score must have evidence or state that evidence is unavailable.
5. Every Certified trust level must have reviewer or certification authority.
6. Every Revoked trust level must have reason and timestamp.
7. Every trust formula must have a version.
8. Every trust assessment used in a decision must be preserved with that decision record.

## Status

Draft. Canonical after governance review.
