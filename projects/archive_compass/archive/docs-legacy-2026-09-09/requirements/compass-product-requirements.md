# Compass Product Requirements Document

## Document control

- **Status:** living synthesis; not separately accepted
- **Version:** 0.9
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Created:** 2026-09-01
- **Last updated:** 2026-09-08
- **Governed by:** [Compass Vision and Scope Charter version 1.0](../charter/compass-vision-and-scope-charter.md)
- **Motivation:** User-authorized Dexter source-of-truth feature build
- **Implementation authority:** None granted by this PRD

## Product purpose

Compass is intended to help an individual Microsoft 365 Copilot user turn approved everyday-work evidence into durable, user-controlled work memory represented by a portable knowledge graph. This PRD normalizes confirmed and provisional requirements already recorded in the accepted Charter; it does not independently promote provisional Charter material to accepted requirements.

## User problem

Relevant work evidence is fragmented across email, Teams conversations, notes, and memory. Manual capture and reconstruction make context, progress, decisions, and relationships difficult to preserve across time. Compass seeks to reduce that upkeep while ensuring AI interpretation cannot silently become authoritative knowledge.

**Authority state:** Source-supported and provisional in the Charter.

## Intended user and context

The confirmed initial audience is an individual Microsoft 365 Copilot user managing customer success plans, Tracking Topics, People, Conversations, and changing work context. No narrower professional persona, organizational deployment, or multi-user hosted control plane is established.

## Required outcomes

| ID | Outcome | Priority | Charter source | Authority state |
| --- | --- | --- | --- | --- |
| OUT-001 | Preserve useful work context over time as durable work memory. | must | Charter section 4 | confirmed |
| OUT-002 | Make changes, rationale, and attention needs visible. | must | Charter section 4 | confirmed |
| OUT-003 | Reduce manual capture, organization, and context recovery. | must | Charter section 4 | confirmed |
| OUT-004 | Keep interpretations reviewable and trusted knowledge user-authorized. | must | Charter sections 4 and 9 | confirmed |

## Product requirements

| ID | Requirement | Priority | Acceptance signal | Charter source | Authority state |
| --- | --- | --- | --- | --- | --- |
| PR-AUTH-001 | AI evidence or interpretation does not become trusted knowledge without user authority. | must | No unapproved evidence-derived authoritative change. | Sections 6 and 9 | confirmed boundary |
| PR-PORT-001 | Authoritative knowledge remains inspectable, readable, and editable outside Compass. | must | Accepted representation can be inspected and validly edited without Compass. | Sections 1, 7, and 9 | confirmed boundary |
| PR-HIST-001 | Normal lifecycle behavior preserves retained historical knowledge rather than destructively deleting it. | must | Retire, archive, or deactivate without losing retained history. | Sections 7 through 9 | confirmed boundary |
| PR-HIST-002 | Topic archival records whether the Topic succeeded, while active Topics do not retain a prior archival outcome. | must | Every archived Topic has explicit boolean `success`; active Topics have null or absent success, and reactivation removes the field. | Sections 7 through 9 | accepted product-owner requirement |
| PR-TRUTH-001 | Partial, uncertain, blocked, rolled-back, or failed actions are not reported as successful. | must | Terminal reports match observed effects and uncertainty. | Sections 8 and 9 | confirmed boundary |
| PR-INT-001 | Routine interactions minimize interruption and ask about meaningful ambiguity rather than file mechanics. | must | A user can understand and complete routine workflows without approval fatigue or specialist protocol. | Sections 9, 13, and 14 | provisional requirement |
| PR-INT-002 | Compass interprets what a useful artifact should contain from direct input, accepted graph context, and authorized Work IQ, then offers an editable suggestion for user confirmation. | must | Artifact-building Skills propose useful content, fields, and relationships in ordinary language; no interpretation is written without confirmation, and follow-up questions are reserved for material ambiguity that cannot be represented safely. | Product-owner decision 2026-09-09 | accepted interaction requirement |
| PR-PRIV-001 | Retrieval, presentation, and retention minimize sensitive evidence and retain limited provenance rather than raw transcripts by default. | must | Scenarios show bounded access and minimized retained content. | Sections 8, 9, and 15 | provisional requirement |
| PR-EVID-001 | Durable Conversations remain grounded in authorized Microsoft 365 evidence identity. | must | Conversation creation and update behavior maintains source traceability. | Section 6 | provisional requirement |
| PR-WIQ-001 | Within a user-authorized production purpose, Compass uses the native Work IQ capabilities Cowork exposes without artificial source-type, result-count, or sample-data restrictions. | must | Skills attempt complete relevant coverage, paginate or continue when the surface supports it, disclose capability or permission gaps, never substitute samples, and keep evidence-derived graph content reviewable before it becomes authoritative. | Product-owner decision 2026-09-08 | accepted production-test requirement |
| PR-GRAPH-001 | The graph represents CSPs, Tracking Topics, People, Conversations, Daily Logs, and accepted relationships in portable Markdown/YAML. | must | Accepted schema and graph scenarios validate required objects and relationships. | Sections 6 and 7 | provisional requirement |
| PR-SAFE-001 | Ambiguous identity, conflict, permission, or recovery state stops the affected write. | must | Negative scenarios fail closed and report blocking scope. | Sections 9, 11, and 15 | provisional requirement |
| PR-TEST-001 | Product and Skill confidence is based on linked test evidence for exact versions and environments. | must | Confidence claims trace to accepted requirements, scenarios, and immutable results. | Sections 8 and 14 | provisional requirement |
| PR-PART-001 | Conversation participants include accepted authors/responders and user-confirmed authored-content mentions, not passive recipients or roster-only members. | must | Schema-v2 scenarios confirm qualification, accumulation, and complete-name identity binding. | Product-owner decision 2026-09-06 | accepted feature requirement |
| PR-TOPIC-001 | Topics retain persistent participant lists populated from aligned Conversations and Topic Interview management; explicit removals resist automatic re-add. | must | Schema-v2 scenarios confirm funneling, non-pruning, exclusion, and explicit re-add. | Product-owner decision 2026-09-06 | accepted feature requirement |
| PR-PARK-001 | Every Conversation records intentional Topic disposition as a valid Topic ID or `parking-lot`. | must | Missing/null/empty disposition is invalid and `parking-lot` derives the Parking Lot view. | Product-owner decision 2026-09-06 | accepted feature requirement |
| PR-ATTN-001 | Every Tracking Topic records whether the user has an action, is waiting on someone or something, or is observing without direct involvement. | must | Topic `attentionState` is exactly `action`, `waiting`, or `observing`; creation and changes require user authority, archival retains it, and reactivation confirms or changes it. | Product-owner decision 2026-09-06 | accepted feature requirement |
| PR-PRIV-002 | Compass does not collect or retain Microsoft 365 UPN as managed Person data. | must | Current Person schema and Skill proposals omit `userPrincipalName`; existing values are not changed without separately disclosed user authority. | Product-owner decision 2026-09-06 | accepted privacy requirement |
| PR-PERSON-001 | Compass accepts normalized email addresses as useful Person attributes without treating them as Person identity or UPN. | must | Person proposals retain reviewed addresses supplied by the user or exposed by authorized Work IQ; stable Compass ID and complete name remain required. | Product-owner decision 2026-09-09 | accepted feature requirement |
| PR-NARR-001 | A Tracking Topic may retain a detailed user-approved career and troubleshooting narrative assembled from content the user offers or explicitly authorizes for review. | must | Content is optional; accepted narratives distinguish evidence, interpretation, disproved hypotheses, cause, resolution, contribution, lessons, and out-of-scope follow-up while excluding raw messages and unnecessary identities by default. | Product-owner decision 2026-09-08 | accepted feature requirement |
| PR-HIGHLIGHT-001 | A user may mark a Topic for deterministic Curator review with managed classification metadata. | must | Optional unique lowercase-kebab `tags` and boolean `reviewBullet` validate; every in-scope `reviewBullet: true` Topic appears once as a distinct Curator bullet without inferring lifecycle or opening follow-up Topics. | Product-owner decision 2026-09-08 | accepted feature requirement |
| PR-RECENCY-001 | Every Tracking Topic and Conversation accurately records when that graph object was last updated. | must | Each Topic and Conversation has a timezone-explicit UTC `updatedAt`; creation initializes it, every successful durable change advances it, and unrelated activity does not change it. | Product-owner direction 2026-09-06 | accepted feature requirement |
| PR-REVIEW-001 | Compass supports a review of Conversations and Topics that meet user-approved evaluation criteria for purge or archival consideration. | must | The review discloses its criteria and scope, identifies matching items without changing them, routes Conversations to an explicit purge decision and Topics to an explicit archive decision, and reports every outcome accurately. | Product-owner direction 2026-09-06 | accepted feature requirement |

## Capability landscape

The Charter confirms five primary Skill areas as a capability landscape, not as implementation or release claims.

| Capability | Intended responsibility | Current Dexter state |
| --- | --- | --- |
| Installation Interview | Establish user context and initial graph structure through guided setup. | Prior artifact requires reconciliation; Perspective Discovery sub-slice paused after a humanistic usability finding. |
| Daily Scan | Turn relevant authorized daily evidence into reviewable Conversation and Activity updates. | Prior artifact requires reconciliation. |
| Tracking Topic Interview | Conversationally manage durable Tracking Topics and their relationships. | Prior artifact requires reconciliation. |
| Curator | Help the user validate relevance, organization, staleness, and attention needs. | Capability only; no Dexter source or evidence. |
| Graph Governor | Govern integrity, supervise agentic activity, and prevent unauthorized or ambiguous modifications. | Experimental read-only synthetic health-scan slice closed with bounded confidence. |

## Knowledge model

- **Evidence** is authorized Microsoft 365 activity.
- **Conversations** are durable records grounded in one Chat ID or Email ID and updated when new activity has the same source identity.
- **Tracking Topics** are user-managed concepts that persist across Conversations.
- **Customer Success Plans** provide customer outcomes and strategic planning context.
- **People** require meaningful first and last names and contribute accepted participant context across Conversations and Topics.
- **Parking Lot** is a derived view of Conversations whose `trackingTopicId` is `parking-lot`, not a stored object.

Detailed fields, cardinality, compatibility, and validation behavior belong in accepted schema and shared-contract specifications.

## Non-goals and exclusions

- A standalone Compass application.
- Automatic promotion of Work IQ findings into authoritative knowledge.
- Raw transcript storage by default.
- Automatic export of production graph content for model training. The graph may support later user-authorized evaluation or training, but that use requires a separately explicit purpose and destination.
- Automatic migration of the existing OneNote corpus.
- Destructive deletion as normal lifecycle behavior.
- Autonomous changes to user-authored guidance.
- A proprietary database as the authoritative representation.
- A multi-user hosted control plane in the first release.
- Claims of safety, compatibility, or readiness unsupported by Dexter evidence.

These exclusions remain provisional where the Charter marks them provisional.

## Constraints and dependencies

- Copilot Cowork support for portable Skills and relevant runtime capabilities.
- Access restricted to evidence available to the signed-in user.
- OneDrive storage and permission behavior.
- Obsidian compatibility with accepted Markdown and YAML conventions.
- Conflict detection and recoverable writes despite no assumed atomic multi-file operation.
- Safe parsing of retrieved and stored content as untrusted input.
- Separate authority for connected retrieval, writes, deployment, sharing, and release.

## Success signals and guardrails

The accepted Charter establishes qualitative success only. Candidate signals include successful installation, useful continued practice, traceable user approval, preserved lifecycle history, low-interruption routine workflows, and all accepted capabilities working within their declared scope. No numeric adoption or time-saving target is established.

Full beta evaluates one complete candidate containing all five Skills and their versioned Orchestration. Pre-beta testing is risk-based and compact: characterize the AI surface, isolate critical durable operations, and rehearse the complete Orchestration before using natural beta workflows to shape usefulness, trust, interruption, continuity, and personality. The accepted [compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md) defines the gates without changing product authority or safety boundaries.

## Active gaps

- Charter provisions marked provisional require user confirmation before they can be treated as accepted product requirements.
- Perspective Discovery candidate review requires redesign for natural, understandable, dignified conversation before resumed testing.
- Participant-management source is updated for schema version 2 but has no runtime evidence yet.
- Schema-version-1 graph migration mechanics remain unspecified and untested.
- Connected writes, persistence, recovery, and broader runtime contracts remain unvalidated.
- No complete five-Skill beta candidate or Compass Orchestration exists yet.

## Traceability

- [Compass source-of-truth register](../source-of-truth-register.md)
- [Compass requirements traceability matrix](requirements-traceability-matrix.md)
- [Compact full-beta test strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- [Accepted Charter](../charter/compass-vision-and-scope-charter.md)

## Revision history

| Version | Date | Change | Motivation |
| --- | --- | --- | --- |
| 0.7 | 2026-09-06 | Added accurate Topic and Conversation update timestamps plus criteria-based purge/archive review as product requirements; removed MVP as a living product-document layer. | Product-owner documentation-model and feature direction. |
| 0.6 | 2026-09-06 | Removed UPN from managed Person data while preserving Compass ID, complete-name, and bounded email-correlation rules. | Product-owner Person UPN removal decision. |
| 0.3 | 2026-09-06 | Added accepted participant qualification, persistent Topic participant management, complete Person names, and intentional Parking Lot disposition. | Product-owner participant-management decision. |
| 0.2 | 2026-09-02 | Added the complete-candidate beta relationship and compact risk-based test strategy. | Reduce testing burden while preserving evidence for consequential operations and integrated behavior. |
| 0.1 | 2026-09-01 | Initial Dexter-native synthesis of accepted and provisional Charter requirements. | User-authorized Dexter source-of-truth feature build |

## Acceptance boundary

This document improves traceability and discoverability. It does not change the Charter's authority classifications, authorize implementation, certify product requirements as accepted, resume paused testing, or create runtime evidence.