# Test plan: HPI Topic narrative and review metadata

## Metadata

- **Owner:** User / product owner
- **Date:** 2026-09-08
- **Status:** active; static construction and packaging authorized, Cowork execution not yet observed
- **Contract:** Shared Contracts and Graph Schema `0.7-hpi-narrative-baseline`, object schema version `2`
- **Scenario:** [HPI narrative lifecycle](../scenarios/2026-09-08-hpi-narrative-lifecycle.md)
- **Fixture:** [Sanitized HPI samples](../test-results/2026-09-08-hpi-narrative-samples/README.md)

## Goals

- Verify optional detailed Topic content can be built from user-offered or explicitly authorized evidence without becoming raw evidence storage.
- Verify `tags` and `reviewBullet` frontmatter, independence from lifecycle fields, and preservation across unrelated changes.
- Verify Skill ownership from Daily Scan handoff through Topic Interview approval, Curator bullet, and Governor validation.
- Verify follow-up ideas remain archived context and never trigger another Topic prompt without user initiation.

## Static cases

| ID | Case | Expected result |
| --- | --- | --- |
| HPI-STATIC-001 | Parse the seven sample objects and resolve all IDs. | One CSP, four People, one Conversation, and one Topic validate; Conversation and Topic participants match; Topic and CSP links resolve. |
| HPI-STATIC-002 | Inspect solved-HPI metadata. | `tags` is exactly a unique normalized list containing `hpi` and `solved`; `reviewBullet` is boolean `true`; archived `success: true` and `attentionState: waiting` remain independent. |
| HPI-STATIC-003 | Inspect narrative structure and minimization. | Applicable sections exist; no raw transcript, bridge link, phone number, end-user ID, or real Person identity is retained. |
| HPI-STATIC-004 | Mutate tags independently: duplicate, uppercase, scalar, empty item. | Graph Governor returns `invalid` for each fresh mutation and changes nothing. |
| HPI-STATIC-005 | Mutate `reviewBullet` to a string, number, and null. | Graph Governor returns `invalid`; absence remains valid and creates no required Curator bullet. |
| HPI-STATIC-006 | Change an unrelated Topic relationship. | Tags, review flag, narrative, and unmanaged content remain unchanged. |
| HPI-STATIC-007 | Scan active source for ownership contradictions. | Daily Scan cannot write Topic content; Topic Interview owns it; Curator is read-only; Governor does not originate changes. |

## Mediated experience claims

| ID | Claim | Observable evidence |
| --- | --- | --- |
| HPI-EXP-001 | Daily Scan accepts optional offered detail without requiring it. | User can skip detail or offer bounded content; retained candidate is minimized and clearly provisional. |
| HPI-EXP-002 | Topic Interview builds a coherent story. | Preview distinguishes facts, interpretation, disproved hypothesis, cause, resolution, contribution, lessons, and follow-up boundary. |
| HPI-EXP-003 | Approval covers exact content and metadata. | Preview shows material narrative sections, `hpi`, `solved`, `reviewBullet: true`, archived success, waiting state, CSP and participant effects. |
| HPI-EXP-004 | Governor protects frontmatter and content. | Pre-write result validates exact fields and authority; post-write verification confirms effects and preservation without claiming story truth. |
| HPI-EXP-005 | Curator renders the intended career-memory bullet. | Exactly one bullet appears for the HPI Topic and no new-Topic prompt appears. |

## Entry criteria

- Exact candidate Skill packages and hashes are recorded.
- Static sample and package checks pass.
- The user runs the experience in an approved Cowork client against only a disposable synthetic graph.
- Any Work IQ use receives a separately displayed bounded read-only authorization; the supplied sanitized case study may be used instead.

## Stop conditions

- A Skill requests or reveals raw work content, real identities, credentials, links, or unrelated graph data.
- Daily Scan writes Topic content or Topic Interview retrieves evidence independently.
- Curator infers a review bullet or proposes a follow-up Topic without user initiation.
- Governor treats narrative plausibility as structural validity or reports an unverified write as committed.
- A connected write becomes partial or unverifiable.

## Exit criteria

- Static cases have immutable results tied to exact source and fixture revisions.
- One mediated experience records prompts and operator-reported responses without work content.
- Curator emits one expected bullet; Governor accounts for all effects; no new Topic is proposed.
- Confidence remains bounded to the exact packages, synthetic graph, and observed surface.
