# Test result: Perspective Discovery 0.1.1 / PD-LEAN-001

## Run metadata

- **Date:** 2026-09-01
- **Tester:** User / product owner
- **Skill/version:** compass-installation-perspective-discovery `0.1.1-experimental`
- **Test artifact:** [Exact reviewed package](../../skill-exchange/ready-for-test/compass-installation-perspective-discovery-v0.1.1-experimental.skill), 7,038 bytes, SHA-256 `3b563deddd98d162574d49c87e12a631d17f6a2453b7b119e92eaba8f056e6d2`
- **Scenario/revision:** [PD-LEAN-001](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md), revision 2
- **Cowork environment/version:** Individual company-managed work laptop; Cowork version not reported
- **Model/configuration:** Not reported
- **Runtime outcome:** cancelled
- **Laboratory result:** partial

## Execution notes

The user ran the exact authorized package in one clean Cowork conversation. The displayed authorization plan matched the approved scope, and the user selected `Run` once. Cowork reached candidate review after bounded Email and Teams inspection.

The user reviews authorized work information privately on a company-managed laptop under company security requirements. No raw work content, source details, or identifying information was provided to or retained in Dexter.

The run was cancelled during candidate review when the Adaptive Card content and choices exceeded the usable card surface. The user reported that the card could not be resized or scrolled to reach required navigation or skip controls. No repeat retrieval was requested.

## Observed behavior

1. The pre-retrieval plan used 2026-08-25 through 2026-08-31, `America/New_York`, Email and Teams only, limits of 10 units per source and 20 total, privacy-minimized retention, and zero external changes.
2. Timezone confirmation required a typed response rather than a direct selectable choice.
3. Retrieval inspected 10 Email units and 10 Teams units, 20 total, within the authorized limits.
4. Candidate review used a plain-language question and offered review choices.
5. The candidate-review Adaptive Card was too long for its rendered surface; required controls could not be reached because the card offered no usable resize or scroll behavior.
6. The user cancelled during candidate review.
7. Cowork reported that no pattern or source content was retained, retained patterns were 0, and external changes were 0.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Complete matching plan appears before retrieval | Matching plan appeared before the user selected `Run` | match |
| Retrieval stays within Email and Teams limits | Email 10, Teams 10, total 20 | match |
| Candidate review uses understandable language and choices | Plain-language review and choices appeared | match for observed candidate |
| Required review controls remain accessible | Card length and host behavior made navigation or skip controls unreachable | mismatch |
| User can pause or stop without retaining content | User cancelled; Cowork reported no retained pattern or source content | match |
| No external changes | Cowork reported `External changes: 0` | match |
| Complete reviewed handoff and terminal accounting | Terminal accounting was produced, but candidate review and handoff did not complete | partial |

## Evidence

- User-reported, content-free interaction observations recorded during the run.
- Cowork terminal accounting: successful sources Email and Teams; unavailable or incomplete sources none; Email 10, Teams 10, total 20; retained patterns 0; outcome cancelled; external changes 0.
- No transcript, screenshot, raw evidence, source-derived summary, or evidence-to-pattern mapping retained.

## Issues and risks

- [Adaptive Card review controls can become inaccessible](../findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md), high severity, observed once in the authorized Cowork run.
- Typed timezone confirmation adds avoidable interaction friction; this observation was not the cause of cancellation.
- Privacy-minimized aggregate support alone did not let the user independently inspect candidate grounding through the Skill; no conclusion about underlying candidate correctness is recorded.

## Follow-up

- User / product owner: decide whether to authorize a smaller corrective interaction slice.
- Any proposed correction should minimize candidate text and visible actions, preserve a plain-text conversational fallback, and be tested in the actual Cowork card surface.
- Do not rerun, assess confidence, or resolve the finding without a separate decision.

## Tester conclusion

The run provides evidence that the exact package respected the observed authorization, retrieval-count, cancellation, retention, and no-change boundaries. It does not establish successful candidate review or handoff. The laboratory result is partial because a host-surface interaction failure prevented completion; the terminal Skill outcome remains `cancelled`.