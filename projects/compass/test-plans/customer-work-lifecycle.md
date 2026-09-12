# Compass Customer Work Lifecycle Test Plan

## Metadata

- **Owner:** User / product owner
- **Orchestration:** [Compass Customer Work Lifecycle](../orchestrations/compass-customer-work-lifecycle/ORCHESTRATION.md)
- **Specifications:** [Installation](../specifications/installation-interview.md); [Activity Scan](../specifications/activity-scan.md); [Graph Governor](../specifications/graph-governor.md); [Curator](../specifications/curator-lifecycle.md)
- **Candidates:** Installation, Activity Scan, Graph Governor, and Curator `0.1.0-local-candidate`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

This plan decides whether the four candidates form one understandable, controlled end-to-end Compass experience. Success requires useful customer-work continuity, clean handoffs, independent validation, four distinct approval boundaries, verified graph state, and truthful degradation when Cowork cannot coordinate Skills directly.

## Representative beta journey

1. Begin with the synthetic fixture graph or route through Installation when no graph exists.
2. Approve a bounded fictional Email and Teams scan containing related customer evidence, distinct work in one source, unrelated internal work, and a recent qualifying item in an old container.
3. Review Activity Scan proposals; inject one invalid relationship so Governor blocks only that operation.
4. Correct and approve the remaining graph effects; verify object and Daily Log read-back.
5. Review the resulting active Efforts and Activities without external disclosure.
6. Opt into Curator's default 14-day review containing stale, current, and uncertain Efforts.
7. Archive one Effort, decline another, and verify retained Activity metadata while every Activity file remains.
8. Separately approve removal of one listed stale Activity and preserve another.
9. Compare the final report with independent fixture inspection.

## Observable confirmations

| ID | Confirmation | Status |
| --- | --- | --- |
| LIFE-ROUTE-001 | Existing and absent graphs route correctly without implicit replacement or unrelated search. | not run |
| LIFE-AUTH-001 | Retrieval, graph write, Effort archive, and Activity removal are four distinct user decisions. | not run |
| LIFE-HANDOFF-001 | Governor receives sufficient base state and expected effects without taking mutation ownership. | not run |
| LIFE-WORK-001 | The verified graph gives a useful current customer-work view after Scan. | not run |
| LIFE-CURATE-001 | Curator classifies message-level recency accurately and preserves before removal. | not run |
| LIFE-EFFECT-001 | Final objects, files, and Daily Logs agree with the report; declined and uncertain items remain. | not run |
| LIFE-FALLBACK-001 | Sequential manual Skill invocation preserves the same contracts when direct orchestration is unavailable. | not run |
| LIFE-QUALITY-001 | The user can understand current work, corrections, approvals, and outcomes without managing YAML. | not run |

## Focused host checks before the journey

1. Load one candidate and sustain a multi-turn exchange.
2. Request a bounded retrieval plan without running retrieval.
3. Supply synthetic files for read-only Governor validation.
4. Determine whether Cowork can hand off among Skills; otherwise use the documented sequential fallback.

## Evidence handling

Use only fictional data for the disconnected run. During later connected testing, the operator reviews work evidence privately on the managed surface. Record only privacy-minimized decisions, counts, host conditions, and operational observations.

## Material stop conditions

Stop for unauthorized access or mutation, disclosure, destructive effect before its dedicated approval, unverified success, graph corruption, or a need to copy identifying work content into project records.

## Execution log

| Date | Environment | Observation |
| --- | --- | --- |
| 2026-09-12 | Local static and structured validation | Four packages matched source byte-for-byte; project links, runtime boundaries, schema sections, fixture YAML, references, cardinality, paths, and Daily Log invariants passed. |
| 2026-09-12 | Local read-only agent-assisted walkthrough | All six stages were traceable without contradiction: existing-graph routing, Scan interpretation, Governor preflight and blocker, Curator classification, preserve-before-remove, and truthful final reporting. No files changed. This is not Cowork capability or runtime evidence. |

## Current assessment

The local four-Skill candidate is internally consistent and ready for Skill host testing. The end-to-end experience remains unestablished on Cowork; begin with Skill loading and a plan-only no-retrieval probe.