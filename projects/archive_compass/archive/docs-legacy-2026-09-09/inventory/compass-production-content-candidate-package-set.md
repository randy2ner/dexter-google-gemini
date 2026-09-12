# Compass production-content candidate package set

## Document control

- **Status:** production shaping baseline and design input; source and packages statically validated; Cowork runtime unrun
- **Version:** `production-content-test-candidate-2026-09-08`
- **Owner:** User / product owner
- **Decision:** [Use production content and native Work IQ capability](../decisions/2026-09-08-use-production-content-and-native-work-iq-capability.md)
- **Milestone:** [Transition from synthetic testing to production release testing](../decisions/2026-09-08-declare-production-release-testing-milestone.md)
- **Sequencing:** [Artifact-first production shaping](../decisions/2026-09-08-adopt-artifact-first-production-shaping.md) may use these packages but does not presume they are the final release-test set
- **Test plan:** [Production content and native Work IQ](../test-plans/2026-09-08-production-content-and-native-work-iq-test-plan.md)
- **Package evidence:** [Production-content package-set validation](../test-results/2026-09-08-production-content-package-set-validation.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.7.0-production-test-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-installation-interview-v0.7.0-production-test-candidate.skill) | 8,648 bytes | `1ffe18ae79c24739f99d0df7e6ea0e29e86b9bf3a322f1c2a3c64778897ce509` |
| Daily Scan | `0.7.0-production-test-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-daily-scan-v0.7.0-production-test-candidate.skill) | 6,322 bytes | `2648d308555bd7b633f6613ef1407a52dbd17d932df0da5e4a079794285b319e` |
| Tracking Topic Interview | `0.7.0-production-test-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-tracking-topic-interview-v0.7.0-production-test-candidate.skill) | 6,895 bytes | `6f3cfc0ca3b27debea496025c91acf212c02a5601078f4ebf5d212c2c3cba55b` |
| Curator | `0.6.0-production-test-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/compass-curator-v0.6.0-production-test-candidate.skill) | 4,922 bytes | `12dce6ec55c914ca785863739cb452a96497ea1af03f35ca4d5d8afbc9623074` |
| Graph Governor | `0.8.0-production-test-candidate` | [package](../../skill-exchange/ready-for-test/2026-09-08-production-content-test/graph-governor-v0.8.0-production-test-candidate.skill) | 12,506 bytes | `c8b239c17fdd287d9340a0ea1bad884c5a556d11e8103e5db5dca673f3d0d3b8` |

## Contract family

The five Skills use Shared Contracts `0.8-production-evidence-baseline`, Graph Schema `0.7-hpi-narrative-baseline` / object schema version 2, and lifecycle orchestration `0.7.0-production-test-candidate`.

Installation Interview, Daily Scan, Tracking Topic Interview, and Curator may use all relevant Work IQ capabilities Cowork exposes within the user-approved purpose and scope. Their instructions prohibit arbitrary numeric limits and sample, fixture, fictional, or synthetic substitution for unavailable production evidence. They require continuation or pagination attempts where exposed and disclosure of incomplete coverage.

Graph Governor deliberately retrieves no Work IQ and judges no narrative truth. This is responsibility separation: evidence-facing Skills propose user-reviewed meaning; Governor validates authority, structure, identity, preservation, and effects.

## Package boundary

The import directory contains exactly five `.skill` files. Each archive has sorted safe relative paths, DEFLATE compression, Unix mode `0644`, fixed timestamp `2026-09-04 00:00:00`, and exact selected source bytes. Curator and Governor repository evaluation cases are excluded. Independent rebuilds were byte-identical.

## Use boundary

This exact set is available for artifact-first production shaping with real production content, not sample-data testing. It may be used, bypassed, redirected, or supplemented by manual editing to discover the target result. Static validation establishes instruction and package properties only. Shaping outcomes do not prove these packages can reproduce the finished graph, and the set is not presumed to be the final release candidate. Production graph content may later support separately authorized evaluation or training preparation, but this package performs no automatic export or model-training submission.
