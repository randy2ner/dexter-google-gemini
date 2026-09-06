# Finding: Protected input blocks portable installation

## Metadata

- **First observed:** 2026-09-04
- **Status:** product response corrected; protected-source runtime retest pending
- **Severity:** high
- **Owner:** User / product owner
- **Affected skills/versions:** `compass-installation-interview` `0.2.1-dogfood-candidate`; Compass `0.3.1-dogfood-candidate`

## Summary

In the observed run, graph writes were refused after a protected Loop page entered the conversation, and managed folders were created before output capability was known. The protected source itself remains valid product input; the defect is failure to preserve that intended input path while ordering output preflight before managed structure.

## Evidence

- [Protected Loop clean-first-run result](../test-results/2026-09-04-compass-clean-first-run-protected-loop-write-blocked.md)

## Reproduction conditions

Observed once after an internally classified Loop `.page` entered the installation conversation and a read reported `Protection: labeled`. It is not established whether attachment alone or the later download/read triggered the label requirement.

## Impact

The user cannot complete first run, Compass cannot substitute labelable Office/PDF containers without breaking its portable schema, and premature folder creation can leave unmanaged empty structure that the run cannot remove.

## Proposed action

Allow user-selected classified Microsoft 365 sources through native Cowork protection; minimize retrieval and retain only approved derivations; require post-retrieval plain-text write/read/delete preflight before managed structure; apply approved bootstrap config-first; and classify only an actual policy refusal as `write-blocked` / `blocked`.

## Resolution

The `0.2.2` label-free avoidance mitigation was rejected and preserved as a superseded candidate. Installation `0.2.3` implements the corrected protected-source approach. Resolution requires package-set inspection and one Cowork first-run retest using a selected protected Loop page; no runtime effectiveness claim exists yet.