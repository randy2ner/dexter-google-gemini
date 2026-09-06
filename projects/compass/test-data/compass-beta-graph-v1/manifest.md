# Fixture manifest: compass-beta-graph-v1

## Identity

- **Fixture:** `compass-beta-graph-v1`
- **Version:** `1.0.0-candidate`
- **Created:** 2026-09-02
- **Graph ID after installation:** `71a65f10-7e2b-4a10-9d21-4e455bc7b301`
- **Configured timezone:** `America/Los_Angeles`
- **Reference date:** `2026-08-24`
- **Content basis:** Wholly generic fictional content created for disconnected Compass testing
- **Prohibited use:** Real, connected, personal, or production graph; source evidence; runtime-success claim

## Layout

| Path | Purpose |
| --- | --- |
| `restore-baseline/graph/` | External pre-installation snapshot used for deterministic materialization and restoration. |
| `materialized/graph/` | Disposable working root. It initially matches the restore baseline. |
| `inputs/daily-scan-2026-08-24.md` | Fixed synthetic Email and Teams evidence presented as untrusted data. |
| `expected/final-graph/` | Expected graph after the complete authorized lifecycle; comparison oracle, not runtime evidence. |
| `operations/lifecycle-operations.md` | Fixed operation IDs, intended effects, conflict injection, and recovery case. |
| `recovery/restore-procedure.md` | Safe materialization and restore procedure. |
| `handoff/compass-beta-graph-v1-baseline.zip` | Minimal transfer copy containing only baseline graph content; not a writable graph root or recovery source. |

## Fixed identities

| Type | ID |
| --- | --- |
| Graph | `71a65f10-7e2b-4a10-9d21-4e455bc7b301` |
| Person | `person:51000000-0000-4000-8000-000000000001` |
| CSP | `csp:52000000-0000-4000-8000-000000000001` |
| Tracking Topic | `tracking-topic:53000000-0000-4000-8000-000000000001` |
| Conversation 1 | `conversation:54000000-0000-4000-8000-000000000001` |
| Conversation 2 | `conversation:54000000-0000-4000-8000-000000000002` |
| Daily Log | `daily-log:2026-08-24` |

## Baseline inventory

| Relative file | Bytes | SHA-256 |
| --- | ---: | --- |
| `README.md` | 299 | `2f344bdb89f8b2157bb8d313401402aef92dc13f9f1834d825b27d46272ff67a` |

Deterministic aggregate: 299 bytes; SHA-256 `5e331cd419d40e43460b21fe792e52d3db91bb855960c106bd12fbafd34c1486`. The baseline and materialized graph must match exactly before any authorized scenario. See the [construction validation](../../docs/test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md).

Transfer archive: 315 bytes; SHA-256 `e219c45332e1502d9556cd11eb00b7e2b26dd19dc41edeec68dae20ea698df8b`. It contains exactly the baseline `README.md`. Upload or extraction does not authorize writes; the resulting Cowork-accessible folder must be identified, backed up, and separately authorized as the graph root.

## Fictional-content declaration

Every name, organization, program, ID, timestamp, source reference, and sentence in this fixture is fictional. Nothing was derived from Microsoft 365, Work IQ, a tenant, customer, person, prior session, or imported package.

## Governing versions

- Shared Contracts and Graph Schema: `0.3-beta-baseline`
- Installation Interview, Daily Scan, Tracking Topic Interview, Curator: `0.1.0-beta-candidate`
- Graph Governor: `0.2.0-beta-candidate`
- Orchestration: `compass-work-memory-lifecycle` `0.1-beta-candidate`

Fixture presence does not authorize Skill execution, connected access, graph writes, Gate 1, beta, deployment, or release.