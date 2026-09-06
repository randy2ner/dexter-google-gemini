# Compass Product Requirements Document

## Document control

- **Status:** living synthesis; not separately accepted
- **Version:** 0.2
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Created:** 2026-09-01
- **Last updated:** 2026-09-02
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
| PR-TRUTH-001 | Partial, uncertain, blocked, rolled-back, or failed actions are not reported as successful. | must | Terminal reports match observed effects and uncertainty. | Sections 8 and 9 | confirmed boundary |
| PR-INT-001 | Routine interactions minimize interruption and ask about meaningful ambiguity rather than file mechanics. | must | A user can understand and complete routine workflows without approval fatigue or specialist protocol. | Sections 9, 13, and 14 | provisional requirement |
| PR-PRIV-001 | Retrieval, presentation, and retention minimize sensitive evidence and retain limited provenance rather than raw transcripts by default. | must | Scenarios show bounded access and minimized retained content. | Sections 8, 9, and 15 | provisional requirement |
| PR-EVID-001 | Durable Conversations remain grounded in authorized Microsoft 365 evidence identity. | must | Conversation creation and update behavior maintains source traceability. | Section 6 | provisional requirement |
| PR-GRAPH-001 | The graph represents CSPs, Tracking Topics, People, Conversations, Daily Logs, and accepted relationships in portable Markdown/YAML. | must | Accepted schema and graph scenarios validate required objects and relationships. | Sections 6 and 7 | provisional requirement |
| PR-SAFE-001 | Ambiguous identity, conflict, permission, or recovery state stops the affected write. | must | Negative scenarios fail closed and report blocking scope. | Sections 9, 11, and 15 | provisional requirement |
| PR-TEST-001 | Product and Skill confidence is based on linked test evidence for exact versions and environments. | must | Confidence claims trace to accepted requirements, scenarios, and immutable results. | Sections 8 and 14 | provisional requirement |

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
- **People** contribute relationship context across Evidence, Conversations, Topics, and CSP-aligned work.
- **Parking Lot** is a derived view of Conversations not currently aligned to a Tracking Topic, not a stored object.

Detailed fields, cardinality, compatibility, and validation behavior belong in accepted schema and shared-contract specifications.

## Non-goals and exclusions

- A standalone Compass application.
- Automatic promotion of Work IQ findings into authoritative knowledge.
- Raw transcript storage by default.
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

## MVP relationship

The current recorded MVP learning slice is [Graph Governor version 0.1.0-experimental read-only synthetic health scan](../mvp/compass-mvp-scope.md). It validates only a narrow subset of `PR-GRAPH-001`, `PR-SAFE-001`, and `PR-TRUTH-001`; it does not validate Compass as a product.

## Active gaps

- Charter provisions marked provisional require user confirmation before they can be treated as accepted product requirements.
- Perspective Discovery candidate review requires redesign for natural, understandable, dignified conversation before resumed testing.
- Daily Scan, Tracking Topic Interview, and Installation Interview prior artifacts require reconciliation.
- Curator has no Dexter specification, source, or test evidence.
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
| 0.2 | 2026-09-02 | Added the complete-candidate beta relationship and compact risk-based test strategy. | Reduce testing burden while preserving evidence for consequential operations and integrated behavior. |
| 0.1 | 2026-09-01 | Initial Dexter-native synthesis of accepted and provisional Charter requirements. | User-authorized Dexter source-of-truth feature build |

## Acceptance boundary

This document improves traceability and discoverability. It does not change the Charter's authority classifications, authorize implementation, certify product requirements as accepted, resume paused testing, or create runtime evidence.