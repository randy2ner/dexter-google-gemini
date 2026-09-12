# Orchestration: Compass Customer Work Lifecycle

## Identity

- **Name:** compass-customer-work-lifecycle
- **Version:** 0.1.0-local-candidate
- **Owner:** User / product owner
- **Status:** validating

## Purpose

Give one user an end-to-end Compass experience from filing-cabinet setup through ordinary customer Activity scanning, validated graph updates, useful work review, and optional lifecycle curation. Multiple Skills are required because installation, connected evidence review, structural validation, and destructive lifecycle effects have different triggers and authority boundaries.

## Trigger

Begin when the user asks to start Compass, catch up on customer work, update the filing cabinet, review current Efforts, or curate stale work. Determine whether a valid graph already exists before routing.

## Dependencies

| Dependency | Type | Compatibility condition | Required | Failure impact |
| --- | --- | --- | --- | --- |
| [Installation Interview](../../skills/compass-installation-interview/SKILL.md) | Skill | Candidate `0.1.0-local-candidate`; invoked only when no usable graph exists or setup is requested | Conditional | New graph cannot be established |
| [Activity Scan](../../skills/compass-activity-scan/SKILL.md) | Skill | Candidate `0.1.0-local-candidate`; retrieval and write approvals remain separate | Yes for ordinary update | Evidence cannot update Activities |
| [Graph Governor](../../skills/compass-graph-governor/SKILL.md) | Skill | Candidate `0.1.0-local-candidate`; read-only preflight and postflight | Yes for mutation | Proposed or observed graph effects cannot be trusted |
| [Curator](../../skills/compass-curator/SKILL.md) | Skill | Candidate `0.1.0-local-candidate`; archive and removal approvals remain separate | Conditional | Lifecycle review or compaction is skipped |
| Copilot Cowork | Skill host | Loads candidates, sustains handoffs, and exposes material tool limits | Yes for host test | Run remains disconnected or blocked |
| User | Human | Reviews retrieval, graph, archive, and removal boundaries | Yes | Consequential stage pauses without effect |

## Flow

1. Identify the explicit graph root and user purpose without accessing work evidence or mutating files.
2. If no valid graph exists or setup is requested, route to Installation Interview. Governor validates the proposed graph and independently validates read-back before installation success.
3. Route ordinary catch-up to Activity Scan. The user approves a bounded Email and Teams plan before retrieval.
4. Activity Scan interprets customer-only Activities and presents exact graph effects. Governor performs preflight validation.
5. The user approves, changes, pauses, or cancels graph changes. Activity Scan owns authorized mutation and read-back; Governor performs postflight validation.
6. Present the current Effort and Activity view from verified graph state. Do not disclose or publish it.
7. Offer, but do not assume, a Curator review. If chosen, Curator proposes the default 14-day criteria and performs read-only classification after criteria approval.
8. Curator obtains exact Effort archive authority, uses Governor preflight and postflight around archive and metadata-retention writes, and leaves Activity files present.
9. Curator separately displays exact removable Activity files and retained metadata. Only explicit removal approval permits those removals, followed by Governor postflight.
10. Return one truthful report separating evidence coverage, verified effects, unapplied proposals, preserved files, blockers, and uncertainty.

## Handoffs and contracts

| From | To | Data or artifact | Success condition |
| --- | --- | --- | --- |
| Router | Installation | Explicit graph root and setup intent | No unrelated location is inspected |
| Installation or Activity Scan | Governor preflight | Graph root, base state, proposed operations, expected paths and Daily Log effects | Report identifies valid operations and bounded blockers |
| Governor preflight | Initiating Skill | Read-only validation report | Initiating Skill preserves its own authority boundary and blocks invalid operations |
| Initiating Skill | Governor postflight | Expected effects, attempted operations, affected paths, and logs | Observed state is independently reconciled with reported effects |
| Activity Scan | Work view | Verified Activities, Efforts, coverage, and uncertainty | View is based only on observed graph state and is not externally disclosed |
| Work view | Curator | Explicit user choice and graph root | Curator does not infer review authority from prior approvals |
| Curator | Governor | Archive or removal proposal and later observed state | Preserve-before-remove and lifecycle invariants are validated |

## Guardrails and approvals

- Retrieval-plan approval authorizes only the displayed read-only access.
- Installation or Scan graph changes require exact proposal approval.
- Curator criteria approval authorizes review only.
- Effort archival requires exact candidate approval and an explicit `success` value.
- Activity removal requires a separate exact-file approval after retained metadata is verified.
- Preparation never authorizes disclosure; no Skill changes source Email or Teams content.
- A host that cannot invoke Skills from an orchestration may run the same sequence through explicit user handoffs without changing these contracts.

## Failure and fallback behavior

- **Skill loading unavailable:** run one independently loaded candidate at a time and preserve the handoff summary.
- **Retrieval unavailable or incomplete:** continue only with direct user input or inspected evidence and label coverage; do not claim complete recency.
- **Governor blocked:** do not perform the affected mutation; return the precise blocker to the initiating Skill.
- **Write or read-back failure:** report only independently observed effects and preserve unapplied work as a proposal.
- **Curator uncertainty:** leave affected Efforts active and Activity files present.
- **Conflict before removal:** stop the affected removal and require fresh validation and approval.

## Test Plans

- [Installation Interview](../../test-plans/installation-interview.md)
- [Activity Scan](../../test-plans/activity-scan.md)
- [Graph Governor](../../test-plans/graph-governor.md)
- [Curator Lifecycle](../../test-plans/curator-lifecycle.md)
- [Customer Work Lifecycle](../../test-plans/customer-work-lifecycle.md)

## Revision guidance

When routing, handoffs, schema, or approvals change, review all participating Skill source, the affected Specifications, this Orchestration, synthetic fixture, packages, and linked Test Plans. Host observations update Test Plans without rewriting prior evidence.