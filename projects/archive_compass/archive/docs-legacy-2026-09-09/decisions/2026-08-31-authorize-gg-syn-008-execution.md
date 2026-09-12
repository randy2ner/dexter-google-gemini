# Decision: Authorize GG-SYN-008 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related finding:** [GG-SYN-007 M-010](../test-results/2026-08-31-graph-governor-gg-syn-007-m-010.md)

## Context

The exact tested Graph Governor package passed all authorized runs through GG-SYN-007. After that evidence was preserved, the user explicitly authorized GG-SYN-008. This final planned scenario tests whether one bounded scan reports both manifested defects in the combined M-002/M-003 fixture without inventing a defect in an unrelated valid object or making a whole-environment health claim.

## Decision

Authorize preparation and one primary execution of [GG-SYN-008 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-008-bounded-honest-report.md) using only isolated fixture `gg-syn-008-combined-m002-m003`.

The run must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating one isolated fictional root under the existing OneDrive `Compass-Test` laboratory area, verifying it before and after the run, selecting only that root through Cowork's native OneDrive picker, and submitting the exact scenario prompt once.

It does not authorize supplying mutation details or expected results to Cowork, prompt variation, retry, file-order variation, repair, normalization, rewriting, another fixture, parent or sibling access, search, recent files, Microsoft 365 retrieval, package replacement, Skill changes, Obsidian, real data, or any health claim beyond the selected root. The file-order variation remains unexecuted because no separately manifested order variant is registered.

## Alternatives considered

- **Name the two expected defects in the prompt:** Rejected because expected-answer hints would weaken evidence of complete reporting.
- **Treat the file-order variation as implicitly executable:** Rejected because no distinct, manifested fixture exists for that variation.
- **Infer overall Graph Governor readiness after this run:** Rejected because the result can support only the exact tested package, fixture, prompt, and observed environment.

## Consequences

- The combined M-002/M-003 fixture produces one immutable result and one post-run byte comparison.
- Missing either manifested defect, inventing an unrelated-object defect, widening the health claim, modifying content, or another unexpected result stops progression pending review.
- No retry, variation, new package, release, or broader lifecycle step is authorized.

## Follow-up

- Project Dexter: prepare and verify the authorized isolated root and register the exact no-hint prompt.
- User / product owner: run the combined fixture once and return the complete response.
- Project Dexter: verify and record the result before any confidence assessment or later decision.