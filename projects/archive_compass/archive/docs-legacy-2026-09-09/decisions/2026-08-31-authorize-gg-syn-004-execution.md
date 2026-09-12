# Decision: Authorize GG-SYN-004 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [GG-SYN-003 M-003](../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md), [M-004](../test-results/2026-08-31-graph-governor-gg-syn-003-m-004.md), and [M-005](../test-results/2026-08-31-graph-governor-gg-syn-003-m-005.md)

## Context

The exact tested Graph Governor package passed GG-SYN-001, both GG-SYN-002 runs, and all three GG-SYN-003 relationship runs. After GG-SYN-003 evidence was preserved, the user directed Project Dexter to proceed to the next steps. The next planned scenario is GG-SYN-004, covering bounded graph-configuration checks.

## Decision

Authorize preparation and one execution of each run defined by [GG-SYN-004 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md):

1. one clean Cowork run using only isolated fixture `gg-syn-004-valid-baseline`;
2. after baseline evidence is preserved and reviewed, one separate clean run using only `gg-syn-004-m-006`; and
3. after M-006 evidence is preserved and reviewed, one separate clean run using only `gg-syn-004-m-007`.

All runs must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating three isolated fictional roots under the existing OneDrive `Compass-Test` laboratory area, verifying each before and after its run, selecting one root at a time through Cowork's native OneDrive picker, and submitting the exact common scenario prompt once per root.

It does not authorize selecting multiple roots together, supplying mutation descriptions or expected results to Cowork, prompt variation, retry, repair, normalization, timezone mapping or replacement, provisional Microsoft 365 retrieval, another fixture, parent or sibling access, search, recent files, package replacement, Skill changes, Obsidian, or real data.

## Alternatives considered

- **Rely only on the prior GG-SYN-001 baseline:** Rejected because GG-SYN-004 requires configuration-focused evidence under one common prompt across all three isolated roots.
- **Combine M-006 and M-007:** Rejected because graph-identity and timezone classification would be confounded.
- **Tell Cowork which defect each root contains:** Rejected because expected-answer hints would weaken behavioral evidence.

## Consequences

- The valid baseline, M-006, and M-007 produce separate immutable results and post-run checks.
- Each later run waits for preservation and review of the preceding result.
- An unsafe or unexpected result stops progression pending review.
- No GG-SYN-005 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify the three authorized isolated roots and register the exact no-hint prompt.
- User / product owner: run the GG-SYN-004 valid baseline first and return its complete response.
- Project Dexter: verify and record each run before directing the next authorized run.