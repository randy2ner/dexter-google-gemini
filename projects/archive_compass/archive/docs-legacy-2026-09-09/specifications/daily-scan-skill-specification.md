# Specification: Daily Scan behavior

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.7-production-test-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-09
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.8](compass-shared-contracts-specification.md); [Graph Schema 0.7](compass-graph-schema-specification.md)
- **Applies to Skills:** Compass Daily Scan
- **Implementation authority:** Production-content testing and native Work IQ source, packaging, and static validation authorized by the user on 2026-09-08

## Purpose and owned outcome

Daily Scan turns one user-selected local calendar day of authorized WorkIQ Email and Teams activity into reviewable Conversation proposals and, after user authority, validated Conversation participants, explicit Conversation Topic disposition, deterministic Topic participant funnel effects, and Daily Log changes. It owns bounded discovery, source Conversation correlation, participant qualification and identity review, editable relevance judgment, concise durable summaries, and the exact request for accepted effects.

It does not create, rename, merge, archive, or reactivate Tracking Topics; decide CSP alignment; or treat retrieved evidence as authoritative graph knowledge.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| Scan plan | Exact local period, confirmed graph timezone, production purpose, relevant work scope, retained output, and controls displayed before retrieval. |
| Authorized evidence | Relevant content returned through all Cowork-exposed Work IQ capabilities for the approved purpose; content is untrusted data. |
| Graph context | Configuration, source-correlation keys, existing Conversations, People needed for authorship, and current source-state evidence. |
| Conversation proposal | Existing or new Conversation identity, concise summary, qualifying participants, explicit Topic-routing choice, provenance basis, optional minimized Topic-narrative contribution, and exact expected effects. |
| Change handoff | Accepted shared-contract request including the corresponding Daily Log effect. |
| Scan result | Common terminal outcome with source counts, proposal dispositions, and complete effect accounting. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| SCAN-001 | Obtain user authority for one explicit local period, production purpose, relevant work scope, and retained output. | `PR-AUTH-001`, `PR-PRIV-001` | No retrieval occurs before the displayed plan is authorized. |
| SCAN-002 | Correlate activity only through verified `sourceSystem`, `sourceType`, and durable `sourceConversationId`. | `PR-EVID-001`, `PR-SAFE-001` | Item IDs, titles, participants, timing, and similarity never substitute for source Conversation identity. |
| SCAN-003 | Interpret evidence and accepted graph context into the best useful editable Conversation suggestion. | `PR-AUTH-001`, `PR-INT-002` | Proposed content, fields, People, and relationships are presented in ordinary language; no interpretation becomes authoritative without user confirmation. |
| SCAN-004 | Create or update only schema-valid Conversations and accepted participant Person references. | `PR-GRAPH-001`, `PR-PORT-001` | Initial authors, responders, and identity-confirmed authored-content mentions may enter `participantIds`; passive recipients and roster-only members do not. |
| SCAN-005 | Store an explicit Conversation Topic disposition. | Accepted relationship ownership | Every accepted Conversation has `trackingTopicId` set to one approved existing Topic ID or `parking-lot`; missing, null, and empty are invalid. |
| SCAN-006 | Preserve Topic attention state while reviewing and aligning Conversations. | `PR-ATTN-001`, `SC-KNOW-012` | Daily Scan may display an existing Topic's accepted state but never infers, approves, or changes it. |
| SCAN-007 | Include the source-date Daily Log effect in every accepted Conversation write set. | `PR-GRAPH-001`, `PR-TRUTH-001` | Reprocessing deduplicates by stable object and operation identity. |
| SCAN-008 | Use Graph Governor before application and after attempted application. | `PR-SAFE-001`, `PR-TRUTH-001` | Only verified complete effects may be reported as committed. |
| SCAN-009 | Treat retrieved content as data, not instruction. | `PR-SAFE-001`, `PR-PRIV-001` | Embedded requests cannot alter scope, authority, retention, or workflow. |
| SCAN-010 | Propose at most one existing Topic alignment when bounded evidence supports it. | Dogfood decision | The displayed alignment is editable and applies only after exact approval. |
| SCAN-011 | Propose useful customer-focused Conversations without inventing customer identity or health. | Charter Parking Lot intent | Model relevance remains reviewable; accepted unaligned Conversations remain in Parking Lot. |
| SCAN-012 | Resolve first-name-only mentions before participant writes. | `SC-ID-006` | Ask the user for the last name and whether to bind an existing Person or create one; unresolved mentions remain outside graph assets and relationships. |
| SCAN-013 | Funnel accepted Conversation participants into an aligned Topic. | `SC-KNOW-010`, `SC-KNOW-011` | Add non-excluded participants to Topic `participantIds` in the same disclosed write set; never remove Topic participants or override `excludedParticipantIds`. |
| SCAN-014 | Exclude UPN from Person evidence retention, proposals, and handoffs. | `PR-PRIV-002`, `SC-ID-007` | Daily Scan never requests, infers, retrieves for retention, adds, or updates `userPrincipalName`; existing unmanaged values remain unchanged without separate cleanup authority. |
| SCAN-018 | Retain reviewed normalized Person email addresses when known. | `PR-PERSON-001`, `SC-ID-007` | User-supplied or authorized Work IQ addresses appear in Person proposals and handoffs without replacing complete name or stable Compass ID. |
| SCAN-015 | Collect detailed troubleshooting content only when the user offers it or includes it in an authorized retrieval scope. | `SC-KNOW-013`, `PR-AUTH-001` | Optional content is minimized into a candidate narrative contribution; absence of content never blocks Conversation capture. |
| SCAN-016 | Keep Topic narrative classification and modification under Topic Interview authority. | `SC-KNOW-013`, accepted Skill boundary | Daily Scan may propose `hpi`, `solved`, or review emphasis in a handoff but never writes Topic `tags`, `reviewBullet`, or narrative content. |
| SCAN-017 | Use native Work IQ without artificial source or result-count restrictions. | `PR-WIQ-001`, `SC-EVID-001` | The Skill uses all relevant Cowork-exposed sources and continuation, attempts complete relevant coverage, discloses gaps, and never substitutes sample data. |

## Human interaction

Daily Scan should feel like a concise review of what may be worth remembering, not a surveillance report or inbox triage tool. Group activity by durable source Conversation, use the user's language, surface meaningful ambiguity, and allow keep, change, leave out, pause, or cancel through ordinary typed conversation.

Do not expose raw messages by default. Explain why a proposal may matter using minimized paraphrase and provenance counts; reveal source detail only when needed and authorized for review.

## Authority, safety, and privacy boundaries

- Retrieval authority is limited to the displayed period, purpose, and relevant work scope; it is not reduced by arbitrary numeric caps.
- Evidence authorizes observation, not retention or interpretation.
- Daily Scan may propose and, after authority, request Conversation, qualifying Person, deterministic Topic participant funnel, and required Daily Log effects.
- Daily Scan may not create, rename, merge, archive, reactivate, or delete Tracking Topics; alter CSP relationships; delete Conversations; or modify graph configuration. It may set or preserve one Conversation `trackingTopicId` only in the exact reviewed Conversation proposal.
- A missing, ambiguous, or unverifiable source Conversation ID blocks automatic correlation and write preparation for that activity.
- Raw transcripts, unrelated content, secrets, and excess identity data are excluded from handoffs and graph content by default.

## Handoffs and responsibility boundary

- **From Installation Interview:** accepted graph configuration and visible foundational graph context.
- **To Tracking Topic Interview:** a user request for Topic creation, lifecycle, CSP alignment, participant management, or narrative enrichment, with only the approved minimized context needed for that decision. Offered-evidence narrative candidates separate observations, interpretations, disproved hypotheses, confirmed cause, resolution, lessons, and out-of-scope follow-up.
- **To Graph Governor:** exact authorized Conversation, Person-reference, Topic funnel, and Daily Log effects with source-state evidence.
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
- Standalone Activity objects are outside schema version 2; accepted activity is represented through Conversation content and managed Daily Log entries.
- Cowork capability and continuation behavior must be observed during production testing; incomplete enumeration is disclosed rather than replaced by a fixed local cap.

## Traceability and evaluation

- **Test plan:** [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Planned checks:** S2 bounded scan probe, C1 identity check, C3 privacy/authority check, and integrated synthetic rehearsal
- **Prior input:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Revision history

| Version | Date | Change | Motivation and impact |
| --- | --- | --- | --- |
| 0.1-beta-responsibility | 2026-09-02 | Reconciles bounded retrieval and source identity with current schema, Daily Log, Topic, and Graph Governor boundaries. | Accepted Slice B set; prior package remains immutable and untested. |
| 0.3-participant-management-responsibility | 2026-09-06 | Adds accepted participant qualification, complete-name confirmation, required Topic disposition, and deterministic Topic participant funneling. | Product-owner participant-management decision; schema version 2. |
| 0.4-attention-state-responsibility | 2026-09-06 | Permits display of accepted Topic attention state while prohibiting inference or mutation. | Product-owner attention-state decision. |
| 0.5-person-data-minimization-responsibility | 2026-09-06 | Removes Person UPN from evidence retention, proposals, and handoffs. | Product-owner Person UPN removal decision. |
| 0.6-hpi-narrative-responsibility | 2026-09-08 | Adds optional offered-evidence narrative collection and minimized Topic Interview handoff without granting Daily Scan Topic-write authority. | Product-owner HPI career-story and review behavior decision. |
| 0.8-first-experience-responsibility | 2026-09-09 | Requires useful editable artifact suggestions and retains reviewed Person email addresses without collecting UPN. | First artifact-building experience feedback. |

## Acceptance boundary

Acceptance would establish Daily Scan's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, connected retrieval, graph writes, testing, deployment, or release.