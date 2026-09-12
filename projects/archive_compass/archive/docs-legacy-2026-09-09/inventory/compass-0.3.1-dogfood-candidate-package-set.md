# Compass 0.3.1 dogfood candidate package set

## Document control

- **Status:** superseded after blocked clean first run by `0.3.2-dogfood-candidate`
- **Version:** 0.3.1-dogfood-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-04
- **Decision:** [Authorize complete dogfood candidate](../decisions/2026-09-04-authorize-complete-dogfood-candidate.md)

## Exact packages

| Skill | Version | Package | SHA-256 |
| --- | --- | --- | --- |
| Installation Interview | `0.2.1-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-installation-interview-v0.2.1-dogfood-candidate.skill` | `7c419594e0f01542bfc0f86909765e46583f9025ac8a0697d0d2e0433c30b1e5` |
| Daily Scan | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-daily-scan-v0.2.0-dogfood-candidate.skill` | `006a08a1877eef9410edb547c13b2ebc4f4ac0d6a244a23addcff54918c6ff20` |
| Tracking Topic Interview | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.2.0-dogfood-candidate.skill` | `b5fb5cd5ecb6cda4be9628369f87112b7f6e5c03df9b51304a3ef2344feb3ad0` |
| Curator | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-curator-v0.2.0-dogfood-candidate.skill` | `ba6a2f0610b0c2e108aed7f2cfadcf44244d76a85fc2649d4bb480a0a317b8ab` |
| Graph Governor | `0.3.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/graph-governor-v0.3.0-dogfood-candidate.skill` | `d5271a1fb9b14205f4eefb9d54e71bc5dc5a40967cfca53c1d919242c6201b4f` |

## First-run acceptance

Use the packages together in a new Cowork task with no graph or fixture attached. The first prompt is `Help me install Compass`. Compass owns the conversational create-or-use-folder choice, foundational interview, bootstrap, and transition to ordinary use.

The coordinating definition is `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`; Shared Contracts and Graph Schema remain `0.3-beta-baseline`.

The first run exposed protected-input ingestion and write-ordering defects in Installation `0.2.1`. Preserve this exact package set and its result; do not use it for the next dogfood run.