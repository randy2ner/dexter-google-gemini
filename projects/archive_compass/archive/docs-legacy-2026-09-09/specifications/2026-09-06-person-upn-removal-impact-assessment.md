# Change Impact Assessment: Person UPN removal

## Document control

- **Date:** 2026-09-06
- **Status:** accepted
- **Owner:** User / product owner
- **Changed source/version:** [Graph Schema `0.6-person-data-minimization-baseline`](compass-graph-schema-specification.md), object schema version 2
- **Motivation:** [Accepted Person UPN removal decision](../decisions/2026-09-06-stop-collecting-person-upn.md)

## Change summary

Current schema-version-2 Person data no longer includes `userPrincipalName`. Compass Skills do not request, infer, retrieve UPN for retention, add it, or update it. Stable Compass Person ID remains authoritative, complete names remain required, and optional normalized email addresses remain available only for source correlation. This removes an optional managed field and does not increment the object schema version.

Existing UPN values become unmanaged frontmatter. Unrelated writes preserve them; removal requires separately disclosed user authority and is not authorized by this change.

## Impact map

| Dependent item | Impact | Required action |
| --- | --- | --- |
| PRD and traceability | affected | Record accepted Person data minimization and evidence boundary. |
| Shared Contracts and Graph Schema | affected | Remove UPN from managed Person data and define existing-value preservation. |
| Installation Interview | affected | Omit UPN from foundational Person collection and proposals. |
| Daily Scan | affected | Omit UPN from evidence-derived Person proposals and handoffs. |
| Tracking Topic Interview | affected | Omit UPN when creating or binding participant People. |
| Graph Governor | affected | Reject proposed effects that introduce or update UPN; preserve pre-existing unmanaged values. |
| Lifecycle Orchestration | affected | Carry only minimized Person data through writer-to-Governor handoffs. |
| Curator | compatible | Reads accepted graph state and creates no Person data; no source change. |
| Existing schema-v2 fixtures | compatible | No current focused fixture contains UPN; validate absence without rewriting completed evidence. |
| Preserved schema-v1 contract and prior packages | historical | Preserve unchanged and version-bound. |

## Smallest justified retest set

- Static source inspection showing no current Person field definition permits UPN.
- Package inspection for the three Person writers and Graph Governor.
- Negative proposal check: new or updated Person effect containing `userPrincipalName` is invalid.
- Preservation check: unrelated update does not remove a pre-existing unmanaged value.
- Retrieval-minimization and conversational checks only after separate runtime authorization.

## Authorization boundary

Source, documentation, test-source, and candidate packaging updates are authorized by the product-owner request. Runtime execution, graph mutation, cleanup of existing values, connected access, migration, promotion, and release remain unauthorized.