# Test result: Compass experience rehearsal preflight

## Run metadata

- **Date:** 2026-09-02
- **Tester:** User / product owner with laboratory assistant
- **Skill/version:** Five-package Compass beta candidate; no package imported or invoked
- **Test artifacts:** [Exact package set](2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- **Scenario/revision:** [Experience-led rehearsal kit](../scenarios/compass-experience-led-rehearsal.md), version 1.0
- **Cowork environment/version:** Microsoft 365 Copilot sign-in through the VS Code integrated automation browser; Cowork version not reached
- **Model/configuration:** Not visible
- **Result:** blocked

## Execution notes

The user shared a browser page. A separate page navigated to Microsoft 365 Copilot and reached Microsoft sign-in. The user reported that Conditional Access requires a device or client application meeting Microsoft management compliance policy. The integrated automation browser did not satisfy that policy, so the Cowork interface was not reached.

## Observed behavior

1. Microsoft authentication reached the organization's Conditional Access boundary.
2. Access was restricted because the browser/device-client context did not meet management compliance policy.
3. No Compass package was imported, activated, or invoked.
4. No Email, Teams, OneDrive, or other connected content was opened.
5. No graph file or external state was changed by the attempted rehearsal.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Reach a company-approved Cowork environment for package preflight | Integrated automation browser was rejected by Conditional Access | Blocked |
| Import five exact candidate packages | Import interface was not reached | Unobserved |
| Begin the fictional-data experience | No Skill was invoked | Unobserved |

## Evidence

- User-reported policy boundary: devices or client applications must meet Microsoft management compliance policy.
- No authentication details, tenant identifiers, screenshots, or connected content retained.

## Issues and risks

- **Environment blocker:** Browser automation cannot be used for this run unless Microsoft recognizes its device/client context as compliant.
- Do not bypass, weaken, or request an exception to Conditional Access for the rehearsal.
- This result says nothing about package importability or Compass runtime behavior.

## Follow-up

- Product owner opens Cowork in an approved managed browser or client and operates the rehearsal using the existing session kit.
- Laboratory assistant supports package identification, prompts, graph inspection, and result recording outside the restricted browser session.

## Tester conclusion

The rehearsal was blocked before candidate execution. Preserve the exact packages and rerun only the environment preflight in a compliant client; no Skill correction or broader regression is indicated.