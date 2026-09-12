# Compass Curator Lifecycle Specification

## Document control

- **Status:** active
- **Version:** 1.2
- **Owner:** User / product owner
- **Created:** 2026-09-12
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-027` through `PR-032`
- **Implementation authority:** Local Skill source, fixtures, and disconnected validation are authorized. Connected OneDrive changes, Activity removal, packaging, deployment, and release remain unauthorized.

## Purpose and applicability

This Specification defines Curator's primary purpose: keep the Compass filing cabinet useful by archiving completed or stale Efforts and removing stale Activity files while preserving their essential metadata on the archived Effort.

## Scope and boundaries

- **In scope:** A default 14-day inactivity review, accurate last-Activity derivation, lifecycle proposals, Effort archival, Activity metadata retention, stale Activity removal, Daily Log indexing, effect verification, and recovery-safe ordering.
- **Out of scope:** Deciding that customer work is complete without evidence or user authority; deleting Efforts; removing Activities from active Efforts; deleting source email or chat; and general graph repair owned by Governor.
- **Authority, privacy, and safety:** Review is read-only. Archival changes require user authority. Activity-file removal is destructive and requires a separate explicit decision after the user sees what will be retained and removed. Curator never removes source evidence.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| CUR-001 | Treat archiving completed or stale Efforts as Curator's primary purpose. | Curator's normal review centers lifecycle candidates and historical compaction rather than broad rewriting of graph content. | Accepted |
| CUR-002 | Default stale-candidate review to 14 days without meaningful customer Activity and disclose the criteria before evaluating the graph. | The user sees the 14-day threshold and can edit, approve, or cancel the criteria and scope before Curator proposes candidates. | Accepted |
| CUR-003 | Propose completed or stale Efforts without changing them during review. | Each candidate includes the evidence for completion or staleness, affected Activities, and intended effects; uncertain candidates remain unresolved. | Accepted |
| CUR-004 | Archive only a user-authorized candidate Effort. | The Effort changes from `active` to `archived`; declined and unresolved candidates remain unchanged. | Accepted |
| CUR-005 | Distinguish Effort archival from Activity staleness. | Archiving an Effort does not by itself remove all linked Activity files; Curator identifies which Activities are stale and explains why. | Accepted |
| CUR-006 | Preserve required metadata for every stale Activity proposed for removal on its archived Effort. | The Effort records stable Activity ID, title, `lastActivityAt`, optional `startedAt`, participating People, concise customer-work summary, and minimized provenance. | Accepted |
| CUR-007 | Verify the archived Effort update before seeking authority to remove Activity files. | Curator reads back the retained metadata; a missing, conflicting, or unverifiable entry leaves its Activity file intact. | Accepted |
| CUR-008 | Obtain explicit user approval for the exact Activity files to remove. | The user sees the retained metadata and removal list; silence, Effort-archive approval, or criteria approval does not authorize removal. | Accepted |
| CUR-009 | Remove only approved stale Activity files after successful preservation and verification. | Removed files have verified historical entries; unapproved, active, blocked, or uncertain Activities remain intact. | Accepted |
| CUR-010 | Preserve graph integrity and index every durable lifecycle change. | No active reference points to a removed Activity, and Effort archival, metadata retention, and Activity removal appear in the applicable Daily Log. | Accepted |
| CUR-011 | Report completed, declined, blocked, partial, cancelled, and uncertain outcomes truthfully. | The report identifies the exact Efforts changed, metadata retained, files removed, files preserved, and unresolved effects. | Accepted |
| CUR-012 | Derive an Effort's last Activity from the newest reliable `lastActivityAt` among its meaningful customer Activities. | The displayed value traces to customer-work content and does not use file modification, graph maintenance, retrieval, indexing, attention state, or Daily Log time as a substitute. | Accepted |
| CUR-013 | Treat recency uncertainty as a review limitation rather than evidence of staleness. | Incomplete Work IQ coverage, missing or conflicting timestamps, future dates, ambiguous timezone, or uncertain Activity alignment prevents a confident stale label and is shown to the user. | Accepted |
| CUR-014 | Use the confirmed graph timezone to present the 14-day cutoff and evaluate timezone-explicit Activity timestamps. | The review displays its cutoff consistently; daylight-saving or local-date presentation does not silently alter stored UTC instants. | Accepted |
| CUR-015 | Trust stored `lastActivityAt` for staleness review only when it was derived from complete-enough item-level evidence under the Activity interpretation contract. | A timestamp derived from thread or chat start, container modification, incomplete continuation, or unknown item coverage is rejected or labeled uncertain. | Accepted |
| CUR-016 | Evaluate Email and Teams chat recency capabilities independently. | A verified Email result does not establish chat behavior, and a limitation in either source is reflected only in the affected review scope. | Accepted |

## Skills and orchestration

| Component | Responsibility | Inputs and outputs | Authority |
| --- | --- | --- | --- |
| Curator Skill | Review lifecycle candidates and execute authorized preserve-before-remove operations. | Inputs: graph, user-approved criteria and scope. Outputs: proposals, archived Efforts, retained Activity metadata, approved removals, Daily Log entries, and verified report. | Read-only review after criteria approval; each Effort archive requires user authority; exact Activity removals require explicit authority after verification. |
| Governor responsibility | Validate structure, references, preservation, and reported effects. | Inputs: proposed and observed graph state. Outputs: validation or bounded blockers. | Does not decide completion, staleness, or removal authority. |

## Interaction and information

| Element | Contract |
| --- | --- |
| Completed Effort | An Effort whose intended customer work or outcome is supported as complete and which the user authorizes for archival. |
| Stale Effort | By default, an Effort whose newest reliable meaningful customer Activity is at or before the review instant minus 14 days, with no unresolved recency gap; staleness is a review signal, not automatic authority. |
| Stale Activity | An Activity on an archived Effort that matches disclosed retention criteria and no longer needs a live standalone file. |
| Lifecycle proposal | Plain-language reason, evidence basis, affected Effort, affected Activities, metadata to retain, files that may later be removed, and uncertainty. |
| Retained metadata | Stable Activity ID, title, `lastActivityAt`, optional `startedAt`, participating People, concise customer-work summary, and minimized provenance on the archived Effort. |
| Last Activity | The newest reliable `lastActivityAt` among meaningful customer Activities related to the Effort, derived from concrete content timestamps or an explicit user-supplied work date. |
| Message-level recency resolution | Skill Host ability to enumerate the relevant items within an authorized source container, access reliable item timestamps, follow available continuation, and identify the newest item that qualifies as customer Activity. |
| Excluded recency signals | File timestamps, `createdAt`, Compass retrieval or scan time, Markdown edits, relationship maintenance, Daily Log entries, attention state, and the mere existence of recent communication. |
| Safe operation order | Review criteria, propose candidates, authorize and verify Effort archive plus metadata retention, disclose exact removals, obtain removal authority, remove files, validate graph, index changes, and report. |

## Constraints and dependencies

- The default inactivity threshold is 14 days; the user may change it for a review without changing the product default.
- Only content that qualifies as a customer Activity can advance last Activity. A recent thread timestamp does not count when its new content is unrelated to the Activity or customer work.
- Curator uses complete authorized evidence available for the review and discloses coverage gaps. Absence of retrieved evidence is not proof of inactivity.
- A stored `lastActivityAt` with unknown derivation is not automatically trusted for destructive lifecycle work. Curator re-grounds it through a verified host capability when authorized or marks recency uncertain.
- Email and Teams chat receive separate capability classifications because their retrieval shapes and timestamp exposure may differ.
- The Knowledge Graph Specification governs archived Activity metadata and preservation-before-removal integrity.
- The Customer Activity Interpretation Specification governs the meaning of retained summaries.
- Connected OneDrive listing, updates, removals, conflict handling, and verification need host capability testing.

## Failure, partial, blocked, and cancellation behavior

- Cancellation during review causes no write or removal.
- Ambiguous completion or current relevance leaves the affected Effort active unless the user resolves it.
- Failed Effort archival or metadata verification leaves every related Activity file intact.
- A conflict after verification but before removal stops affected removals and triggers revalidation.
- Partial removal is reported file by file; Curator does not claim the lifecycle operation completed.
- Curator never compensates for a failed write by deleting additional content.

## Decisions and open questions

- **Accepted:** Curator primarily archives completed or stale Efforts and removes stale Activity files after preserving metadata on the archived Effort.
- **Accepted:** Effort archival and Activity removal are separate user decisions.
- **Accepted:** Preservation and verification precede Activity removal.
- **Accepted:** Curator removes no source email or chat content.
- **Accepted:** Curator defaults to 14 days of inactivity measured from meaningful customer Activity.
- **Accepted:** Graph maintenance and incomplete evidence do not create or prove customer-work recency.
- **Accepted:** Message-level recency resolution is a material Skill Host characteristic recorded separately for Email and Teams chat.
- **Open:** Representative use will determine whether specific customers or Effort types need an explicitly selected threshold different from the default.

## Implementation status

- **Implemented:** `compass-curator` `0.1.0-local-candidate`, runtime lifecycle contract, importable package, orchestration handoffs, and synthetic fixture.
- **Not implemented:** Verified Cowork adaptation and observed connected behavior.

## Test Plans

- [Curator Lifecycle Test Plan](../test-plans/curator-lifecycle.md): Verifies candidate review, archival authority, metadata retention, safe removal ordering, and partial-effect reporting.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 1.0 | 2026-09-12 | Established Curator's primary lifecycle purpose and preserve-before-remove contract. |
| 1.1 | 2026-09-12 | Set the default inactivity threshold to 14 days and defined accurate last Activity from meaningful customer-work timestamps with explicit uncertainty handling. |
| 1.2 | 2026-09-12 | Required verified message-level recency derivation, continuation coverage, and separate Email and Teams host capability classifications. |

## Acceptance boundary

This active Specification authorizes local Skill implementation, fixtures, and disconnected validation. It does not authorize connected graph changes, Activity removal, packaging, deployment, or release.