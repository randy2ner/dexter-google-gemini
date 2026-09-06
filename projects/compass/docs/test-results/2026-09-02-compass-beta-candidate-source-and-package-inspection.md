# Test results: Compass beta-candidate source and package inspection

## Document control

- **Status:** complete
- **Version:** 1.0
- **Owner:** User / product owner
- **Tested on:** 2026-09-02
- **Last updated:** 2026-09-02
- **Authority:** Accepted Slice D disconnected construction only

## Scope

Inspect the exact five editable Skill sources and deterministic packages selected by the [Slice D construction plan](../specifications/2026-09-02-slice-d-beta-candidate-construction-plan.md). No Skill was imported, invoked, or connected to Cowork, Microsoft 365, Work IQ, OneDrive, or a personal graph.

## Direct observations

1. Each source has root `SKILL.md` YAML delimiters, the expected lowercase name, its candidate version in the body, `0.3-beta-baseline`, and `compass-work-memory-lifecycle` `0.1-beta-candidate`.
2. Installation Interview, Daily Scan, and Tracking Topic Interview each declare all ten accepted handoff fields: `requestId`, `initiatingSkill`, `authoritySource`, `operationType`, `targetObjects`, `expectedEffects`, `sourceState`, `evidenceReferences`, `approvalReference`, and `correlationId`.
3. Each mutating Skill couples durable change with the Daily Log, requires Graph Governor pre-validation and post-verification, and limits Gate 0 graph work to a disposable synthetic graph.
4. Daily Scan prohibits Topic/CSP mutation and similarity-based identity. Tracking Topic Interview limits status to `active` or `archived`, preserves surviving identity, and prohibits Topic deletion. Curator declares no mutation path. Graph Governor preserves bounded health scanning and adds pre-validation, post-verification, and synthetic recovery supervision without direct write or semantic-choice authority.
5. All referenced source files exist. No package contains an absolute path, traversal, backslash path, duplicate, directory entry, unexpected member, or binary member.
6. Every archived member is byte-equal to its current source. An independent in-memory rebuild using sorted POSIX member names, timestamp `1980-01-01T00:00:00`, mode `0644`, UTF-8 names, and DEFLATE produced byte-identical archives.

## Package observations

| Package | Members | Bytes | SHA-256 | Result |
| --- | ---: | ---: | --- | --- |
| [compass-installation-interview-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-installation-interview-v0.1.0-beta-candidate.skill) | 2 | 4,010 | `7894c0b152692746d636b12a372c581aad2a90c148a79d0eb6807f7d506a1b7f` | Pass |
| [compass-daily-scan-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-daily-scan-v0.1.0-beta-candidate.skill) | 2 | 3,999 | `b18e91a50b3c264fdc9b82264e10b8037ea41269a035be0a425f3cc50c2fd59f` | Pass |
| [compass-tracking-topic-interview-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.1.0-beta-candidate.skill) | 2 | 3,685 | `9e9b84884f78e3abca185a957bf7fbe43da1ebe688c3d5a315cd68f46ad221d7` | Pass |
| [compass-curator-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-curator-v0.1.0-beta-candidate.skill) | 2 | 3,483 | `96f14d27f034a2804424b31b4bbf8b6e9b847bdcf1d1425dc2f3dbbd4aadf49e` | Pass |
| [graph-governor-v0.2.0-beta-candidate.skill](../../skill-exchange/ready-for-test/graph-governor-v0.2.0-beta-candidate.skill) | 4 | 12,188 | `e0be28fb7d8c2ee1a0b21ace26fb35b6fc6ac4cd27218bae6348018c72b587c3` | Pass |

## Interpretation

The five exact source/package pairs pass the disconnected construction checks required before Gate 0 compatibility review. This supports package identity and static contract consistency only.

## Limitations

- No Cowork import, invocation, card rendering, typed fallback, cancellation, retrieval, graph application, persistence, conflict, or recovery behavior was observed.
- The prior Graph Governor `0.1.0-experimental` evidence does not transfer to `0.2.0-beta-candidate`.
- Package presence in `ready-for-test/` is not beta, deployment, release, or Gate 1 authorization.