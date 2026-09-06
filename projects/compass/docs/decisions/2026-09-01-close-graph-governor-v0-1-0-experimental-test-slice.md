# Decision: Close Graph Governor 0.1.0-experimental test slice

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related evidence:** [Bounded confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md), [synthetic read-only test plan](../test-plans/2026-08-28-graph-governor-synthetic-read-only-test-plan.md)

## Context

All eight primary Graph Governor synthetic read-only scenarios were executed using the exact tested package and isolated fictional fixtures. Thirteen primary fixture runs passed their recorded expectations, including the GG-SYN-007 same-conversation refusal turn. Pre-run and post-run evidence found no fixture byte changes. Continuing to add variations would impose delay without resolving a specific blocker to this bounded experimental objective.

The exact Cowork version, model, and configuration were not reported for the runs. The GG-SYN-008 file-order variation was not manifested or executed. These gaps limit reproducibility and generalization but do not invalidate the directly observed primary-matrix evidence.

On 2026-09-01, the user authorized one closure batch for Graph Governor.

## Decision

Close the Graph Governor `0.1.0-experimental` synthetic read-only test slice as **validated for its bounded experimental scope**, subject to the [confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md).

Accept the missing Cowork runtime metadata as a documented reproducibility limitation rather than attempting to reconstruct or fabricate it. Do not require the GG-SYN-008 file-order variation for closure. Preserve the tested package, source, fixtures, preflights, decisions, and results without rewriting historical evidence.

This decision completes the current test slice. It does not approve deployment, release, publication, production or real-graph use, writes, live Microsoft 365 access, integration, another Graph Governor version, or another Skill.

## Alternatives considered

- **Continue adding mutations and variations:** Rejected because the primary matrix is complete and no remaining variation is tied to a current closure decision.
- **Block closure until runtime metadata is recovered:** Rejected because the metadata was not captured and cannot be reconstructed reliably after the runs.
- **Declare general or production readiness:** Rejected because the evidence covers only the exact experimental package, accepted read-only subset, fictional fixtures, and observed Cowork runs.

## Consequences

- The test plan is complete and closed with explicit limitations.
- Graph Governor remains experimental; its validated status applies only to the bounded read-only synthetic scope.
- The file-order variation becomes a future optional candidate, not test debt required for this closure.
- Future changes use impact-based regression selection instead of automatically repeating the entire matrix.
- Historical test records and the exact tested package remain immutable evidence.

## Follow-up

- Project Dexter: update the test plan and Skill profile to reference this closure and confidence assessment.
- User / product owner: explicitly authorize any next Skill, new Graph Governor version, regression execution, integration work, release evaluation, or broader lifecycle step.