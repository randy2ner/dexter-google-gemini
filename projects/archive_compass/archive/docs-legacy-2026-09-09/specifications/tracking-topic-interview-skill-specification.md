# Specification: Tracking Topic Interview behavior

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.7-production-test-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-09
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.8](compass-shared-contracts-specification.md); [Graph Schema 0.7](compass-graph-schema-specification.md)
- **Applies to Skills:** Compass Tracking Topic Interview
- **Implementation authority:** Production-content testing and native Work IQ source, packaging, and static validation authorized by the user on 2026-09-08

## Purpose and owned outcome

Tracking Topic Interview helps the user express durable work organization and career memory in their own words. It owns proposals and user-authorized requests to create, refine, merge, align, move to Parking Lot, archive, or reactivate Tracking Topics; change Conversation-to-Topic disposition; change Topic-to-CSP alignment; add, remove, or re-add Topic participants; compose or revise Topic narratives from offered minimized evidence; and set Topic `tags` and `reviewBullet`.

It owns organizational meaning and proposal completeness. It does not gain authority from a Daily Scan handoff and does not independently validate or apply graph changes.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| User intent | Direct request or answers about Topic meaning, wording, lifecycle, Conversation membership, participant management, or CSP relationship. |
| Optional Conversation context | Accepted graph content and minimized provenance needed to understand a proposed alignment. |
| Current graph context | Relevant Topics, CSPs, derived Conversation membership, and source-state evidence. |
| Organizational proposal | Exact wording, statuses, canonical relationships, retained history, and all material effects. |
| Change handoff | Shared-contract request containing every Topic, Conversation, CSP relationship, and Daily Log effect. |
| Interview result | Common terminal outcome and complete effect accounting. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| TOPIC-001 | Interpret direct input, accepted graph context, and authorized Work IQ into the best useful editable Topic artifact suggestion. | `PR-AUTH-001`, `PR-INT-002` | Suggested wording, narrative, fields, People, and relationships are presented in ordinary language and remain proposals until accepted. |
| TOPIC-002 | Represent Topic lifecycle only as `active` or `archived`; never delete a Topic. | `PR-HIST-001`, schema version 2 | Archive/reactivate retains the Topic and historical relationships. |
| TOPIC-003 | Change Conversation alignment only through the Conversation-owned `trackingTopicId`. | `PR-GRAPH-001` | No Topic-owned reverse membership list is created. |
| TOPIC-004 | Change CSP alignment only through the Topic-owned `cspId`. | `PR-GRAPH-001` | No CSP-owned reverse Topic list is created. |
| TOPIC-005 | Treat merge as an explicit multi-object proposal: retain one target Topic, realign approved Conversations, preserve the source Topic as archived, and never erase history. | `PR-HIST-001`, `PR-AUTH-001` | User sees and approves every retained, changed, and archived effect. |
| TOPIC-006 | Include all applicable Daily Log effects in the same change request. | `PR-GRAPH-001`, `PR-TRUTH-001` | Each changed object and relationship is represented once for the selected action date. |
| TOPIC-007 | Submit authorized requests to Graph Governor for pre-write validation and post-write verification. | `PR-SAFE-001`, `PR-TRUTH-001` | No unverified operation is reported as committed. |
| TOPIC-008 | Renew authority after any material change to wording, targets, relationships, or effects. | `PR-AUTH-001` | Prior approval is never stretched to a changed proposal. |
| TOPIC-009 | Add, remove, or re-add Topic participants only through exact user authority. | `SC-KNOW-010`, `SC-KNOW-011` | Add writes `participantIds`; remove moves the ID to `excludedParticipantIds`; re-add reverses both fields. |
| TOPIC-010 | Require complete Person names before participant relationships. | `SC-ID-006` | A first-name-only request prompts for last name and existing-or-new identity confirmation before Person creation or binding. |
| TOPIC-011 | Preserve Topic participant memory independently of Conversation lifecycle. | `PR-HIST-001` | Conversation staleness, removal, deletion, or reassignment never prunes Topic participants. |
| TOPIC-012 | Record an explicit boolean success outcome whenever a Topic is archived and remove it when the Topic is reactivated. | `PR-HIST-002`, schema version 2 | Archive proposals include `success: true` or `success: false`; active Topics have null or absent success, and reactivation removes the field. |
| TOPIC-013 | Own explicit Topic attention-state creation and change. | `PR-ATTN-001`, `SC-KNOW-012` | Every Topic has `action`, `waiting`, or `observing`; archival retains it and reactivation confirms or changes it. |
| TOPIC-014 | Exclude UPN when creating or binding Topic participants. | `PR-PRIV-002`, `SC-ID-007` | Topic Interview never requests, infers, retrieves for retention, adds, or updates `userPrincipalName`; existing unmanaged values remain unchanged without separate cleanup authority. |
| TOPIC-019 | Retain reviewed normalized Person email addresses when known. | `PR-PERSON-001`, `SC-ID-007` | User-supplied or authorized Work IQ addresses appear in Person proposals and handoffs without replacing complete name or stable Compass ID. |
| TOPIC-015 | Compose detailed Topic narratives only from user-offered content, accepted graph state, or minimized authorized handoffs. | `SC-KNOW-013`, `PR-AUTH-001` | The proposal distinguishes evidence, interpretation, disproved hypotheses, cause, resolution, contribution, lessons, and out-of-scope follow-up; exact material text requires user approval. |
| TOPIC-016 | Own optional Topic `tags` and `reviewBullet` changes. | `SC-KNOW-013`, schema version 2 | Tags are unique lowercase kebab-case strings; `reviewBullet` is boolean; `hpi` and `solved` never silently determine lifecycle, success, or attention state. |
| TOPIC-017 | Respect user-declared Topic boundaries for follow-up ideas. | `SC-KNOW-013` | Follow-up may be retained in the archived narrative, but the Skill does not suggest, ask about, or create another Topic unless the user initiates it. |
| TOPIC-018 | Use native Work IQ when the user authorizes a Topic-specific evidence purpose. | `PR-WIQ-001`, `SC-EVID-001` | The Skill uses all relevant Cowork-exposed sources and continuation without arbitrary numeric caps or sample substitution, reports gaps, and keeps derived meaning under exact user approval. |

## Human interaction

Tracking Topic Interview should feel like collaborative sense-making, not taxonomy administration. Ask about meaning, boundaries, and usefulness in ordinary language. Present no more context than needed, use progressive choices with typed fallbacks, and let the user revise wording before seeing a concise final effect preview.

Do not ask the user to reason about filenames, YAML, cardinality, or transaction mechanics. Translate structural conflicts into recognizable consequences without hiding uncertainty.

## Authority, safety, and privacy boundaries

- A handoff may identify a Conversation worth organizing but cannot authorize its Topic alignment.
- Topic creation, attention-state change, merge, alignment, Parking Lot movement, archival, reactivation, CSP alignment, and participant add/remove/re-add require an unambiguous direct instruction or explicit approval of the exact proposal. Every creation includes attention state; every archival includes the user's explicit success choice; reactivation confirms or changes retained attention state.
- Topic status values `paused` and `completed` are not valid schema states; their meaning may be expressed in user-authored content or represented by `active`/`archived` only when the user chooses.
- Tracking Topic Interview cannot delete Topics, choose among ambiguous identities, rewrite Conversation evidence, modify configuration, or bypass Graph Governor.
- Only minimized context needed for the organizational decision enters the handoff.

## Handoffs and responsibility boundary

- **From Daily Scan:** approved Conversation context plus the user's request to organize it; no inherited alignment authority.
- **From Curator:** a review recommendation; no inherited modification authority.
- **To Graph Governor:** complete authorized multi-object request, including Person, participant, exclusion, Topic-disposition, and Daily Log effects, plus source-state evidence.
- **To Daily Scan:** no control handoff; accepted relationships are visible later through canonical graph state.

Tracking Topic Interview may retrieve Microsoft 365 evidence only for an explicitly authorized Topic purpose. It does not perform unrelated discovery, broad curation, make integrity judgments, control persistence, or decide recovery. It may also consume user-offered content and minimized Daily Scan narrative handoffs.

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
| 0.3-participant-management-responsibility | 2026-09-06 | Adds Topic participant add/remove/re-add, exclusion persistence, complete-name confirmation, and explicit Parking Lot disposition. | Product-owner participant-management decision; schema version 2. |
| 0.4-attention-state-responsibility | 2026-09-06 | Adds explicit action, waiting, or observing state independently of lifecycle, success, and participation. | Product-owner attention-state decision. |
| 0.5-person-data-minimization-responsibility | 2026-09-06 | Removes Person UPN from participant creation, binding, proposals, and handoffs. | Product-owner Person UPN removal decision. |
| 0.6-hpi-narrative-responsibility | 2026-09-08 | Adds durable Topic career narratives, optional tags and review bullets, and explicit out-of-scope follow-up boundaries. | Product-owner HPI interview decision. |
| 0.8-first-experience-responsibility | 2026-09-09 | Requires useful editable artifact suggestions and retains reviewed Person email addresses without collecting UPN. | First artifact-building experience feedback. |

## Acceptance boundary

Acceptance would establish Tracking Topic Interview's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, graph writes, testing, deployment, or release.