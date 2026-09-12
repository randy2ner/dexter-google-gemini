# Marquee Product Requirements Document

## Document control

- **Status:** active
- **Owner:** User / product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-11
- **Governed by:** [Marquee Project Charter](CHARTER.md)

This PRD is active as product guidance. Its accepted outcomes and boundaries come from the Charter; requirements derived from draft Specifications remain proposed behavior until the product owner explicitly accepts those Specifications. Candidate implementation and packaging make that behavior testable, not accepted or proven.

## Product purpose and user problems

Marquee helps people recognize the significance of their work, retain an accurate career story, and express it confidently in recurring professional exercises. It serves users who find self-promotion or career writing difficult and who otherwise must reconstruct accomplishments, goals, feedback, and evidence from scattered Microsoft 365 sources under time pressure.

The initial beta applies this experience to a CareerHub Development Plan and a manager-requested OneNote questionnaire. It must remain useful when direct destination editing, Work IQ, or graph mutation is unavailable.

## Prioritized outcomes

| ID | Outcome | Priority | Charter state |
| --- | --- | --- | --- |
| OUT-001 | Users explain their contribution and significance in a confident, specific, authentic professional voice. | must | accepted |
| OUT-002 | Users retain inspectable, accurate career knowledge and recognize accomplishments or strengths they might otherwise omit. | must | accepted |
| OUT-003 | Users complete CareerHub and manager-questionnaire exercises with less reconstruction and stronger career insight. | must | accepted |
| OUT-004 | Finished Outlet content is credible, polished, audience-aware, and ready for use or user-managed transfer. | must | accepted |
| OUT-005 | Marquee connects strengths, evidence, perspectives, aspirations, and actions into coherent career direction. | should | accepted |
| OUT-006 | Guidance retained from an Outlet makes repeated use easier without becoming an activity ledger or rigid script. | should | accepted |
| OUT-007 | The core experience can later support additional professional Outlets such as reviews, manager conversations, and LinkedIn. | could | accepted future direction |

## Product requirements and acceptance signals

| ID | Requirement | Priority | Acceptance signal | State |
| --- | --- | --- | --- | --- |
| PR-001 | Establish and evolve a user-confirmed, inspectable Marquee graph without unauthorized or destructive changes. | must | The independently inspected root and structure match user approval; actual effects and failures are reported truthfully. | proposed; implemented for evaluation |
| PR-002 | Retain useful career knowledge with transparent placement, provenance, confirmation state, and privacy-minimized content. | must | Artifacts are readable and reusable; users understand and can correct what was retained; unconfirmed knowledge never appears accepted. | proposed; implemented for evaluation |
| PR-003 | Recognize repeatable career Outlets and distinguish them from ordinary career-knowledge conversations. | must | Explicit and conversational Outlet requests enter the right flow; ambiguous requests receive focused clarification; ordinary events do not create generic Outlet guidance. | proposed; implemented for evaluation |
| PR-004 | Choose a completion approach based on observed host capability and desired user involvement, with a usable drafting fallback. | must | The approach matches actual capability and user preference; unavailable automation does not produce false completion claims or a dead end. | proposed; implemented for evaluation |
| PR-005 | Provide personalized, evidence-grounded career advice with independent judgment and clear expertise boundaries. | must | Advice reveals significance or a stronger action, explains its reasoning, distinguishes fact from judgment, and preserves authentic voice. | proposed; implemented for evaluation |
| PR-006 | Produce strong CareerHub Development Plan and manager OneNote questionnaire content while preserving user control over destination actions. | must | Participants rate the work useful and authentic; output fits the actual exercise; submission or sharing occurs only under exact authority. | proposed beta behavior; implemented for evaluation |
| PR-007 | Retain accurate, portable Outlet guidance based on observed useful process. | should | Later assistance becomes more accurate or efficient without private facts, unsupported rules, or administrative burden. | proposed; implemented for evaluation |
| PR-008 | Preserve privacy, identity, effect truth, and user authority throughout every experience. | must | No unrelated access, sensitive retention, invented evidence, unauthorized external effect, or materially false reporting occurs. | accepted Charter boundary; implemented for evaluation |

## Required capabilities

| Capability | Why it is needed | Skill host dependency | State |
| --- | --- | --- | --- |
| Portable Skill invocation and natural conversation | All Marquee outcomes | Host can load the Skill and sustain the conversation. | needs verification |
| Visible source inspection | Understand actual Outlet instructions and avoid asking users to repeat visible context. | Host exposes only user-authorized open, attached, or linked material. | needs verification |
| User-selected OneDrive folder inspection and mutation | Create and maintain the Marquee graph. | Host can inspect and write Markdown within an explicitly confirmed root. | needs verification |
| Durable Markdown continuity | Resume confirmed and unconfirmed knowledge across summons. | Host can rediscover and update graph artifacts in later interactions. | needs verification |
| Authorized Work IQ retrieval | Reduce reconstruction with relevant work context. | Host can retrieve minimum relevant authorized context without broad or hidden access. | needs verification; optional fallback exists |
| CareerHub or OneNote destination interaction | Apply approved content directly when useful. | Host may expose inspect or edit capability separately; access does not imply submission authority. | unknown; complete-draft fallback required |

## Non-goals

- Replace legal, medical, financial, human-resources, or employer-policy expertise.
- Track Marquee activity, capability, or user behavior in a separate ledger.
- Assume direct editing, submission, publication, sharing, or messaging authority.
- Embed one participant's private career knowledge or preferences in the distributable Skill.
- Expand the initial beta beyond CareerHub and the manager OneNote questionnaire merely because later Outlets are envisioned.

## Constraints and dependencies

- The user owns their career story, graph, professional decisions, and final representations.
- Work IQ and destination access must be purpose-limited and explicitly authorized; private source results remain on the managed surface.
- The graph must remain user-managed, inspectable, and separable from the distributable Skill.
- Direct destination automation is best effort. A polished, transfer-ready draft is the dependable fallback.
- Claims about access, writes, completion, and retained knowledge require observable evidence on the current host.
- The beta must discover whether one Skill remains sufficient or coordinated Skills become necessary.

## Specification index

| Specification | Requirements covered | State |
| --- | --- | --- |
| [Marquee graph creation](specifications/marquee-graph-creation.md) | `PR-001`, `PR-002`, `PR-008` | draft for review; candidate implementation unaccepted and unproven |
| [Marquee Outlet orchestration](specifications/marquee-outlet-orchestration.md) | `PR-003`, `PR-004`, `PR-006`, `PR-007`, `PR-008` | draft for review; candidate implementation unaccepted and unproven |
| [Marquee career expertise and advice](specifications/marquee-career-expertise-and-advice.md) | `PR-005`, `PR-006`, `PR-008` | draft for review; candidate implementation unaccepted and unproven |

## Open questions

- Which graph, Work IQ, CareerHub, and OneNote capabilities are available on the intended Skill host, and under what permissions and interaction controls?
- Does repeated use produce Outlet guidance that materially improves later assistance?
- Does the single-Skill candidate remain coherent after representative beta use, or is orchestration warranted?
- Can the same core experience serve multiple beta users without embedding private knowledge or one user's preferences?

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Reconciled product, Specification, Skill, and package states so candidate implementation supports review and host testing without implying acceptance or runtime proof. |
| 2026-09-11 | Created from the accepted Charter direction and the three existing behavioral Specifications so product priorities, requirements, capability dependencies, and acceptance signals govern continued beta development. |

## Authority boundary

This PRD defines desired outcomes and requirements under the Charter. It does not establish untested host capability or authorize connected access, mutation, submission, publication, sharing, messaging, deployment, or release.