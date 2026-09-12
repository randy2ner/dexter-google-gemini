# Change impact and retesting

## Document control

- **Status:** living
- **Version:** 2.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Compile beta observations into one compatible rewrite and choose the smallest useful follow-up without creating an assessment document for every edit.

## Impact analysis

Use a standalone impact assessment only when a proposed change can affect authority, privacy, identity, retained history, recoverability, or effect truth. Otherwise record the change and dependencies in the consolidated beta result or rewrite summary.

When an assessment is justified, record:

1. the changed source and exact revision;
2. why it changed;
3. affected requirements and acceptance criteria;
4. affected specifications, source, packages, and Orchestrations;
5. evidence that remains applicable;
6. evidence invalidated or made uncertain;
7. whether the full beta journey or one focused diagnostic best evaluates the rewrite; and
8. the decision enabled by that evidence.

## Retest selection

| Change | Typical response |
| --- | --- |
| Editorial clarification with no behavioral effect | Link the clarification; no rerun |
| Requirement or interaction change | Include it in the next complete beta journey; add no standalone test by default |
| Parser, schema, or ordinary contract change | Rebuild the compatible candidate and rerun the complete journey |
| Authority, privacy, identity, history, recovery, or effect-truth change | Run one focused diagnostic if needed, then rerun the complete journey |
| Package-only metadata change | Reinspect package and test runtime discovery if affected |
| Runtime or model change | Run a compact smoke suite focused on runtime-sensitive behavior |
| Broad architectural change | Justify broader regression explicitly |

## Stop rule

Do not add a test unless its possible outcomes can change the rewrite, beta decision, or treatment of a material risk. Record optional variations as gaps rather than mandatory debt.

Do not perform serial compatibility rewrites after each non-blocking observation. Finish the representative journey, group findings by root cause, update all affected Skills and Orchestration together, and produce one new complete candidate.

## Evidence preservation

Never overwrite earlier results. New results identify the changed subject and link the impact assessment that selected them.