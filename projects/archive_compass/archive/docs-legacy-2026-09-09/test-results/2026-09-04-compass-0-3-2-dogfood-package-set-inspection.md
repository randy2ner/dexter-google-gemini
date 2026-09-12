# Test result: Compass 0.3.2 dogfood package set inspection

## Run metadata

- **Date:** 2026-09-04
- **Tester:** GitHub Copilot as laboratory assistant
- **Skill/version:** Compass `0.3.2-dogfood-candidate` exact five-package set
- **Test artifact:** [Compass 0.3.2 package manifest](../inventory/compass-0.3.2-dogfood-candidate-package-set.md)
- **Scenario/revision:** [Protected-input impact assessment](../specifications/2026-09-04-protected-installation-input-impact-assessment.md)
- **Cowork environment/version:** not used; static local inspection only
- **Result:** pass

## Observed behavior

1. All five manifest artifacts exist and match their recorded SHA-256 values.
2. Every archive uses safe member paths, DEFLATE, fixed `2026-09-04 00:00:00` timestamps, and mode `0644`.
3. Every archived member is byte-equal to its current source file.
4. Installation `0.2.2` contains both expected members, matching versions, and all seven protected-input, preflight, blocked-outcome, config-first, and schema-preservation behaviors.
5. Daily Scan, Tracking Topic Interview, Curator, and Graph Governor retain the exact hashes recorded in `0.3.1`.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Installation is the only changed package | Only Installation hash differs from `0.3.1` | match |
| Every exact package is deterministic and source-faithful | All structural, metadata, hash, and source-byte checks passed | match |
| Corrected Installation safeguards are packaged | Seven explicit semantic assertions passed | match |

## Evidence

- Installation SHA-256: `befc99fdea10f3a96d99358f367e8d25b466eebbb0d61a73a06754b3805e399f`
- Final audit terminal: `PASS 0.3.2 FINAL`

## Issues and risks

- Static package fidelity does not establish Cowork runtime compliance.
- The protected-input finding remains mitigated, not resolved, until one clean first-run retest succeeds.

## Follow-up

- Use only the exact `0.3.2` set for the next clean first-run Cowork task.
- Begin with `Help me install Compass` and supply foundational content only as typed or pasted text.

## Tester conclusion

The exact corrected package set is internally consistent and ready for the smallest justified connected retest. No connected behavior claim is made by this inspection.