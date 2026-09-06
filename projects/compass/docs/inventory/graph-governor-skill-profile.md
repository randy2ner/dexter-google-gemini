# Skill profile: graph-governor

## Identity

- **Name:** graph-governor
- **Owner:** User / product owner
- **Current version:** `0.2.0-beta-candidate`
- **Status:** developing; candidate source and package inspected; new modes runtime untested
- **Source:** [Skill source](../../skills/graph-governor/SKILL.md)

## Purpose and boundaries

Graph Governor validates exact change handoffs, verifies attempted effects, supervises separately authorized recovery on a disposable synthetic graph, and preserves its bounded read-only health scan. It does not choose semantic meaning, originate graph changes, directly write files, access connected evidence, or claim persistence behavior.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Compass charter](../charter/compass-vision-and-scope-charter.md) | Governance | 1.0 accepted | Yes | Charter change requires scope review. |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Responsibility revision requires scope review; implementation changes require affected scenario reruns. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` | Yes | Responsibility revision requires fixture review; implementation changes require affected scenario reruns. |
| [Graph Governor specification](../specifications/graph-governor-skill-specification.md) | Skill specification | Accepted Slice B responsibility | Yes | Responsibility changes require profile and scenario review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.1-beta-candidate` | Yes | Handoff or outcome changes require compatibility review. |
| [Beta lifecycle fixture](../../test-data/compass-beta-graph-v1/manifest.md) | Test data | `1.0.0-candidate` | Yes for Gate 1 | Fixture revisions require exact hash review. |
| [Synthetic Compass graph fixture](../../test-data/gg-synthetic-graph-v1/manifest.md) | Test data | 1.0.0; disconnected construction validation passed | Yes | Fixture revisions require exact version recording and delta revalidation. |
| Copilot Cowork portable Skill support | Runtime | Must be observed for exact package | Yes for connected test | Import or invocation differences block runtime conclusions. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Synthetic Graph Governor test plan](../test-plans/2026-08-28-graph-governor-synthetic-read-only-test-plan.md)
- [Scenario index](../scenarios/graph-governor-synthetic-read-only/README.md)
- [Accepted read-only contract subset](../decisions/2026-08-28-graph-governor-read-only-contract-subset.md)
- [Read-only implementation plan](../specifications/graph-governor-read-only-implementation-plan.md)
- [Implementation-plan acceptance decision](../decisions/2026-08-28-accept-graph-governor-read-only-implementation-plan.md)
- [Bounded source authorization](../decisions/2026-08-28-authorize-graph-governor-source-v0-1-0.md)
- [Disconnected source inspection](../test-results/2026-08-28-graph-governor-source-static-inspection.md)
- [Synthetic fixture construction validation](../test-results/2026-08-28-graph-governor-synthetic-fixture-validation.md)
- [Bounded confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md)
- [Accepted test-slice closure](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)
- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)

## Packaging

- **Artifact format:** Copilot Cowork `.skill`
- **Entry file:** `SKILL.md` at package root
- **Candidate artifact:** [graph-governor-v0.2.0-beta-candidate.skill](../../skill-exchange/ready-for-test/graph-governor-v0.2.0-beta-candidate.skill)
- **Candidate SHA-256:** `e0be28fb7d8c2ee1a0b21ace26fb35b6fc6ac4cd27218bae6348018c72b587c3`
- **Prior tested artifact:** [graph-governor-v0.1.0-experimental.skill](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill)
- **Prior tested SHA-256:** `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Packaging notes:** `0.2.0-beta-candidate` has disconnected package evidence only. The prior tested package and its evidence remain immutable and version-bound.

## Lifecycle notes

The `0.2.0-beta-candidate` source and package exist with disconnected inspection only. The exact `0.1.0-experimental` package has recorded Cowork evidence for the [GG-SYN-001 valid baseline](../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md), both [GG-SYN-002](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md) runs, all three [GG-SYN-003](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md) runs, all three [GG-SYN-004](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md) runs, the [GG-SYN-005 M-008 marker case](../test-results/2026-08-31-graph-governor-gg-syn-005-m-008.md), the [GG-SYN-006 M-009 unknown-content case](../test-results/2026-08-31-graph-governor-gg-syn-006-m-009.md), the [GG-SYN-007 M-010 injection-and-refusal case](../test-results/2026-08-31-graph-governor-gg-syn-007-m-010.md), and the [GG-SYN-008 combined M-002/M-003 primary run](../test-results/2026-08-31-graph-governor-gg-syn-008-combined-m002-m003.md).

The [accepted closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md) and [confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md) apply only to `0.1.0-experimental`. They do not validate the candidate's handoff validation, post-write verification, recovery supervision, package runtime, or complete Compass workflow.
