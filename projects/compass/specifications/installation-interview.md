# Compass Installation Interview Specification

## Document control

- **Status:** active
- **Version:** 1.2
- **Owner:** User / product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-004` through `PR-016`, `PR-019`, `PR-020`, and `PR-022` through `PR-025`
- **Implementation authority:** Local Skill source, fixtures, and disconnected validation are authorized. Connected retrieval, OneDrive writes, packaging, deployment, and release remain unauthorized.

## Purpose and applicability

This Specification defines the first complete Compass experience: an Installation Interview that builds the user's initial durable knowledge graph across multiple current Efforts. It applies to `compass-installation-interview` version `0.1.0-local-candidate` on Copilot Cowork and separates implemented Skill guidance from unverified host capability.

## Scope and boundaries

- **In scope:** Guided discovery of current customer Efforts; a bounded Work IQ retrieval plan; authorized retrieval from email and chat, including group and meeting chats; interpretation of meaningful customer-work Activities; accumulation and refinement of inspectable working knowledge; verification of the initial OneDrive Markdown/YAML graph; and Daily Log indexing.
- **Out of scope:** Ongoing scanning after installation, lifecycle management, cross-host compatibility claims, audience-facing workload reports, packaging, and connected execution.
- **Authority, privacy, and safety:** Retrieval remains within a visible user-approved plan. Working knowledge preserves source context and remains inspectable and correctable. Ambiguous placement and destructive, overwriting, or disclosing changes require user direction. No connected retrieval or write is authorized by this Specification.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| INST-001 | Conduct a conversational interview that learns the user's role and current Efforts in the user's own terminology. | The user can describe several different forms of work without translating them into graph or storage mechanics. | Accepted |
| INST-002 | Propose a bounded Work IQ retrieval plan identifying sources, date range, and limits. | The user sees one understandable plan and can edit, approve, or cancel it before retrieval begins. | Accepted |
| INST-003 | Retrieve only approved email and chat evidence, including approved group and meeting chat scope. | Reported retrieval and visible source use remain within the approved plan; unavailable or ambiguous access is reported rather than bypassed. | Accepted |
| INST-004 | Distinguish retrieved evidence from Compass interpretation and create Activities only for meaningful customer work. | The user can inspect source context, understand what Compass added, connected, or summarized, and see that unrelated internal work was excluded. | Accepted |
| INST-005 | Help the user review and refine CSPs, Efforts, Conversations, People, and relationships without exposing storage mechanics. | The user can correct content or placement through ordinary conversation and direct file editing. | Accepted |
| INST-006 | Create structurally valid graph objects in Markdown/YAML in the user's selected OneDrive location. | Source-derived fragments become inspectable working knowledge with preserved source context and valid relationships. | Accepted |
| INST-007 | Preserve accepted relationship cardinality. | Each Effort has zero or one CSP; each Conversation has exactly one Effort or Parking Lot disposition; People may relate to multiple Efforts and Conversations. | Accepted |
| INST-008 | Index every durable installation change in the Daily Log. | The applicable dated index records each durable graph change without becoming a second relationship authority. | Accepted |
| INST-009 | Verify durable effects before reporting installation success. | The completion report distinguishes verified writes, no-write outcomes, blocked work, partial effects, and uncertainty. | Accepted |
| INST-010 | Preserve host independence in the durable result. | The installed graph contains no required hidden Cowork state and remains inspectable through ordinary OneDrive file access. | Accepted |

## Skills and orchestration

| Component | Responsibility | Inputs and outputs | Authority |
| --- | --- | --- | --- |
| `compass-installation-interview` `0.1.0-local-candidate` | Own the complete first installation conversation from interview through verified graph creation. | Inputs: direct user answers, approved retrieval plan, and authorized Work IQ evidence. Outputs: verified initial working graph or an honest no-write, blocked, partial, or uncertain result. | May retrieve only after plan approval and may refine the graph within the authorized task; material ambiguity, disclosure, overwrite, or destructive effects require user direction. |

Installation remains one coherent user-triggered Skill, but its graph changes use the independent `compass-graph-governor` validation contract. The `compass-customer-work-lifecycle` Orchestration may route a new user through Installation before ordinary Activity Scan and Curator behavior; it does not absorb Installation's retrieval or write approvals.

## Interaction and information

| Element | Contract |
| --- | --- |
| Effort language | Use **Effort** as the canonical graph concept while recognizing Tracking Topic and domain-specific labels in conversation. |
| Retrieval plan | State sources, date range, and limits in user-facing language before any Work IQ retrieval. |
| Evidence | Treat retrieved email and chat as evidence, not authoritative graph knowledge. |
| Working knowledge | Accumulate useful fragments in inspectable files and refine them as later context improves understanding. |
| User correction | Let the user correct content or placement through ordinary conversation or direct file editing. |
| Knowledge graph | Represent CSPs, Efforts, Conversations, People, Parking Lot disposition, and Daily Logs in inspectable Markdown/YAML files in OneDrive. |
| Customer Activity interpretation | Apply the [Customer Activity Interpretation Specification](customer-activity-interpretation.md); coherent customer work, not source-container boundaries, determines each Conversation or Activity. |
| Relationships | An Effort has zero or one CSP and many Conversations or People; a Conversation has one Effort or Parking Lot disposition; a Person may relate to many Efforts and Conversations. |
| Daily Log | Index accepted graph changes by date; do not use it as work-event history or relationship authority. |

## Constraints and dependencies

- Copilot Cowork is the first Skill Host; all required host capabilities remain unverified.
- Work IQ must expose authorized email and chat evidence with enough observable boundaries to support `INST-003`.
- Cowork must support multi-turn refinement while preserving source context and user corrections.
- Cowork must create, update, and verify Markdown/YAML files in the user's selected OneDrive location.
- The local candidate must remain self-contained and use its packaged runtime references rather than Dexter-root governance files.

## Failure, partial, blocked, and cancellation behavior

- Cancellation before retrieval produces no retrieval and no graph write.
- Materially ambiguous placement stops the affected change and asks the user; ordinary refinement continues without a formal promotion workflow.
- Missing access, ambiguous evidence identity, unsupported file operations, conflicts, or unverifiable effects stop the affected operation.
- Installation never reports success for an effect it cannot verify in the durable graph.

## Decisions and open questions

- **Accepted:** Installation creates source-derived Conversations and structurally valid Effort and Person relationships rather than deferring all Conversation creation to a later scan.
- **Accepted:** Graph Governor is a separate read-only validation Skill; Curator is a separate lifecycle Skill with distinct archival and removal approvals.
- **Accepted:** One Skill owns the first coherent installation experience.
- **Open:** What practical scan limits should Installation propose in the first Cowork experience?

## Implementation status

- **Implemented:** `skills/compass-installation-interview/SKILL.md` version `0.1.0-local-candidate`, its self-contained graph and Activity references, importable package, active contracts, and linked Test Plans.
- **Not implemented:** Verified Cowork adaptation, connected retrieval, and connected OneDrive behavior.

## Test Plans

- [`../test-plans/installation-interview.md`](../test-plans/installation-interview.md): Focused host capability checks and the complete Installation Interview journey.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 0.1 | 2026-09-11 | Created the first proposed behavioral contract from the accepted Charter and PRD direction. |
| 0.2 | 2026-09-11 | Replaced review-before-write with provisional persistence and explicit promotion to accepted knowledge. |
| 1.0 | 2026-09-12 | Activated the build contract and simplified installation to accumulating and refining inspectable working knowledge. |
| 1.1 | 2026-09-12 | Identified the first implemented local candidate and aligned the Specification with its self-contained runtime contracts. |
| 1.2 | 2026-09-12 | Aligned Installation with the confirmed Graph Governor and customer-work lifecycle orchestration boundaries. |

## Acceptance boundary

This active Specification authorizes local implementation of the Installation Interview Skill and disconnected validation. It does not establish Cowork capability or authorize connected retrieval, OneDrive writes, packaging, deployment, or release.