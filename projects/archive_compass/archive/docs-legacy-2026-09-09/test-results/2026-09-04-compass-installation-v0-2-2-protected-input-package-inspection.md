# Test result: Installation 0.2.2 protected-input package inspection

## Run metadata

- **Date:** 2026-09-04
- **Tester:** GitHub Copilot as laboratory assistant
- **Skill/version:** `compass-installation-interview` `0.2.2-dogfood-candidate`
- **Test artifact:** `../../skill-exchange/ready-for-test/compass-installation-interview-v0.2.2-dogfood-candidate.skill`
- **Scenario/revision:** [Protected-input impact assessment](../specifications/2026-09-04-protected-installation-input-impact-assessment.md)
- **Cowork environment/version:** not used; static local inspection only
- **Result:** pass

## Execution notes

The package was built twice from current source using sorted relative members, DEFLATE, fixed `2026-09-04 00:00:00` timestamps, Unix regular-file metadata, and mode `0644`. A first general semantic harness produced false negatives because its assertions did not match valid Markdown wording. A replacement named literal audit checked each requirement directly against packaged text.

## Observed behavior

1. The archive contains only `SKILL.md` and `references/behavior-contract.md`.
2. Every archived member is byte-equal to current source and uses safe relative paths, fixed metadata, DEFLATE, and mode `0644`.
3. An independent rebuild was byte-identical.
4. Both source files identify `0.2.2-dogfood-candidate`.
5. Packaged text prohibits attached or linked document ingestion and stops on `Protection: labeled`.
6. Packaged text requires a root-level disposable plain-text probe before managed structure and verified cleanup before continuation.
7. Packaged text maps refusal to `write-blocked` / `blocked`, requires config-first bootstrap, and prohibits Office/PDF substitution.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Deterministic, source-faithful package | Final archive reproduced and matched current source | match |
| Protected-input hard stop | Present in Skill and behavior contract | match |
| Preflight before managed structure | Present with cleanup verification | match |
| Honest policy refusal and schema preservation | `write-blocked` / `blocked`; no Office/PDF substitution | match |

## Evidence

- Size: 6,691 bytes
- SHA-256: `befc99fdea10f3a96d99358f367e8d25b466eebbb0d61a73a06754b3805e399f`
- Named final audit: all 12 structural, version, and semantic assertions passed.

## Issues and risks

- Static instructions do not prove Cowork will obey the protection stop or operation ordering.
- A new user-confirmed root must exist before it can be probed, so an empty root may remain after a refusal.

## Follow-up

- Run one clean first-run retest in a new label-free Cowork task using exact Compass `0.3.2` packages.
- Do not deliberately import a protected document merely to recreate the failure.

## Tester conclusion

The exact package faithfully contains the intended mitigation and is ready for bounded runtime retest. This result does not claim that the first-run defect is resolved in Cowork.