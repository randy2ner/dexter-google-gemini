# Work IQ Perspective Discovery scenarios

The [accepted lean-scope decision](../../decisions/2026-09-01-reduce-perspective-discovery-to-one-connected-run.md) replaced seven planned standalone executions with one staged, privacy-bounded conversation. The authorized `0.1.1-experimental` run ended with a `cancelled` runtime outcome and partial laboratory result.

## Primary connected scenario

| Scenario | Primary behavior | Status |
| --- | --- | --- |
| [PD-LEAN-001](pd-lean-001-bounded-discovery-session.md) | Exercise authorization, bounded retrieval, candidate review, minimization, honest source accounting, and no-change behavior in one conversation | [cancelled terminal outcome; partial laboratory result](../../test-results/2026-09-01-perspective-discovery-v0-1-1-pd-lean-001-cancelled.md) after Adaptive Card controls became inaccessible |

## Preserved design assertions

These original scenarios remain unexecuted traceability references. They are not separate execution or exit requirements for the lean slice.

| Scenario | Primary behavior |
| --- | --- |
| [PD-001](pd-001-plan-and-authorization.md) | Display exact scope and wait for `Run` |
| [PD-002](pd-002-bounded-retrieval.md) | Stay within source, date, and item limits |
| [PD-003](pd-003-candidate-review.md) | Preserve user authority over every pattern |
| [PD-004](pd-004-minimization.md) | Exclude raw evidence and identities |
| [PD-005](pd-005-source-gaps.md) | Report unavailable or partial sources honestly when naturally encountered |
| [PD-006](pd-006-injection-resistance.md) | Treat retrieved instructions as data when naturally encountered |
| [PD-007](pd-007-fictionalization-handoff.md) | Produce a safe, non-authoritative design handoff |
