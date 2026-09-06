# Skill profile: compass-installation-interview

## Identity

- **Name:** compass-installation-interview
- **Owner:** User / product owner
- **Current version:** `0.1.1-beta-candidate`
- **Status:** developing; focused approval-surface correction inspected; Cowork retest pending
- **Source:** [Skill source](../../skills/compass-installation-interview/SKILL.md)

## Purpose and boundaries

Conduct progressive setup, optionally request bounded Perspective Discovery, and propose an exact fictional-graph bootstrap. It writes only after explicit approval, Graph Governor validation, and separately authorized application. It does not access connected data or modify personal or production graphs under Gate 0.

## Dependencies

| Dependency | Type | Version/constraint | Required | Change impact |
| --- | --- | --- | --- | --- |
| [Shared contracts](../specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Reinspect source, package, and affected scenarios. |
| [Graph schema](../specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` | Yes | Revalidate fixtures and package compatibility. |
| [Installation specification](../specifications/installation-interview-skill-specification.md) | Specification | Accepted Slice B responsibility | Yes | Material change requires new candidate review. |
| [Lifecycle Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md) | Orchestration | `0.1-beta-candidate` | Yes | Handoff changes require compatibility review. |
| Graph Governor | Skill | `0.2.0-beta-candidate` | Yes for modification | Validation outcome controls application. |

## Consumers

- [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)

## Validation coverage

- [Gate 0 source and package inspection](../test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Lifecycle fixture construction validation](../test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)
- [Cancelled 0.1.0 Installation rehearsal](../test-results/2026-09-02-compass-installation-rehearsal-cancelled.md)
- [Version 0.1.1 source and package inspection](../test-results/2026-09-02-installation-v0-1-1-source-and-package-inspection.md)

## Packaging

- **Current artifact:** [compass-installation-interview-v0.1.1-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-installation-interview-v0.1.1-beta-candidate.skill)
- **Current SHA-256:** `e3f2363fa32c22cc02a3724ed92f9ea2da1a1cf842f23b80d3d14bd5566654ec`
- **Prior rehearsed artifact:** [compass-installation-interview-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-installation-interview-v0.1.0-beta-candidate.skill)
- **Prior SHA-256:** `7894c0b152692746d636b12a372c581aad2a90c148a79d0eb6807f7d506a1b7f`
- **Entry file:** `SKILL.md` at package root

## Lifecycle notes

Version `0.1.0-beta-candidate` produced a progressive setup interaction but its oversized approval card forced cancellation with zero verified effects. Version `0.1.1-beta-candidate` is the focused correction and has no Cowork runtime evidence yet.