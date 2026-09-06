# Decision: Authorize GG-SYN-003 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [GG-SYN-002 M-001 result](../test-results/2026-08-31-graph-governor-gg-syn-002-m-001.md) and [M-002 result](../test-results/2026-08-31-graph-governor-gg-syn-002-m-002.md)

## Context

The exact tested Graph Governor package passed GG-SYN-001 and both GG-SYN-002 runs. The next scenario tests whether it distinguishes three forward-relationship defects without inventing reverse relationships or modifying any graph. The user authorized GG-SYN-003 and requested preparation of the test files and next-step instructions.

## Decision

Authorize preparation and one execution of each run defined by [GG-SYN-003 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md):

1. one clean Cowork run using only isolated fixture `gg-syn-003-m-003`;
2. after M-003 evidence is preserved and reviewed, one separate clean run using only `gg-syn-003-m-004`; and
3. after M-004 evidence is preserved and reviewed, one separate clean run using only `gg-syn-003-m-005`.

All runs must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating three isolated fictional roots under the existing OneDrive `Compass-Test` laboratory area, verifying each before and after its run, selecting one root at a time through Cowork's native OneDrive picker, and submitting the exact common scenario prompt once per root.

It does not authorize selecting multiple roots together, supplying mutation descriptions or expected results to Cowork, prompt variation, retry, repair, normalization, modification, another fixture, parent or sibling access, search, recent files, Microsoft 365 retrieval, package replacement, Skill changes, Obsidian, or real data.

## Alternatives considered

- **Combine all relationship mutations in one root:** Rejected because defect classification and effect evidence would be confounded.
- **Tell Cowork each seeded relationship defect:** Rejected because expected-answer hints would weaken behavioral evidence.
- **Authorize later scenarios simultaneously:** Rejected because lifecycle expansion remains evidence-gated.

## Consequences

- M-003, M-004, and M-005 produce separate immutable results and post-run checks.
- Each later run waits for preservation and review of the preceding result.
- An unsafe or unexpected result stops progression pending review.
- No GG-SYN-004 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify only the three authorized isolated roots and register the exact no-hint prompt.
- User / product owner: run M-003 first and return its complete response.
- Project Dexter: verify and record each run before directing the next authorized run.