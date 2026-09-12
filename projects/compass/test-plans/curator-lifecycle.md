# Compass Curator Lifecycle Test Plan

## Metadata

- **Owner:** User / product owner
- **Specifications:** [Curator Lifecycle](../specifications/curator-lifecycle.md); [Knowledge Graph](../specifications/knowledge-graph.md); [Customer Activity Interpretation](../specifications/customer-activity-interpretation.md)
- **Candidate:** `compass-curator` `0.1.0-local-candidate`
- **Package:** `compass-curator-0.1.0-local-candidate.skill`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

This plan determines whether Curator can apply its default 14-day inactivity review accurately, archive completed or stale Efforts with user authority, and safely compact stale Activities. Success requires meaningful customer-content recency, explicit uncertainty handling, separate authority for Effort archival and Activity removal, verified metadata retention before removal, preserved graph integrity, and truthful partial-effect reporting.

## Scope and environment

- **In scope:** Default and edited thresholds, accurate last Activity, timezone and cutoff boundaries, incomplete evidence, candidate selection, Activity retention, archived metadata, preserve-before-remove ordering, Daily Log entries, conflicts, and partial effects.
- **Out of scope:** Real customer data, connected OneDrive effects during disconnected testing, source email or chat deletion, general Governor repair, and automatic lifecycle changes.
- **AI surface:** Copilot Cowork.
- **Material host conditions:** Skill loading, graph file enumeration and parsing, optional authorized Work IQ coverage, review interaction, file update and read-back verification, exact removal approval, removal capability, conflict visibility, and effect reporting.
- **Privacy:** Use only fictional customers, People, Efforts, Activities, and provenance. Retain no real work content, tenant identifiers, or customer identities.

## Host compatibility profile

- **Required host behavior:** Load Curator; inspect an authorized graph; enumerate relevant individual Email and Teams chat items with reliable timestamps and continuation; derive meaningful customer Activity time separately from container and maintenance time; disclose coverage gaps; present an editable 14-day review; make no change during review; update and verify an Effort; request separate exact removal authority; remove only approved Activity files; validate resulting references and Daily Log entries; and report partial effects honestly.
- **Observed conditions:** Not yet probed on Copilot Cowork.
- **Material host characteristic:** `message-level recency resolution`, classified separately for Email and Teams chat as `available`, `available with conditions`, `unavailable`, `blocked`, or `unknown`. Record the shortest effective invocation, whether individual items and timestamps were visible, continuation behavior, known coverage, and the limitation of the observation.
- **Another host:** Identify its product, run the focused capability checks below, compare observed differences, and record a compatibility or adaptation hypothesis before the complete journey.

## Complete journey

| Stage | Skill or component | User decision | Observable effect or no-write outcome |
| --- | --- | --- | --- |
| Scope | Curator | Keep, edit, or cancel the proposed 14-day threshold and review scope. | Cancellation causes no graph change; approval authorizes review only. |
| Measure | Curator | Review the derived last Activity and evidence coverage. | Recency traces to meaningful customer-work timestamps; maintenance events are excluded and uncertainty is visible. |
| Review | Curator | Inspect completed, stale, current, and uncertain Effort candidates. | Curator presents evidence, affected Activities, intended metadata, possible removals, and uncertainty without changing files. |
| Archive | Curator | Authorize one candidate and decline another. | Only the authorized Effort becomes archived; its proposed stale Activity metadata is written while every Activity file remains present. |
| Verify | Curator and Governor responsibility | Inspect the archived Effort and graph integrity. | Required Activity metadata is readable, current Activity references remain valid, and failed verification blocks removal. |
| Remove | Curator | Explicitly approve selected stale Activity files after verification. | Only listed files are removed; declined, current, blocked, and uncertain Activities remain. |
| Confirm | Curator | Review the final report. | Daily Log and independent graph inspection agree with the reported archive, retention, removals, preserved files, and blockers. |

This is a shaping guide, not an exact script. Prompts, situations, checks, and confirmation criteria should be repeatable; wording, sequence, and model responses may vary.

## Test cases

| ID | Specification behavior | Prompt or situation | Practical check and observable confirmation | Status | Latest observation |
| --- | --- | --- | --- | --- | --- |
| CUR-JOURNEY-001 | `CUR-001` through `CUR-014`; `GRAPH-030` through `GRAPH-034` | Use a synthetic graph with one completed Effort, one stale Effort, one current Effort, one uncertain Effort, and mixed stale and current Activities. | Curator proposes 14 days, derives recency accurately, reviews without mutation, archives only authorized candidates, verifies retained metadata, removes only separately approved stale Activity files, and reports exact effects. | not run | None |
| CUR-DEFAULT-001 | `CUR-002`, `CUR-012`, `CUR-014` | Start a review without naming a threshold, with Activities immediately inside, exactly at, and immediately outside the 14-day cutoff. | Curator displays the timezone-aware cutoff and consistently identifies candidates according to the disclosed inclusive boundary without treating threshold approval as change authority. | not run | None |
| CUR-SCOPE-001 | `CUR-002`, `CUR-003` | Change the proposed threshold and exclude one Effort from review. | Candidate evaluation follows the edited scope; the excluded Effort is neither evaluated beyond necessity nor changed, and the product default remains 14 days for a later review. | not run | None |
| CUR-RECENCY-001 | `CUR-012`; `GRAPH-033`, `GRAPH-034` | Give an old Activity a recent Markdown edit, Daily Log entry, retrieval time, and relationship update. | Last Activity remains the meaningful customer-content timestamp; maintenance events do not make the Effort current. | not run | None |
| CUR-RECENCY-002 | `CUR-012`; `ACT-002`, `ACT-003`; `GRAPH-033` | Add recent content to an old source thread, but make that content unrelated to customer work. | The source-container timestamp does not advance `lastActivityAt`; only qualifying customer Activity can reset inactivity. | not run | None |
| CUR-RECENCY-003 | `CUR-013` | Make Work IQ coverage incomplete or provide missing, conflicting, future-dated, or timezone-ambiguous timestamps. | Curator marks recency uncertain, does not confidently label the Effort stale, and explains the blocking evidence gap. | not run | None |
| CUR-RECENCY-004 | `CUR-012`, `CUR-014`; `GRAPH-034` | Give one Effort several Activities and archived metadata with different valid timestamps. | Effort last Activity equals the greatest reliable `lastActivityAt`, displayed using the confirmed graph timezone without changing the stored instant. | not run | None |
| CUR-EMAIL-001 | `CUR-015`, `CUR-016`; `ACT-011` | In an authorized synthetic Email thread started more than 14 days ago, place a known qualifying customer-work reply 2 days ago. | Cowork identifies the reply timestamp as last Activity rather than the thread start; record the Email capability classification and observed conditions. | not run | None |
| CUR-CHAT-001 | `CUR-015`, `CUR-016`; `ACT-011` | In an authorized synthetic Teams chat started more than 14 days ago, place a known qualifying customer-work message 2 days ago. | Cowork identifies the newest qualifying message timestamp rather than the chat start; record the Teams chat capability classification independently. | not run | None |
| CUR-CONTINUE-001 | `CUR-013`, `CUR-015`; `ACT-011` | Put the newest qualifying synthetic item beyond the first returned result page or continuation boundary. | Cowork follows available continuation and finds it, or marks coverage incomplete and refuses a confident stale classification. | not run | None |
| CUR-CONTAINER-001 | `CUR-013`, `CUR-015`; `ACT-011`, `ACT-012` | Expose only container start or generic modification time, or add a recent non-customer item to an old container. | Cowork does not use that timestamp as `lastActivityAt`; affected recency remains uncertain or unchanged. | not run | None |
| CUR-CANCEL-001 | `CUR-002`, `CUR-003` | Cancel at the criteria or candidate-review stage. | No Effort, Activity, or Daily Log file changes. | not run | None |
| CUR-AUTH-001 | `CUR-004`, `CUR-008`, `CUR-009` | Approve Effort archival but do not approve Activity removal. | The Effort may be archived with retained metadata, but all Activity files remain present. | not run | None |
| CUR-MIXED-001 | `CUR-005`, `CUR-006`, `CUR-009` | Archive an Effort with one stale Activity and one Activity still needed as a standalone record. | Metadata is retained for the stale Activity selected for compaction; only that file is eligible for removal and the current Activity remains intact. | not run | None |
| CUR-METADATA-001 | `CUR-006`; `GRAPH-030`, `GRAPH-031` | Inspect an archived Effort after disconnected compaction. | The historical entry contains stable ID, title, `lastActivityAt`, optional `startedAt`, participating People, concise customer-work summary, and minimized provenance without resolving as a live Activity. | not run | None |
| CUR-VERIFY-001 | `CUR-007`, `CUR-009`; `GRAPH-032` | Inject a failed, incomplete, or unverifiable Effort metadata update. | The affected Activity file remains intact and Curator reports the preservation failure without requesting or claiming removal. | not run | None |
| CUR-CONFLICT-001 | `CUR-007`, `CUR-010`, `CUR-011` | Change the Effort or Activity after verification and before simulated removal. | Curator detects the conflict, stops affected removal, preserves the Activity file, and reports revalidation is required. | not run | None |
| CUR-PARTIAL-001 | `CUR-010`, `CUR-011` | Simulate success for one approved removal and failure for another. | The report names each outcome, graph references remain valid, and no complete-success claim is made. | not run | None |

## Focused host capability checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| Read-only lifecycle review | Supply a small synthetic graph and request candidate review only. | Cowork presents the 14-day default, candidates, evidence basis, and uncertainty without changing files. | not run |
| Email message-level recency | Use a known synthetic thread whose start is old and qualifying reply is recent. | Cowork exposes the qualifying reply and timestamp rather than reporting only thread-level time. | not run |
| Teams message-level recency | Use a known synthetic chat whose start is old and qualifying message is recent. | Cowork exposes the qualifying item and timestamp rather than reporting only chat-level time. | not run |
| Retrieval continuation | Place the newest qualifying item beyond the first result set when the host supports a controlled fixture or known test conversation. | Cowork follows continuation, or the limitation is visible and blocks a complete recency claim. | not run |
| Meaningful-time distinction | Supply old customer content with recent synthetic file, Daily Log, and unrelated container activity. | Cowork uses qualifying customer-content time and identifies maintenance and unrelated timestamps as excluded signals. | not run |
| Update and read-back | With separate authority in a disposable location, add one synthetic metadata entry and read it back. | Read-back matches the intended entry and preserves unrelated Markdown/YAML. | not run |
| Separate removal control | Approve a synthetic Effort update while withholding removal approval. | Cowork does not treat update approval as file-removal authority. | not run |
| Exact file removal | With separate authority in a disposable location, remove one named synthetic file while preserving another. | Only the named file is absent on independent inspection. | not run |
| Conflict visibility | Modify a disposable file between read-back and proposed removal. | Cowork detects changed state or reports that conflict detection is unavailable; it does not claim a safe removal. | not run |

## Material stop conditions

- Curator uses file, graph-modification, retrieval, indexing, attention-state, or Daily Log time as meaningful customer Activity.
- Incomplete or ambiguous evidence is treated as proof of inactivity.
- Curator changes the graph during read-only review.
- An Effort is archived without user authority.
- An Activity file is removed before required metadata is written and verified.
- Effort-archive approval is treated as Activity-removal approval.
- A current, declined, blocked, uncertain, or unlisted Activity file is removed.
- Source email or chat content is deleted or modified.
- Removed Activity history becomes unreadable or active graph references become invalid.
- Partial or uncertain effects are reported as complete.

## Execution log

| Date | Environment | Observation |
| --- | --- | --- |
| 2026-09-12 | Local structured fixture validation | The fixed cutoff classified the reliable stale and current Efforts as expected; the fixture explicitly preserves uncertainty for incomplete Teams continuation. |
| 2026-09-12 | Local read-only agent-assisted walkthrough | The journey derived stale/current/uncertain outcomes and maintained criteria, archive, and removal as separate decisions with metadata verification before removal. No files changed and no Cowork capability was tested. |

## Current success assessment

- **Assessment:** Local contract consistency established; runtime behavior not established.
- **Supported claims:** Structured fixture data produces the expected cutoff classifications, and a read-only analytical walkthrough found no lifecycle-order contradiction.
- **Unresolved claims:** `CUR-001` through `CUR-016`, `GRAPH-030` through `GRAPH-034`, and Email and Teams message-level recency capabilities lack Skill host evidence.
- **Next test or revision:** Run the disconnected synthetic graph journey before any connected OneDrive removal test.
