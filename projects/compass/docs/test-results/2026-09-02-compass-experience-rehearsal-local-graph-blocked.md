# Test result: Compass experience rehearsal local graph access

## Run metadata

- **Date:** 2026-09-02
- **Tester:** User / product owner
- **Skill/version:** `compass-installation-interview` `0.1.0-beta-candidate`
- **Test artifact:** [Exact candidate package set](2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- **Scenario/revision:** [Experience-led rehearsal kit](../scenarios/compass-experience-led-rehearsal.md), version 1.0
- **Cowork environment/version:** Approved managed Cowork client; exact version not visible
- **Model/configuration:** Not visible
- **Result:** blocked, then paused cleanly

## Execution notes

All five packages had been uploaded in the approved managed client. Installation Interview requested the exact disposable graph root. The supplied Windows path was not accessible from the Cowork rehearsal workspace. The user followed the boundary instruction and paused rather than substituting another location.

## Observed behavior

1. Installation Interview requested one explicit graph root and offered `Pause` or `Cancel`.
2. Cowork reported that `C:\Repos\Dexter\projects\compass\test-data\compass-beta-graph-v1\materialized\graph` was inaccessible from its workspace.
3. The user selected `Pause`.
4. Cowork reported that nothing was retained or changed and no external systems were accessed.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Installation stops when the designated graph is inaccessible | Skill requested direction and accepted Pause | Match |
| No silent storage substitution | No substitute graph was selected | Match |
| Exact terminal effect accounting | Nothing retained or changed; no external access reported | Match, user-reported |
| Continue the Compass journey | Local graph unavailable to Cowork | Blocked |

## Evidence

- Product-owner transcription of the Cowork prompts and terminal response.
- No raw work content, tenant details, or authentication evidence retained.

## Issues and risks

- **Environment integration blocker:** Cowork cannot address the local Windows graph path.
- A connected or uploaded write target would change the approved storage boundary and requires explicit identification, backup, and authorization.
- Uploading an archive alone may permit reading but does not establish a writable graph hierarchy.

## Follow-up

- Prepare a minimal baseline handoff containing only the disposable graph content, without expected outputs, operations, or recovery source.
- In the approved client, create or select a dedicated Cowork-accessible disposable folder and retain an external verified backup.
- Record and explicitly authorize that exact folder before resuming Installation Interview.

## Tester conclusion

The candidate failed no product assertion in this step. It stopped at an inaccessible storage boundary and paused with zero reported effects. Resume only after establishing an accessible, isolated, backed-up write target.