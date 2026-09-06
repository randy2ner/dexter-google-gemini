# Change Impact Assessment: Perspective Discovery 0.1.2 progressive interaction

## Document control

- **Date:** 2026-09-01
- **Status:** accepted
- **Owner:** User / product owner
- **Changed source/version:** [Perspective Discovery source](../../skills/compass-installation-perspective-discovery/SKILL.md), planned `0.1.2-experimental`
- **Motivation:** [Adaptive Card accessibility finding](../findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md) and explicit user direction to use UTC rather than fail when timezone discovery is unavailable

## Change summary

Replace the long, multi-action candidate review with short progressive conversational turns and typed fallbacks. Make technical review metadata optional. Use a disclosed UTC fallback when Cowork exposes no IANA timezone. Add a fixed synthetic interface-preview mode so the affected interaction can be observed in Cowork without Work IQ retrieval.

Retrieval sources, date-window length, evidence limits, minimization, authorization, output authority, and no-change behavior do not change.

## Impact map

| Dependent item | Current version/evidence | Impact | Required action |
| --- | --- | --- | --- |
| Perspective Discovery specification | Version 1.0 accepted | Timezone and review interaction affected | Revise living specification to 1.1 and preserve acceptance history. |
| `PR-INT-001` | Open usability evidence | Directly affected | Link the new smoke-test evidence when available. |
| `PR-PRIV-001` | Partial connected evidence | Boundary unchanged | Do not rerun privacy retrieval for the UI-only correction. |
| Skill source and package-local references | `0.1.1-experimental` | Directly affected | Revise to `0.1.2-experimental` and inspect exact package. |
| PD-LEAN-001 revision 2 | Cancelled runtime outcome | Historical evidence remains valid | Do not rewrite or rerun it under this authorization. |
| Adaptive Card accessibility finding | Open | Corrective claim proposed | Keep open until Cowork smoke-test evidence exists. |
| Perspective Discovery confidence | None | No sufficient evidence | Do not create an assessment. |

## Evidence disposition

- **Still applicable:** All `0.1.0` and `0.1.1` package inspections and connected observations remain historical evidence for those exact packages.
- **Invalidated or uncertain:** No prior result supports operability of the new progressive interaction or UTC fallback.

## Smallest justified retest set

| Test | Reason | Decision enabled |
| --- | --- | --- |
| [PD-UI-001](../scenarios/workiq-perspective-discovery/pd-ui-001-progressive-interaction-smoke.md) | Observe the exact affected controls in Cowork using fixed synthetic text and no retrieval | Whether the accessibility finding is mitigated enough to consider a connected rerun. |

## Excluded regression

- No Email or Teams retrieval because retrieval limits and privacy behavior did not cause the UI failure.
- No Graph Governor, graph, file, handoff-storage, source-gap, or injection test because those claims are unaffected.
- No broad action-branch matrix; one progressive path and typed escape path are sufficient for this correction gate.

## Authorization required

The [accepted corrective-slice decision](../decisions/2026-09-01-authorize-perspective-discovery-v0-1-2-progressive-interaction-slice.md) authorizes source/package work and one no-retrieval Cowork smoke test. Any Work IQ retrieval or repeat requires a separate decision.