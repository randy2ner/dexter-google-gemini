# Test result: Compass clean first run with protected Loop input

## Run metadata

- **Date:** 2026-09-04
- **Tester:** User / product owner
- **Skill/version:** `compass-installation-interview` `0.2.1-dogfood-candidate`
- **Test artifact:** `../../skill-exchange/ready-for-test/compass-installation-interview-v0.2.1-dogfood-candidate.skill`
- **Scenario/revision:** [Compass dogfood clean first run](../scenarios/compass-dogfood-clean-first-run.md), version 1.0
- **Cowork environment/version:** Approved managed Cowork client; exact host version not recorded
- **Result:** blocked; first-run experience failed

## Execution notes

The user imported an internally classified Loop page to define CSPs. This was a natural deviation from the scenario's no-attachment starting condition and exposed an unhandled information-protection interaction. Observations below are based on the user's report and Cowork's relayed diagnostic account; Dexter did not independently inspect tenant logs or protected content.

## Observed behavior

1. A read of the imported `.page` reported `Protection: labeled`.
2. Cowork later reported that the conversation required every output file to carry a sensitivity label.
3. All 17 attempted plain-text Markdown or YAML writes were refused because the file types could not carry the required label.
4. Cowork classified the refusal as non-retryable.
5. Six empty folders had already been created and could not be rolled back in the run.
6. No Compass configuration, object, or Daily Log content was written.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Natural installation accepts direct foundational input without crossing a privacy boundary. | Installation ingested a protected Loop page and did not stop at the labeled-content signal. | mismatch |
| A predictable write incompatibility is detected before managed structure is created. | Six empty folders preceded the first decisive plain-text refusal. | mismatch |
| A blocked environment produces honest bounded effects. | The writes were refused, but empty structure remained. | partial |

## Evidence

- User-relayed Cowork diagnostic account; no protected source content, identities, tenant URLs, or raw transcript retained in Dexter.

## Issues and risks

- High: a protected input can make Compass's required portable plain-text graph unwritable for the session.
- High: write capability was not proven before structural effects, leaving orphaned folders.
- Unknown: available evidence does not distinguish whether attaching the Loop page or downloading/reading it caused the session to require labels.

## Follow-up

- Revise Installation to prohibit attached or linked document ingestion, hard-stop on protection signals, preflight representative plain-text capability, and apply approved bootstrap config-first.
- Preserve `0.2.1` and this result. Repackage and rerun only clean first-run Installation using `0.2.2` in a new label-free session.

## Tester conclusion

The strongest supported mechanism is incompatibility between a label-required conversation and Compass's schema-required plain-text files. The exact point at which the session became label-required remains unproven. The failed experience is actionable because both ingestion behavior and write ordering are under Installation's control.