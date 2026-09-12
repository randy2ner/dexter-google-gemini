# Compass Installation Interview Test Plan

## Metadata

- **Owner:** User / product owner
- **Specifications:** [Compass Installation Interview Specification](../specifications/installation-interview.md); [Compass Knowledge Graph Specification](../specifications/knowledge-graph.md); [Customer Activity Interpretation Specification](../specifications/customer-activity-interpretation.md)
- **Candidate:** `compass-installation-interview` `0.1.0-local-candidate`
- **Package:** `compass-installation-interview-0.1.0-local-candidate.skill`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

This plan determines whether an exact Installation Interview candidate can guide one user from initial conversation to a verified OneDrive knowledge graph without exceeding retrieval or write authority. Success requires the complete journey to preserve conversational quality, evidence boundaries, source context, graph relationships, user correction, durable effects, and truthful reporting. Focused capability checks establish prerequisites but do not establish the complete experience.

## Scope and environment

- **In scope:** `INST-001` through `INST-010`, including the complete installation journey and focused Cowork capability checks that block candidate design.
- **Out of scope:** Ongoing Daily Scan behavior, Effort lifecycle management, audience-facing reports, another Skill Host, broad production-readiness claims, and unresolved schema choices.
- **AI surface:** Copilot Cowork with the exact candidate selected or loaded as a Skill source.
- **Material host conditions:** Signed-in Microsoft 365 identity and permissions; Skill loading and invocation; Work IQ email and chat retrieval, item-level timestamps, and continuation; multi-turn state; proposal controls; OneDrive path and file operations; Markdown/YAML preservation; and observable effect verification.
- **Privacy:** The operator reviews source results privately on the company-managed surface. Test records retain only privacy-minimized decisions, counts, capability observations, and non-identifying excerpts; they do not retain names, customer content, message text, tenant identifiers, or confidential graph content.

## Host compatibility profile

- **Required host behavior:** Load or invoke the Installation Skill; sustain a guided multi-turn interview; present and honor a bounded retrieval plan; retrieve authorized email and group or meeting chat evidence; preserve source context; support ordinary correction and refinement; create and verify OneDrive Markdown/YAML files; preserve relationship cardinality; and report partial, blocked, cancelled, and uncertain effects honestly.
- **Observed conditions:** None yet. Every required Cowork capability is `needs verification` in the PRD.
- **Another host:** Identify its product, run the focused capability checks below, compare retrieval, review, permission, context, and file-handling differences with Cowork, and record a compatibility or adaptation hypothesis before attempting the complete journey.

## Complete journey

| Stage | Skill or component | User decision | Observable effect or no-write outcome |
| --- | --- | --- | --- |
| Begin | Installation Interview | Invoke Compass and choose to begin setup. | Skill explains the installation purpose and starts a natural interview without retrieval or writes. |
| Understand | Installation Interview | Describe role, current Efforts, language, and priorities. | Skill distinguishes several Efforts and preserves meaningful user terminology without exposing storage mechanics. |
| Plan | Installation Interview | Edit, approve, or cancel proposed sources, date range, and limits. | No Work IQ retrieval occurs before approval; cancellation ends with no retrieval and no graph write. |
| Discover | Cowork and Work IQ | Allow the approved bounded scan. | Retrieval stays within approved email and chat scope and reports unavailable or ambiguous sources honestly. |
| Populate | Installation Interview | Allow the bounded scan to populate structurally valid customer-work Activities and other working knowledge. | Source-derived CSPs, Efforts, Activities, People, Parking Lot dispositions, and relationships are inspectable, retain source context, and exclude work without a material customer connection. |
| Refine | Installation Interview and Graph Governor | Correct, reorganize, or clarify accumulated knowledge. | Ordinary refinements remain easy; Governor blocks structural defects while materially ambiguous placement asks the user rather than inventing certainty. |
| Persist | Cowork and OneDrive | Review the durable graph effects. | Markdown/YAML objects and Daily Log entries preserve accepted cardinality, source context, user content, and every durable change. |
| Verify | Installation Interview | Review the completion report. | Reported success, partial effects, blockers, cancellation, or uncertainty matches independently inspected OneDrive state. |

This is a shaping guide, not an exact script. Prompts, situations, checks, and confirmation criteria should be repeatable; wording, sequence, and model responses may vary.

## Test cases

| ID | Specification behavior | Prompt or situation | Practical check and observable confirmation | Status | Latest observation |
| --- | --- | --- | --- | --- | --- |
| INST-JOURNEY-001 | `INST-001` through `INST-010` | Complete installation with several privacy-safe current Efforts and an approved bounded email/chat scan. | The journey reaches a verified initial working graph with source context, structurally valid relationships, a dated change index, and no hidden-host dependency. | not run | None |
| INST-AUTH-001 | `INST-002`, `INST-003` | Edit or cancel the proposed retrieval plan before approval. | Cowork honors the revised sources, date range, and limits, or performs no retrieval after cancellation. | not run | None |
| INST-REFINE-001 | `INST-004`, `INST-005`, `INST-006`; `GRAPH-025`, `GRAPH-026` | Populate two source-derived Conversations, correct one interpretation, and move the other between Parking Lot and an Effort. | Both remain grounded in source context; ordinary corrections persist without schema work; an ambiguous placement pauses for user direction. | not run | None |
| INST-GRAPH-001 | `INST-006`, `INST-007`, `INST-008`; `GRAPH-001` through `GRAPH-029` | Approve objects representing several Efforts, Activities, People, at least one CSP alignment, and one Parking Lot Activity; then rename or move one object and add unrelated frontmatter and Markdown before a managed update. | OneDrive contains valid graph configuration and accepted folders; readable filenames preserve stable identity across rename or move; files preserve accepted fields, cardinality, source context, and user-added content; every durable change has one Daily Log entry under the confirmed local date. | not run | None |
| INST-GRAPH-002 | `GRAPH-021`, `GRAPH-024`, `GRAPH-028`, `GRAPH-029` | Attempt to create a second object whose title produces an existing filename slug in the same object-type folder. | Compass pauses only the affected write, asks the user for a distinct filename, and neither overwrites nor merges either object. | not run | None |
| INST-EFFECT-001 | `INST-009` | Cause or encounter one blocked, partial, conflicting, or unverifiable write condition in a disposable test graph. | The terminal report does not claim complete installation and identifies the affected scope without inventing effects. | not run | None |
| INST-PORT-001 | `INST-010` | Inspect the completed graph through ordinary OneDrive file access without relying on the Cowork conversation. | Markdown/YAML content is understandable, complete for the tested scope, and contains no required hidden Cowork state. | not run | None |
| INST-ACT-001 | `INST-004` through `INST-007`; `ACT-001` through `ACT-008` | Include related evidence across email and chat, distinct customer work in one thread, and unrelated internal work in the synthetic installation input. | Installation groups and splits by coherent customer Activity, excludes unrelated work, preserves source context, and establishes valid People and Effort relationships. | not run | None |
| INST-RECENCY-001 | `INST-003`, `INST-004`, `INST-006`; `ACT-011`, `ACT-012`; `GRAPH-033` | Supply an old synthetic thread or chat containing a recent qualifying customer-work item and a separate recent non-customer item. | The created Activity records the qualifying item's timestamp as `lastActivityAt`, not container start, generic modification, retrieval time, or unrelated-item time. | not run | None |

## Focused host capability checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| Skill loading and invocation | Load a minimal non-connected candidate that identifies its purpose and asks one setup question. | Cowork invokes the intended Skill and continues a coherent multi-turn exchange. | not run |
| Bounded plan before retrieval | Ask the candidate to propose an email/chat scan plan but not run it. | Cowork displays sources, date range, and limits and waits for a user decision without retrieving evidence. | not run |
| Work IQ email retrieval | After approving a narrow plan, request metadata-level discovery for a known non-sensitive time window. | Cowork returns only in-scope email results or reports a specific access limitation. | not run |
| Work IQ group and meeting chat retrieval | After approving a narrow plan, request metadata-level discovery for known non-sensitive chat contexts. | Cowork distinguishes supported group or meeting chat access and remains within the approved window and limits. | not run |
| Email item timestamps and continuation | Use an authorized synthetic old thread with a recent known reply and, when possible, enough items to require continuation. | Cowork exposes individual qualifying content timestamps and reaches the newest in-scope item, or reports a limitation that blocks confident `lastActivityAt`. | not run |
| Teams item timestamps and continuation | Use an authorized synthetic old chat with a recent known message and, when possible, enough items to require continuation. | Cowork exposes individual qualifying content timestamps and reaches the newest in-scope item, or reports a limitation that blocks confident `lastActivityAt`. | not run |
| Working-knowledge refinement | Present synthetic source-derived graph content and ask the user to correct one item and reorganize another. | Cowork preserves source context and user edits without requiring schema instructions or a formal promotion workflow. | not run |
| OneDrive Markdown/YAML write | With separate approval, create one disposable Markdown file with simple YAML in a user-selected test location, read it back, and remove it only after separate cleanup approval. | Cowork reports the exact path and read-back content; independent inspection matches. | not run |
| Relationship preservation | Use a synthetic in-memory proposal with one CSP, two Efforts, Conversations, and shared People. | Cowork detects an invalid multi-CSP Effort or multi-Effort Conversation and permits valid many-to-many Person relationships. | not run |

## Material stop conditions

- Retrieval begins before the user approves a visible bounded plan.
- Unauthorized access, retention, or mutation occurs.
- Potentially identifying work content would need to be copied into Dexter records.
- Source-derived interpretation loses its source context or is represented as a source fact.
- Identity or relationship cardinality is corrupted.
- History is destructively lost or durable state becomes unrecoverable.
- Consequential approval or cancellation is unusable.
- Reported effects materially differ from independently inspected OneDrive state.

Record ordinary friction and non-blocking incompatibilities through the complete journey. Do not rebuild the candidate after each observation.

## Execution log

Append observations; do not rewrite an earlier run to match later expectations.

No runs recorded.

## Current success assessment

- **Assessment:** Not established.
- **Supported claims:** The Test Plan structure and expected behaviors are defined; no Cowork capability or Compass runtime behavior has been observed.
- **Unresolved claims:** `INST-001` through `INST-010` and every focused host capability check.
- **Next test or revision:** Inspect the local candidate against its runtime references, then run the smallest blocking Cowork capability probe before relying on connected retrieval or writes.