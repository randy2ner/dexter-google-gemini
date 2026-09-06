# Decision: Accept the Graph Governor read-only implementation plan

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Synthetic fixture construction validation](../test-results/2026-08-28-graph-governor-synthetic-fixture-validation.md)

## Context

The bounded read-only contract subset is accepted, the synthetic fixture family is validated for construction, and the Graph Governor implementation plan identifies an exact three-file source shape, traceability matrix, disconnected checks, stop conditions, and lifecycle gates. The user stated, “I approve,” after reviewing the planning gate.

## Decision

Accept the [Graph Governor read-only implementation plan](../specifications/graph-governor-read-only-implementation-plan.md) as the source-design baseline for planned version `0.1.0-experimental`.

This decision approves the plan only. It does not authorize creation of the planned source files or execution of the planned disconnected checks.

## Alternatives considered

- **Revise the plan before acceptance:** Not selected by the user.
- **Treat plan approval as source authorization:** Rejected because the accepted plan requires a separate explicit source-creation decision.

## Consequences

- The exact planned source structure and static-check scope are stable for the next authorization gate.
- A material plan revision requires renewed review before source creation.
- Graph Governor remains unimplemented and every GG-SYN scenario remains unexecuted.

## Follow-up

- User / product owner: separately authorize or defer creation of exactly the three planned source files and disconnected static checks.
- Project Dexter: do not create source, package, upload, or run Graph Governor without the corresponding explicit authorization.
