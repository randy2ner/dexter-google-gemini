# Skill profile: compass-curator

## Identity

- **Name:** compass-curator
- **Owner:** User / product owner
- **Current version:** `0.6.0-production-test-candidate`
- **Status:** production-content source packaged and statically inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-curator/SKILL.md)

## Purpose and boundaries

Perform bounded read-only graph review using the graph and authorized current Work IQ as non-authoritative context, separate observations from interpretation, and route proposal-only recommendations to the owning Skill. Curator never edits the graph, invokes a writer, or reports recommendations as completed effects.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.8-production-evidence-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.7-hpi-narrative-baseline` / schema 2 | Yes | Revalidate fixture compatibility. |
| [Curator specification](../specifications/curator-skill-specification.md) | Specification | `0.6-production-test-responsibility` | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.7.0-production-test-candidate` | Yes | Routing changes require compatibility review. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)
- [Attention-state package inspection](../test-results/2026-09-06-compass-0-5-0-attention-state-package-inspection.md)
- [HPI narrative static validation](../test-results/2026-09-08-hpi-narrative-static-validation.md)
- [Production-content package-set validation](../test-results/2026-09-08-production-content-package-set-validation.md)

## Packaging

- **Artifact:** [compass-curator-v0.6.0-production-test-candidate.skill](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-curator-v0.6.0-production-test-candidate.skill)
- **SHA-256:** `12dce6ec55c914ca785863739cb452a96497ea1af03f35ca4d5d8afbc9623074`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Candidate source and package inspection does not establish runtime graph reading, recommendation quality, routing, or interaction behavior.