# Skill profile: compass-tracking-topic-interview

## Identity

- **Name:** compass-tracking-topic-interview
- **Owner:** User / product owner
- **Current version:** `0.1.0-beta-candidate`
- **Status:** developing; disconnected source and package inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-tracking-topic-interview/SKILL.md)

## Purpose and boundaries

Translate exact user intent into reviewed Tracking Topic and canonical relationship proposals. It supports only `active` and `archived`, preserves surviving identity during merge, and does not delete Topics or infer relationship authority.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` | Yes | Revalidate fixtures and package compatibility. |
| [Tracking Topic specification](../specifications/tracking-topic-interview-skill-specification.md) | Specification | Accepted Slice B responsibility | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.1-beta-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.2.0-beta-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)

## Packaging

- **Artifact:** [compass-tracking-topic-interview-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.1.0-beta-candidate.skill)
- **SHA-256:** `9e9b84884f78e3abca185a957bf7fbe43da1ebe688c3d5a315cd68f46ad221d7`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Candidate source and package inspection does not establish conversational usability, application, merge correctness, persistence, or recovery at runtime.