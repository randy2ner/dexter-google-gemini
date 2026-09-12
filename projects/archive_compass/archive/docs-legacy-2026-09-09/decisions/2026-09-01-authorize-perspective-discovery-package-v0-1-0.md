# Decision: Authorize Perspective Discovery package version 0.1.0-experimental

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Disconnected source inspection](../test-results/2026-08-28-perspective-discovery-source-static-inspection.md), [Graph Governor bounded closure](2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)

## Context

Graph Governor `0.1.0-experimental` completed its bounded closure. The next documented Compass lifecycle gate is packaging the already implemented and statically inspected Installation Interview Perspective Discovery source. The exact three-file source passed disconnected inspection on 2026-08-28, but package creation remained separately gated. On 2026-09-01, the user directed Project Dexter to proceed to the next step.

## Decision

Authorize deterministic creation and disconnected archive inspection of `compass-installation-perspective-discovery-v0.1.0-experimental.skill` from the exact source hashes recorded in the source-inspection result:

- `SKILL.md`: 8,018 bytes, SHA-256 `6af46fc9ce5987f98c27e392100ba0a202d03870f51fd733fbe654a5c8500c7a`;
- `references/behavior-contract.md`: 3,135 bytes, SHA-256 `45854d78c96915ba95f38aa0d975698b38f2ae3cd71cb904cd7f40e0d342d94b`; and
- `references/evaluation-cases.md`: 2,189 bytes, SHA-256 `6d6ceb6816fa7f33347dc5abc41988467ffb9ec906423367df2458349840c43a`.

The package must contain only those three members at their declared relative paths. Inspection may verify safe paths, metadata, CRCs, UTF-8 text, source-byte identity, frontmatter identity, deterministic rebuild identity, package size, and SHA-256.

After all checks pass, retain the exact immutable artifact in `skill-exchange/ready-for-test/`. That location records package-review state only.

This decision does not authorize Cowork import, Work IQ access, Microsoft 365 retrieval, connected execution, test-date selection, graph access or writes, another Skill, source revision, package replacement, deployment, or release.

## Alternatives considered

- **Begin connected testing immediately:** Rejected because exact package construction and review precede connected-test authorization.
- **Modify source during packaging:** Rejected because the package must preserve the reviewed source bytes.
- **Rework prior incoming Installation artifacts:** Rejected because received specimens remain immutable reference evidence.

## Consequences

- Package evidence applies only to the exact resulting artifact hash.
- Any source mismatch stops packaging and requires review rather than silent rebuilding from changed bytes.
- Passing package checks supports package-review readiness only, not Cowork or Work IQ behavior confidence.

## Follow-up

- Project Dexter: create and inspect the package once, record immutable evidence, and update the Skill profile.
- User / product owner: separately authorize any Cowork import or connected Work IQ run after reviewing package evidence and a lean test scope.