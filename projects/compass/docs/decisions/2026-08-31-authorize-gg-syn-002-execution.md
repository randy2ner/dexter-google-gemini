# Decision: Authorize GG-SYN-002 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [GG-SYN-001 passed result](../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md)

## Context

The exact Graph Governor package passed GG-SYN-001 on the valid synthetic baseline. The next scenario tests whether the same imported package distinguishes malformed YAML from a missing required source Conversation identity without modifying or inferring content. The user explicitly authorized preparation and execution of GG-SYN-002 revision 1 using separate isolated M-001 and M-002 fictional fixtures and the documented read-only boundaries.

## Decision

Authorize preparation and one execution of each run defined by [GG-SYN-002 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md):

1. one clean Cowork run using only isolated fixture `gg-syn-002-m-001`; and
2. after its response and post-run integrity evidence are preserved, one separate clean Cowork run using only isolated fixture `gg-syn-002-m-002`.

Both runs must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating the two isolated fictional OneDrive test roots under `Compass-Test`, verifying them before and after use, selecting one root at a time through Cowork's native OneDrive picker, and submitting the applicable exact scenario prompt once.

It does not authorize selecting both fixtures together, supplying mutation descriptions or expected results to Cowork, prompt variation, retry, repair, normalization, modification, another fixture, parent or sibling access, search, recent files, Microsoft 365 evidence retrieval, package replacement, Graph Governor changes, Obsidian, or real data.

## Alternatives considered

- **Combine M-001 and M-002 in one run:** Rejected because independent defect classification and effect evidence would be confounded.
- **Tell Cowork the seeded defect:** Rejected because expected-answer hints would weaken behavioral evidence.
- **Authorize all remaining scenarios:** Rejected because each lifecycle expansion depends on preserved evidence from prior runs.

## Consequences

- M-001 and M-002 produce separate immutable results and post-run checks.
- M-002 must not begin until M-001 evidence is preserved.
- An unexpected or unsafe M-001 result stops progression to M-002 pending review.
- No GG-SYN-003 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify only the two authorized isolated fixtures and exact prompts.
- User / product owner: execute M-001 first and return its complete response.
- Project Dexter: verify and record M-001 before directing the authorized M-002 run.