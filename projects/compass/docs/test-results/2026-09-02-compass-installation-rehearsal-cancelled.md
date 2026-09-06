# Test result: Compass Installation experience rehearsal

## Run metadata

- **Date:** 2026-09-02
- **Tester:** User / product owner
- **Skill/version:** `compass-installation-interview` `0.1.0-beta-candidate`; `graph-governor` appeared as a participating Skill
- **Test artifact:** [Exact candidate package set](2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- **Scenario/revision:** [Experience-led rehearsal kit](../scenarios/compass-experience-led-rehearsal.md), version 1.0
- **Cowork environment/version:** Approved managed Cowork client; exact version not visible
- **Model/configuration:** Not visible
- **Result:** cancelled; partial laboratory result

## Execution notes

The user resumed Installation Interview against the explicitly authorized `SampleCompass` synchronized graph. The interaction collected timezone, a fictional responsibility statement, one CSP, one Tracking Topic aligned to that CSP, and one fictional Person. Cowork then rendered the bootstrap proposal in an oversized Adaptive Card.

The user could not practically reach or perform the intended Change action. Closing the card cancelled the operation.

## Observed behavior

1. Installation Interview accepted the exact graph root and confirmed `America/Los_Angeles`.
2. It progressively collected one fictional CSP, Tracking Topic, and Person without opening real connected content.
3. It produced an exact bootstrap preview containing object IDs, wording, relationship direction, source-state hash, recovery limitation, and approval choices.
4. The preview did not state exact relative paths for the four Markdown object effects.
5. The Daily Log description proposed one Configuration entry recording the three created objects rather than explicit object entries under the CSP, Tracking Topic, and Person sections.
6. The Adaptive Card included enough content and surrounding interface text that the user could not perform the intended revision path.
7. Closing the card produced `Cancelled`. Cowork reported no approval, write, or retention.
8. External inspection found only the original `README.md`, 299 bytes, SHA-256 `2f344bdb89f8b2157bb8d313401402aef92dc13f9f1834d825b27d46272ff67a`. No `_compass`, `csps`, `tracking-topics`, `people`, or `daily-logs` path exists.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Progressive conversational setup | Timezone, purpose, CSP, Topic, and Person collected progressively | Match |
| Concise, operable approval and revision turn | Oversized Adaptive Card prevented practical Change action | Mismatch |
| Exact target effects before approval | Filenames were shown without complete relative paths; Daily Log object entries were underspecified | Mismatch |
| Closing/cancelling retains nothing | Cowork reported cancellation and external inspection found no changes | Match |
| No connected source access | No external source content was requested or reported | Match |

## Evidence

- Product-owner transcription of the complete Cowork preview and cancellation response.
- Read-only external inspection of the authorized graph after cancellation.
- No raw work content, authentication data, or tenant identifier retained.

## Issues and risks

- [Bootstrap approval card blocks practical review](../findings/2026-09-02-installation-bootstrap-approval-card-blocks-review.md).
- Exact effect paths and Daily Log entries need correction before approval can be informed.
- Package upload and partial interaction do not establish successful installation, write behavior, or post-write verification.

## Follow-up

- Revise only Installation Interview's bootstrap preview guidance to use concise plain text with typed `Approve`, `Change`, `Pause`, and `Cancel` fallbacks.
- Require exact relative paths and explicit per-object Daily Log entries in the preview.
- Repackage Installation Interview under a new candidate version and resume the experience from setup; do not rerun unrelated package imports or isolated tests.

## Tester conclusion

The candidate demonstrated useful progressive setup and safe cancellation, but the approval surface blocked completion. A focused Installation source correction is required before the rehearsal can continue.