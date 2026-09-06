# Compass Vision and Scope Charter

## Document control

- **Status:** Accepted
- **Project:** Compass
- **Version:** 1.0
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Created:** 2026-08-28
- **Approved:** 2026-08-28 by explicit user decision
- **Implementation authority:** None granted by this charter

## Source register

This charter synthesizes all user-provided source material currently in the charter intake directory:

| Source | Contribution to this draft | Treatment |
| --- | --- | --- |
| [Quick Start Guide](source-material/Compass_README.md) | Vision, user experience, knowledge concepts, and proposed Skill set | Candidate intent and explanatory framing |
| [Product Spec](source-material/product-spec.md) | Problem, goals, non-goals, roles, requirements, boundaries, and success signals | Previously marked approved in its source context; non-binding in Dexter until reaffirmed |
| [Project State](source-material/project-state.md) | Historical decisions, approvals, experiments, implementation claims, and current-state projections | Unverified Aegis-produced source history; not Dexter test evidence or active authorization |
| [Technical Spec](source-material/technical-spec.md) | Accepted architecture, graph model, storage contract, integrity rules, and technical risks | Candidate constraint set; too detailed to reproduce in the charter |

The source files remain unchanged. This charter summarizes them and does not supersede them unless the user explicitly approves that relationship.

## 1. Vision

**Confirmed synthesis**

Compass is intended to help an individual turn approved evidence from everyday work into a durable, user-controlled knowledge graph. It should make work context easier to capture, connect, inspect, correct, recover, and reuse while preserving the user's judgment over what becomes trusted knowledge.

The intended experience can be summarized as:

> Conversations become evidence. People become context. Tracking Topics become progress. The graph becomes memory.

Compass is envisioned as a set of portable Copilot Cowork Skills rather than a standalone application. Markdown and YAML provide an inspectable representation, OneDrive provides user-controlled storage, Obsidian provides a navigation and editing surface, and Work IQ provides provisional Microsoft 365 evidence.

**State:** Confirmed by the user on 2026-08-28.

## 2. Problem and opportunity

**Source-supported candidate statement**

The user currently maintains work knowledge manually in OneNote while relevant evidence remains fragmented across email, Teams conversations, notes, and memory. Continuous manual capture and reconstruction make it difficult to preserve context, understand progress, recover decisions, and connect work across time.

Compass is an opportunity to reduce that upkeep and teach linked knowledge-management practices without allowing AI interpretation to silently become authoritative knowledge.

**State:** Provisional — the source is clear, but the user should confirm that this remains the current problem.

## 3. Intended user

**Confirmed initial user definition**

An individual Microsoft 365 Copilot user who manages customer success plans (CSPs), Tracking Topics, People, Conversations, and changing work context.

The Contoso advisor described in the Quick Start Guide is treated as a fictional explanatory persona, not as evidence of a real organization or user population.

**State:** Confirmed at the audience level on 2026-08-28. A narrower professional role or persona has not been established.

## 4. Desired outcomes

The user identified four primary charter-level outcomes:

1. **Durable work memory** — preserve useful work context over time.
2. **Progress visibility** — see what changed, why it changed, and what needs attention.
3. **Less manual upkeep** — reduce manual capture, organization, and context recovery.
4. **User-controlled knowledge** — keep interpretations reviewable and trusted knowledge user-authorized.

The source material also proposes that Compass may help the user:

- transition recurring work-knowledge maintenance away from a manual practice;
- learn to work alongside Copilot through everyday use, building linked knowledge management habits naturally over time;
- turn authorized Microsoft 365 evidence into reviewable proposals;
- turn authorized Microsoft 365 evidence into grounded knowledge that can be reviewed, reused, and shared across AI solutions   and business stakeholders with transparency;
- maintain awareness across many topics by surfacing meaningful changes, emerging activity, and items that may require renewed attention; and
- retain authority to confirm, edit, reject, or directly author knowledge.

**State:** Four primary outcomes confirmed on 2026-08-28; additional source-derived outcomes remain provisional.

## 5. Candidate capability landscape

The source material describes five connected capability areas:

1. **Installation Interview** — Learns the user's role, customers, and priority areas through guided conversation; establishes the initial knowledge graph structure, prepares or validates the OneDrive-hosted Obsidian-compatible workspace, and provides the context used to recognize customer-related activity and important topics over time.
2. **Daily Scan** — review one selected local calendar day of authorized email and Teams activity, transform relevant activity into durable work memory, create or update Conversation and Activity Markdown files within the knowledge graph, maintain relationship metadata, and propose new or changed Conversations for user review.
3. **Tracking Topic Interview** — conversationally explore, create, refine, connect, merge, realign, or retire Tracking Topics; maintain the Topic Markdown files and metadata that represent durable concepts within the knowledge graph; manage Topic-to-CSP relationships; and govern how Conversations are associated with Topics.
4. **Curator** — review the knowledge graph with the user to validate activity, relevance, and organization; confirm last-activity reporting; identify stale, completed, emerging, or overlooked Topics and Conversations; recommend consolidation, reclassification, archival, or reactivation actions; and help ensure the collection remains accurate, useful, and aligned to the user's work.
5. **Graph Governor** — serve as the governing authority for the knowledge graph, supervising agentic activity, enforcing graph integrity rules, validating structural consistency, resolving safely determinable issues, preserving historical truth, and preventing unauthorized or ambiguous modifications to durable work memory.


**State:** Five primary Skills confirmed on 2026-08-28; additional functionality remain provisional.

## 6. Knowledge and authority model

Compass transforms authorized Microsoft 365 activity into durable work memory organized as a connected knowledge graph.

### Core Knowledge Objects

**Evidence** represents authorized Microsoft 365 activity, including emails, chats, meetings, transcripts, files, and calendar activity.

**Conversations** represent durable work-memory records scoped to the lifecycle of a single Chat ID or Email ID. Every Conversation is grounded by and continuously linked to its authoritative Microsoft 365 evidence source. A Conversation accumulates derived context, relationships, classifications, and activity over time while preserving alignment to the evidence record from which it originated. New activity associated with the same Chat ID or Email ID updates the existing Conversation; activity associated with a different Chat ID or Email ID creates a separate Conversation.

**Tracking Topics** represent user-managed concepts such as initiatives, technologies, objectives, problem spaces, responsibilities, or areas of interest that persist beyond individual communications. A Topic provides continuity across many related Conversations.

**Customer Success Plans (CSPs)** represent durable customer outcomes, strategic objectives, and business priorities that provide planning context for Tracking Topics.

**People** provide relationship context throughout the graph and may participate in Conversations, contribute Evidence, and influence the evolution of Topics and CSP-aligned work.

### Knowledge Relationships

```text
Evidence
    ↓
Conversation
    ↓
Tracking Topic
    ↓
   CSP

People ──┬── participate in Conversations
         ├── contribute Evidence
         └── provide relationship context
```

- Evidence grounds Conversations.
- Conversations provide history, context, and continuity of work.
- Tracking Topics organize related Conversations into durable concepts.
- CSPs provide strategic alignment and business outcomes.
- People provide relationship context across the graph.

### Parking Lot Conversations

**Parking Lot** is not a stored object.

Parking Lot is a derived view consisting of Conversations that are not currently aligned to a Tracking Topic. It serves as a holding area for information that is worth remembering but does not currently warrant active tracking or participation.

Items in the Parking Lot may include:

- Upcoming meetings, commitments, or follow-up items where the user wants to "put a pin in it" for future attention.
- Questions, requests, or problems that were resolved through a single interaction and do not require ongoing tracking.
- Standalone pieces of information that may be useful later but do not currently contribute to a broader Topic.
- Activity that is too vague, immature, or isolated to justify association with an existing Tracking Topic.
- Conversations the user is no longer actively participating in but wishes to retain for awareness and future reference.

The Parking Lot acts as a temporary or long-term memory shelf for information that remains relevant enough to retain, but not significant enough to organize into durable Topic-based work memory. Conversations may remain in the Parking Lot indefinitely or later be associated with a Tracking Topic as their importance, context, or relevance evolves.

### Key Principle

Compass does not treat email, chat messages, meetings, or documents as the final destination of knowledge.

Instead, Compass transforms authorized Microsoft 365 activity into durable work memory that can be reviewed, connected, organized, validated, and reused across future AI experiences while remaining transparent and understandable to both people and AI systems.

## Authority Principles

> Compass proposes; the user confirms, edits, or initiates.

### Authority Hierarchy

- Authorized Microsoft 365 activity is authoritative for evidence of activity and observable events.
- The durable knowledge graph is authoritative for Conversations, Tracking Topics, CSP alignments, and organizational decisions after validation.
- User-authored and user-approved changes are authoritative.
- Valid direct edits to the knowledge graph remain authoritative.
- AI-generated classifications, alignments, summaries, and recommendations are proposals until accepted by the user.
- Tracking Topic suggestions may be authored by Cowork based on comprehension of Conversations, observed activity patterns, and knowledge gathered through Topic Interviews.
- Information captured and confirmed during a Topic Interview takes precedence over inferred Topic suggestions, classifications, relationships, and organizational recommendations.
- Topic creation, Topic alignment, Topic retirement, and Topic merging remain user-approved decisions regardless of how strongly supported a suggestion may be.

### Governance Principles

- Work IQ and other discovery mechanisms may propose changes but do not independently modify authoritative graph state.
- Ambiguous, consequential, or organizational decisions require user review.
- Deterministic and uniquely correct system actions may be performed automatically by the Graph Governor.
- User intent always outranks a prior proposal.
- The purpose of automation is to reduce effort, not transfer ownership of decisions.

**State:** Provisional — strongly supported by current research, domain modeling, and workflow analysis.

## 7. In scope

Candidate first-release scope includes:

- portable Copilot Cowork Skills;
- a user-controlled OneDrive-hosted Markdown/YAML graph;
- Obsidian-compatible inspection, navigation, and direct editing;
- authorized Work IQ evidence presented as proposals;
- CSPs, Tracking Topics, People, Conversations, Daily Logs, and their approved relationships;
- explicit review before scan-derived knowledge becomes authoritative;
- historical retention through archival and deactivation rather than normal deletion;
- validation of changed files and affected relationships;
- conflict-aware and recoverable graph writes that do not report false success; and
- evidence-based testing before broader use.

**State:** Provisional pending acceptance of the complete charter.

## 8. Out of scope

The sources consistently exclude:

- a standalone Compass application;
- automatic promotion of Work IQ findings into authoritative knowledge;
- raw transcript storage by default;
- automatic migration of the existing OneNote corpus;
- destructive deletion as normal lifecycle behavior;
- autonomous changes to user-authored guidance;
- requiring the user to direct routine file mechanics;
- a proprietary database as the authoritative representation;
- a multi-user hosted control plane in the first release; and
- claims of implementation safety that are not supported by test evidence.

**State:** Provisional.

## 9. Operating principles

1. **User authority:** The user owns the graph and consequential decisions.
2. **Evidence before authority:** Retrieved evidence remains provisional until approved.
3. **Inspectable knowledge:** Authoritative content remains readable and editable outside Compass.
4. **Preserved language:** Unrelated maintenance must not silently rewrite user prose.
5. **History over deletion:** Lifecycle actions preserve useful historical context.
6. **Fail closed:** Ambiguous identity, conflict, permission, or recovery state stops the affected write.
7. **Honest reporting:** Partial, uncertain, blocked, or rolled-back outcomes are never described as successful.
8. **Low interruption:** Defaults and conventions resolve routine mechanics; questions focus on meaningful ambiguity.
9. **Data minimization:** Store summaries and limited provenance rather than raw transcripts by default.
10. **Evidence-based evolution:** Changes are evaluated with linked scenarios and results.

### Confirmed non-negotiable boundaries

The user confirmed that these boundaries must hold regardless of later implementation choices:

- **User-approved authority:** AI evidence or interpretation does not become trusted knowledge without user authority.
- **Inspectable, portable data:** Authoritative knowledge remains readable and editable outside Compass.
- **Preserved history:** Normal lifecycle behavior does not destructively erase retained knowledge.
- **No false success:** Partial, uncertain, blocked, or failed actions are reported honestly.

Other source-derived principles remain candidates for later confirmation or specification.

**State:** Four boundaries confirmed on 2026-08-28; remaining principles provisional.

## 10. Roles and decision authority

| Actor | Candidate responsibility | Authority boundary |
| --- | --- | --- |
| User / product owner | Own vision, scope, graph, approvals, language, and consequential decisions | Sole authority to accept this charter and authorize implementation or connected tests |
| Dexter | Facilitate the charter, classify statements, preserve traceability, record experiments and results, and identify gaps or conflicts | May not invent requirements, approve Compass, implement it, or claim unobserved outcomes |
| Compass | Retrieve authorized evidence, propose connections, and perform authorized routine work | Must remain inside explicit workflow and user-authority boundaries |
| Work IQ | Supply evidence available through the user's Microsoft 365 permissions | Evidence provider only; no authority over graph state or relationships |
| Obsidian | Provide an optional human editing and navigation surface | Direct valid user edits remain authoritative |
| OneDrive | Host the proposed graph under user-controlled permissions | Storage does not imply safe atomic multi-file transaction behavior |

**State:** Provisional.

## 11. Constraints and dependencies

Candidate constraints and dependencies include:

- Microsoft 365 Copilot Cowork support for portable Skills;
- access only to evidence the signed-in user is authorized to retrieve;
- OneDrive storage and permissions;
- Obsidian compatibility with selected Markdown and YAML conventions;
- no assumption of atomic multi-file writes;
- conflict detection before replacing user-editable canonical notes;
- safe parsing and treatment of retrieved or stored content as untrusted input;
- preservation of package structure required by Cowork; and
- separate approval for connected access, writes, deployment, sharing, or release.

The Technical Spec records unresolved or partially verified runtime contracts. Those details belong in specifications, decisions, and test evidence rather than being silently resolved in this charter.

**State:** Provisional.

## 12. Assumptions and hypotheses

### Assumptions carried from source material

- The intended user can access relevant Work IQ evidence and write to a selected OneDrive location.
- Cowork can provide a behaviorally suitable review interaction for consolidated proposals.
- OneNote migration is not required to demonstrate first-release value.
- Markdown/YAML can remain sufficiently portable and usable through Obsidian.

### Hypotheses requiring evidence

- The graph will reduce enough manual upkeep to be worth maintaining.
- Linked knowledge will improve continuity, review preparation, and progress awareness.
- Four Skills can cooperate without creating excessive approval fatigue or micromanagement.
- Cowork and OneDrive can satisfy the required safety, concurrency, and recovery contracts.
- The user will find the graph useful enough to continue the practice.

**State:** Provisional classifications.

## 13. Success signals and guardrails

### Candidate success signals

- The user completes installation and opens the graph in Obsidian.
- The user can use all accepted first-release capabilities successfully.
- Every scan-derived authoritative update is traceable to explicit user approval.
- Lifecycle operations preserve historical knowledge.
- Routine workflows do not repeatedly ask the user to direct mechanical choices.
- The graph proves useful enough for continued linked knowledge-management practice.

### Candidate release guardrails

- Zero unapproved scan-derived authoritative changes.
- Zero normal lifecycle deletions of retained historical knowledge.
- Zero falsely reported successful writes.
- No release acceptance when routine workflows produce material approval fatigue or micromanagement.

The charter uses qualitative success only. No numeric adoption, time-saving target, or future requirement to create one is established by this charter. Test plans may still define observable scenario outcomes without converting them into product-performance targets.

**State:** Qualitative framing confirmed on 2026-08-28; the individual signals remain subject to whole-charter acceptance.

## 14. Dexter governance expectations

Dexter should take over from Aegis with a smaller, less complicated footprint focused on managing Skills and testing how each Skill behaves in scenarios through natural-language instructions.

For Compass, this means Dexter should:

- specialize in Skill and Orchestration records rather than becoming a general product-development bureaucracy;
- use small, understandable documents and approval steps;
- design scenario runs around natural-language use in Copilot Cowork;
- capture each Skill's distinctive behavior, tone, interaction pattern, and user experience—its “vibe”—as observable scenario expectations;
- separate claimed behavior from behavior observed during a run;
- preserve concise evidence and lessons without reproducing an oversized append-only control system; and
- wait for explicit user direction before building, packaging, or advancing implementation.

**State:** Confirmed by the user on 2026-08-28.

## 15. Risks

- AI-generated proposals may be mistaken for authoritative facts.
- Work evidence may expose more content than necessary if retrieval and presentation are not bounded.
- YAML serialization or maintenance may unintentionally alter user-authored content.
- Concurrent OneDrive edits may cause lost updates without verified conditional-write behavior.
- Multi-file operations may leave inconsistent state without durable recovery.
- Weak source identity may create duplicates or incorrect correlation.
- Excessive confirmations may make Compass harder to use than the manual process.
- Skill portability or target-runtime behavior may differ from assumptions.
- Prior source records may not map cleanly into Dexter's evidence and approval model.

**State:** Provisional.

## 16. Source reconciliation findings

The source-assisted review found the following reconciliation conditions and recorded their current disposition:

1. **Prior-effort provenance:** The files were produced through an Agent Builder solution identified by the user as Aegis. The user has not reviewed them sufficiently to attest to every claim. The prior Compass effort worked in some ways but not all, and Dexter is intended to take over where Aegis failed.
2. **Lifecycle wording:** The current Compass project overview says implementation has not started. More precisely, no implementation has started under Dexter, while source material describes prior Aegis-led design, packaging, and connected testing that has not yet been reconciled.
3. **Approval portability:** Product and Technical Specs labeled approved or accepted in the Aegis-produced source context are not binding in Dexter. Important decisions must be reaffirmed before they become binding Dexter project records.
4. **Historical claims:** Project State is useful source material but is not accepted as verified Dexter test evidence. Claims about prior actions and outcomes require later review against available artifacts and user recollection.
5. **Current first-release baseline:** The four named capabilities are not approved as the Dexter implementation baseline. The user will provide prior Skills at a later building stage for assessment.
6. **Active approvals:** Approval entries in the imported source are not active Dexter authorizations. Dexter requires current, explicit direction for future work.
7. **Quantitative success:** The user selected qualitative success only for the charter.
8. **Audience boundary:** The initial audience is individual Microsoft 365 Copilot users; a narrower professional persona is not established.

## 17. Interview record

### Round 1 — 2026-08-28

| Topic | User response | Charter treatment |
| --- | --- | --- |
| Imported authority | Reaffirm important decisions before treating them as binding. | Prior approvals remain non-binding source history until reaffirmed. |
| Recorded work | The files were built through Aegis; the user has not reviewed them for full accuracy. The project worked in some ways but not all. Dexter is being built to take over where Aegis failed. | Preserve provenance and uncertainty; do not import claims as verified Dexter evidence. |
| First-release baseline | Prior Skills will be supplied and evaluated when building begins; the current task is only the charter. | Defer Skill baseline, MVP, and implementation decisions. |

### Round 2 — 2026-08-28

| Topic | User response | Charter treatment |
| --- | --- | --- |
| Vision | Accurate as written. | Mark the synthesized vision confirmed. |
| Initial user | Individual Microsoft 365 users. | Use a broader individual-user definition rather than product-owner-only scope. |
| Priority outcomes | Durable work memory, progress visibility, less manual upkeep, and user-controlled knowledge. | Make these the four primary charter outcomes; keep other outcomes provisional. |

### Round 3 — 2026-08-28

| Topic | User response | Charter treatment |
| --- | --- | --- |
| Non-negotiable boundaries | User-approved authority, inspectable portable data, preserved history, and no false success. | Mark these four boundaries confirmed regardless of implementation. |
| Success framing | Qualitative only. | Do not invent numeric targets or require later quantitative baselines in the charter. |
| Dexter versus Aegis | Make the process less complicated and smaller in footprint; specialize in managing Skills and testing their unique “vibe” through scenario runs using natural-language instructions. | Add explicit Dexter governance expectations and avoid importing Aegis's large control structure. |

## 18. Remaining open interview questions

No blocking charter-interview questions remain. Items deliberately deferred beyond the charter are:

1. Which prior Skills should continue, change, combine, or retire.
2. Which prior Aegis claims can be verified from supplied artifacts and rerun scenarios.
3. The MVP or first-release capability set.
4. Detailed schemas, storage mechanisms, and runtime architecture.
5. Scenario definitions for each Skill's behavior and “vibe.”

## 19. Acceptance boundary

Version 1.0 was explicitly accepted by the user on 2026-08-28 after the source-assisted interview addressed all charter-level questions.

Acceptance establishes project direction. It does not itself authorize implementation, package creation, connected retrieval, graph writes, deployment, publication, or release.
