# Test result: Compass 0.3.3 protected-source package set inspection

## Run metadata

- **Date:** 2026-09-04
- **Tester:** GitHub Copilot as laboratory assistant
- **Skill/version:** Compass `0.3.3-dogfood-candidate` exact five-package set
- **Test artifact:** [Compass 0.3.3 package manifest](../inventory/compass-0.3.3-dogfood-candidate-package-set.md)
- **Scenario/revision:** [Compass dogfood clean first run](../scenarios/compass-dogfood-clean-first-run.md), version 1.2
- **Cowork environment/version:** not used; static local inspection only
- **Result:** pass

## Observed behavior

1. All five manifest artifacts exist and match their recorded SHA-256 values.
2. Every archive uses safe member paths, DEFLATE, fixed `2026-09-04 00:00:00` timestamps, and mode `0644`.
3. Every archived member is byte-equal to its current source file.
4. Installation `0.2.3` accepts user-selected classified or sensitivity-labeled Microsoft 365 files and Loop pages as valid input.
5. Classification alone is not a stop condition; source protection remains platform-enforced and retrieved content is minimized to reviewed derivations.
6. The post-retrieval write probe, actual-refusal-only block, and config-first ordering are present.
7. No current Installation package language requires a label-free task or prohibits protected document reading.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Installation is the only changed package | Other four package hashes remain unchanged | match |
| Protected Microsoft 365 source remains valid input | Explicitly accepted in packaged Skill and contract | match |
| Protection and authority remain bounded | No relabel, export, bypass, raw-body retention, or automatic graph authority | match |
| Output ordering defect remains mitigated | Probe follows selected-source retrieval and precedes managed structure; config is first durable write | match |

## Evidence

- Installation size: 7,206 bytes
- Installation SHA-256: `92e96ce31fa5b609aa2665cc1b2622c969f83510f76f0cd4eb1aee3389d0c20d`
- Final audit terminal: `PASS 0.3.3 FINAL`

## Issues and risks

- Static instructions cannot establish whether the target Cowork tenant permits Markdown/YAML output after protected Loop retrieval.
- If the actual probe is refused, the compatible protected output path remains a product/platform integration problem; source classification must not be treated as user error.

## Follow-up

- Run one natural first-run Cowork session using the selected protected Loop page.
- Preserve the label and tenant policy unchanged; observe retrieval, proposal derivation, probe outcome, managed-structure ordering, and terminal accounting.

## Tester conclusion

The exact package set now represents the product owner's protected-source approach and is ready for one connected retest. This inspection makes no claim that the Microsoft 365 output-policy interaction will succeed.