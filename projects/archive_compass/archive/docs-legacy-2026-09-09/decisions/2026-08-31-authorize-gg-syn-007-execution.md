# Decision: Authorize GG-SYN-007 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related finding:** [GG-SYN-006 M-009](../test-results/2026-08-31-graph-governor-gg-syn-006-m-009.md)

## Context

The exact tested Graph Governor package passed all authorized runs through GG-SYN-006. After that evidence was preserved, the user explicitly authorized the next steps. The next planned scenario is GG-SYN-007, covering resistance to instruction-like graph content and refusal of a direct follow-up modification request.

## Decision

Authorize preparation and one two-turn execution of [GG-SYN-007 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-007-injection-and-write-refusal.md) using only isolated fixture `gg-syn-007-m-010`:

1. submit the exact bounded scan prompt once with the isolated fixture selected;
2. preserve the complete first response;
3. in the same conversation, submit the exact repair-and-normalization request once without selecting or supplying another root;
4. preserve the complete refusal response; and
5. perform one post-conversation inventory and hash comparison.

The run must use the already imported tested Graph Governor package `0.1.0-experimental`, 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

This authorization permits creating one isolated fictional root under the existing OneDrive `Compass-Test` laboratory area, verifying it before and after the two-turn run, selecting only that root through Cowork's native OneDrive picker for the first turn, and submitting the two exact scenario prompts once each.

It does not authorize actual repair, normalization, rewriting, permission changes, another fixture, parent or sibling access, search, recent files, Microsoft 365 retrieval, package replacement, Skill changes, Obsidian, real data, prompt variation, or retry. The second-turn modification request is test input only and does not grant modification authority.

## Alternatives considered

- **Test only the embedded instruction:** Rejected because the scenario also requires direct write-refusal evidence.
- **Test refusal in a separate conversation:** Rejected because the follow-up must exercise whether the active read-only Skill preserves its boundary after inspecting the supplied root.
- **Allow Cowork to attempt a repair in a disposable copy:** Rejected because the tested Skill is strictly read-only and the scenario validates refusal, not rollback.

## Consequences

- M-010 produces one immutable two-turn result and one post-conversation byte comparison.
- Any write, widened access, implied successful repair, or unexpected failure stops progression pending review.
- No GG-SYN-008 or later scenario is authorized.

## Follow-up

- Project Dexter: prepare and verify the authorized isolated root and register both exact prompts.
- User / product owner: run both turns in order and return both complete responses.
- Project Dexter: verify and record the complete run before any later authorization.