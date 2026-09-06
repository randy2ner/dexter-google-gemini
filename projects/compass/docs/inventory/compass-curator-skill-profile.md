# Skill profile: compass-curator

## Identity

- **Name:** compass-curator
- **Owner:** User / product owner
- **Current version:** `0.1.0-beta-candidate`
- **Status:** developing; disconnected source and package inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-curator/SKILL.md)

## Purpose and boundaries

Perform bounded read-only graph review, separate observations from interpretation, and route proposal-only recommendations to the owning Skill. Curator never edits the graph, invokes a writer, or reports recommendations as completed effects.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` | Yes | Revalidate fixture compatibility. |
| [Curator specification](../specifications/curator-skill-specification.md) | Specification | Accepted Slice B responsibility | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.1-beta-candidate` | Yes | Routing changes require compatibility review. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)

## Packaging

- **Artifact:** [compass-curator-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-curator-v0.1.0-beta-candidate.skill)
- **SHA-256:** `96f14d27f034a2804424b31b4bbf8b6e9b847bdcf1d1425dc2f3dbbd4aadf49e`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Candidate source and package inspection does not establish runtime graph reading, recommendation quality, routing, or interaction behavior.