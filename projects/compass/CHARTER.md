# Compass Charter

## Document control

- **Status:** accepted
- **Development phase:** Build active; four-Skill local candidate passed disconnected validation and is ready for Skill host testing
- **Owner:** User / product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-12

## Sources of truth

| Document | Responsibility | Status |
| --- | --- | --- |
| This Charter | Vision, purpose, intended users, desired outcomes, scope, boundaries, and authority | Accepted |
| [Product Requirements Document](PRD.md) | Prioritized outcomes, product requirements, required capabilities, acceptance signals, non-goals, constraints, and dependencies governed by this Charter | Active |

The active Specifications define the Installation Interview, Knowledge Graph, Customer Activity Interpretation, and Curator Lifecycle contracts. The local Installation Skill candidate begins Build; linked Test Plans guide disconnected validation and the first complete Skill Host experience.

## Vision and purpose

Compass helps a person build durable, user-controlled memory from their work. Portability supports that personal experience by keeping the user's knowledge and workflows independent of any single Skill Host; building a general-purpose knowledge framework is not a coequal product purpose.

## Intended users

The initial user is a Cloud Solution Architect specializing in Identity and Access Management, with supporting expertise in Cybersecurity and Threat Intelligence. Their work includes varied efforts that must be understood and prioritized with other people.

The first experience serves three audiences for customer-work transparency:

- account managers supporting the user's contract, who need to understand and represent the user's work, value, and service;
- customer stakeholders, who need appropriate visibility into work performed for them and the ability to help prioritize attention; and
- leadership, who need concise evidence of customer impact, workload, risks, and priorities.

## Desired outcomes

- **Accepted:** A person can preserve and reuse useful work context as durable personal work memory.
- **Accepted:** A person can track and prioritize the Efforts in which they are involved, even when those Efforts have different forms or domain-specific names.
- **Accepted:** A person can resume an effort with its important context intact after an interruption ranging from overnight to weeks.
- **Accepted:** A person can quickly communicate an effort's vision and ideas and repurpose its context into useful documentation and artifacts.
- **Accepted:** Coworkers, peers, and customers can understand the relevant work well enough to represent its value or help prioritize the user's attention.
- **Accepted:** The Installation Interview establishes Compass by building an initial durable knowledge graph from a guided interview and authorized work evidence.
- **Accepted:** Installation may create and refine Conversations from its authorized Work IQ scan and relate them to Efforts and People as part of the initial graph.
- **Accepted:** A Conversation, also called an Activity, is Compass's durable interpretation of a meaningful unit of customer work. It is not an email thread, chat, meeting, or message container.
- **Accepted:** Only work attributable to an identifiable customer relationship, outcome, commitment, or need becomes an Activity. Internal work qualifies only when it materially advances that customer work.
- **Accepted:** Activities provide a concise factual core for transparency with account managers supporting the user's contract, customer stakeholders, and leadership; communication remains appropriate to its intended audience.
- **Accepted:** The knowledge graph represents Efforts, Conversations, People, Customer Success Plans (CSPs), and dated history or a Daily Log.
- **Accepted:** Each Effort aligns with at most one CSP and may relate to many Conversations and People. Each Conversation aligns with exactly one Effort or appears in the Parking Lot. People may participate in multiple Efforts and Conversations.
- **Accepted:** **Effort** is the canonical graph term. Compass recognizes Tracking Topic, topic, critical situation, major project, product interpretation, design change request, security recommendation, and other domain-specific terms as descriptions of an Effort.
- **Accepted:** Compass accumulates useful fragments as inspectable working knowledge that the user and Compass can refine as understanding improves.
- **Accepted:** The Daily Log uses minimal entries to index durable graph changes and support graph-activity metrics. It does not serve as a diary of work events or a second authority for graph relationships.
- **Accepted:** The durable knowledge graph is represented as inspectable Markdown and YAML files stored in the user's OneDrive. This storage contract is independent of the Skill Host that executes Compass Skills.
- **Accepted:** Curator's primary purpose is lifecycle maintenance: help the user archive completed or stale Efforts and remove stale Activity files after preserving their essential metadata on the archived Effort.
- **Accepted:** Curator defaults its inactivity review to 14 days. It measures inactivity from meaningful customer Activity, not file modification, graph maintenance, retrieval time, attention state, or Daily Log recency.

## Scope and boundaries

- **In scope:** An initial Installation Interview that builds a Markdown/YAML knowledge graph in the user's OneDrive across current customer Efforts through guided conversation and an authorized Microsoft 365 Work IQ scan.
- **Out of scope:** General internal work, administration, professional development, product exploration, or coordination that cannot be materially connected to an identifiable customer's work.
- **Authority and control:** Before retrieval, Compass proposes the evidence sources, date range, and limits for the user to edit or approve. Compass may add and refine working knowledge within the authorized task; it asks when placement is materially ambiguous or a change could disclose, overwrite, or destroy important content. The user can inspect, edit, correct, or remove graph content through ordinary files and Compass interactions.
- **Privacy and safety:** Work evidence access must remain within the approved bounded retrieval plan. An Activity's presence in the graph does not authorize disclosure. Audience-facing communication includes only context appropriate to the named audience and remains reviewable before sharing.

## Experience principles

### Energy to mass

> Evidence becomes Activity. Activity becomes knowledge. Knowledge becomes durable evidence for what comes next.

Compass treats customer work as a cycle between energy and mass:

- **Mass is tangible evidence.** Recorded email and chat content, grounded when available by an Email ID or Chat ID, gives Compass something concrete from which to understand the work.
- **Energy is Activity.** Compass interprets the movement within that evidence: customer progress, decisions, risks, commitments, outcomes, insights, and next steps. The source contains the facts; the Activity expresses what the customer work means and how it is moving.
- **Energy becomes new mass.** Compass refines Activities into durable Markdown summaries, relationships, and evolving context around Efforts, CSPs, People, and their constructs.
- **New mass releases more energy.** The accumulated graph gives future conversations and evidence enough context to recover momentum, improve interpretation, and produce the next useful refinement.

The filing cabinet is therefore not a static archive. It is a renewable cycle in which concrete customer evidence becomes useful understanding, and useful understanding becomes durable material that can support future customer work.

## Candidate capability landscape

| Capability | Intended contribution | State |
| --- | --- | --- |
| Effort memory | Preserve context about varied forms of work under the canonical Effort concept while recognizing the user's domain-specific language. | Accepted |
| Installation Interview | Build the initial durable knowledge graph, including source-derived Conversations and relationships, through a guided interview and authorized Work IQ scan across the user's current Efforts. | Local candidate implemented; host support needs verification |
| Work evidence discovery | Find context relevant to current efforts in authorized email and chat evidence, including group and meeting chats. | Accepted for the first experience; host support needs verification |
| Customer Activity interpretation | Interpret authorized evidence and direct user input as meaningful units of customer work rather than mirroring source threads or messages. | Accepted |
| Retrieval planning | Propose a bounded evidence scope from the interview and obtain user edits or approval before retrieval. | Accepted for the first experience; host support needs verification |
| Portable knowledge representation | Represent Efforts, Conversations, People, CSPs, the Parking Lot disposition, and Daily Logs as durable working knowledge with the accepted relationships. | Accepted |
| Change history | Record minimal dated entries for durable graph changes so graph-activity metrics can be derived without duplicating object relationships. | Accepted |
| OneDrive persistence | Store the durable Markdown/YAML graph in the user's OneDrive independently of Skill Host state. | Accepted; host support needs verification |
| Governor | Protect graph structure, identity, relationships, user-authored content, and truthful effects. | Accepted responsibility; separate read-only Skill implemented as a local candidate |
| Curator | Use a default 14-day meaningful-customer-activity window to review completed or stale Efforts, then compact stale Activities into retained metadata on an authorized archived Effort before removing the Activity files. | Accepted primary responsibility; host support needs verification |
| Context recovery | Help the user regain an effort's important context after interruptions without reconstructing it from scattered sources. | Provisional |
| Communication and artifact reuse | Help the user express an effort's vision and ideas and reuse retained context in documentation and other artifacts. | Provisional |
| Workload and priority communication | Help the user show relevant workload and effort value to the appropriate audience so attention can be prioritized. | Provisional |

## Skill Host

A **Skill Host** is the product and operating environment that loads or invokes a Skill. It may combine an AI model with tools and connectors, permissions, available context, conversation state, and user interaction controls. Selecting a host does not establish its capabilities or compatibility.

| Candidate Skill Host | Intended use | State |
| --- | --- | --- |
| Copilot Cowork | First target for the Installation Interview, authorized Microsoft 365 Work IQ evidence retrieval, proposal review, and OneDrive graph creation. | Selected; required capabilities need verification |

## Constraints and dependencies

- The first experience depends on authorized Microsoft 365 Work IQ access to email and chat evidence, including group and meeting chats.
- Copilot Cowork is the first target Skill Host; this does not make Cowork part of the authoritative graph or establish compatibility.
- The knowledge graph's Markdown/YAML files are critical installation artifacts stored in the user's OneDrive and follow the active Knowledge Graph Specification.
- The Skill Host must preserve source context, user-authored content, and the user's ability to inspect and correct working knowledge.
- The Skill Host must not retrieve Work IQ evidence before the user approves or edits the proposed sources, date range, and limits.
- OneDrive path behavior, permissions, writes, conflicts, and effect verification must be established before connected installation.
- Curator must verify retained Activity metadata on an archived Effort before removing any Activity file, and removal requires an explicit user decision because it is destructive.

## Open questions

- What context about an Effort must remain available to support continuity, communication, and reuse?
- What details should each audience receive when the same Activity is communicated to account managers, customer stakeholders, or leadership?

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Reset to a clean Dexter interview scaffold; prior Compass material is reference input rather than accepted current direction. |
| 2026-09-11 | Established personal work memory as Compass's product purpose; portability supports that experience rather than defining a coequal framework product. |
| 2026-09-11 | Established tracking and prioritizing varied forms of effort as an accepted outcome; retained the common Effort concept as provisional pending terminology and knowledge-model decisions. |
| 2026-09-11 | Added continuity across interruptions and rapid communication and artifact reuse as accepted outcomes. |
| 2026-09-11 | Established coworkers, peers, and customers as audiences for communicating value, workload, and priorities; left the user's exact role and disclosure boundaries open. |
| 2026-09-11 | Established a Cloud Solution Architect specializing in Identity and Access Management, with supporting Cybersecurity and Threat Intelligence expertise, as the initial user. |
| 2026-09-11 | Established an Installation Interview spanning multiple current efforts or tracked topics as the first complete experience, replacing the single-effort assumption. |
| 2026-09-11 | Clarified that installation builds the initial durable knowledge graph through an interview and authorized Work IQ scan of email and chat evidence; retained files, schema, and write authority as open design questions. |
| 2026-09-11 | Required explicit user review and approval before evidence-derived proposals become durable graph knowledge. |
| 2026-09-11 | Accepted five graph concepts: efforts or tracked topics, conversations, people, strategic outcomes or plans, and dated history or a daily log; retained terminology, relationships, and schema as provisional. |
| 2026-09-11 | Confirmed Customer Success Plan terminology and accepted relationship cardinality: one optional CSP per Topic, many Conversations and People per Topic, many Topics and Conversations per Person, and one Topic or Parking Lot disposition per Conversation. |
| 2026-09-11 | Established Effort as the canonical graph term and retained Tracking Topic and domain-specific labels as recognized natural-language descriptions. |
| 2026-09-11 | Defined the Daily Log as a dated index of accepted graph changes rather than work events or relationship authority. |
| 2026-09-11 | Required the authoritative knowledge graph to use inspectable Markdown/YAML files in the user's OneDrive, independently of the executing Skill Host. |
| 2026-09-11 | Selected Copilot Cowork as the first target Skill Host while leaving every required host capability subject to verification. |
| 2026-09-11 | Assigned creation of reviewed Conversations and their Effort and Person relationships to Installation, superseding the archived design that deferred Conversation creation to Daily Scan. |
| 2026-09-11 | Required Installation to propose a bounded Work IQ retrieval plan and obtain user edits or approval before retrieval. |
| 2026-09-11 | Simplified the Daily Log to minimal per-change entries that support graph-activity metrics. |
| 2026-09-11 | Superseded review-before-write: source-derived content may enter as provisional knowledge; Governor protects integrity, Curator supports formalization, and user review promotes content to accepted knowledge. |
| 2026-09-12 | Simplified Compass to an inspectable working-knowledge filing cabinet, accepted the Charter, and authorized progression to local build work. |
| 2026-09-12 | Defined Conversation as customer-work Activity, excluded work without a material customer connection, and established account managers, customer stakeholders, and leadership as transparency audiences. |
| 2026-09-12 | Added the Energy to mass mantra: tangible customer evidence becomes interpreted Activity, which is refined into durable Markdown knowledge that supports future work. |
| 2026-09-12 | Entered coordinated Build with local Installation, Activity Scan, Graph Governor, and Curator candidates plus one customer-work lifecycle Orchestration. |
| 2026-09-12 | Established Curator's primary purpose: archive completed or stale Efforts and remove stale Activity files only after retaining their metadata on the archived Effort. |
| 2026-09-12 | Set Curator's default inactivity window to 14 days and separated meaningful customer Activity recency from graph-maintenance timestamps and incomplete evidence. |
| 2026-09-12 | Completed Discovery for the first coherent candidate and began Build with the local Compass Installation Interview Skill. |

## Authority boundary

This Charter records product direction. It does not by itself authorize implementation, connected access, external effects, publication, or release.