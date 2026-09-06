# Scenario: Valid synthetic graph baseline

## Metadata

- **Scenario ID:** gg-syn-001-valid-baseline
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** graph-governor
- **Risk/priority:** high
- **Status:** executed; passed on 2026-08-31

## Objective

Determine whether the exact Graph Governor package recognizes the complete synthetic baseline as valid within the bounded read-only contract.

## Preconditions

- First-slice decision and bounded contracts are accepted.
- Exact package and fixture versions are recorded.
- Fixture baseline hashes match its manifest.
- [GG-SYN-001 execution authorization](../../decisions/2026-08-31-authorize-gg-syn-001-execution.md) is accepted.
- [GG-SYN-001 preflight](../../experiments/2026-08-31-gg-syn-001-preflight.md) passed for the exact isolated fixture copy and package.

## Test data

Use only the valid baseline defined by the [fixture specification](../../specifications/graph-governor-synthetic-fixture-specification.md).

## Steps

1. Provide the unchanged baseline graph to Graph Governor.
2. Request a read-only health scan of the complete supplied graph.
3. Capture the complete response and visible environment details.

## Expected behavior

- Reports the bounded graph as valid without inventing issues.
- Identifies the inspected scope and exact fixture identity.
- Makes no modification and claims no connected capability.

## Variations and edge cases

- Repeat in a new Cowork conversation with the same package and fixture.

## Evidence to capture

- Package hash, fixture manifest hash, complete response, visible Cowork environment, and before/after fixture hashes.

## Cleanup

- Remove only the disposable Cowork attachment or test-session copy; preserve the registered specimen and result.

## Recorded result

- [2026-08-31 GG-SYN-001 result](../../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md): **pass** for the exact package and valid synthetic baseline. Post-run fixture and package verification passed.
