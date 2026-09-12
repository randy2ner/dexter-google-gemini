# Test plan: Topic archival success

## Metadata

- **Owner:** User / product owner
- **Period:** 2026-09-06 onward
- **Skills/versions:** Tracking Topic Interview `0.3.1-archival-success-candidate`; Graph Governor `0.4.1-archival-success-candidate`
- **Status:** active; static construction authorized, behavioral execution not authorized

## Goals

- Verify the schema-v2 status/success invariant.
- Verify exact user authority for archival success and removal on reactivation.
- Verify merge-source archival carries one success decision per source Topic.

## Out of scope

- Microsoft 365 access, personal graphs, schema-v1 migration, connected writes, deployment, promotion, and release.

## Environments

- Disconnected fictional files under `test-data/compass-topic-archival-success-v2/`.
- Cowork behavioral execution only after separate authorization.

## Scenario matrix

| Scenario | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| [Topic archival success lifecycle](../scenarios/compass-topic-archival-success-lifecycle.md) | high | disconnected fictional graph, then separately authorized Cowork | Project Dexter / product owner | planned |

## Entry criteria

- Revised source and candidate packages are statically inspected.
- The fixture parses and satisfies all positive status/success combinations.
- Negative variants are created only in a disposable copy.

## Exit criteria

- Direct evidence covers both boolean values, invalid combinations, exact approval, merge, and reactivation removal.
- Results separate static observations from runtime behavior.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Success is inferred from “completed” or stale context. | User meaning is fabricated. | Require a direct question and exact boolean preview. |
| Reactivation leaves a stale outcome. | Active Topic state is misleading. | Require field removal and post-write absence verification. |
| YAML boolean is quoted. | Value becomes a string. | Parse safely and require native boolean type. |

## Reporting

Add dated immutable results under `docs/test-results/`. Do not revise prior participant-management evidence.