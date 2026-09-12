# Skill profile: compass-installation-interview

## Identity

- **Name:** compass-installation-interview
- **Owner:** User / product owner
- **Current version:** `0.7.0-production-test-candidate`
- **Status:** production-content source packaged and statically inspected; runtime untested
- **Source:** [Skill source](../../skills/compass-installation-interview/SKILL.md)

## Purpose and boundaries

Conduct progressive setup from direct answers and all relevant authorized Work IQ, then propose a schema-v2 foundation with complete-name People and reviewed initial Topics. It never substitutes sample data or imposes arbitrary result caps, and writes only after explicit approval, Graph Governor validation, and separately authorized application.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.8-production-evidence-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.7-hpi-narrative-baseline` / schema 2 | Yes | Revalidate fixtures and package compatibility. |
| [Installation specification](../specifications/installation-interview-skill-specification.md) | Specification | `0.7-production-test-responsibility` | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.7.0-production-test-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.8.0-production-test-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)
- [Cancelled 0.1.0 Installation rehearsal](../test-results/2026-09-02-compass-installation-rehearsal-cancelled.md)
- [Version 0.1.1 source and package inspection](../test-results/2026-09-02-installation-v0-1-1-source-and-package-inspection.md)
- [Attention-state package inspection](../test-results/2026-09-06-compass-0-5-0-attention-state-package-inspection.md)
- [Person data-minimization package inspection](../test-results/2026-09-06-compass-0-6-0-person-data-minimization-package-inspection.md)
- [HPI narrative static validation](../test-results/2026-09-08-hpi-narrative-static-validation.md)
- [Fresh installation package-set validation](../test-results/2026-09-08-fresh-installation-package-set-validation.md)
- [Production-content package-set validation](../test-results/2026-09-08-production-content-package-set-validation.md)

## Packaging

- **Current artifact:** [compass-installation-interview-v0.7.0-production-test-candidate.skill](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-installation-interview-v0.7.0-production-test-candidate.skill)
- **Current SHA-256:** `1ffe18ae79c24739f99d0df7e6ea0e29e86b9bf3a322f1c2a3c64778897ce509`
- **Prior rehearsed artifact:** `compass-installation-interview-v0.1.0-beta-candidate.skill`; historical evidence retained, package not present in the current exchange
- **Prior SHA-256:** `7894c0b152692746d636b12a372c581aad2a90c148a79d0eb6807f7d506a1b7f`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Prior runtime evidence remains version-bound. Version `0.7.0-production-test-candidate` has deterministic package evidence only and no Cowork runtime evidence.