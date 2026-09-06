# Skill profile: compass-installation-perspective-discovery

## Identity

- **Name:** compass-installation-perspective-discovery
- **Owner:** User / product owner
- **Current version:** `0.1.2-experimental`
- **Status:** developing; corrective source and uninspected candidate package exist; interface behavior untested
- **Source:** [Skill source](../../skills/compass-installation-perspective-discovery/SKILL.md)

## Purpose and boundaries

Conduct one user-authorized, read-only Work IQ Perspective Discovery interaction in Copilot Cowork and produce reviewed generic patterns for later fictional test design. It does not install Compass, create graph content, retain Work IQ evidence, perform external actions, or invoke Graph Governor.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Compass charter](../charter/compass-vision-and-scope-charter.md) | Governance | 1.0 accepted | Yes | Charter change requires scope review. |
| [Perspective Discovery specification](../specifications/installation-interview-perspective-discovery-skill-specification.md) | Skill specification | 1.1 accepted revision | Yes | Material change requires a new Skill version and affected-test review. |
| Copilot Cowork portable Skill support | Runtime | Package import and partial connected interaction observed; exact runtime metadata unavailable | Yes | Runtime differences limit reproducibility and confidence. |
| Work IQ Email and Teams access | Data capability | Calling user's permissions; exact exposed behavior unverified | Yes | Missing or different capability produces partial or blocked results. |

## Consumers

- Human-led synthetic fixture design after minimization and fictionalization review

## Validation coverage

- [Perspective Discovery scenarios](../scenarios/workiq-perspective-discovery/README.md)
- [Perspective Discovery test plan](../test-plans/2026-08-28-workiq-perspective-discovery-test-plan.md)
- [Accepted lean connected-scope decision](../decisions/2026-09-01-reduce-perspective-discovery-to-one-connected-run.md)
- [Lean privacy-bounded connected scenario](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md)
- [Lean connected-run authorization](../decisions/2026-09-01-authorize-perspective-discovery-lean-connected-run.md)
- [Lean connected-run local preflight](../experiments/2026-09-01-perspective-discovery-lean-connected-preflight.md)
- [Disconnected source inspection](../test-results/2026-08-28-perspective-discovery-source-static-inspection.md)
- [Deterministic package inspection](../test-results/2026-09-01-perspective-discovery-package-inspection.md)
- [Candidate-review usability finding](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)
- [Conversational-review change impact](../specifications/2026-09-01-perspective-discovery-conversational-review-impact-assessment.md)
- [Version 0.1.1 source and package inspection](../test-results/2026-09-01-perspective-discovery-v0-1-1-source-and-package-inspection.md)
- [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)

## Packaging

- **Artifact format:** Copilot Cowork `.skill`
- **Entry file:** Root `SKILL.md`
- **Latest inspected artifact:** [compass-installation-perspective-discovery-v0.1.1-experimental.skill](../../skill-exchange/ready-for-test/compass-installation-perspective-discovery-v0.1.1-experimental.skill)
- **Latest inspected artifact SHA-256:** `3b563deddd98d162574d49c87e12a631d17f6a2453b7b119e92eaba8f056e6d2`
- **Latest package inspection:** [Version 0.1.1 source and package inspection](../test-results/2026-09-01-perspective-discovery-v0-1-1-source-and-package-inspection.md)
- **Candidate artifact:** [compass-installation-perspective-discovery-v0.1.2-experimental.skill](../../skill-exchange/ready-for-test/compass-installation-perspective-discovery-v0.1.2-experimental.skill); presence recorded, inspection not completed
- **Packaging notes:** See the [implementation plan](../specifications/installation-interview-perspective-discovery-implementation-plan.md). The `0.1.1` connected run has a cancelled terminal outcome and partial laboratory result. No `0.1.2` runtime result or confidence assessment exists.

## Lifecycle notes

Source version `0.1.2-experimental` adds progressive three-choice turns, typed fallbacks, and a disclosed UTC fallback. Its candidate package is present but uninspected. The earlier `0.1.0` and `0.1.1` packages and evidence remain unchanged; `0.1.1` ended with a cancelled runtime outcome and partial laboratory result. No `0.1.2` runtime result or confidence assessment exists, and the Skill is not validated.
