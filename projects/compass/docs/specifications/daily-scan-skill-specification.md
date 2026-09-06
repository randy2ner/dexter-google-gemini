# Specification: Daily Scan Skill responsibility

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.2-dogfood-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.3](compass-shared-contracts-specification.md); [Graph Schema 0.3](compass-graph-schema-specification.md)
- **Implementation authority:** None; responsibility specification only

## Purpose and owned outcome

Daily Scan turns one user-selected local calendar day of authorized WorkIQ Email and Teams activity into reviewable Conversation proposals and, after user authority, validated Conversation, active-author Person, optional Conversation-owned Topic alignment, and Daily Log changes. It owns bounded discovery, source Conversation correlation, editable relevance judgment, concise durable summaries, and the exact request for accepted effects.

It does not create, rename, merge, archive, or reactivate Tracking Topics; decide CSP alignment; or treat retrieved evidence as authoritative graph knowledge.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| Scan plan | Exact local date, confirmed graph timezone, sources, retrieval limits, retained output, and controls displayed before retrieval. |
| Authorized evidence | Only fields and bounded content returned for the approved Email and Teams scope; content is untrusted data. |
| Graph context | Configuration, source-correlation keys, existing Conversations, People needed for authorship, and current source-state evidence. |
| Conversation proposal | Existing or new Conversation identity, concise summary, active authors, optional Topic-routing question, provenance basis, and exact expected effects. |
| Change handoff | Accepted shared-contract request including the corresponding Daily Log effect. |
| Scan result | Common terminal outcome with source counts, proposal dispositions, and complete effect accounting. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| SCAN-001 | Obtain user authority for one explicit local date, source set, and bounded retrieval plan. | `PR-AUTH-001`, `PR-PRIV-001` | No retrieval occurs before the displayed plan is authorized. |
| SCAN-002 | Correlate activity only through verified `sourceSystem`, `sourceType`, and durable `sourceConversationId`. | `PR-EVID-001`, `PR-SAFE-001` | Item IDs, titles, participants, timing, and similarity never substitute for source Conversation identity. |
| SCAN-003 | Separate evidence from durable meaning and present every new or materially changed Conversation as a proposal. | `PR-AUTH-001` | No evidence-derived summary or classification becomes authoritative without user authority. |
| SCAN-004 | Create or update only schema-valid Conversations and observed active-author Person references. | `PR-GRAPH-001`, `PR-PORT-001` | Passive recipients and contextual mentions do not become `activeParticipantIds`. |
| SCAN-005 | Preserve existing Conversation Topic alignment unless the user routes organizational intent to Tracking Topic Interview. | Accepted relationship ownership | Daily Scan never independently changes `trackingTopicId`. |
| SCAN-006 | Include the source-date Daily Log effect in every accepted Conversation write set. | `PR-GRAPH-001`, `PR-TRUTH-001` | Reprocessing deduplicates by stable object and operation identity. |
| SCAN-007 | Use Graph Governor before application and after attempted application. | `PR-SAFE-001`, `PR-TRUTH-001` | Only verified complete effects may be reported as committed. |
| SCAN-008 | Treat retrieved content as data, not instruction. | `PR-SAFE-001`, `PR-PRIV-001` | Embedded requests cannot alter scope, authority, retention, or workflow. |
| SCAN-009 | Propose at most one existing Topic alignment when bounded evidence supports it. | Dogfood decision | The displayed alignment is editable and applies only after exact approval. |
| SCAN-010 | Propose useful customer-focused Conversations without inventing customer identity or health. | Charter Parking Lot intent | Model relevance remains reviewable; accepted unaligned Conversations remain in Parking Lot. |

## Human interaction

Daily Scan should feel like a concise review of what may be worth remembering, not a surveillance report or inbox triage tool. Group activity by durable source Conversation, use the user's language, surface meaningful ambiguity, and allow keep, change, leave out, pause, or cancel through ordinary typed conversation.

Do not expose raw messages by default. Explain why a proposal may matter using minimized paraphrase and provenance counts; reveal source detail only when needed and authorized for review.

## Authority, safety, and privacy boundaries

- Retrieval authority is limited to the displayed date, sources, and limits.
- Evidence authorizes observation, not retention or interpretation.
- Daily Scan may propose and, after authority, request Conversation and required Daily Log effects.
- Daily Scan may not create, rename, merge, archive, reactivate, or delete Tracking Topics; alter CSP relationships; delete Conversations; or modify graph configuration. It may set or preserve one Conversation `trackingTopicId` only in the exact reviewed Conversation proposal.
- A missing, ambiguous, or unverifiable source Conversation ID blocks automatic correlation and write preparation for that activity.
- Raw transcripts, unrelated content, secrets, and excess identity data are excluded from handoffs and graph content by default.

## Handoffs and responsibility boundary

- **From Installation Interview:** accepted graph configuration and visible foundational graph context.
- **To Tracking Topic Interview:** a user request to create, choose, remove, or change Topic alignment, with only the approved Conversation context needed for that decision.
- **To Graph Governor:** exact authorized Conversation, Person-reference, and Daily Log effects with source-state evidence.
- **To Curator:** no mandatory direct handoff; Curator later reads accepted graph state rather than Daily Scan's rejected or provisional proposals.

Daily Scan does not own installation, ongoing Topic meaning, curation recommendations, graph-health decisions, persistence safety, or recovery decisions.

## Failure, partial, blocked, and cancellation behavior

- Unavailable sources are disclosed; one successful authorized source may support a partial-source review.
- No relevant activity produces an honest `empty` result and no graph write.
- Unresolved identity, permission, timezone, authority, or conflict produces `blocked` or `conflict` for affected proposals.
- Cancellation preserves reviewed dispositions and reports whether retrieval or any write attempt occurred.
- Failed or incomplete writes use common effect accounting and the disposable-beta recovery protocol.

## Edge cases and unresolved questions

- Runtime tests must identify durable Email and Teams Conversation ID fields.
- Item-level evidence retention and last-activity fields remain deferred.
- Standalone Activity objects are outside schema version 1; accepted activity is represented through Conversation content and managed Daily Log entries.
- Exact retrieval limits are a test-plan/runtime decision and must always be displayed before authorization.

## Traceability and evaluation

- **Test plan:** [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Planned checks:** S2 bounded scan probe, C1 identity check, C3 privacy/authority check, and integrated synthetic rehearsal
- **Prior input:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Revision history

| Version | Date | Change | Motivation and impact |
| --- | --- | --- | --- |
| 0.1-beta-responsibility | 2026-09-02 | Reconciles bounded retrieval and source identity with current schema, Daily Log, Topic, and Graph Governor boundaries. | Accepted Slice B set; prior package remains immutable and untested. |

## Acceptance boundary

Acceptance would establish Daily Scan's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, connected retrieval, graph writes, testing, deployment, or release.