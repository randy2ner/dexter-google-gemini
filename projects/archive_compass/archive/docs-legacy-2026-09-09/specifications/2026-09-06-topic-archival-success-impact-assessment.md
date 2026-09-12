# Change Impact Assessment: Topic archival success

## Document control

- **Date:** 2026-09-06
- **Status:** accepted
- **Owner:** User / product owner
- **Changed source/version:** [Graph Schema `0.4.1-archival-success-baseline`](compass-graph-schema-specification.md), object schema version 2
- **Motivation:** [Accepted archival-success decision](../decisions/2026-09-06-record-topic-archival-success.md)

## Change summary

Tracking Topic `success` records a required boolean outcome while archived. Active Topics permit absent or null success, and reactivation removes the field. This is a conditional schema-v2 field addition, not a schema-version migration.

## Impact map

| Dependent item | Impact | Required action |
| --- | --- | --- |
| PRD | affected | Record the accepted archival outcome requirement. |
| Graph Schema | affected | Define field type, lifecycle conditions, and reactivation removal. |
| Tracking Topic Interview | affected | Ask for, preview, and hand off exact success values; remove the field on reactivation. |
| Graph Governor | affected | Validate state combinations, authority, and post-write removal. |
| Lifecycle Orchestration | affected | Carry success through archival and merge-source archival handoffs. |
| Installation Interview | compatible | Active Topic creation may continue to omit the field. No source change. |
| Daily Scan | compatible | Does not own Topic archival. No source change. |
| Curator | compatible | Recommends review but does not choose lifecycle meaning or success. No source change. |
| Existing schema-v2 fixture and completed result | remains exact historical evidence | Preserve unchanged; create a focused additive fixture. |
| Prior packages | remain exact historical artifacts | Preserve unchanged and create new candidate versions only for changed Skills. |

## Smallest justified retest set

- Static parse and invariant checks for active-absent, active-null, archived-true, and archived-false Topics.
- Tracking Topic Interview archival prompt and exact preview.
- Merge-source archival with one explicit success value per source Topic.
- Graph Governor rejection of missing, null, string, and inconsistent archived values.
- Reactivation preview, write handoff, and post-write verification of field absence.

## Authorization boundary

Source, test-source, and candidate packaging updates are authorized by the product-owner request. Runtime execution, graph mutation, connected access, migration, promotion, and release remain unauthorized.