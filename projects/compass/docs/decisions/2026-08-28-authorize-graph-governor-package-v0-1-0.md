# Decision: Authorize Graph Governor package version 0.1.0-experimental

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Disconnected source inspection](../test-results/2026-08-28-graph-governor-source-static-inspection.md)

## Context

The exact three-file Graph Governor source passed bounded disconnected inspection. No package exists. The user explicitly directed, “proceed with package creation.”

## Decision

Authorize deterministic creation and disconnected archive inspection of `graph-governor-v0.1.0-experimental.skill` from the exact source hashes recorded in the source-inspection result.

The package must contain only root `SKILL.md`, `references/read-only-contract.md`, and `references/evaluation-cases.md`. Package inspection may verify paths, metadata, CRCs, UTF-8 text, source-byte identity, deterministic rebuild identity, byte size, and SHA-256.

After those checks pass, place the exact immutable artifact in `skill-exchange/ready-for-test/`. This location records review state only and does not authorize Cowork upload or execution.

## Alternatives considered

- **Rebuild or revise source during packaging:** Rejected because the package must preserve the reviewed source bytes.
- **Upload immediately after packaging:** Rejected because Cowork upload and execution remain separate authorization gates.
- **Add a generated manifest inside the package:** Rejected because the accepted package contains exactly three Markdown members.

## Consequences

- Package evidence will apply only to the exact artifact hash produced by this decision.
- Any source edit requires a new source inspection and a new package version or revision.
- Package construction cannot establish Cowork import, discovery, activation, graph access, or scenario behavior.

## Follow-up

- Create and inspect the deterministic package once from the recorded source.
- Record an immutable package-inspection result and update the Skill profile.
- Do not upload or execute the package without separate explicit authorization.
