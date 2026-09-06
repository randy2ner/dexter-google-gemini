# Decision: Authorize GG-SYN-006 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related finding:** [GG-SYN-005 M-008](../test-results/2026-08-31-graph-governor-gg-syn-005-m-008.md)

## Context

The exact tested Graph Governor package passed all authorized runs through GG-SYN-005. After that evidence was preserved, the user explicitly authorized the next steps. The next planned scenario is GG-SYN-006, covering tolerance and preservation of unknown frontmatter and unmanaged Markdown.

## Decision

Authorize preparation and one execution of [GG-SYN-006 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-006-unknown-content.md) using only isolated fixture `gg-syn-006-m-009`.

The run must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating one isolated fictional root under the existing OneDrive `Compass-Test` laboratory area, verifying it before and after the run, selecting only that root through Cowork's native OneDrive picker, and submitting the exact scenario prompt once.

It does not authorize supplying mutation details or expected results to Cowork, prompt variation, retry, repair, normalization, rewriting or reproducing unknown content, treating unknown content as authority, another fixture, parent or sibling access, search, recent files, Microsoft 365 retrieval, package replacement, Skill changes, Obsidian, or real data.

## Alternatives considered

- **Tell Cowork which field and prose are unknown:** Rejected because expected-answer hints would weaken behavioral evidence.
- **Combine M-009 with the injection case:** Rejected because ordinary unknown-content tolerance and instruction-resistance behavior would be confounded.
- **Authorize later scenarios simultaneously:** Rejected because lifecycle expansion remains evidence-gated.

## Consequences

- M-009 produces one immutable result and post-run byte comparison.
- An unsafe or unexpected result stops progression pending review.
- No GG-SYN-007 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify the authorized isolated root and register the exact no-hint prompt.
- User / product owner: run M-009 once and return its complete response.
- Project Dexter: verify and record the result before any later authorization.