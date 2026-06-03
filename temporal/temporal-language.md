# OpenDataWorld Temporal Language

Time is not a catalog.

Time is a universal primitive and language for expressing state, events, validity, duration, recurrence, ordering, causality, windows, deadlines, schedules, and temporal conditions.

## Core Idea

```text
Time is a programming language for governed change.
```

OpenDataWorld needs a temporal language because data, policies, trust, lineage, decisions, outcomes, access, agents, approvals, and audits are all time-bound.

## Temporal North Star

```text
Every governed system must be able to answer:
What was true, when was it true, who knew it, what changed, why did it change, and what should happen next?
```

## Temporal Language Layers

```text
Temporal Primitive
    ↓
Temporal Operator
    ↓
Temporal Expression
    ↓
Temporal Rule
    ↓
Temporal Program
    ↓
Temporal Validation
```

## 1. Temporal Primitives

Temporal primitives are the base values of the temporal language.

```text
Instant
Interval
Duration
Event
State
Version
Snapshot
Projection
Recurrence
Deadline
Schedule
Window
Clock
Calendar
Timezone
```

### Examples

```text
2026-06-03T10:00:00+05:30
5 days
next 30 days
between approval and publication
version as of decision time
current state as of now
```

## 2. Temporal Operators

Temporal operators define relationships over time.

```text
before
after
during
within
between
until
since
from
to
next
previous
last
first
every
asOf
at
on
by
expiresAfter
startsAfter
endsBefore
validDuring
effectiveFrom
effectiveUntil
```

## 3. Temporal Expressions

Temporal expressions combine primitives and operators.

```text
after 5 days
within 5 days after approval
5 days before expiry
next 5 days
previous 30 days
until revoked
since last update
between approval and publication
every 90 days
first Monday after approval
as of decision time
valid from publication until revoked
```

## 4. Temporal Rules

Temporal rules attach temporal expressions to governance, data, analytics, decisions, and agent workflows.

```text
Policy must be reviewed every 180 days.
Access expires 30 days after approval.
Dataset must be reviewed within 5 days before publication.
Trust assessment is valid until revoked or until validUntil.
Decision must preserve data versions as of decisionTime.
Agent action must be audited at execution time.
Outcome must be measured within 30 days after action completion.
```

## 5. Temporal Programs

Temporal programs are executable temporal rules.

Example:

```yaml
program: accessExpiry
when:
  event: accessApproved
then:
  grantAccess:
    validFrom: event.time
    validUntil: event.time + duration("30 days")
  schedule:
    event: accessReview
    at: validUntil - duration("5 days")
```

Example:

```yaml
program: publicationReview
when:
  stateChange:
    objectType: Dataset
    to: ProposedForPublication
then:
  requireReview:
    within: duration("5 days")
  blockPublicationUntil:
    condition: review.status == "Approved"
```

Example:

```yaml
program: trustExpiry
when:
  objectType: TrustAssessment
  state: Active
then:
  validUntil:
    min:
      - property: validUntil
      - event: revokedAt
  requireReassessment:
    before: validUntil
```

## Temporal Grammar

A minimal grammar:

```ebnf
TemporalExpression = RelativeExpression | AbsoluteExpression | IntervalExpression | RecurrenceExpression | EventExpression ;

AbsoluteExpression = "at" DateTime | "on" Date ;

RelativeExpression = Operator Duration Anchor? ;

IntervalExpression = "between" Anchor "and" Anchor
                   | "from" Anchor "to" Anchor
                   | "during" Anchor ;

RecurrenceExpression = "every" Duration Anchor? ;

EventExpression = "after" Event
                | "before" Event
                | "until" Event
                | "since" Event
                | "asOf" Event ;

Operator = "before" | "after" | "within" | "next" | "previous" | "last" | "first" ;

Anchor = Event | DateTime | StateChange | PropertyReference ;

Duration = Number TimeUnit ;

TimeUnit = "second" | "minute" | "hour" | "day" | "week" | "month" | "quarter" | "year" ;
```

## Canonical Temporal Fields

These fields should be used consistently across schemas, graph records, registry records, policies, controls, and audits.

```text
createdAt
updatedAt
recordedAt
eventTime
observedAt
validFrom
validTo
effectiveFrom
effectiveTo
publishedAt
deprecatedAt
archivedAt
revokedAt
approvedAt
rejectedAt
accessedAt
executedAt
completedAt
calculatedAt
madeAt
measuredAt
expiresAt
reviewedAt
nextReviewAt
versionTime
snapshotTime
projectionTime
```

## Temporal Invariants

```text
Identity is stable.
State is temporal.
Relationships are temporal.
Policies are temporal.
Trust is temporal.
Lineage is temporal.
Decisions are temporal.
Outcomes are temporal.
Audits are append-only.
Current state is a projection over history.
```

## Temporal Semantics

### `before`

```text
A before B means A.time < B.time.
```

### `after`

```text
A after B means A.time > B.time.
```

### `within`

```text
A within duration after B means B.time <= A.time <= B.time + duration.
```

### `next`

```text
next 5 days means interval [anchorTime, anchorTime + 5 days].
```

### `previous`

```text
previous 30 days means interval [anchorTime - 30 days, anchorTime].
```

### `until`

```text
valid until X means validTo = X or earlier revocation event.
```

### `since`

```text
since X means interval [X.time, anchorTime].
```

### `asOf`

```text
asOf T means evaluate the state using facts, events, and versions valid at T.
```

## Temporal Query Examples

```text
Show datasets published in the previous 30 days.
Show policies expiring in the next 5 days.
Show trust assessments valid as of decision time.
Show decisions made after insight publication.
Show outcomes measured within 30 days after action completion.
Show agent actions executed after approval but before expiry.
Show all changes since last review.
```

## Temporal Governance Rules

1. Every registry record must have `createdAt` and `updatedAt`.
2. Every graph edge must have `recordedAt`.
3. Every event must have `eventTime` and `recordedAt`.
4. Every policy activated must have `effectiveFrom`.
5. Every policy retired should have `effectiveTo`.
6. Every trust assessment must have `calculatedAt`.
7. Every decision must have `madeAt`.
8. Every outcome must have `measuredAt`.
9. Every agent action must have `executedAt` and trace timing.
10. No current-state update may destroy prior state.
11. Every derived state must be reproducible from events, versions, or snapshots.

## Relationship to Other Layers

```text
Temporal Language applies to:
├── Registry Records
├── Graph Nodes
├── Graph Edges
├── Schemas
├── Policies
├── Controls
├── Classifications
├── Taxonomies
├── Trust Assessments
├── Metrics
├── Insights
├── Decisions
├── Outcomes
├── Agents
├── Approvals
└── Audits
```

## What Time Is Not

```text
Time is not a catalog.
Time is not a taxonomy.
Time is not a classification.
Time is not merely a timestamp field.
```

## What Time Is

```text
Time is a primitive.
Time is an axis.
Time is a language.
Time is a validator.
Time is a scheduler.
Time is a replay mechanism.
Time is a projection mechanism.
Time is how governed change becomes explainable.
```

## Status

Draft. Canonical after governance review.
