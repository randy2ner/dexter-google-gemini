# Change Impact Assessment: Participant and Topic management

## Document control

- **Date:** 2026-09-06
- **Status:** accepted
- **Owner:** User / product owner
- **Changed source/version:** [Shared Contracts and Graph Schema `0.4-participant-management-baseline`](compass-shared-contracts-specification.md)
- **Motivation:** [Accepted participant-management decision](../decisions/2026-09-06-accept-participant-and-topic-management.md)

## Change summary

Schema version 2 replaces Conversation active-author-only links with accepted participant links, requires complete Person names and explicit Topic disposition, and adds persistent Topic participant and exclusion state. The change is semantic and breaking; it is not an editorial extension to schema version 1.

## Impact map

| Dependent item | Current version/evidence | Impact | Required action |
| --- | --- | --- | --- |
| PRD | `0.2` | affected | Add accepted feature requirements and preserve provisional Charter states. |
| Shared Contracts / Graph Schema | `0.3-beta-baseline`, schema 1 | affected | Adopt `0.4` and schema 2; preserve v1 history. |
| Installation Interview | `0.2.3` | affected | Require complete names and reviewed initial Topic participants. |
| Daily Scan | `0.2.0` | affected | Qualify participants, confirm names, write explicit disposition, and funnel participants. |
| Tracking Topic Interview | `0.2.0` | affected | Own participant add/remove/re-add and exclusion state. |
| Curator | `0.2.0` | affected | Recommend participant review without applying changes. |
| Graph Governor | `0.3.0` | affected | Validate schema-v2 fields, ownership, identities, sentinel, and touched closure. |
| Lifecycle Orchestration | `0.2.0` | affected | Coordinate the new interactions and handoffs. |
| Completed test results and packages | Through package set `0.3.3` | still applicable only to exact prior specimens | Preserve unchanged; transfer no confidence to v2. |
| Schema-v1 fixtures | Existing beta and Governor fixtures | still applicable as historical/regression inputs | Preserve; create separate schema-v2 source fixture. |

## Evidence disposition

- **Still applicable:** Completed results remain direct evidence for their exact schema-v1 packages and environments.
- **Invalidated or uncertain:** No prior result establishes schema-v2 participant qualification, Topic persistence/exclusion, complete-name prompting, or explicit Parking Lot behavior.

## Smallest justified retest set

| Test | Reason | Decision enabled |
| --- | --- | --- |
| [Participant-management schema scenario](../scenarios/compass-participant-management-schema-v2.md) | Exercises the new fields and negative identity/disposition cases. | Static candidate readiness. |
| Installation focused interaction | Confirms complete-name and initial participant review. | Installation candidate usability. |
| Daily Scan plus Topic Interview integration | Confirms funnel, removal suppression, and re-add. | Cross-Skill behavior readiness. |
| Graph Governor pre/post validation | Confirms enforcement and effect accounting. | Write-candidate readiness. |

## Excluded regression

- Protected-source Installation behavior is unchanged except for generated graph schema and does not require repeating source-classification discovery before static validation.
- Historical Graph Governor schema-v1 scenario results are not rerun or rewritten.
- Connected Microsoft 365 and personal-graph migration are excluded until separately authorized.

## Authorization required

The user authorized coordinated source and static-validation work on 2026-09-06. Runtime execution, connected access, migration of an existing graph, packaging promotion, deployment, and release remain separately authorized actions.