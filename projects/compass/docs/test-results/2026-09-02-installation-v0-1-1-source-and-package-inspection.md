# Test result: Installation Interview 0.1.1 source and package inspection

## Run metadata

- **Date:** 2026-09-02
- **Tester:** Laboratory assistant
- **Skill/version:** `compass-installation-interview` `0.1.1-beta-candidate`
- **Test artifact:** [compass-installation-interview-v0.1.1-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-installation-interview-v0.1.1-beta-candidate.skill)
- **Scenario/revision:** Focused correction from the [approval-card finding](../findings/2026-09-02-installation-bootstrap-approval-card-blocks-review.md)
- **Cowork environment/version:** Not used
- **Model/configuration:** Not applicable
- **Result:** pass for disconnected source/package inspection

## Observed behavior

1. Source version and handoff identity are `0.1.1-beta-candidate`.
2. Bootstrap previews must use concise plain text and must not use an Adaptive Card, table, attachment, or container that can hide or separate choices.
3. Preview requirements now include every exact graph-root-relative path and separate Daily Log entries for Configuration, CSPs, Tracking Topics, and People.
4. The decision prompt requires directly typeable `Approve`, `Change`, `Pause`, and `Cancel` choices.
5. The package contains exactly `SKILL.md` and `references/behavior-contract.md`; both are byte-equal to source.
6. Fixed timestamps, DEFLATE compression, safe sorted paths, effective mode `0644`, version text, and independent byte-identical rebuild passed.

## Artifact identity

- **Bytes:** 4,383
- **SHA-256:** `e3f2363fa32c22cc02a3724ed92f9ea2da1a1cf842f23b80d3d14bd5566654ec`

## Tester conclusion

The focused source and package correction is ready for Cowork retest. This inspection does not establish that Cowork will follow the plain-text guidance or that Installation can write and verify the graph.