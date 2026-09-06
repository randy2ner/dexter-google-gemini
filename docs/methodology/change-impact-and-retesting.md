# Change impact and retesting

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Determine what must change or be retested when a living source of truth evolves, without defaulting to a full regression suite.

## Impact analysis

For each material change, record:

1. the changed source and exact revision;
2. why it changed;
3. affected requirements and acceptance criteria;
4. affected specifications, source, packages, and Orchestrations;
5. evidence that remains applicable;
6. evidence invalidated or made uncertain;
7. the smallest justified test set; and
8. the decision enabled by that testing.

## Retest selection

| Change | Typical response |
| --- | --- |
| Editorial clarification with no behavioral effect | Link the clarification; no rerun |
| Requirement or interaction change | Rerun direct acceptance and adjacent safety scenarios |
| Parser, schema, contract, or authority-boundary change | Rerun affected positive, negative, safety, and combined cases |
| Package-only metadata change | Reinspect package and test runtime discovery if affected |
| Runtime or model change | Run a compact smoke suite focused on runtime-sensitive behavior |
| Broad architectural change | Justify broader regression explicitly |

## Stop rule

Do not add a test unless its possible outcomes can change a decision, confidence claim, implementation, or risk treatment. Record optional variations as gaps rather than mandatory debt when they do not block the current decision.

## Evidence preservation

Never overwrite earlier results. New results identify the changed subject and link the impact assessment that selected them.