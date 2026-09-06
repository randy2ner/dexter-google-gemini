# Specification: Curator Skill responsibility

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.2-dogfood-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.3](compass-shared-contracts-specification.md); [Graph Schema 0.3](compass-graph-schema-specification.md)
- **Implementation authority:** None; responsibility specification only

## Purpose and owned outcome

Curator helps the user review whether retained work memory remains relevant, understandable, organized, and worthy of attention. It owns bounded graph review, prioritized observations, and recommendations for user consideration.

Curator does not own graph meaning or modification. Recommendations become organizational proposals only when the user chooses to continue through Tracking Topic Interview, or other exact change requests only through the responsible Skill and Graph Governor boundary.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| Review scope | User-selected graph area, object types, time context, or question; never an implied whole-graph claim. |
| Accepted graph state | Portable objects and canonical relationships within the authorized review scope. |
| Integrity observations | Existing Graph Governor results when relevant; Curator does not duplicate structural authority. |
| Review report | Prioritized observations separated from interpretations and recommendations. |
| Recommendation handoff | Object IDs, user-facing rationale, proposed review question, and only the graph context needed by the responsible Skill. |
| Review result | Honest scope, unavailable context, recommendations accepted for follow-up, and external changes count. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| CUR-001 | Review only the bounded scope authorized by the user and disclose coverage. | `PR-AUTH-001`, `PR-TRUTH-001` | Curator never describes a partial review as whole-graph validation. |
| CUR-002 | Separate observed graph state, interpretation, and recommendation. | `PR-TRUTH-001` | Each recommendation identifies its accepted source objects without presenting inference as fact. |
| CUR-003 | Preserve history and use latest recorded Compass activity only as a review signal. | `PR-HIST-001` | Daily Log recency is labeled non-authoritative for source activity; no lifecycle change occurs without user confirmation. |
| CUR-004 | Route Topic meaning, merge, alignment, archival, and reactivation to Tracking Topic Interview. | `PR-AUTH-001`, accepted Skill boundary | The handoff carries no inherited modification authority. |
| CUR-005 | Route structural integrity and repair questions to Graph Governor. | `PR-SAFE-001` | Curator does not classify its own recommendation as structurally valid. |
| CUR-006 | Minimize displayed and handed-off content. | `PR-PRIV-001` | Reports use object labels, concise rationale, and bounded context rather than raw evidence. |
| CUR-007 | Make unresolved last-activity semantics visible. | Accepted baseline deferral | Curator does not calculate or confirm authoritative recency before that contract exists. |

## Human interaction

Curator should feel like a thoughtful periodic review with a trusted colleague, not judgment, scoring, or productivity surveillance. Begin with what the user wants to improve, present a short prioritized set, and ask whether each item is still useful or needs attention. Avoid labels that imply failure, neglect, employee performance, or customer health unless the user has explicitly established that meaning.

Every recommendation supports typed keep, explore, defer, or dismiss paths. Dismissal affects the recommendation only; it is not authority to modify the graph object.

## Authority, safety, and privacy boundaries

- Read access supports review only and does not authorize graph changes.
- Curator may recommend consolidation, reclassification, archival, reactivation, or Conversation deletion review, but may not apply any of them.
- Tracking Topics are never deleted. Conversation deletion requires separate review and explicit approval through the responsible change path.
- Curator may derive latest recorded Compass activity from Daily Logs but may not claim authoritative source activity or infer sensitive traits, performance, intent, or customer health.
- Recommendations exclude raw evidence and unrelated graph content by default.
- Curator does not modify configuration, objects, relationships, Daily Logs, or user-authored content.

## Handoffs and responsibility boundary

- **To Tracking Topic Interview:** user-selected recommendation concerning Topic meaning, lifecycle, consolidation, or relationships.
- **To Graph Governor:** user-selected integrity question or bounded health-scan request.
- **To Daily Scan:** no mutation handoff; the user may separately initiate a scan when missing recent evidence is the issue.
- **From other Skills:** accepted graph state only, not provisional proposals or hidden conversational memory.

Curator owns prioritization and understandable review. It does not own installation, source retrieval, Conversation capture, organizational authority, structural validation, persistence, or recovery.

## Failure, partial, blocked, and cancellation behavior

- Missing or inaccessible graph context produces a bounded partial or blocked review with no inferred replacement.
- No noteworthy observations produces an honest empty review, not a whole-graph health guarantee.
- Cancellation makes no graph changes and reports the scope already inspected.
- A recommendation declined or dismissed remains non-authoritative and creates no Daily Log activity.
- A downstream handoff failure leaves the recommendation unapplied and reports that distinction.

## Edge cases and unresolved questions

- Staleness thresholds remain user judgment. Curator may present Daily Log-derived latest recorded Compass activity and ask whether the content is stale or completed.
- Automatic scheduling and unattended curation are outside the beta responsibility.
- Recommendation dismissal retention is an Orchestration or later product decision, not authoritative graph state in schema version 1.

## Traceability and evaluation

- **Test plan:** [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Planned checks:** S3 boundary probe and integrated synthetic rehearsal
- **Source gap:** No prior Curator package or runtime evidence exists.

## Revision history

| Version | Date | Change | Motivation and impact |
| --- | --- | --- | --- |
| 0.1-beta-responsibility | 2026-09-02 | Defines Curator as bounded review and recommendation, with no independent modification authority. | Accepted Slice B set and beta baseline. |

## Acceptance boundary

Acceptance would establish Curator's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, graph access, graph writes, testing, deployment, or release.