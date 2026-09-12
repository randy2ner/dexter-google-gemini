# Decision: Adopt experience-led beta route

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery controls were inaccessible](../findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md); [candidate review was too technical](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)

## Context

The seven-check pre-beta strategy still made technical primitives the user's path into Compass. The product owner wants to evaluate Compass by talking with Cowork through a recognizable work-memory experience, while retaining enough setup, restoration, and effect inspection to establish whether continued development use is responsible.

Gate 0 produced five exact statically inspected candidate packages, an accepted Orchestration, and a restorable fictional graph. None of the beta-candidate packages has runtime evidence.

## Decision

Adopt Option B: one realistic Compass experience rehearsal followed, when no blocking condition is observed, by rapid transition to a separately authorized development beta.

1. Treat package import, Skill availability, graph access, and capability visibility as a brief operator preflight, not separate product tests.
2. Use one natural setup-to-review Compass journey as the primary first runtime evaluation.
3. Observe interaction, routing, authority, identity, history, effect accounting, privacy, and recoverability within that journey rather than requiring isolated tests first.
4. Run a focused technical test only when the rehearsal exposes a specific failure or leaves a beta-blocking uncertainty.
5. Record one compact rehearsal result. Ordinary usefulness, wording, interruption, judgment, and personality issues become development feedback rather than admission blockers.
6. Require a separate explicit decision before development beta begins with real work evidence or connected storage.

## Alternatives considered

- **Seven staged pre-beta checks:** Provides better fault isolation but delays recognizable product use and repeats setup around technical primitives.
- **Immediate unbounded beta:** Produces natural feedback sooner but lacks a controlled first graph, exact package boundary, and demonstrated stop path.

## Consequences

- The [compact seven-check strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md) is superseded for future Compass candidate evaluation.
- The [experience-led rehearsal plan](../test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md) becomes the current test strategy.
- Existing completed results remain unchanged and version-bound.
- The rehearsal can establish enough evidence to propose development beta, but it cannot itself authorize beta, deployment, or release.

## Follow-up

- Laboratory assistant prepares the exact session kit and preserves runtime fields as blank until directly observed.
- Product owner conducts or explicitly authorizes the Cowork rehearsal.
- Product owner decides after the rehearsal whether to stop, revise, run one focused diagnostic, or authorize development beta.