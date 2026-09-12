# Test plan: Topic attention state

## Metadata

- **Owner:** User / product owner
- **Period:** 2026-09-06 onward
- **Skills/versions:** Installation, Daily Scan, Tracking Topic Interview, and Curator `0.4.0-attention-state-candidate`; Graph Governor `0.5.0-attention-state-candidate`
- **Status:** active; static construction authorized, behavioral execution not authorized

## Goals

- Verify all three accepted values and rejection of missing or unknown values.
- Verify explicit user authority and non-inference across every Skill.
- Verify independence from lifecycle and archival success.

## Out of scope

- Connected Microsoft 365 access, personal-graph mutation, schema-v1 migration, deployment, promotion, and release.

## Environments

- Disconnected fictional fixture under `test-data/compass-topic-attention-state-v2/`.
- Cowork behavioral execution only after separate authorization.

## Scenario matrix

| Scenario | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| [Topic attention-state lifecycle](../scenarios/compass-topic-attention-state-lifecycle.md) | high | disconnected fictional graph, then separately authorized Cowork | Project Dexter / product owner | planned |

## Entry criteria

- Candidate packages and fixture pass static inspection.
- Any invalid variant is created only in a disposable copy.

## Exit criteria

- Evidence covers all values, invalid values, initial choice, change, cancellation, non-inference, archival retention, and reactivation confirmation.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Activity is mistaken for user intent. | State becomes misleading. | Require explicit choice or approval; prohibit silent derivation. |
| Observing is mistaken for inactivity. | Useful awareness may be archived or omitted. | Keep lifecycle and attention state independent. |
| Waiting is mistaken for validation `blocked`. | Product meaning and operation outcome are conflated. | Keep attention enum separate from common terminal outcomes. |

## Reporting

Record dated immutable results under `docs/test-results/`. Do not revise prior package or fixture evidence.