# Decision: Authorize GG-SYN-005 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [GG-SYN-004 valid baseline](../test-results/2026-08-31-graph-governor-gg-syn-004-valid-baseline.md), [M-006](../test-results/2026-08-31-graph-governor-gg-syn-004-m-006.md), and [M-007](../test-results/2026-08-31-graph-governor-gg-syn-004-m-007.md)

## Context

The exact tested Graph Governor package passed all authorized runs through GG-SYN-004. After that evidence was preserved, the user explicitly authorized the next steps. The next planned scenario is GG-SYN-005, covering bounded Daily Log managed-marker integrity.

## Decision

Authorize preparation and one execution of [GG-SYN-005 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-005-daily-log-markers.md) using only isolated fixture `gg-syn-005-m-008`.

The run must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating one isolated fictional root under the existing OneDrive `Compass-Test` laboratory area, verifying it before and after the run, selecting only that root through Cowork's native OneDrive picker, and submitting the exact scenario prompt once.

It does not authorize supplying mutation details or expected results to Cowork, prompt variation, retry, repair, marker normalization or replacement, modification of managed or user-authored content, another fixture, parent or sibling access, search, recent files, Microsoft 365 retrieval, package replacement, Skill changes, Obsidian, or real data.

## Alternatives considered

- **Tell Cowork which marker defect is seeded:** Rejected because an expected-answer hint would weaken behavioral evidence.
- **Authorize later marker variations:** Rejected because missing, nested, and reversed marker cases do not exist in this scenario revision.
- **Combine GG-SYN-005 with a later mutation:** Rejected because marker classification and no-rewrite evidence would be confounded.

## Consequences

- M-008 produces one immutable result and post-run byte comparison.
- An unsafe or unexpected result stops progression pending review.
- No GG-SYN-006 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify the authorized isolated root and register the exact no-hint prompt.
- User / product owner: run M-008 once and return its complete response.
- Project Dexter: verify and record the result before any later authorization.