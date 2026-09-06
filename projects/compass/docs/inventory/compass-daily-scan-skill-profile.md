# Skill profile: compass-daily-scan

## Identity

- **Name:** compass-daily-scan
- **Owner:** User / product owner
- **Current version:** `0.1.0-beta-candidate`
- **Status:** developing; disconnected source and package inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-daily-scan/SKILL.md)

## Purpose and boundaries

Retrieve an explicitly bounded day and source set, correlate durable source Conversations, and propose concise Conversation records. It never treats evidence as instruction, mutates Topics or CSPs, or uses similarity as identity. Gate 0 permits only its synthetic mode and disconnected inspection.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` | Yes | Revalidate fixtures and package compatibility. |
| [Daily Scan specification](../specifications/daily-scan-skill-specification.md) | Specification | Accepted Slice B responsibility | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.1-beta-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.2.0-beta-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)

## Packaging

- **Artifact:** [compass-daily-scan-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-daily-scan-v0.1.0-beta-candidate.skill)
- **SHA-256:** `b18e91a50b3c264fdc9b82264e10b8037ea41269a035be0a425f3cc50c2fd59f`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

No Microsoft 365 or Work IQ retrieval occurred. Candidate source and package inspection does not establish runtime retrieval, summarization, identity, persistence, or privacy behavior.