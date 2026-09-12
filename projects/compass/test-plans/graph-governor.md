# Compass Graph Governor Test Plan

## Metadata

- **Owner:** User / product owner
- **Specifications:** [Graph Governor](../specifications/graph-governor.md); [Knowledge Graph](../specifications/knowledge-graph.md)
- **Candidate:** `compass-graph-governor` `0.1.0-local-candidate`
- **Package:** `compass-graph-governor-0.1.0-local-candidate.skill`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

Governor succeeds when it detects structural and effect-integrity defects precisely, accepts valid graph state without mutation, and never confuses structural validity with factual correctness or authority.

## Complete journey

| Stage | Input | Observable result |
| --- | --- | --- |
| Preflight | Valid graph plus proposed Activity update | Governor returns valid operations and no write |
| Defect | Inject malformed ID, invalid disposition, overlapping People, and collision | Each defect produces a bounded blocker |
| Preserve | Add unknown YAML and user Markdown | Valid managed proposal preserves both |
| Postflight | Supply expected and attempted effects with resulting files | Governor reports only observed effects and reconciles Daily Log entries |

## Test cases

| ID | Behavior | Practical confirmation | Status |
| --- | --- | --- | --- |
| GOV-SCHEMA-001 | `GOV-001` through `GOV-004` | Valid fixtures pass; malformed configuration, fields, timestamps, and duplicate IDs are pinpointed. | not run |
| GOV-REL-001 | `GOV-005` | Multiple CSPs, invalid Activity disposition, duplicate participants, and overlapping Effort participant sets block. | not run |
| GOV-LIFE-001 | `GOV-006` | Active-Effort removal and incomplete retained Activity metadata block. | not run |
| GOV-PATH-001 | `GOV-007` | Wrong folder and filename collision are reported without invented repair. | not run |
| GOV-PREFLIGHT-001 | `GOV-008`, `GOV-011` | Structurally valid proposal is not described as factually true or authorized. | not run |
| GOV-POST-001 | `GOV-009`, `GOV-010`, `GOV-012` | Missing file or Daily Log effect appears under unverified effects and prevents complete success. | not run |
| GOV-NOWRITE-001 | All | Hashes of fixture files are unchanged by validation. | not run |

## Host compatibility profile

- **Required host behavior:** Load Skill, read explicit file scope, parse YAML/Markdown, compare proposals and resulting state, and return a stable report without mutation.
- **Observed conditions:** Not yet probed on Copilot Cowork.
- **Another host:** Run valid, invalid, preservation, and no-write cases before relying on its validation.

## Material stop conditions

Stop if Governor writes or repairs, misses a destructive invariant, treats unavailable state as valid, claims factual truth, grants authority, or reports attempted effects as observed.

## Execution log

| Date | Environment | Observation |
| --- | --- | --- |
| 2026-09-12 | Local package and fixture validation | The package matched source byte-for-byte. The valid fixture passed structured checks for schemas, references, cardinality, paths, and logs. |
| 2026-09-12 | Local read-only agent-assisted walkthrough | Preflight accepted the valid Scan proposal and the injected dual `effortId`/Parking Lot disposition produced the expected blocker. Validation was analytical and caused no file changes; Cowork behavior was not tested. |

## Current assessment

The local contract, valid fixture, and targeted invalid-disposition reasoning are consistent; runtime success is not established. Next load Governor on Cowork with synthetic files and verify no-write behavior.