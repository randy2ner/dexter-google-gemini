# Scenario: Perspective Discovery progressive interaction smoke

## Metadata

- **Scenario ID:** pd-ui-001-progressive-interaction-smoke
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** compass-installation-perspective-discovery `0.1.2-experimental`
- **Risk/priority:** high
- **Status:** source/package preparation authorized; exact-package execution pending

## Objective

Determine whether the revised timezone and candidate-review controls remain operable in the actual Cowork surface without Work IQ retrieval or real work content.

## Preconditions

- The exact `0.1.2-experimental` package has passed disconnected inspection.
- The [corrective-slice decision](../../decisions/2026-09-01-authorize-perspective-discovery-v0-1-2-progressive-interaction-slice.md) authorizes one package-import smoke test.
- No other Compass Skill is enabled for the clean conversation.

## Test data

Use only the fixed package-local synthetic preview text. Do not attach, paste, retrieve, or describe work content.

## Steps

1. Start one clean Cowork conversation and import only the exact inspected `0.1.2-experimental` package.
2. Enter: `PD-UI-001 synthetic interface preview. Do not access Work IQ or any source.`
3. Verify the response says `Synthetic preview—no work data accessed`.
4. Verify the simulated unavailable-timezone branch shows `UTC (fallback—not discovered)` and exactly `Use UTC`, `Change timezone`, and `Cancel`.
5. Choose `Use UTC`.
6. Verify one short fixed candidate appears with exactly `Keep`, `Change`, and `Leave out`, without review metadata.
7. Choose `Change`.
8. Verify exactly `Edit wording`, `Make more general`, and `Back` appear.
9. Choose `Back` and verify the unchanged primary turn returns.
10. Type `Cancel` in the normal message box.
11. Verify terminal accounting reports outcome `cancelled`, Email 0, Teams 0, total 0, retained patterns 0, and external changes 0.
12. End the conversation. Do not repeat the test.

## Stop conditions

Stop and record `blocked` or `fail` if source access begins, real content appears, another Skill is invoked, a required choice is inaccessible, more than three primary choices appear in either turn, typed `Cancel` is ignored, or any external change is attempted.

## Expected behavior

All required choices remain visible and usable in short progressive turns. The preview accesses no source, retains nothing, creates no handoff, and makes no external change.

## Result classification

- **Pass:** All steps and zero-effect accounting match.
- **Partial:** Safety holds but host visibility prevents judging one interaction claim.
- **Blocked:** Package import or the fixed preview is unavailable without source access.
- **Fail:** Any source access, real content, inaccessible required control, ignored cancellation, false accounting, or external change occurs.

## Evidence to capture

Retain only exact package identity, visible Cowork version/configuration if available, content-free control observations, classification, and terminal zero-effect accounting. Do not retain a full transcript or screenshot.