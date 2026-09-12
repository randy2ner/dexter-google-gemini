# Compass HPI narrative candidate package set

## Document control

- **Status:** source, fixture, and packages statically validated; behavioral execution unrun
- **Version:** `fresh-installation-hpi-narrative-candidate-2026-09-08`
- **Owner:** User / product owner
- **Decision:** [HPI Topic narrative and review metadata](../decisions/2026-09-08-accept-hpi-topic-narrative-and-review-metadata.md)
- **Test plan:** [HPI Topic narrative and review metadata](../test-plans/2026-09-08-hpi-topic-narrative-and-review-test-plan.md)
- **Package-set evidence:** [Fresh installation package-set validation](../test-results/2026-09-08-fresh-installation-package-set-validation.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.6.0-hpi-narrative-compatible-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-fresh-installation/compass-installation-interview-v0.6.0-hpi-narrative-compatible-candidate.skill) | 8,216 bytes | `53fed88327382393d86a1e79c99817e5f38ff1cf6ad47e6a805ac02fa5be1a9a` |
| Daily Scan | `0.6.0-hpi-narrative-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-fresh-installation/compass-daily-scan-v0.6.0-hpi-narrative-candidate.skill) | 6,027 bytes | `51648ba315d3f6ce5c5790ba1c4d882b727f579d073c37567a2af1fc38db9f4a` |
| Tracking Topic Interview | `0.6.0-hpi-narrative-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-fresh-installation/compass-tracking-topic-interview-v0.6.0-hpi-narrative-candidate.skill) | 6,470 bytes | `c29f2b7cfc90f2e762551697a5d59acbe8a4c8325039ad014cf7485bd0302653` |
| Curator | `0.5.0-hpi-narrative-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-fresh-installation/compass-curator-v0.5.0-hpi-narrative-candidate.skill) | 5,521 bytes | `25851b0684577b8bd6369a728fc676da4303b18fb63e83a9513a9b401f693fb7` |
| Graph Governor | `0.7.0-hpi-narrative-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-fresh-installation/graph-governor-v0.7.0-hpi-narrative-candidate.skill) | 15,137 bytes | `d8eb9798481aa95052280ccb1e9fe17102fc5b696a61f6821547289897f67443` |

## Compatibility boundary

Installation Interview advances only for compatibility with the current contracts, orchestration, and Governor handoff. It still creates foundational objects before optional narrative metadata and routes any offered narrative or review-metadata intent to Tracking Topic Interview after verified setup.

Perspective Discovery is deliberately excluded from the recommended fresh-installation import set. Its latest `0.1.2-experimental` package is optional and has not completed static package inspection or runtime evaluation; excluding it removes a known accessibility and confidence variable from the first installation experience.

The set targets object schema version 2 and Shared Contracts/Graph Schema `0.7-hpi-narrative-baseline`. Lifecycle orchestration source is `0.6.0-hpi-narrative-candidate` but is not packaged as a Skill.

## Package boundary

The five import copies are collected under `ready-for-test/2026-09-08-fresh-installation/` and are byte-identical to their independently verified source archives. Each archive contains root `SKILL.md` and every regular file under its source `references/` directory. Members are sorted safe relative paths, DEFLATE-compressed, mode `0644`, timestamped `2026-09-04 00:00:00`, and byte-equal to source. Independent rebuilds were byte-identical. Prior artifacts remain unchanged.

## Use boundary

The packages are ready only for the planned mediated test. Static validation does not establish Cowork import, retrieval, conversational quality, approval behavior, graph writes, persistence, Curator output, Governor runtime decisions, or connected-system effects.
