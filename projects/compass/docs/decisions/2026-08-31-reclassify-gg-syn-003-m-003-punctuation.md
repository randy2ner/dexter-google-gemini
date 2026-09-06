# Decision: Reclassify GG-SYN-003 M-003 punctuation

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Supersedes:** [Minor-format-deviation disposition](2026-08-31-accept-gg-syn-003-m-003-minor-format-deviation.md)
- **Related result:** [GG-SYN-003 M-003](../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md)

## Context

The exact M-003 response ended with `External changes: 0.`. Subsequent review identified that the revision 1 test prompt placed its own sentence-ending period immediately after the inline-formatted requested line. Revision 2 isolated the line, made zero the final prompt character, and produced the requested punctuation-free line in both M-004 and M-005.

## Decision

Attribute the M-003 punctuation to ambiguity introduced by the revision 1 test prompt, not to a Graph Governor functional or report-format deviation. Record M-003 as passed without a Skill deviation.

Preserve the original response, the prompt ambiguity, the earlier provisional disposition, and the revision 2 results as historical evidence. Do not claim that the later observations prove deterministic punctuation behavior beyond these runs.

## Consequences

- M-003 remains a pass for its relationship-integrity objective and no-change behavior.
- The terminal punctuation row is not scored against Graph Governor because the test instruction was ambiguous.
- The earlier minor-deviation disposition is superseded rather than deleted.
- Revision 2 remains the clearer prompt form for future tests.

## Follow-up

- Remove the minor-deviation label from current scenario, plan, and result status summaries.
- Keep the exact M-003 Cowork response unchanged in its test result.