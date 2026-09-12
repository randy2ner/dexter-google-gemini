# Skill profile: graph-governor

## Identity

- **Name:** graph-governor
- **Owner:** User / product owner
- **Current version:** `0.8.0-production-test-candidate`
- **Status:** production-content source packaged and statically inspected; runtime untested
- **Source:** [Skill source](../../skills/graph-governor/SKILL.md)

## Purpose and boundaries

Graph Governor validates exact production change handoffs, verifies attempted effects, and preserves its bounded read-only health scan. It does not choose semantic meaning, originate graph changes, directly write files, retrieve Work IQ, automatically repair or roll back production state, or claim persistence behavior.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Compass charter](../charter/compass-vision-and-scope-charter.md) | Governance | 1.0 accepted | Yes | Charter change requires scope review. |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.8-production-evidence-baseline` | Yes | Responsibility revision requires scope review; implementation changes require affected scenario reruns. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.7-hpi-narrative-baseline` / schema 2 | Yes | Responsibility revision requires fixture review; implementation changes require affected scenario reruns. |
| [Graph Governor specification](../specifications/graph-governor-skill-specification.md) | Skill specification | `0.8-production-test-responsibility` | Yes | Responsibility changes require profile and scenario review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.7.0-production-test-candidate` | Yes | Handoff or outcome changes require compatibility review. |
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
- [Archival-success package inspection](../test-results/2026-09-06-compass-0-4-1-archival-success-package-inspection.md)
- [Archival-success fixture validation](../test-results/2026-09-06-compass-topic-archival-success-v2-fixture-validation.md)
- [Attention-state package inspection](../test-results/2026-09-06-compass-0-5-0-attention-state-package-inspection.md)
- [Attention-state fixture validation](../test-results/2026-09-06-compass-topic-attention-state-v2-fixture-validation.md)
- [Person data-minimization package inspection](../test-results/2026-09-06-compass-0-6-0-person-data-minimization-package-inspection.md)
- [HPI narrative static validation](../test-results/2026-09-08-hpi-narrative-static-validation.md)
- [Production-content package-set validation](../test-results/2026-09-08-production-content-package-set-validation.md)

## Packaging

- **Artifact format:** Copilot Cowork `.skill`
- **Entry file:** `SKILL.md` at package root
- **Candidate artifact:** [graph-governor-v0.8.0-production-test-candidate.skill](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/graph-governor-v0.8.0-production-test-candidate.skill)
- **Candidate SHA-256:** `c8b239c17fdd287d9340a0ea1bad884c5a556d11e8103e5db5dca673f3d0d3b8`
- **Prior tested artifact:** [graph-governor-v0.1.0-experimental.skill](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill)
- **Prior tested SHA-256:** `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Packaging notes:** `0.8.0-production-test-candidate` has deterministic package evidence only. Repository evaluation cases are excluded from the production package. Prior packages and their evidence remain immutable and version-bound.

## Lifecycle notes

The `0.8.0-production-test-candidate` source and package have disconnected package inspection only. The exact `0.1.0-experimental` package has recorded Cowork evidence for the [GG-SYN-001 valid baseline](../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md), both [GG-SYN-002](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md) runs, all three [GG-SYN-003](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md) runs, all three [GG-SYN-004](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md) runs, the [GG-SYN-005 M-008 marker case](../test-results/2026-08-31-graph-governor-gg-syn-005-m-008.md), the [GG-SYN-006 M-009 unknown-content case](../test-results/2026-08-31-graph-governor-gg-syn-006-m-009.md), the [GG-SYN-007 M-010 injection-and-refusal case](../test-results/2026-08-31-graph-governor-gg-syn-007-m-010.md), and the [GG-SYN-008 combined M-002/M-003 primary run](../test-results/2026-08-31-graph-governor-gg-syn-008-combined-m002-m003.md).

The [accepted closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md) and [confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md) apply only to `0.1.0-experimental`. They do not validate the candidate's handoff validation, post-write verification, recovery supervision, package runtime, or complete Compass workflow.
