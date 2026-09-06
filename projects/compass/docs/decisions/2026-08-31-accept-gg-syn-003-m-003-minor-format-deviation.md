# Decision: Accept GG-SYN-003 M-003 minor format deviation

- **Date:** 2026-08-31
- **Status:** superseded by [the punctuation reclassification](2026-08-31-reclassify-gg-syn-003-m-003-punctuation.md)
- **Deciders:** User / product owner
- **Related result:** [GG-SYN-003 M-003](../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md)

## Context

The M-003 response matched the expected relationship-integrity behavior and its post-run fixture and package verification passed. Its final line was `External changes: 0.` rather than the requested literal `External changes: 0` because of one terminal period. No implemented parser, orchestration, API, or downstream Skill consumes that prose. The current consumer is human review and evidence preservation.

## Decision

Classify the added period as a minor, non-functional report-format deviation. Accept M-003 as passed with that deviation recorded, without retrying or changing the tested package.

Proceed to the already authorized M-004 run under the unchanged scenario prompt and existing sequential controls. M-005 remains gated until M-004 evidence is preserved and reviewed.

## Alternatives considered

- **Keep M-003 partial and stop:** Rejected because the punctuation does not change the represented zero value, relationship finding, effect accounting, or current human consumption.
- **Retry M-003:** Rejected because a retry is not needed to establish the tested relationship behavior and would require separate authority.
- **Treat prose as a machine interface:** Rejected for this run because no machine consumer exists or has been tested. Any future machine handoff must define and test a structured contract rather than rely on punctuation-sensitive natural language.

## Consequences

- The exact observed response remains preserved unchanged in the M-003 result.
- M-003 is recorded as passed with one minor format deviation.
- This decision does not establish durability for a future parser or authorize a future machine consumer.
- M-004 may proceed once its fixture and package readiness are reverified.

## Follow-up

- Project Dexter: retain the minor deviation in the immutable result and update scenario tracking.
- User / product owner: run M-004 once in a clean Cowork conversation using only `gg-syn-003-m-004` and the unchanged common prompt.
- Project Dexter: preserve and review M-004 before directing M-005.