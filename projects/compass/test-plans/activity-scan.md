# Compass Activity Scan Test Plan

## Metadata

- **Owner:** User / product owner
- **Specifications:** [Activity Scan](../specifications/activity-scan.md); [Customer Activity Interpretation](../specifications/customer-activity-interpretation.md); [Knowledge Graph](../specifications/knowledge-graph.md)
- **Candidate:** `compass-activity-scan` `0.1.0-local-candidate`
- **Package:** `compass-activity-scan-0.1.0-local-candidate.skill`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

Activity Scan succeeds when it updates an existing synthetic graph from a bounded evidence set while preserving separate retrieval and write authority, customer-only interpretation, stable identity, accurate item-level recency, exact review, Governor validation, and truthful read-back.

## Host compatibility profile

- **Required host behavior:** Skill loading, graph read, bounded Email and Teams retrieval, item timestamps and continuation, multi-item interpretation, proposal review, Markdown/YAML update, and read-back.
- **Observed conditions:** Not yet probed on Copilot Cowork.
- **Privacy:** Use fictional fixture data for disconnected testing. Connected tests remain private on the managed surface and retain only minimized operational observations.

## Complete journey

| Stage | User decision | Observable result |
| --- | --- | --- |
| Open | Select an existing graph and request catch-up | Scan validates the explicit graph without searching other locations |
| Plan | Edit or approve Email and Teams scope | No retrieval occurs before approval |
| Interpret | Review grouped and split Activities | Only customer work appears; provenance and recency coverage remain visible |
| Validate | Inspect Governor preflight | Invalid operations are blocked without mutation |
| Apply | Approve exact graph effects | Only reviewed files and Daily Log entries change |
| Verify | Inspect report and files | Read-back matches claims; partial coverage and effects remain explicit |

## Test cases

| ID | Behavior | Practical confirmation | Status |
| --- | --- | --- | --- |
| SCAN-AUTH-001 | `SCAN-002`, `SCAN-009` | Retrieval approval causes no graph write; cancelling the write proposal preserves the graph. | not run |
| SCAN-CUST-001 | `SCAN-003` through `SCAN-006` | Mixed customer and internal evidence yields only customer Activities, grouped by work rather than source. | not run |
| SCAN-CONT-001 | `SCAN-005` | Ambiguous continuation is proposed as unresolved rather than merged by title or participants. | not run |
| SCAN-TIME-001 | `SCAN-006` | A recent qualifying item in an old container sets `lastActivityAt`; recent unrelated content does not. | not run |
| SCAN-PEOPLE-001 | `SCAN-007` | Stable People are reused; ambiguous identity blocks only the affected relationship. | not run |
| SCAN-PLACE-001 | `SCAN-008` | Every Activity has exactly one Effort or Parking Lot disposition. | not run |
| SCAN-EFFECT-001 | `SCAN-009` through `SCAN-012` | Proposal, preflight, approved writes, Daily Log, postflight, and report agree exactly. | not run |

## Focused host checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| Skill loading | Invoke the candidate with a synthetic graph | Cowork identifies ordinary scan purpose and asks for scope | not run |
| Plan without retrieval | Request a scan plan and withhold approval | Cowork waits without accessing evidence | not run |
| Email item recency | Use an old synthetic thread with a recent qualifying reply | Cowork exposes item-level timestamp or labels the limitation | not run |
| Teams item recency | Use an old synthetic chat with a recent qualifying message | Cowork classifies Teams capability independently | not run |
| Update and read-back | Approve one disposable synthetic Activity update | Independent inspection matches the report | not run |

## Material stop conditions

Stop for retrieval before approval, source mutation, raw transcript retention, non-customer Activity creation, guessed continuity or identity, write before exact approval, or reported effects that differ from read-back.

## Execution log

| Date | Environment | Observation |
| --- | --- | --- |
| 2026-09-12 | Local structured fixture validation | All 10 graph objects parsed; schema, IDs, references, cardinality, paths, Daily Log shape, and fixture lifecycle expectations passed. This does not establish Skill behavior. |
| 2026-09-12 | Local read-only agent-assisted walkthrough | E-1 and E-3 updated one Activity, E-4 formed a separate Activity, E-2 and E-5 were excluded, and E-6 preserved a Teams coverage gap. No files changed and no Cowork capability was tested. |

## Current assessment

The local contract and fixture are internally consistent; runtime success is not established. Next run the smallest Cowork loading and plan-only probe.