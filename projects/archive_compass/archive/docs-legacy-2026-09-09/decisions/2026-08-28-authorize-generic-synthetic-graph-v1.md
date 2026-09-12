# Decision: Authorize generic synthetic graph version 1

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Context

The user directed Project Dexter to continue with steps to build the synthetic graph. Perspective Discovery has not been run, so no Work IQ-derived content is available for safe fictionalization. The accepted test plan permits wholly generic fictional content as a fallback.

## Decision

Authorize creation and disconnected validation of `gg-synthetic-graph-v1` using only generic fictional content and the accepted fixture specification version 1.0.

The authorized first construction step includes the valid baseline graph, an external fixture manifest, and later controlled mutation variants derived from that baseline. It excludes Graph Governor Skill implementation, packaging, Cowork upload, test execution, Work IQ access, OneDrive access, and real graph access.

## Alternatives considered

- **Wait for Perspective Discovery:** Not selected because generic fictional content can exercise the structural contracts without preventing a later perspective-informed fixture revision.
- **Use real or prior-project content:** Rejected because it would weaken privacy, isolation, and reproducibility.

## Consequences

- Fixture version 1 tests structure rather than personal relevance.
- A later perspective-informed fixture must receive a distinct version and separate hashes.
- Fixture validation is not Graph Governor test evidence.

## Follow-up

- Validate baseline structure, references, exact file inventory, and hashes.
- Create each mutation as a controlled baseline-derived variant and validate its declared delta.
- Obtain separate authorization before implementing Graph Governor.
