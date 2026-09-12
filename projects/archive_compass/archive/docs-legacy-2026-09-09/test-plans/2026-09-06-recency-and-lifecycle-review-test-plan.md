# Test plan: Recency and lifecycle review

## Metadata

- **Owner:** User / product owner
- **Period:** 2026-09-06 onward
- **Requirements:** `PR-RECENCY-001`, `PR-REVIEW-001`
- **Specification:** [Recency and lifecycle review specification](../specifications/recency-and-lifecycle-review-specification.md)
- **Status:** planned; no implementation or execution authorized

## Goals

- Verify accurate `updatedAt` initialization and advancement for Tracking Topics and Conversations.
- Verify failed or unrelated activity does not advance an object timestamp.
- Verify disclosed criteria and bounded scope produce the correct review candidates.
- Verify candidate identification never causes an automatic purge or archive.
- Verify authorized Conversation purge and Topic archival follow their distinct history and approval contracts.

## Planned scenarios

| ID | Specification behavior | Expected evidence | Status |
| --- | --- | --- | --- |
| RLR-001 | Creation initializes `updatedAt` to `createdAt`. | Parsed fictional Topic and Conversation after verified creation. | planned |
| RLR-002 | Successful object and owner-field changes advance `updatedAt`. | Before/after timestamps and verified effects for content, alignment, and participant changes. | planned |
| RLR-003 | Rejected, blocked, conflicted, rolled-back, and unrelated operations do not advance it. | Exact before/after comparison for each outcome class. | planned |
| RLR-004 | Bounded disclosed criteria classify matching, non-matching, and unevaluable items correctly. | Review report compared with a fixed fictional fixture and evaluation time. | planned |
| RLR-005 | Matching criteria cause no automatic change. | Fixture remains byte-identical after recommendation-only review. | planned |
| RLR-006 | Approved Conversation purge preserves required history and relationships. | Verified deletion effects and Daily Log tombstone without Person deletion or Topic-participant pruning. | planned |
| RLR-007 | Approved Topic archival preserves the Topic and relationships. | Verified `archived` status, boolean `success`, retained `attentionState`, advanced `updatedAt`, and Daily Log effect. | planned |
| RLR-008 | Keep, defer, change, and cancel paths preserve authority boundaries. | Interaction record and zero unauthorized graph effects. | planned |

## Test data

Use a disposable fictional schema-version-2 fixture containing:

- Topics and Conversations on both sides of each selected threshold;
- equal-boundary timestamps;
- one missing and one invalid timestamp;
- active and archived Topics;
- aligned, Parking Lot, and participant-bearing Conversations; and
- protected exclusions from the review scope.

Exact fixture construction begins only after the schema integration is accepted.

## Entry criteria

- The technical specification and field integration are accepted.
- Exact affected Skill and Orchestration versions are registered.
- The fixture is disposable, fictional, and has a verified baseline.

## Exit criteria

- Every planned scenario has an immutable result linked to its exact specification and artifact versions.
- Timestamp precision, boundary comparisons, authority, history preservation, and effect reporting have direct evidence.
- Unexecuted scenarios remain `planned`; static inspection is not presented as runtime confidence.

## Out of scope

- Personal or connected graph cleanup.
- Automatic unattended purge or archival.
- Treating `updatedAt` as Microsoft 365 source activity or user attention.
- Deployment, promotion, or release.