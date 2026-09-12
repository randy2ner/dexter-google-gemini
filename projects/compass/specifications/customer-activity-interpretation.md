# Compass Customer Activity Interpretation Specification

## Document control

- **Status:** active
- **Version:** 1.2
- **Owner:** User / product owner
- **Created:** 2026-09-12
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-022` through `PR-026` and `PR-032`
- **Implementation authority:** Local Skill source, fixtures, and disconnected validation are authorized. Connected retrieval, disclosure, OneDrive writes, packaging, deployment, and release remain unauthorized.

## Purpose and applicability

This Specification defines how Compass interprets direct user input and authorized work evidence into Conversations, also called Activities. An Activity is a durable account of meaningful customer work for transparency with account managers supporting the user's contract, customer stakeholders, and leadership. It is not a copy of a communication container.

This behavior applies whenever a Compass Skill creates, updates, summarizes, or communicates an Activity.

## Scope and boundaries

- **In scope:** Customer relevance, Activity boundaries, evidence grouping, useful content, relationship interpretation, minimized provenance, and audience-appropriate communication.
- **Out of scope:** General internal administration, professional development, product exploration, or coordination without a material connection to identifiable customer work; raw transcript retention; automatic external sharing; and detailed graph serialization.
- **Authority, privacy, and safety:** Retrieval requires its own authorized boundary. Internal evidence may support an Activity, but graph presence never authorizes disclosure. Compass must not invent customer identity, impact, commitments, decisions, or outcomes. The user reviews content before it is shared externally.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| ACT-001 | Interpret a Conversation or Activity as one coherent unit of meaningful customer work, not as an email thread, chat, meeting, message, or other source container. | The Activity describes work performed or advanced for a customer and remains understandable without opening its sources. | Accepted |
| ACT-002 | Require a material connection to an identifiable customer relationship, outcome, commitment, or need. | Generic internal work is excluded; internal work qualifies only when the Activity can state how it materially serves the customer. | Accepted |
| ACT-003 | Determine Activity boundaries from the work itself. | Several evidence items or source types may form one Activity, while one source may produce several Activities when it contains distinct customer work. | Accepted |
| ACT-004 | Capture the useful factual core: what happened, why it matters to the customer, relevant People, and the related Effort or Parking Lot disposition. | The Activity gives its audiences useful transparency without requiring a raw transcript. | Accepted |
| ACT-005 | Include progress, decisions, risks, commitments, insights, outcomes, and next steps only when present in the evidence or direct user account. | Missing details remain absent or visibly uncertain; Compass does not complete a plausible narrative by invention. | Accepted |
| ACT-006 | Preserve minimized provenance that distinguishes evidence from Compass interpretation. | A reader can understand the basis of a source-derived Activity without retaining unrelated content or a raw transcript. | Accepted |
| ACT-007 | Use stable Compass Activity identity independently of source identity. | A change in source location does not change Activity identity, and a shared source container does not force unrelated customer work into one Activity. | Accepted |
| ACT-008 | Ask the user only when customer relevance, Activity boundaries, identity continuity, Effort placement, or a consequential factual claim remains materially ambiguous. | Ordinary clear cases proceed; consequential ambiguity is not hidden by confident wording. | Accepted |
| ACT-009 | Adapt communication to the named audience while preserving the Activity's factual core. | Account managers, customer stakeholders, and leadership receive relevant framing without unrelated or audience-inappropriate detail. | Accepted |
| ACT-010 | Treat preparation for sharing as distinct from authorization to disclose. | Compass presents reviewable content and does not send, publish, or expose it without authority for that effect. | Accepted |
| ACT-011 | Derive `lastActivityAt` from the newest reliable timestamp among the individual evidence items that contain meaningful customer work for the Activity. | An old thread or chat with a recent qualifying reply uses the reply timestamp, not the container start time. | Accepted |
| ACT-012 | Advance `lastActivityAt` only when newly considered content qualifies as part of the customer Activity. | A recent unrelated, administrative, or non-customer message in the same source container does not make the Activity current. | Accepted |

## Skills and orchestration

| Component | Responsibility | Inputs and outputs | Authority |
| --- | --- | --- | --- |
| `compass-installation-interview` `0.1.0-local-candidate` | Interpret customer Activities while establishing the initial graph. | Direct user input and authorized evidence become working Activity objects and relationships. | May prepare local or authorized graph changes; connected access and writes require separate authority. |
| `compass-activity-scan` | Find and refine customer Activities during ordinary work. | Authorized evidence and existing graph context become new or updated Activity proposals. | Retrieval and graph-change approvals are separate and remain within the user's approved task boundary. |
| Communication or Curator behavior | Prepare audience-appropriate transparency from Activities. | Selected Activities become reviewable accounts for one named audience. | Preparation does not authorize disclosure. |

## Interaction and information

| Element | Contract |
| --- | --- |
| Customer work | Work materially attributable to an identifiable customer's relationship, outcome, commitment, or need. |
| Internal customer work | Internal coordination, analysis, escalation, preparation, or follow-through that materially advances identifiable customer work. |
| Excluded internal work | Administration, learning, exploration, or coordination with no material customer connection. |
| Activity boundary | One coherent customer-work development; channels and thread boundaries are supporting evidence, not the unit of knowledge. |
| Activity recency | The newest reliable timestamp of an individual message, reply, meeting contribution, or explicit user-supplied work event that qualifies as meaningful customer work within the Activity. |
| Source-container time | Thread or chat start, creation, or generic modification time may help locate evidence but never substitutes for message-level Activity recency. |
| Factual core | What happened, why it matters to the customer, relevant People, related Effort or Parking Lot, and supported progress, decision, risk, commitment, insight, outcome, or next step. |
| Account manager framing | Contract-relevant service, commitments, dependencies, workload, value, and follow-through needed to represent or coordinate the work. |
| Customer framing | Relevant progress, decisions, risks, commitments, outcomes, and next steps expressed without internal-only context. |
| Leadership framing | Concise customer impact, material risk, workload, priority, and evidence of contribution at an appropriate level of detail. |

## Constraints and dependencies

- Customer identity or relationship context must come from the user, the graph, or authorized evidence; it is never inferred from weak similarity alone.
- Source access and retrieval scope are governed by the invoking Skill's approved plan.
- When a source contains multiple items, the Skill Host must expose enough item-level content and timestamps to identify the newest qualifying customer-work item. Container metadata alone is insufficient.
- Retrieval must follow continuation or pagination needed for the authorized scope; an uninspected remainder creates a recency coverage gap.
- The Knowledge Graph Specification governs Activity identity, relationships, preservation, and serialization.
- Host support for cross-source retrieval and audience-aware review needs verification on Copilot Cowork.

## Failure, partial, blocked, and cancellation behavior

- If no material customer connection is supported, do not create an Activity.
- If evidence supports customer relevance but not a consequential detail, preserve the gap or uncertainty rather than inventing it.
- If Activity boundaries or continuity remain materially ambiguous, ask one focused question or leave the affected interpretation unresolved.
- If item-level timestamps are unavailable, ambiguous, or incompletely retrieved, do not assign a confident `lastActivityAt` from the source-container start or modification time.
- If audience suitability cannot be established, prepare no shareable account and explain what needs review.
- Report inaccessible sources, partial coverage, and unsupported claims without implying complete evidence review.

## Decisions and open questions

- **Accepted:** Conversation and Activity are equivalent Compass terms; Activity better expresses the intended meaning.
- **Accepted:** Only customer work belongs in Activities.
- **Accepted:** Internal work qualifies only when it materially advances identifiable customer work.
- **Accepted:** The intended transparency audiences are account managers supporting the user's contract, customer stakeholders, and leadership.
- **Accepted:** Source containers do not determine Activity boundaries.
- **Accepted:** Source containers do not determine Activity recency; the newest qualifying item does.
- **Open:** Representative use will refine which details each audience finds useful or inappropriate without changing the customer-only boundary.

## Implementation status

- **Implemented:** Product and graph contracts, synthetic fixture, and customer-only, cross-source, and message-level recency guidance in Installation and Activity Scan `0.1.0-local-candidate` Skills.
- **Not implemented:** Verified Cowork adaptation and observed runtime behavior.

## Test Plans

- [Customer Activity Interpretation Test Plan](../test-plans/customer-activity-interpretation.md): Verifies customer-only relevance, grouping, grounded content, and audience adaptation.
- [Installation Interview Test Plan](../test-plans/installation-interview.md): Exercises Activity interpretation during initial graph creation.
- [Curator Lifecycle Test Plan](../test-plans/curator-lifecycle.md): Verifies message-level recency resolution, continuation coverage, and source-specific host capability.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 1.0 | 2026-09-12 | Established customer-only Activity interpretation and transparency for account managers, customer stakeholders, and leadership. |
| 1.1 | 2026-09-12 | Defined message-level Activity recency and prohibited thread or chat start time and unrelated recent content from advancing `lastActivityAt`. |
| 1.2 | 2026-09-12 | Traced the Activity interpretation contract to the first local Installation Skill candidate. |

## Acceptance boundary

This active Specification authorizes local Skill implementation, fixtures, and disconnected validation of Activity interpretation. It does not authorize connected retrieval, graph writes, disclosure, packaging, deployment, or release.