# Decision: Clarify GG-SYN-003 terminal-line prompt

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related result:** [GG-SYN-003 M-003](../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md)

## Context

The GG-SYN-003 revision 1 prompt ended its final instruction with a period immediately after the inline-formatted literal `External changes: 0`. Cowork returned that punctuation as part of its final line. The M-003 result initially preserved this as a minor non-functional format deviation; that provisional classification was later [superseded by attribution to test-prompt ambiguity](2026-08-31-reclassify-gg-syn-003-m-003-punctuation.md).

## Decision

For M-004 and M-005, clarify only the final prompt instruction by placing the required terminal line on its own and making the zero the final character of the prompt. Explicitly state that no punctuation or other characters may follow the zero.

Do not retry M-003. Preserve its revision 1 result and disposition. Treat the clarified prompt as GG-SYN-003 revision 2 for the remaining sequential runs.

## Consequences

- M-003 remains evidence for revision 1.
- M-004 and, if later authorized by the existing evidence gate, M-005 use revision 2.
- The graph-inspection scope, safety controls, expected relationship behavior, package, and fixtures remain unchanged.
- Comparison of terminal punctuation across revisions is observational; one future response cannot establish general output determinism.

## Follow-up

- User / product owner: run M-004 once with the revision 2 prompt.
- Project Dexter: preserve the response exactly and perform post-run verification before M-005.