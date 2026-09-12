# Skill profile: compass-daily-scan

## Identity

- **Name:** compass-daily-scan
- **Owner:** User / product owner
- **Current version:** `0.7.0-production-test-candidate`
- **Status:** production-content source packaged and statically inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-daily-scan/SKILL.md)

## Purpose and boundaries

Retrieve all relevant authorized Work IQ for the selected period, purpose, and work scope, correlate durable Conversations, confirm qualifying participants, and prepare minimized optional Topic-narrative handoffs without writing Topic meaning. It uses continuation where available and discloses incomplete coverage rather than substituting sample data.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.8-production-evidence-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.7-hpi-narrative-baseline` / schema 2 | Yes | Revalidate fixtures and package compatibility. |
| [Daily Scan specification](../specifications/daily-scan-skill-specification.md) | Specification | `0.7-production-test-responsibility` | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.7.0-production-test-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.8.0-production-test-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)
- [Attention-state package inspection](../test-results/2026-09-06-compass-0-5-0-attention-state-package-inspection.md)
- [Person data-minimization package inspection](../test-results/2026-09-06-compass-0-6-0-person-data-minimization-package-inspection.md)
- [HPI narrative static validation](../test-results/2026-09-08-hpi-narrative-static-validation.md)
- [Production-content package-set validation](../test-results/2026-09-08-production-content-package-set-validation.md)

## Packaging

- **Artifact:** [compass-daily-scan-v0.7.0-production-test-candidate.skill](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-daily-scan-v0.7.0-production-test-candidate.skill)
- **SHA-256:** `2648d308555bd7b633f6613ef1407a52dbd17d932df0da5e4a079794285b319e`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

The current candidate has deterministic package evidence only. It does not establish runtime retrieval, participant confirmation, Topic funneling, persistence, or privacy behavior.