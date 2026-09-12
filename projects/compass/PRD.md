# Compass Product Requirements Document

## Document control

- **Status:** active
- **Development phase:** Build active; four-Skill local candidate passed disconnected validation and is ready for Skill host testing
- **Owner:** User / product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-12
- **Governed by:** [Compass Charter](CHARTER.md)

## Product purpose and user problems

Compass enables a Cloud Solution Architect specializing in Identity and Access Management, with supporting Cybersecurity and Threat Intelligence expertise, to preserve and reuse useful work context as durable, user-controlled personal work memory. The work to be remembered is organized around Efforts that the person needs to track and prioritize. Efforts can take different forms and may be described with domain-specific terms. Today, interruptions make it difficult to regain context and efficiently communicate or repurpose an Effort's vision and ideas. Coworkers and peers need to understand and represent the user's value and service, while customers need appropriate workload visibility to help prioritize attention.

## Prioritized outcomes

| ID | Outcome | Priority | Charter state |
| --- | --- | --- | --- |
| OUT-001 | A person can preserve and reuse useful work context as durable personal work memory. | Must | Accepted |
| OUT-002 | A person can track and prioritize Efforts across different forms of work without losing their domain-specific meaning. | Must | Accepted |
| OUT-003 | A person can resume an effort with important context intact after an interruption ranging from overnight to weeks. | Must | Accepted |
| OUT-004 | A person can quickly communicate an effort's vision and ideas and repurpose its context into useful documentation and artifacts. | Must | Accepted |
| OUT-005 | Coworkers and peers can understand and represent the user's relevant work, value, and service. | Must | Accepted |
| OUT-006 | Customers can understand the user's relevant workload and help prioritize which efforts receive attention. | Must | Accepted |
| OUT-007 | A person can establish an initial durable knowledge graph across current Efforts through a guided interview and authorized work-evidence scan. | Must | Accepted |
| OUT-008 | Account managers supporting the user's contract, customer stakeholders, and leadership can understand relevant customer work from concise, audience-appropriate Activities. | Must | Accepted |
| OUT-009 | The filing cabinet remains useful over time by archiving completed or stale Efforts and compacting stale Activity detail without losing historical accountability. | Must | Accepted |
| OUT-010 | A person can scan recent customer conversations during ordinary work and update the filing cabinet without repeating installation. | Must | Accepted |

## Product requirements and acceptance signals

| ID | Requirement | Priority | Acceptance signal | State |
| --- | --- | --- | --- | --- |
| PR-001 | Compass must retain enough context for the user to resume an effort after an overnight or multi-week interruption. | Must | In a representative return, the user can recover the effort's important context without manually reconstructing it from scattered sources. | Accepted |
| PR-002 | Compass must help the user reuse retained effort context when communicating vision and ideas or creating documentation and artifacts. | Must | In a representative effort, the user can efficiently produce an accurate, fit-for-purpose explanation or artifact from retained context. | Accepted |
| PR-003 | Compass must help the user communicate relevant Effort value and workload in a form appropriate to internal peers or customers. | Must | A representative audience can understand the relevant Efforts and either represent the user's contribution or make an informed priority decision without receiving unrelated personal work memory. | Accepted |
| PR-004 | The Installation Interview must build the initial durable knowledge graph across the user's current Efforts through guided conversation and an authorized Microsoft 365 Work IQ scan. | Must | The completed installation has durable graph artifacts grounded in the interview and authorized evidence, without requiring the user to direct storage mechanics. | Accepted |
| PR-005 | The installation scan must consider authorized email and chat evidence, including group and meeting chats, for context relevant to current Efforts. | Must | The installation can show which authorized evidence types it considered and distinguish retrieved evidence from durable graph knowledge. | Accepted |
| PR-006 | Source-derived fragments must remain inspectable, correctable working knowledge with enough source context to distinguish evidence from Compass interpretation. | Must | The user can inspect and correct accumulated knowledge, and Compass does not present its interpretation as source fact. | Accepted |
| PR-007 | The durable knowledge graph must represent Efforts, Conversations, People, Customer Success Plans, the Parking Lot disposition, and Daily Logs without depending on hidden host-only state. | Must | The installed graph preserves each concept and relationship in its portable representation. | Accepted |
| PR-008 | Each Effort must align with zero or one CSP and may relate to many Conversations and People. | Must | The graph prevents an Effort from having more than one CSP while preserving multiple Conversation and Person relationships. | Accepted |
| PR-009 | Each Conversation must align with exactly one Effort or have a Parking Lot disposition. | Must | Every durable Conversation resolves to one Effort or Parking Lot, never several Efforts or no disposition. | Accepted |
| PR-010 | A Person may participate in multiple Efforts and Conversations. | Must | The same stable Person can be related to multiple Efforts and Conversations without duplication as separate people. | Accepted |
| PR-011 | Compass must use Effort as the canonical graph concept while recognizing Tracking Topic and domain-specific work labels as equivalent user language when appropriate. | Must | The user can describe work naturally and Compass represents it as an Effort without discarding the user's meaningful terminology. | Accepted |
| PR-012 | The Daily Log must record minimal entries for every durable graph change by user-local date so graph-activity metrics can be derived without creating work-event history or relationship authority. | Must | Each durable graph change contributes one entry with timestamp, object type, stable object ID, and change type. | Accepted |
| PR-013 | The durable knowledge graph must use inspectable Markdown and YAML files stored in the user's OneDrive. | Must | The complete graph remains readable and editable through ordinary file access without relying on hidden Skill Host state. | Accepted |
| PR-014 | Compass must preserve the graph's meaning when different compatible Skill Hosts read or write its files. | Must | A host adaptation can interpret and update the accepted graph contract without changing object meaning, identity, or relationship cardinality. | Accepted; compatibility untested |
| PR-015 | The Installation Interview may create Conversations from selected Work IQ evidence and establish structurally valid Effort and Person relationships in the initial graph. | Must | Installation creates inspectable working knowledge with source context and valid relationships that the user can refine through ordinary Compass use. | Accepted |
| PR-016 | Before Work IQ retrieval, Installation must propose a bounded plan specifying evidence sources, date range, and limits for user editing or approval. | Must | No retrieval begins until the user approves or edits the visible plan, and the observed retrieval remains within the resulting scope. | Accepted |
| PR-017 | Every graph object must use the shared identity header and preserve unrecognized frontmatter and user-authored Markdown during managed updates unless safe parsing is impossible. | Must | Objects retain stable identity and creation metadata across moves or renames, and a managed update does not remove unrelated user content. | Accepted |
| PR-018 | The OneDrive graph root must contain `_compass/config.yaml`, `CSPs/`, `Efforts/`, `People/`, `Conversations/`, and `Daily Logs/`; paths and filenames are transport locations rather than object identity. | Must | Every managed object is stored under its object-type folder, and moving or renaming a file does not change its stable object identity. | Accepted |
| PR-019 | Governor must protect graph integrity and truthful effects, while Curator must help organize, reconcile, and improve working knowledge. | Must | Structurally invalid or destructive changes are blocked, ordinary refinements remain easy, and no component misreports durable effects. | Accepted |
| PR-020 | `_compass/config.yaml` must identify schema version 2, one stable UUID graph ID, and one confirmed IANA timezone. | Must | The installed graph has a stable identity, an unambiguous schema contract, and deterministic user-local Daily Log dates. | Accepted |
| PR-021 | Graph object filenames must use readable lowercase kebab-case title slugs while stable YAML IDs remain authoritative; a same-folder slug collision requires a user-selected distinct filename. | Must | Users can recognize files by name, and Compass never overwrites, merges, or invents a suffix when title slugs collide. | Accepted |
| PR-022 | Compass must represent a Conversation, also called an Activity, as a meaningful unit of customer work rather than as a source thread, chat, meeting, or message container. | Must | Each Activity explains what customer work occurred and why it matters; source boundaries do not dictate Activity boundaries. | Accepted |
| PR-023 | Compass must create Activities only for work materially attributable to an identifiable customer relationship, outcome, commitment, or need. | Must | Generic internal work is excluded; internal work is included only when its material customer connection is evident. | Accepted |
| PR-024 | Compass must interpret Activity boundaries across authorized evidence and direct user input. | Must | Evidence from multiple sources may support one coherent Activity, and one source may yield multiple Activities when it contains distinct units of customer work. | Accepted |
| PR-025 | Each Activity must provide a concise factual account of what happened, why it matters to the customer, relevant People, its Effort or Parking Lot disposition, and useful progress, decision, risk, commitment, insight, or next-step context when present. | Must | A reader can understand the customer work and its significance without reading raw source content. | Accepted |
| PR-026 | Activity communication must be adapted to account managers supporting the user's contract, customer stakeholders, or leadership without treating graph presence as disclosure authority. | Must | The user can review an audience-appropriate account that omits unrelated, sensitive, or audience-inappropriate context before it is shared. | Accepted |
| PR-027 | Curator's primary purpose must be to identify completed or stale Efforts for review and archive those the user authorizes. | Must | Curator discloses the applicable completion or staleness basis, proposes candidates without changing them, and archives only the Efforts the user authorizes. | Accepted |
| PR-028 | Before removing a stale Activity file related to an archived Effort, Curator must preserve essential Activity metadata on that Effort. | Must | The archived Effort retains each removed Activity's stable ID, title, `lastActivityAt`, optional `startedAt`, participating People, concise customer-work summary, and minimized provenance. | Accepted |
| PR-029 | Curator must verify the archived Effort's retained Activity metadata before requesting authority to remove stale Activity files. | Must | No Activity file is removed unless its metadata is readable on the archived Effort and the user explicitly approves the disclosed removals. | Accepted |
| PR-030 | Curator must preserve graph integrity and report partial lifecycle effects truthfully. | Must | References to removed Activities do not remain active, every archive and removal is indexed in the Daily Log, and blocked, partial, or uncertain effects are not reported as complete. | Accepted |
| PR-031 | Curator must default stale-candidate review to 14 days without meaningful customer Activity while allowing the user to change the threshold or scope. | Must | The proposed review visibly uses 14 days unless edited, and threshold approval authorizes review rather than archival or removal. | Accepted |
| PR-032 | Last Activity must be derived from the newest reliable timestamp of meaningful customer-work content associated with an Effort. | Must | File modification, graph maintenance, retrieval, indexing, attention state, and Daily Log timestamps do not reset inactivity; incomplete source coverage or ambiguous timestamps prevent a confident stale classification. | Accepted |
| PR-033 | Activity Scan must update an existing graph from a user-approved Email and Teams scope during ordinary work. | Must | The user can run a bounded scan without reinstalling Compass, and no retrieval occurs before plan approval. | Accepted |
| PR-034 | Activity Scan must distinguish retrieval authority from graph-change authority. | Must | Approved retrieval produces a reviewable proposal; no graph mutation occurs until the user separately approves exact effects. | Accepted |
| PR-035 | Activity Scan must interpret, correlate, and place customer Activities using work meaning and graph context rather than source-container or title similarity alone. | Must | Related evidence may refine one Activity, distinct work remains separate, and consequential ambiguity is unresolved rather than guessed. | Accepted |
| PR-036 | Activity Scan must disclose source coverage, continuation, and recency limits. | Must | The scan report identifies inspected, unavailable, incomplete, and uncertain evidence and does not claim complete recency from partial results. | Accepted |
| PR-037 | Activity Scan must preserve stable People and Activity identity during updates. | Must | Existing objects are reused only when identity or continuity is supported; ambiguous cases do not silently merge. | Accepted |
| PR-038 | Activity Scan must present exact graph paths, relationships, provenance, preserved content, and Daily Log effects before mutation. | Must | The user can understand and edit the complete durable proposal without reading schema internals. | Accepted |
| PR-039 | Activity Scan must verify approved graph effects and report partial or blocked results truthfully. | Must | Read-back and Daily Log state agree with every claimed effect. | Accepted |
| PR-040 | Activity Scan must never alter source email or chat or retain raw transcripts in the graph. | Must | Source systems remain unchanged and durable provenance is minimized. | Accepted |
| PR-041 | Graph Governor must validate graph configuration, canonical entity schemas, identity, references, cardinality, lifecycle invariants, paths, and preservation without mutation. | Must | Invalid structure produces precise blockers and validation itself causes no graph change. | Accepted |
| PR-042 | Graph Governor must validate proposed operations before mutation and observed graph state after mutation. | Must | Initiating Skills receive preflight and postflight results tied to a disclosed base state and expected effects. | Accepted |
| PR-043 | Graph Governor must reconcile verified durable effects with Daily Log entries. | Must | Missing, duplicate, or unsupported change entries prevent a complete-success claim. | Accepted |
| PR-044 | Graph Governor must distinguish structural validity from substantive truth and user authority. | Must | A valid result does not claim factual correctness or authorize retrieval, mutation, disclosure, archival, or removal. | Accepted |
| PR-045 | Compass graph writers must follow one canonical serialization and write procedure. | Must | Installation, Activity Scan, and Curator produce compatible Markdown/YAML with stable IDs, preserved content, validated relationships, read-back, and dated change indexing. | Accepted |

## Required capabilities

| Capability | Why it is needed | Skill Host dependency | State |
| --- | --- | --- | --- |
| Effort memory | Supports `OUT-001`, `OUT-002`, and `PR-011` by retaining useful context around work the user tracks and prioritizes while interpreting domain-specific language. | Cowork must interpret the user's language and work with the durable graph representation. | Needs verification |
| Guided installation conversation | Supports `OUT-007` by eliciting and distinguishing multiple current Efforts without requiring the user to direct storage mechanics. | Cowork must support a multi-turn conversation and preserve enough state to review and confirm the proposed result. | Implemented in local candidate; host needs verification |
| Bounded retrieval approval | Enforces `PR-016` by separating interview and planning from evidence access. | Cowork must present a visible sources/date-range/limits plan and wait for user editing or approval before Work IQ retrieval. | Needs verification |
| Work evidence retrieval | Supports `OUT-007` and `PR-005` by finding relevant context in authorized email and chat evidence, including group and meeting chats. | Cowork must provide authorized Microsoft 365 Work IQ retrieval with observable source boundaries. | Needs verification |
| Initial Conversation creation | Supports `PR-015` by turning authorized evidence into durable Conversations and structurally valid relationships during installation. | Cowork must preserve source context and verified OneDrive effects. | Needs verification |
| Customer Activity interpretation | Supports `OUT-008` and `PR-022` through `PR-026` by finding coherent customer work across evidence and expressing why it matters. | Cowork must interpret across authorized results, preserve minimized provenance, and avoid inventing customer relevance. | Implemented in local candidate; host needs verification |
| Audience-aware Activity communication | Supports `PR-026` by adapting the same factual Activity to the named audience. | Cowork must distinguish account manager, customer, and leadership contexts and support review before disclosure. | Needs verification |
| Curator lifecycle review | Supports `OUT-009` and `PR-027` through `PR-032` by applying a default 14-day meaningful-Activity review, preserving Activity history, and carrying out authorized archival and removal. | Cowork must distinguish source-content time from graph-maintenance time, disclose incomplete evidence coverage, present editable criteria and exact effects, update and verify the Effort before removing Activity files, and report partial effects honestly. | Local candidate implemented; host needs verification |
| Ongoing Activity Scan | Supports `OUT-010` and `PR-033` through `PR-040` by refreshing customer Activities without reinstalling Compass. | Cowork must support bounded recurring retrieval, item-level timestamps, continuation, proposal review, and verified graph updates. | Local contract active; host needs verification |
| Durable graph creation | Supports `PR-004` and `PR-013` by creating and verifying the Markdown/YAML files that make the initial knowledge graph persistent in OneDrive. | Cowork must create, update, and verify files in the user's selected OneDrive location. | Implemented in local candidate; host needs verification |
| Knowledge refinement | Supports `PR-006` and `PR-019` by keeping working knowledge inspectable, editable, and grounded in source context. | Cowork must let the user correct, organize, and refine graph content without schema work. | Needs verification |
| Graph governance | Supports `PR-019` and `PR-041` through `PR-045` by validating structure, identity, relationships, preservation, and reported effects. | Cowork must apply the graph contract and verify durable effects without obstructing ordinary refinement. | Local candidate implemented; host needs verification |
| Portable knowledge representation | Supports `PR-007` through `PR-010` and `PR-014` by preserving the accepted graph concepts and relationships outside hidden host state. | Cowork must read and write Markdown/YAML without silently changing meaning, identity, or cardinality. | Needs verification |
| Dated change indexing | Supports `PR-012` by recording minimal durable-change entries from which graph-activity metrics can be derived. | Cowork must determine the user-local date and update the portable representation without creating competing relationship state. | Needs verification |
| Context recovery | Supports `OUT-003` by presenting useful retained context when the user returns to an Effort. | Cowork must retrieve the authorized durable context for the selected Effort. | Needs verification |
| Communication and artifact reuse | Supports `OUT-004` by applying retained context to the user's current communication or artifact need. | Cowork must use authorized context and create or return the requested content or artifact. | Needs verification |
| Audience-aware workload communication | Supports `OUT-005` and `OUT-006` by presenting relevant Effort context without exposing unrelated memory. | Cowork must distinguish the intended audience and let the user review what will be disclosed. | Needs verification |

## Non-goals

- None accepted yet.

## Constraints and dependencies

- No product-specific constraints or dependencies accepted yet.
- Skill Host capabilities must be observed or safely probed before the design relies on them.
- Copilot Cowork is the selected first Skill Host; selection does not establish any required capability or cross-host compatibility.

## Specification index

| Specification | Requirements covered | State |
| --- | --- | --- |
| [Installation Interview](specifications/installation-interview.md) | `PR-004` through `PR-016`, `PR-019`, `PR-020` | Active |
| [Knowledge Graph](specifications/knowledge-graph.md) | `PR-007` through `PR-014`, `PR-017` through `PR-021` | Active |
| [Customer Activity Interpretation](specifications/customer-activity-interpretation.md) | `PR-022` through `PR-026` | Active |
| [Curator Lifecycle](specifications/curator-lifecycle.md) | `PR-027` through `PR-032` | Active |
| [Activity Scan](specifications/activity-scan.md) | `PR-033` through `PR-040` | Active |
| [Graph Governor](specifications/graph-governor.md) | `PR-019`, `PR-041` through `PR-045` | Active |

## Open questions

- What information and relationships make an effort understandable and actionable over time?
- What details should be included or withheld for account managers, customer stakeholders, and leadership in representative use?

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Created as a source of truth governed by the reset Charter. |
| 2026-09-11 | Added the accepted personal work memory outcome from the Charter interview. |
| 2026-09-11 | Added tracking and prioritizing varied efforts as an accepted outcome and recorded the common Effort concept as provisional. |
| 2026-09-11 | Added continuity and reuse outcomes with provisional requirements and acceptance signals. |
| 2026-09-11 | Added internal-peer and customer outcomes for communicating value, workload, and priorities, with audience-aware disclosure as a provisional requirement. |
| 2026-09-11 | Established the initial Cloud Solution Architect role and its Identity and Access Management, Cybersecurity, and Threat Intelligence context. |
| 2026-09-11 | Established the multi-effort Installation Interview as the first complete experience and added its provisional requirement and host needs. |
| 2026-09-11 | Clarified that installation builds durable graph artifacts through an interview and Work IQ scan; accepted the evidence types while leaving schema and write authority open. |
| 2026-09-11 | Required explicit review and approval before evidence-derived proposals become durable graph knowledge. |
| 2026-09-11 | Added the five accepted graph concepts while leaving terminology, relationships, and schema provisional. |
| 2026-09-11 | Confirmed CSP terminology and accepted Topic, Conversation, Person, and Parking Lot relationship cardinality. |
| 2026-09-11 | Established Effort as the canonical graph concept and made recognition of Tracking Topic and domain-specific synonyms a requirement. |
| 2026-09-11 | Defined the Daily Log as a dated index of accepted graph changes and added its acceptance signal. |
| 2026-09-11 | Required the authoritative graph to use Markdown/YAML in OneDrive and added host-independent semantic portability requirements. |
| 2026-09-11 | Selected Copilot Cowork as the first Skill Host and marked every required host capability as needing verification. |
| 2026-09-11 | Assigned reviewed Conversation creation to Installation and superseded the archived Daily Scan-only ownership assumption. |
| 2026-09-11 | Required a visible, editable, bounded retrieval plan before Installation accesses Work IQ evidence. |
| 2026-09-11 | Simplified Daily Log entries to the minimum needed for graph-change indexing and graph-activity metrics. |
| 2026-09-11 | Accepted the shared graph-object identity header, formatting conventions, and preservation of user-added content. |
| 2026-09-11 | Accepted the object-type OneDrive folder layout with `Efforts/` replacing the archived `Tracking Topics/` folder. |
| 2026-09-11 | Superseded review-before-write with provisional durable knowledge, explicit promotion to accepted knowledge, Governor integrity, and Curator formalization responsibilities. |
| 2026-09-11 | Accepted schema version 2, stable UUID graph identity, and confirmed IANA timezone as the complete graph configuration baseline. |
| 2026-09-11 | Required readable lowercase kebab-case title-slug filenames while retaining stable YAML IDs as object identity. |
| 2026-09-11 | Required a user-selected distinct filename when readable title slugs collide. |
| 2026-09-12 | Activated the PRD for build and simplified Compass to accumulating and refining inspectable working knowledge. |
| 2026-09-12 | Added customer-only Activity interpretation and audience-appropriate transparency for account managers, customer stakeholders, and leadership. |
| 2026-09-12 | Defined Curator's primary lifecycle purpose and the preserve-before-remove contract for stale Activities on archived Efforts. |
| 2026-09-12 | Set the default stale-review threshold to 14 days and required meaningful source-content recency rather than graph-edit recency. |
| 2026-09-12 | Completed Discovery for the Installation candidate and began Build with `compass-installation-interview` version `0.1.0-local-candidate`. |
| 2026-09-12 | Established Activity Scan and Graph Governor as dedicated Build components and required one canonical graph serialization and write procedure. |
| 2026-09-12 | Completed the local four-Skill candidate, packages, orchestration, synthetic fixture, structural validation, and disconnected lifecycle walkthrough; Cowork behavior remains unverified. |

## Authority boundary

This PRD defines desired outcomes and requirements under the Charter. It does not independently accept provisional Charter direction or authorize implementation or external effects.