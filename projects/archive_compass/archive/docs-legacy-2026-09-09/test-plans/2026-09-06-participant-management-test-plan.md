# Test plan: Compass participant management schema version 2

## Metadata

- **Owner:** User / product owner
- **Period:** Beginning 2026-09-06
- **Skills/versions:** Installation `0.3.0`, Daily Scan `0.3.0`, Tracking Topic Interview `0.3.0`, Curator `0.3.0`, Graph Governor `0.4.0`, Orchestration `0.3.0`
- **Status:** draft; execution not authorized

## Goals

- Verify Conversation participant qualification and complete-name identity handling.
- Verify explicit Topic disposition and derived Parking Lot behavior.
- Verify Topic participant funneling, persistence, exclusion, and explicit re-add.
- Verify Skill authority boundaries, Daily Log effects, and Governor enforcement.

## Out of scope

- Production or personal-graph migration.
- Unbounded Microsoft 365 retrieval.
- Transfer of prior package confidence to schema version 2.
- Last-activity, stale-retention duration, Person merge, and connected recovery design.

## Environments

- Disconnected schema-v2 synthetic fixture for static and Governor checks.
- Separately authorized Cowork connected dogfood graph for later interaction checks.

## Scenario matrix

| Scenario | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| [Participant-management schema scenario](../scenarios/compass-participant-management-schema-v2.md) | high | Disconnected synthetic | Project Dexter / user | planned |
| Installation complete-name prompt | high | Cowork dogfood | User | not authorized |
| Daily Scan participant and Parking Lot review | high | Cowork dogfood | User | not authorized |
| Topic remove, suppressed funnel, and explicit re-add | high | Cowork dogfood | User | not authorized |
| Curator participant recommendation handoff | medium | Cowork dogfood | User | not authorized |

## Entry criteria

- Updated source and schema-v2 fixture pass static consistency checks.
- Exact candidate packages and hashes are recorded before Cowork execution.
- Runtime graph is disposable or has an explicitly approved recovery boundary.

## Exit criteria

- Each executed scenario has an immutable result separating observation from interpretation.
- No successful claim precedes Governor post-write verification.
- Findings and affected source revisions are linked before retest.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Mention resolution binds the wrong Person | Incorrect durable relationships | Require complete name and user confirmation; fail closed on ambiguity. |
| Topic removal is silently reversed | User intent is lost | Persist exclusion and require explicit re-add. |
| Schema-v1 graph is changed by v2 writer | Incompatible graph state | Block mutation pending reviewed migration. |
| Multi-file connected write is partial | Topic and Conversation disagree | Governor validation, exact effect accounting, and `recovery-required`. |

## Reporting

Record dated results under `docs/test-results/`, findings under `docs/findings/`, and confidence only after linking exact package versions, fixture identity, environment, and observed outcomes.