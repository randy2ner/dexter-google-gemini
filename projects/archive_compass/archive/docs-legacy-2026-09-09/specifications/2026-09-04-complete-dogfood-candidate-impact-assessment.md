# Change impact assessment: Complete dogfood candidate

## Document control

- **Status:** accepted implementation basis
- **Version:** 1.0
- **Owner:** User / product owner
- **Last updated:** 2026-09-04
- **Decision:** [Authorize complete dogfood candidate](../decisions/2026-09-04-authorize-complete-dogfood-candidate.md)

## Changed contracts

| Surface | Change |
| --- | --- |
| Installation | Permit a user-selected connected OneDrive graph and carry normative bootstrap schema needed in a clean session. |
| Daily Scan | Permit bounded connected WorkIQ retrieval, reviewed model relevance, customer-focused Parking Lot capture, and approved `trackingTopicId` effects. |
| Tracking Topic Interview | Accept archival handoffs based on derived Daily Log recency and user-confirmed completion or staleness. |
| Curator | Derive latest recorded graph activity from Daily Logs and use explicit action labels for review paths. |
| Graph Governor | Validate and verify connected graph requests; connected failures never enter synthetic rollback. |
| Orchestration | Coordinate installation, connected daily capture, inline alignment authority, curation, and manual-recovery stops. |

## Preserved contracts

- Conversation owns `trackingTopicId`; Tracking Topic owns `cspId`.
- Parking Lot remains a derived view, not a stored object.
- Evidence remains non-authoritative until reviewed.
- Tracking Topics are archived, never deleted.
- Graph Governor does not originate semantic changes or directly write files.
- Every durable update includes a Daily Log effect and post-write verification.

## Evidence impact

Prior synthetic and beta-candidate results remain evidence only for their exact versions. The dogfood set needs one connected, mediated end-to-end experience. Focused follow-up is required only for a material defect or unresolved capability exposed by that experience.

## Recovery impact

Synthetic disposable operations may retain the accepted rollback protocol. Connected graph operations have no automatic delete-based rollback. Any partial or unverifiable connected write returns `recovery-required` and blocks dependent writes until the user restores or explicitly resolves the graph.