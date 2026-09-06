# Test results: compass-beta-graph-v1 construction validation

## Document control

- **Status:** complete
- **Version:** 1.0
- **Owner:** User / product owner
- **Tested on:** 2026-09-02
- **Last updated:** 2026-09-02
- **Authority:** Accepted Slice D disconnected fixture construction only

## Scope

Validate the wholly fictional [compass-beta-graph-v1 fixture](../../test-data/compass-beta-graph-v1/manifest.md), expected final graph, separate restore baseline, and deterministic restoration. This was construction validation, not Skill execution.

## Direct observations

1. The fixture contains only generic fictional content and reserved `.invalid` author addresses. It contains no tenant identifier, credential, token, personal graph, or retrieved Microsoft 365 content.
2. The expected final configuration and six managed Markdown objects parse as YAML/schema version 1 records.
3. Object IDs are unique. Person, CSP, Tracking Topic, Conversation, and Daily Log references resolve.
4. Canonical direction is preserved: Tracking Topic owns `cspId`; Conversation owns `activeParticipantIds` and `trackingTopicId`; no reverse authoritative arrays exist.
5. Tracking Topic status is `active`. Both accepted managed Daily Log markers occur exactly once in the expected final Daily Log, and its graph links resolve.
6. The external restore baseline and initial materialized graph have identical relative members, byte counts, and SHA-256 values.

## Baseline inventory

| Relative file | Bytes | SHA-256 |
| --- | ---: | --- |
| `README.md` | 299 | `2f344bdb89f8b2157bb8d313401402aef92dc13f9f1834d825b27d46272ff67a` |

- **Aggregate bytes:** 299
- **Deterministic aggregate SHA-256:** `5e331cd419d40e43460b21fe792e52d3db91bb855960c106bd12fbafd34c1486`

## Restore verification

A temporary copy outside the fixture was created from the baseline. Its `README.md` was modified and one declared synthetic extra file was added. Only that temporary materialized copy was cleared and restored from the baseline.

| Check | Observation |
| --- | --- |
| Relative members | Exact match |
| Byte counts | Exact match |
| Per-file SHA-256 | Exact match |
| Temporary directory cleanup | Completed |
| Fixture modification during simulation | None |

## Interpretation

The fixture meets the Slice D construction checkpoint: the pre-installation baseline is reproducible, the expected final graph is internally coherent against the accepted schema subset, and the documented restoration mechanism reproduces the baseline in an isolated simulation.

## Limitations

- The expected final graph is an oracle, not evidence that any Skill can create it.
- No Skill application, injected failure, concurrent writer, Cowork runtime, connected graph, or persistent recovery was exercised.
- Restoration is authorized only for this disposable fixture in a separately authorized test.