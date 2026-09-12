# Compass 0.5.0 attention-state candidate package set

## Document control

- **Status:** source, packages, and fixture statically validated; behavioral execution not authorized
- **Version:** 0.5.0-attention-state-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-06
- **Decision basis:** [Accepted Topic attention-state decision](../decisions/2026-09-06-add-topic-attention-state.md)
- **Test plan:** [Topic attention-state test plan](../test-plans/2026-09-06-topic-attention-state-test-plan.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.4.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/compass-installation-interview-v0.4.0-attention-state-candidate.skill) | 7,791 bytes | `26edb2814dfdf5bacda414174e3250852c1e8ab94e05362cd09229aa87541d5e` |
| Daily Scan | `0.4.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/compass-daily-scan-v0.4.0-attention-state-candidate.skill) | 5,150 bytes | `1ea4e4df421dc1cca0b68c99556b6309493e308aa855ade06ae0da5bb46a6dca` |
| Tracking Topic Interview | `0.4.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.4.0-attention-state-candidate.skill) | 5,538 bytes | `e86389fd5de080985d862624a5a8baa9898384d528271ace1ead49d5a77b2f50` |
| Curator | `0.4.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/compass-curator-v0.4.0-attention-state-candidate.skill) | 3,932 bytes | `8c14d0b4daf99c6452f9e8189451abfc6878fd06bb977671f6e694bf8b936f9a` |
| Graph Governor | `0.5.0-attention-state-candidate` | [package](../../skill-exchange/ready-for-test/graph-governor-v0.5.0-attention-state-candidate.skill) | 13,539 bytes | `135378988643603bbe5b1fee316ea8753ee860cfd2ba68a9a0e9c4fdbf8ce38c` |

## Package boundary

Each package contains current `SKILL.md` and every source-local reference file. Entries are sorted safe relative paths, DEFLATE-compressed, mode `0644`, and timestamped `2026-09-04 00:00:00`. Independent rebuilds were byte-identical, and prior package bytes were unchanged.

All five packages share object schema version 2 and Shared Contracts/Graph Schema `0.5-attention-state-baseline`.

## Use boundary

Static inspection does not establish Cowork import, prompting, state changes, non-inference, persistence, connected access, migration, or runtime correctness. Do not use these packages to mutate a schema-version-1 or personal graph without separately authorized migration and runtime validation.