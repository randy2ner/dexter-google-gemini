# Compass Activity Scan Specification

## Document control

- **Status:** active
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-12
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-033` through `PR-040`
- **Implementation authority:** Local Skill source, synthetic fixtures, disconnected validation, and packaging are authorized. Connected retrieval, OneDrive writes, disclosure, deployment, and release remain unauthorized.

## Purpose and applicability

Activity Scan helps the user keep Compass current during ordinary work. It reviews a user-approved Email and Teams scope, interprets meaningful customer work into new or updated Activities, and proposes exact graph changes for review and Governor validation.

## Scope and boundaries

- **In scope:** Bounded evidence retrieval, customer-only Activity interpretation, cross-source grouping, Activity continuity, message-level recency, People and Effort relationships, Parking Lot disposition, exact graph proposals, verified writes, and Daily Log indexing.
- **Out of scope:** Initial graph installation, lifecycle archival or removal, broad graph repair, external disclosure, and source mutation.
- **Authority:** Scan-plan approval authorizes retrieval only. Graph mutation requires a second explicit approval after the user sees exact proposed effects.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| SCAN-001 | Start from an existing valid Compass graph and a user-visible purpose. | Activity Scan identifies the graph and intended customer-work update without searching unrelated locations. | Accepted |
| SCAN-002 | Propose an editable Email and Teams retrieval plan with date range, limits, and continuation expectations. | No retrieval begins until the user approves the displayed read-only scope. | Accepted |
| SCAN-003 | Retrieve only within the approved scope and disclose inaccessible sources or incomplete continuation. | The result distinguishes inspected, unavailable, and unresolved evidence coverage. | Accepted |
| SCAN-004 | Apply the Customer Activity Interpretation Specification to direct user input and retrieved evidence. | Only coherent customer work becomes an Activity; source containers do not dictate boundaries. | Accepted |
| SCAN-005 | Correlate evidence to an existing Activity only when continuity is supported by work meaning and graph context. | Weak title, participant, or container similarity does not silently merge Activities. | Accepted |
| SCAN-006 | Derive `lastActivityAt` from the newest qualifying item and retain source-specific coverage limits. | Container, retrieval, file, and unrelated-message times do not advance Activity recency. | Accepted |
| SCAN-007 | Resolve People by stable graph identity and propose new People only when meaningful names and reviewed identity evidence are available. | Existing People are reused safely; ambiguous identity blocks only the affected relationship or creation. | Accepted |
| SCAN-008 | Relate every Activity to exactly one Effort or Parking Lot disposition. | Ambiguous placement is reviewable and unresolved rather than guessed. | Accepted |
| SCAN-009 | Present exact creates and updates, preserved content, provenance, paths, and Daily Log effects before mutation. | The user can change, approve, pause, or cancel the proposal without hidden writes. | Accepted |
| SCAN-010 | Obtain Governor validation before mutation and validate observed state again after mutation. | Structurally invalid proposals are blocked and attempted effects are not mistaken for durable effects. | Accepted |
| SCAN-011 | Re-read targets, apply only approved changes, preserve unrelated content, append Daily Log entries, and read back results. | Verified graph state matches approved effects and remains portable Markdown/YAML. | Accepted |
| SCAN-012 | Report completed, partial, blocked, cancelled, and uncertain outcomes precisely. | The report names inspected coverage, verified effects, unapplied proposals, and unresolved recency or identity. | Accepted |

## Skills and orchestration

| Component | Responsibility | Authority |
| --- | --- | --- |
| `compass-activity-scan` | Retrieve approved evidence and propose or apply reviewed Activity-centered graph changes. | Retrieval-plan approval and graph-change approval are separate. |
| `compass-graph-governor` | Validate proposal and observed graph state. | Validation does not grant retrieval or write authority. |
| `compass-customer-work-lifecycle` | Route ordinary scan results into graph update, work view, or optional Curator review. | Preserves each participating Skill's approval boundary. |

## Failure and cancellation

- Invalid graph configuration blocks the scan before retrieval.
- Cancellation before retrieval causes no access or graph change; cancellation after retrieval causes no graph change.
- Incomplete coverage, missing item timestamps, ambiguous continuity, identity, or placement remains visible and blocks only claims or effects that depend on it.
- A changed target after review requires a refreshed proposal and validation.
- Source email and chat are never changed, deleted, or retained as raw transcripts.

## Implementation status

- **Implemented:** `compass-activity-scan` `0.1.0-local-candidate`, runtime references, importable package, active contracts, orchestration handoffs, and synthetic fixture.
- **Not implemented:** Verified Cowork adaptation and observed runtime behavior.

## Test Plans

- [Activity Scan Test Plan](../test-plans/activity-scan.md)
- [Customer Activity Interpretation Test Plan](../test-plans/customer-activity-interpretation.md)
- [Customer Work Lifecycle Test Plan](../test-plans/customer-work-lifecycle.md)

## Acceptance boundary

This Specification authorizes local implementation, fixtures, disconnected validation, and packaging. It does not authorize connected retrieval, graph writes, disclosure, deployment, or release.