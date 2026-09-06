# Specification: Tracking Topic Interview Skill responsibility

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.2-dogfood-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.3](compass-shared-contracts-specification.md); [Graph Schema 0.3](compass-graph-schema-specification.md)
- **Implementation authority:** None; responsibility specification only

## Purpose and owned outcome

Tracking Topic Interview helps the user express durable work organization in their own words. It owns proposals and user-authorized requests to create, refine, merge, align, unalign, archive, or reactivate Tracking Topics; to change Conversation-to-Topic alignment; and to change Topic-to-CSP alignment.

It owns organizational meaning and proposal completeness. It does not gain authority from a Daily Scan handoff and does not independently validate or apply graph changes.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| User intent | Direct request or answers about Topic meaning, wording, lifecycle, Conversation membership, or CSP relationship. |
| Optional Conversation context | Accepted graph content and minimized provenance needed to understand a proposed alignment. |
| Current graph context | Relevant Topics, CSPs, derived Conversation membership, and source-state evidence. |
| Organizational proposal | Exact wording, statuses, canonical relationships, retained history, and all material effects. |
| Change handoff | Shared-contract request containing every Topic, Conversation, CSP relationship, and Daily Log effect. |
| Interview result | Common terminal outcome and complete effect accounting. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| TOPIC-001 | Preserve the user's wording and distinguish direct instruction from AI suggestion. | `PR-AUTH-001`, `PR-INT-001` | Suggested names or meanings remain proposals until accepted. |
| TOPIC-002 | Represent Topic lifecycle only as `active` or `archived`; never delete a Topic. | `PR-HIST-001`, schema version 1 | Archive/reactivate retains the Topic and historical relationships. |
| TOPIC-003 | Change Conversation alignment only through the Conversation-owned `trackingTopicId`. | `PR-GRAPH-001` | No Topic-owned reverse membership list is created. |
| TOPIC-004 | Change CSP alignment only through the Topic-owned `cspId`. | `PR-GRAPH-001` | No CSP-owned reverse Topic list is created. |
| TOPIC-005 | Treat merge as an explicit multi-object proposal: retain one target Topic, realign approved Conversations, preserve the source Topic as archived, and never erase history. | `PR-HIST-001`, `PR-AUTH-001` | User sees and approves every retained, changed, and archived effect. |
| TOPIC-006 | Include all applicable Daily Log effects in the same change request. | `PR-GRAPH-001`, `PR-TRUTH-001` | Each changed object and relationship is represented once for the selected action date. |
| TOPIC-007 | Submit authorized requests to Graph Governor for pre-write validation and post-write verification. | `PR-SAFE-001`, `PR-TRUTH-001` | No unverified operation is reported as committed. |
| TOPIC-008 | Renew authority after any material change to wording, targets, relationships, or effects. | `PR-AUTH-001` | Prior approval is never stretched to a changed proposal. |

## Human interaction

Tracking Topic Interview should feel like collaborative sense-making, not taxonomy administration. Ask about meaning, boundaries, and usefulness in ordinary language. Present no more context than needed, use progressive choices with typed fallbacks, and let the user revise wording before seeing a concise final effect preview.

Do not ask the user to reason about filenames, YAML, cardinality, or transaction mechanics. Translate structural conflicts into recognizable consequences without hiding uncertainty.

## Authority, safety, and privacy boundaries

- A handoff may identify a Conversation worth organizing but cannot authorize its Topic alignment.
- Topic creation, merge, alignment, unalignment, archival, reactivation, and CSP alignment require an unambiguous direct instruction or explicit approval of the exact proposal.
- Topic status values `paused` and `completed` are not valid schema states; their meaning may be expressed in user-authored content or represented by `active`/`archived` only when the user chooses.
- Tracking Topic Interview cannot delete Topics, choose among ambiguous identities, rewrite Conversation evidence, modify configuration, or bypass Graph Governor.
- Only minimized context needed for the organizational decision enters the handoff.

## Handoffs and responsibility boundary

- **From Daily Scan:** approved Conversation context plus the user's request to organize it; no inherited alignment authority.
- **From Curator:** a review recommendation; no inherited modification authority.
- **To Graph Governor:** complete authorized multi-object request and source-state evidence.
- **To Daily Scan:** no control handoff; accepted relationships are visible later through canonical graph state.

Tracking Topic Interview does not own evidence retrieval, Conversation summarization, broad curation, integrity judgment, persistence mechanics, or recovery decisions.

## Failure, partial, blocked, and cancellation behavior

- Ambiguous Topic identity, CSP identity, merge target, or Conversation set blocks the affected proposal.
- A declined proposal is `rejected` and leaves graph state unchanged.
- An intervening edit produces `conflict`; the changed proposal returns for review.
- Cancellation preserves current graph state and reports whether any write was attempted.
- Synthetic multi-object failure may follow disposable-beta recovery. Connected partial or unverifiable effects stop as `recovery-required` for user-led resolution.

## Edge cases and unresolved questions

- Curator may provide latest recorded Compass activity derived from Daily Logs. It cannot drive lifecycle automatically; the user must confirm stale or completed meaning and approve the exact archival proposal.
- CSP retirement is outside this responsibility until a later contract exists.
- Person merge and Conversation deletion are outside this Skill.
- A future schema may define richer lifecycle language; this version uses only `active` and `archived`.

## Traceability and evaluation

- **Test plan:** [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Planned checks:** S3 authority/handoff probe, C2 write/recovery check, C3 privacy/authority check, and integrated synthetic rehearsal
- **Prior input:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Revision history

| Version | Date | Change | Motivation and impact |
| --- | --- | --- | --- |
| 0.1-beta-responsibility | 2026-09-02 | Reconciles prior Topic interaction with current lifecycle, relationship, Daily Log, authority, and Graph Governor contracts. | Accepted Slice B set; prior package remains immutable and untested. |

## Acceptance boundary

Acceptance would establish Tracking Topic Interview's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, graph writes, testing, deployment, or release.