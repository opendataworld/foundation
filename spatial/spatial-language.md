# OpenDataWorld Spatial Language

Location is not just a catalog.

Location is a universal primitive, axis, coordinate system, jurisdiction boundary, and namespace scope where local meaning, law, governance, identifiers, and data rules differ.

## Core Idea

```text
Location is a language for governed place, boundary, jurisdiction, coverage, proximity, movement, and scope.
```

## Spatial North Star

```text
Every governed system must be able to answer:
Where is this true, where does it apply, which boundary governs it, what jurisdiction controls it, and how does location change meaning, access, trust, analytics, and action?
```

## Spatial Language Layers

```text
Spatial Primitive
    ↓
Spatial Operator
    ↓
Spatial Expression
    ↓
Jurisdiction Rule
    ↓
Spatial Program
    ↓
Spatial Validation
```

## What Location Is

```text
Location is a primitive.
Location is an axis.
Location is a boundary.
Location is a jurisdiction.
Location is a namespace when local variation exists.
Location is a governance scope.
Location is a query dimension.
Location is a policy condition.
Location is an analytics dimension.
Location is a trust context.
```

## What Location Is Not

```text
Location is not merely a catalog.
Location is not merely a taxonomy.
Location is not merely a string field.
Location is not only latitude and longitude.
```

## Spatial Primitives

```text
Country
Jurisdiction
AdministrativeArea
Region
State
Province
District
County
City
Town
Village
PostalCode
Address
Place
Point
Line
Polygon
Boundary
Area
Route
Distance
CoverageArea
ServiceArea
Timezone
CoordinateReferenceSystem
GeoHash
```

## Country as Primitive

Country is a first-class spatial primitive.

```text
Country = spatial primitive
Country = jurisdiction root
Country = governance boundary
Country = namespace boundary where needed
```

Country is used to answer:

```text
Which sovereign boundary applies?
Which legal system applies?
Which public-data rules apply?
Which residency or localization rules apply?
Which administrative hierarchy applies?
Which identifiers are valid?
Which language or localization applies?
```

## Country as Namespace

Country becomes a namespace when country-specific meaning, policy, law, taxonomy, identifier, classification, publication rule, or governance exists.

Recommended namespace format:

```text
odw.country.<ISO-3166-1-alpha-2>.*
```

Examples:

```text
odw.country.IN.*
odw.country.US.*
odw.country.SG.*
odw.country.DE.*
```

Global foundation records remain global:

```text
odw.foundation.*
odw.schema.*
odw.graph.*
odw.policy.*
odw.control.*
```

Country-specific extensions are scoped:

```text
odw.country.IN.policy.dataResidency.v1
odw.country.IN.taxonomy.administrativeArea.v1
odw.country.IN.classification.governmentRestrictedData.v1
odw.country.IN.registry.publicDataPortal.v1
```

## Namespace Rule

```text
Global foundation defines the canonical base.
Country namespace extends, maps, constrains, or specializes the base.
Country namespace must not silently redefine global meaning.
```

Country may:

```text
Add local policy
Add local taxonomy
Add local identifiers
Add local administrative hierarchy
Add local data-publication rules
Add local privacy or consent mappings
Add local language and localization mappings
Add local controls
Add local registries
```

Country must not:

```text
Silently redefine canonical global terms
Break global schema compatibility without explicit mapping
Remove provenance, lineage, trust, audit, or policy requirements
Hide local variation behind global identifiers
```

## Spatial Operators

```text
at
in
inside
outside
near
within
between
from
to
intersects
contains
coveredBy
covers
overlaps
adjacentTo
crosses
nearest
fartherThan
withinDistance
withinJurisdiction
underAuthorityOf
```

## Spatial Expressions

```text
in India
inside Karnataka
within 5 km of a facility
near this district
between City A and City B
from source location to service location
covered by this jurisdiction
outside restricted boundary
intersects service area
nearest public health facility
within this country namespace
under authority of this regulator
```

## Administrative Hierarchy

A country may define its own administrative hierarchy.

Generic hierarchy:

```text
Country
    ↓
AdministrativeAreaLevel1
    ↓
AdministrativeAreaLevel2
    ↓
AdministrativeAreaLevel3
    ↓
Locality
    ↓
Address
```

Example India-style mapping:

```text
Country: India
    ↓
State / Union Territory
    ↓
District
    ↓
Subdistrict / Taluk / Tehsil / Block
    ↓
City / Town / Village
    ↓
Ward / Local Area
    ↓
Address / Geo Point
```

Example US-style mapping:

```text
Country: United States
    ↓
State
    ↓
County
    ↓
City / Town
    ↓
ZIP Code / Census Tract
    ↓
Address / Geo Point
```

## Spatial Rules

Spatial rules attach location expressions to data, policy, governance, trust, analytics, decisions, and agents.

Examples:

```text
Dataset is valid only within India.
Policy applies inside a country jurisdiction.
Trust assessment is valid only for a specific region.
Data residency rule applies within a country namespace.
Publication rule differs by country.
Facility coverage metric is grouped by district.
Agent may act only inside approved jurisdiction.
Decision outcome must be measured for the affected region.
```

## Spatial Programs

Example: jurisdiction-scoped policy.

```yaml
program: countryScopedPolicy
when:
  resource.country: IN
then:
  applyPolicyNamespace: odw.country.IN.policy.*
  requireMappingsTo:
    - odw.policy.*
```

Example: nearby facility query.

```yaml
program: nearestFacility
input:
  location: Point
  radius: 5 km
then:
  find:
    type: HealthFacility
    where:
      withinDistance:
        from: input.location
        distance: input.radius
```

Example: publication jurisdiction gate.

```yaml
program: publicationJurisdictionGate
when:
  lifecycleState: ProposedForPublication
then:
  require:
    - country
    - jurisdiction
    - publicationPolicy
    - license
    - sensitivityClassification
```

## Canonical Spatial Fields

```text
country
countryCode
jurisdiction
jurisdictionType
administrativeArea
administrativeAreaLevel1
administrativeAreaLevel2
administrativeAreaLevel3
locality
address
postalCode
latitude
longitude
geometry
boundary
coverageArea
serviceArea
coordinateReferenceSystem
timezone
spatialScope
spatialValidity
```

## Country Namespace Fields

```yaml
countryCode: string
countryName: string
namespace: string
iso3166Alpha2: string
iso3166Alpha3: string
jurisdictionRoot: string
administrativeHierarchy: array
languageDefaults: array
currencyDefault: string
timezoneDefaults: array
policyNamespace: string
taxonomyNamespace: string
classificationNamespace: string
registryNamespace: string
```

## Spatial Invariants

```text
Place is contextual.
Boundary is temporal.
Jurisdiction is authoritative.
Country may scope policy.
Country may scope namespace.
Country-specific meaning must map to global meaning.
Spatial validity must be explicit for local or jurisdictional claims.
Location-sensitive trust must declare spatial scope.
Location-sensitive decisions must preserve geography used.
```

## Relationship to Time

Time tells when something is true.
Location tells where something is true.

Together:

```text
Spatiotemporal truth = what was true, where, and when.
```

Examples:

```text
Facility boundary as of 2026.
District classification before boundary change.
Policy effective in India after 2026-01-01.
Trust assessment valid in Karnataka until revoked.
Outcome measured in affected districts within 30 days after action.
```

## Relationship to Identity

Identity tells who or what.
Location tells where it applies.

Examples:

```text
Organization registered in country.
Dataset owned by ministry in jurisdiction.
Agent permitted to act within approved region.
Policy issued by national authority.
```

## Relationship to Policy

Policy may be spatially scoped.

```text
Policy applies in country.
Policy applies inside jurisdiction.
Policy applies outside restricted boundary.
Policy applies to datasets published for a geography.
```

## Relationship to Analytics

Analytics may be spatially grouped, filtered, compared, or scoped.

```text
Metric by country.
Insight by district.
Outcome by affected region.
Benchmark across states.
Facility coverage within 5 km.
```

## Relationship to Agents

Agents must respect spatial scope.

```text
Agent may access data only for approved jurisdiction.
Agent may publish only for approved geography.
Agent recommendations must disclose spatial scope.
Agent action must preserve location context.
```

## Spatial Validation Rules

1. Location-sensitive records must declare spatial scope.
2. Country-specific extensions must map to global foundation concepts.
3. Country namespaces must use stable country codes.
4. Administrative hierarchy must be versioned where used for decisions or analytics.
5. Spatial boundaries must have provenance.
6. Spatial boundaries should be temporal because boundaries can change.
7. Policy with spatial scope must declare jurisdiction.
8. Trust assessment with spatial scope must declare where it is valid.
9. Decision records using geography must preserve geographic version or boundary reference.
10. Agent actions with jurisdictional limits must preserve spatial scope and policy decision.

## Status

Draft. Canonical after governance review.
