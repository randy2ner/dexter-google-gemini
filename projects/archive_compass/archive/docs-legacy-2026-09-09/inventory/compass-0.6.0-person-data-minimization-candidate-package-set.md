# Compass 0.6.0 Person data-minimization candidate package set

## Document control

- **Status:** source and packages statically validated; behavioral execution not authorized
- **Version:** 0.6.0-person-data-minimization-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-06
- **Decision basis:** [Accepted Person UPN removal decision](../decisions/2026-09-06-stop-collecting-person-upn.md)
- **Test plan:** [Person UPN removal test plan](../test-plans/2026-09-06-person-upn-removal-test-plan.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.5.0-person-data-minimization-candidate` | [package](../../skill-exchange/ready-for-test/compass-installation-interview-v0.5.0-person-data-minimization-candidate.skill) | 7,989 bytes | `28d3078a0d78574e3c002d0a39c5f5b0e47a5c1e5beeb1ff73e5f66a5d054091` |
| Daily Scan | `0.5.0-person-data-minimization-candidate` | [package](../../skill-exchange/ready-for-test/compass-daily-scan-v0.5.0-person-data-minimization-candidate.skill) | 5,357 bytes | `1853e3c4abf0bb44b8c057da816cc5aa6d60f1cc0f0c8b233d0b819d20797aed` |
| Tracking Topic Interview | `0.5.0-person-data-minimization-candidate` | [package](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.5.0-person-data-minimization-candidate.skill) | 5,745 bytes | `a5aa03d60efdd701c33ae6114dba61e92ceac448f8bb32d399133110eb814a4b` |
| Curator | `0.4.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/compass-curator-v0.4.0-attention-state-candidate.skill) | 3,932 bytes | `8c14d0b4daf99c6452f9e8189451abfc6878fd06bb977671f6e694bf8b936f9a` |
| Graph Governor | `0.6.0-person-data-minimization-candidate` | [package](../../skill-exchange/ready-for-test/graph-governor-v0.6.0-person-data-minimization-candidate.skill) | 13,763 bytes | `762154e199e648692c00c735ebc91e8a79ca21e9b49641de175e4de87c29ef15` |

## Compatibility boundary

Installation Interview, Daily Scan, and Tracking Topic Interview advance because they can propose Person creation or binding. Graph Governor advances because it validates those effects. Curator creates no Person data, so its exact prior attention-state package remains compatible and byte-identical.

The package set targets object schema version 2 and the current Shared Contracts/Graph Schema `0.6-person-data-minimization-baseline`. The unchanged Curator package still declares the prior `0.5-attention-state-baseline`; it remains compatible because Curator does not create, bind, or modify Person data. The preserved Graph Governor schema-version-1 read-only reference remains historical and does not authorize current UPN collection.

## Package boundary

Each changed package contains current `SKILL.md` and every source-local reference file. Entries are sorted safe relative paths, DEFLATE-compressed, mode `0644`, and timestamped `2026-09-04 00:00:00`. Independent rebuilds were byte-identical and every entry matched source bytes. Prior package files remained unchanged.

## Use boundary

Static inspection does not establish Cowork import, prompting, retrieval minimization, validation behavior, state changes, persistence, cleanup, connected access, migration, or runtime correctness. This set does not authorize mutation of schema-version-1, personal, or connected graphs.