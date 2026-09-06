# Change Impact Assessment: Perspective Discovery conversational candidate review

## Document control

- **Date:** 2026-09-01
- **Status:** accepted for authorized corrective slice
- **Owner:** User / product owner
- **Changed source/version:** [Perspective Discovery source](../../skills/compass-installation-perspective-discovery/SKILL.md), `0.1.0-experimental` to `0.1.1-experimental`
- **Motivation:** [Candidate-review usability finding](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md) and [revision decision](../decisions/2026-09-01-authorize-perspective-discovery-conversational-review-revision.md)

## Change summary

The candidate-review protocol retains the accepted four semantic outcomes but changes their presentation. The Skill first explains that it is asking whether a privacy-minimized pattern is useful for fictional test design, then asks a natural question and offers `Yes`, `Change the wording`, `Make it more general`, and `Leave this out`. Technical category, evidence-count, candidate-ID, and pending-state details remain available as secondary review references rather than leading the conversation.

No retrieval source, date window, inspection limit, retention rule, authority boundary, graph boundary, handoff contract, or terminal outcome changes.

## Impact map

| Dependent item | Current version/evidence | Impact | Required action |
| --- | --- | --- | --- |
| [Compass PRD `PR-INT-001`](../requirements/compass-product-requirements.md) | 0.1, provisional requirement | Directly affected | Keep gap open until focused runtime evidence exists. |
| [Accepted Perspective Discovery specification](installation-interview-perspective-discovery-skill-specification.md) | 1.0 | No semantic contract change | Implement section 7 dispositions using clearer user-facing language and conform to section 12 interaction style. |
| Perspective Discovery source | `0.1.0-experimental` | Directly affected | Create `0.1.1-experimental` source revision and changelog. |
| Exact reviewed package | `0.1.0-experimental`, SHA-256 `0dfa685330afabe0d3e3e31ad1b5beaf3211c0d275dc1aaac845c92896bfb56f` | Superseded for future candidate-review testing, preserved as evidence subject | Create a new deterministic package and identity; do not overwrite or move the old specimen. |
| [Lean scenario](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md) | Revision 1, paused | Candidate-review wording affected | Advance the living scenario to revision 2 for the new package while preserving old result records. |
| [Perspective Discovery test plan](../test-plans/2026-08-28-workiq-perspective-discovery-test-plan.md) | Paused | Focused retest selection affected | Limit next connected run to one candidate-review and handoff path after exact-package authorization. |
| Existing test results and finding | Dated immutable records | No change | Preserve unchanged. |
| Confidence | None | No change | Do not create confidence before terminal evidence exists. |

## Evidence disposition

- **Still applicable:** Static and connected observations for `0.1.0-experimental` remain valid only as history of that exact package. Pre-retrieval observations may inform risk but do not validate `0.1.1-experimental`.
- **Invalidated or uncertain:** Candidate-review usability and all runtime behavior of `0.1.1-experimental` remain untested until a new connected run identifies the exact package.

## Smallest justified retest set

| Test | Reason | Decision enabled |
| --- | --- | --- |
| One revised PD-LEAN-001 conversation emphasizing candidate review and terminal handoff | Directly observes the changed interaction while retaining authorization, privacy, and no-change boundaries | Decide whether the conversational defect is resolved for the bounded slice. |

The new package must begin a clean Cowork conversation. Prior retrieved work content will not be copied into Dexter or reused as fixture data.

## Excluded regression

- Do not execute seven separate evaluation cases; they remain package-local design assertions.
- Do not manufacture source gaps or injection content.
- Do not test graph writes, installation, Orchestration, or other Skills.
- Do not rerun Graph Governor; it has no dependency on this change.

## Authorization required

The accepted revision decision authorizes source revision, disconnected static checks, deterministic packaging, and package inspection. Connected Cowork import, retrieval, and execution require a separate decision identifying the exact new package.