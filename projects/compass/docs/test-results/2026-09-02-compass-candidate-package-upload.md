# Test result: Compass candidate package upload

## Run metadata

- **Date:** 2026-09-02
- **Tester:** User / product owner
- **Skill/version:** Five-package Compass beta candidate
- **Test artifact:** [Exact package set](2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- **Scenario/revision:** [Experience-led rehearsal kit](../scenarios/compass-experience-led-rehearsal.md), version 1.0
- **Cowork environment/version:** Approved managed Cowork client; exact visible version not yet recorded
- **Model/configuration:** Not visible
- **Result:** partial

## Execution notes

After the integrated automation browser was blocked by Conditional Access, the product owner used an approved managed Cowork client and reported that all five candidate `.skill` files were uploaded.

## Observed behavior

1. User reported upload completion for all five exact candidate package files.
2. Cowork displayed support for `.md`, `.zip`, and `.skill` imports.
3. Displayed Skill names, activation state, invocation, routing, handoffs, and behavior have not yet been recorded.
4. No connected content access or graph write was reported during upload.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Cowork accepts five separate `.skill` uploads | User reported all five uploaded | Match, user-reported |
| Cowork displays the expected five Skill identities | Not yet recorded | Unobserved |
| Candidate Skills can be invoked | Not yet attempted | Unobserved |

## Evidence

- Product-owner report in the active laboratory session.
- Exact local package names and hashes remain recorded in the source/package inspection and session kit.

## Issues and risks

- Upload completion does not establish that Cowork parsed, activated, or will invoke each package correctly.
- The managed Cowork page is not accessible to the laboratory assistant, so visible UI facts require product-owner reporting.

## Follow-up

- Record the five names Cowork displays and whether each is selectable.
- If identities are correct, begin the authorized fictional-data rehearsal with Installation Interview.

## Tester conclusion

Package upload crossed the environment blocker in a compliant client. The rehearsal has not begun, and no candidate runtime claim is supported yet.