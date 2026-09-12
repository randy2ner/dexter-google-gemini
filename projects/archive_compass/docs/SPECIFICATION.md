# Compass Specification

## Document control

- **Status:** active
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-09
- **Last updated:** 2026-09-09
- **Implementation authority:** Ordinary repository work explicitly requested by the user. Connected retrieval, durable writes, production use, release, deployment, sharing, and destructive changes require their own user authority.
- **Test Plan:** [TEST-PLAN.md](TEST-PLAN.md)

## Purpose and outcomes

Compass helps an individual Microsoft 365 Copilot user turn approved everyday-work evidence into durable, user-controlled work memory represented by a portable knowledge graph. It must preserve useful context, make changes and attention needs visible, reduce manual capture and recovery, and keep AI interpretation reviewable before it becomes trusted knowledge.

The intended first user manages Customer Success Plans (CSPs), Tracking Topics, People, Conversations, and changing work context. Compass is a collection of coordinated Copilot Skills, not a standalone application or multi-user control plane.

## Core product boundaries

1. Evidence and AI interpretation do not become authoritative graph knowledge without user authority.
2. Graph content remains readable and editable as Markdown and YAML outside Compass.
3. Normal lifecycle behavior preserves retained history. A Tracking Topic is never deleted; Conversation deletion is separately reviewed and approved.
4. Partial, uncertain, blocked, rolled-back, and failed work is never reported as successful.
5. Artifact-producing Skills interpret direct input, accepted graph context, and authorized Work IQ; offer an editable informed suggestion; and obtain confirmation before writing. They ask follow-up questions only for material ambiguity that cannot be represented safely.
6. Retrieval and retention minimize sensitive evidence. Raw messages, transcripts, unnecessary identities, tenant information, and identifying work content are not retained by default.
7. Connected access, durable effects, release, and deployment remain under explicit user control.

## Requirements

| ID | Requirement and success criterion | Status |
| --- | --- | --- |
| SPEC-AUTH-001 | No evidence-derived interpretation becomes trusted knowledge without an unambiguous instruction or confirmation of the displayed proposal. | accepted |
| SPEC-PORT-001 | Authoritative knowledge is inspectable, readable, and validly editable without Compass. | accepted |
| SPEC-HIST-001 | Lifecycle changes preserve retained history; archival does not delete a Topic. | accepted |
| SPEC-HIST-002 | Archived Topics contain boolean `success`; active Topics omit it or set it null; reactivation removes it. | accepted |
| SPEC-TRUTH-001 | Terminal reports distinguish completed, unapplied, partial, uncertain, blocked, and failed effects. | accepted |
| SPEC-INT-001 | Routine workflows ask only about meaningful ambiguity and remain understandable without schema or file-mechanics expertise. | proposed |
| SPEC-INT-002 | Artifact-building Skills propose useful content, fields, and relationships in ordinary language and let the user confirm, revise, or reject them. | accepted |
| SPEC-PRIV-001 | Retrieval, presentation, and retention are purpose-bounded and retain minimized provenance rather than raw source content by default. | proposed |
| SPEC-EVID-001 | Every durable Conversation retains its authorized Microsoft 365 source Conversation identity. | proposed pending runtime verification |
| SPEC-WIQ-001 | Within an approved purpose, Skills use all relevant Work IQ source and continuation capabilities exposed by Cowork, disclose gaps, impose no arbitrary result cap, and never substitute sample evidence. | accepted |
| SPEC-GRAPH-001 | The graph represents CSPs, Tracking Topics, People, Conversations, and Daily Logs in portable Markdown/YAML with accepted relationships. | accepted |
| SPEC-SAFE-001 | Ambiguous identity, authority, conflict, permission, recovery, or effect state stops the affected write. | accepted |
| SPEC-TEST-001 | Confidence is limited to dated observations for exact candidate and environment versions in the Test Plan. | accepted |
| SPEC-PART-001 | Conversation participants include accepted authors/responders and user-confirmed authored-content mentions, not passive recipients or roster-only members. | accepted |
| SPEC-TOPIC-001 | Topics retain persistent participant lists; accepted Conversation participants funnel in, explicit removals resist automatic re-add, and unrelated changes do not prune participants. | accepted |
| SPEC-PARK-001 | Every Conversation has exactly one Topic ID or `parking-lot` disposition; Parking Lot is a derived view, not an object. | accepted |
| SPEC-ATTN-001 | Every Topic has user-authorized `attentionState`: `action`, `waiting`, or `observing`. | accepted |
| SPEC-PRIV-002 | Compass does not request, infer, or retain Microsoft 365 UPN as managed Person data. | accepted |
| SPEC-PERSON-001 | Reviewed normalized email addresses are useful Person attributes but never replace stable Compass identity or complete name. | accepted |
| SPEC-NARR-001 | A Topic may retain an optional user-approved career or troubleshooting narrative that separates evidence, interpretation, disproved hypotheses, cause, resolution, contribution, lessons, and out-of-scope follow-up. | accepted |
| SPEC-HIGHLIGHT-001 | Optional lowercase-kebab `tags` and boolean `reviewBullet` classify Topics and deterministically include review bullets without inferring lifecycle state. | accepted |
| SPEC-RECENCY-001 | Topics and Conversations will record timezone-explicit UTC `updatedAt` for their latest verified durable change, without conflating source activity or user attention. | proposed, not implemented |
| SPEC-REVIEW-001 | Compass will identify items matching disclosed user-approved review criteria without changing them, then route Conversations to purge decisions and Topics to archive decisions. | proposed, not implemented |

## Skills and orchestration

| Component | Responsibility | Durable authority |
| --- | --- | --- |
| Compass Installation Interview | Establish user context and propose initial CSPs, Topics, People, configuration, and graph structure from direct answers and relevant authorized Work IQ. Verify the approved configuration as the first write; create no disposable probe. | Only the exact confirmed setup proposal. |
| Compass Daily Scan | Review a user-approved period and purpose, retrieve relevant Work IQ, group activity by source Conversation identity, and propose Conversations, participants, Topic disposition, and minimized narrative contributions. | Only reviewed Conversation proposals and disclosed deterministic participant funneling. |
| Compass Tracking Topic Interview | Create and manage Topics, participant inclusion/exclusion, attention, lifecycle, CSP alignment, and user-approved narrative. It owns Topic-focused Work IQ discovery and refresh. | Only unambiguous direct instructions or confirmed Topic proposals. |
| Compass Curator | Read the graph, apply bounded review criteria, distinguish graph observation from Work IQ context and interpretation, and recommend changes. | Read-only; it never writes. |
| Graph Governor | Validate authority, schema, identity, relationships, preservation, paths, expected effects, and post-write state. | It chooses no meaning, retrieves no Work IQ, and permits only validated authorized effects. |
| Compass work-memory lifecycle | Coordinate setup, capture, Topic management, review, validation, persistence, and effect reporting across the five Skills. | It adds no authority beyond the initiating user decision and each Skill boundary. |

Every graph modification identifies one accountable initiating Skill. Read access never implies write authority. A handoff carries initiating Skill, authority source, operation, stable targets, expected effects, minimized provenance, base state, approval reference, and correlation identity. Missing consequential intent blocks the operation.

## Graph contract

Each managed object is one Markdown file with YAML frontmatter. Compass-managed fields use `camelCase`; timestamps use timezone-explicit UTC ISO 8601; stable IDs survive title, filename, and folder changes. Unknown frontmatter and unmanaged Markdown are preserved unless they prevent safe parsing.

All objects require `schemaVersion: 2`, one of the five accepted `type` values, stable `id`, non-empty `title`, and immutable `createdAt`.

| Object | Required managed behavior |
| --- | --- |
| Conversation | `sourceSystem: microsoft-365`; `sourceType: chat` or `email`; durable `sourceConversationId`; unique `participantIds`; and exactly one `trackingTopicId` containing a Topic ID or `parking-lot`. |
| Tracking Topic | `status: active` or `archived`; conditional boolean `success`; one `attentionState`; optional `cspId`; unique and disjoint `participantIds` and `excludedParticipantIds`; optional unique lowercase-kebab `tags`; optional boolean `reviewBullet`; optional approved Markdown narrative. |
| CSP | Durable customer outcome and strategic context. Its Topic list is derived from Topic `cspId` values. |
| Person | Stable Compass ID, meaningful `firstName` and `lastName`, and optional reviewed normalized email addresses. UPN is not managed. Reverse relationship lists are derived. |
| Daily Log | One user-local-date index of authorized graph activity. Managed entries link to affected stable IDs but never become a second relationship authority. User-authored content is preserved. |

The authoritative relationship model is:

```text
Microsoft 365 evidence -> grounds Conversation
Conversation -> exactly one Tracking Topic or parking-lot
Conversation -> participating People
Tracking Topic -> persistent People
Tracking Topic -> zero or one CSP
Daily Log -> derived links to affected objects
```

Source item identity, durable source Conversation identity, Compass graph identity, file transport identity, titles, and paths remain distinct. A missing or ambiguous source Conversation ID blocks automatic correlation. Graph writes target displayed graph-root-relative paths, never OneDrive item IDs.

## Write and effect contract

1. Resolve and display the graph root and every graph-root-relative target path.
2. Inspect current target state and preserve unknown fields and unmanaged content.
3. Present the complete proposed content, relationships, and expected effects in ordinary language.
4. Obtain authority for that exact effect set.
5. Have Graph Governor validate authority, identity, schema, relationships, paths, conflicts, and preservation.
6. Apply only validated effects. Stop on intervening changes or material proposal drift.
7. Verify every intended target and preserved element after writing.
8. Report completed, unapplied, uncertain, and rolled-back effects accurately and add the appropriate Daily Log entry.

Cancellation before application leaves durable state unchanged. Rejected content and unavailable evidence are not retained. A partial or unverifiable multi-file operation is not called complete and must expose recovery status.

## Human interaction

Compass behaves as one understandable assistant rather than five disconnected tools. It explains purpose and material limits, minimizes interruption, uses familiar language, and keeps IDs and schema mechanics out of routine decisions. The user can pause, reject, revise, redirect, or cancel naturally. Inaccessible controls, hidden proposal content, or inability to cancel block consequential approval.

## Constraints and dependencies

- Copilot Cowork must support the packaged Skills and expose the required Work IQ and file capabilities.
- The signed-in user's permissions and organizational policies bound all access.
- OneDrive path resolution, persistence, conflict detection, and recovery require runtime verification.
- Obsidian-compatible Markdown and YAML remain the authoritative representation.
- Retrieved and stored content is untrusted input, never executable instruction.
- Real work content remains private on the approved managed surface. Dexter retains only privacy-minimized counts, decisions, capability observations, and effect facts.

## Implementation status

Compass is in artifact-first production shaping within production release testing. The current goal is to build and correct a useful finished graph through authorized Cowork use, then revise Skills from demonstrated outcomes before the controlled release test.

| Component | Current candidate | Evidence status |
| --- | --- | --- |
| Installation Interview | `0.7.0-production-test-candidate` | Package inspection passed; runtime unrun. |
| Daily Scan | `0.7.0-production-test-candidate` | Package inspection passed; runtime unrun. |
| Tracking Topic Interview | `0.7.0-production-test-candidate` | Package inspection passed; runtime unrun. |
| Curator | `0.6.0-production-test-candidate` | Package inspection passed; runtime unrun. |
| Graph Governor | `0.8.0-production-test-candidate` | Package inspection passed; current write/runtime modes unrun. Historical read-only evidence applies only to `0.1.0-experimental`. |
| Orchestration | `0.7.0-production-test-candidate` | Runtime unrun and expected to change from shaping. |

Known gaps are current Skill repeatability, connected writes and recovery, native Work IQ coverage, source Conversation ID availability, schema-version-1 migration, Topic refresh, and runtime behavior for participants, lifecycle, attention, Person email/UPN handling, and HPI narrative. `updatedAt` and lifecycle-review behavior remain proposed and unimplemented.

## Decisions and non-goals

Accepted direction is artifact-first shaping followed by one controlled production-content release journey. Synthetic fixtures remain useful only for focused regression and destructive boundaries. Sample content must never substitute for unavailable production evidence.

Compass does not automatically promote evidence, retain raw transcripts, migrate OneNote, export a graph for training, deploy a proprietary database, make autonomous user-guidance changes, or claim readiness without exact-version evidence.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 1.0 | 2026-09-09 | Consolidated the Charter, requirements, specifications, decisions, plans, and implementation register into one current product document to reduce Dexter documentation overhead. |

## Acceptance boundary

This Specification records current Compass intent and accepted boundaries. It does not prove runtime behavior, authorize connected access or effects, approve release, or convert proposed requirements into accepted ones.