# Skill profile: compass-tracking-topic-interview

## Identity

- **Name:** compass-tracking-topic-interview
- **Owner:** User / product owner
- **Current version:** `0.7.0-production-test-candidate`
- **Status:** production-content source packaged and statically inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-tracking-topic-interview/SKILL.md)

## Purpose and boundaries

Translate exact user intent and, when authorized, all relevant Work IQ for the Topic purpose into reviewed narrative, metadata, participant, lifecycle, and canonical relationship proposals. It preserves history and exclusions, discloses coverage gaps, and never substitutes sample data.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.8-production-evidence-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.7-hpi-narrative-baseline` / schema 2 | Yes | Revalidate fixtures and package compatibility. |
| [Tracking Topic specification](../specifications/tracking-topic-interview-skill-specification.md) | Specification | `0.7-production-test-responsibility` | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.7.0-production-test-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.8.0-production-test-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

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

- **Artifact:** [compass-tracking-topic-interview-v0.7.0-production-test-candidate.skill](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-tracking-topic-interview-v0.7.0-production-test-candidate.skill)
- **SHA-256:** `6f3cfc0ca3b27debea496025c91acf212c02a5601078f4ebf5d212c2c3cba55b`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Candidate source and package inspection does not establish conversational usability, application, merge correctness, persistence, or recovery at runtime.