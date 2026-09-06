# Decision: Authorize Perspective Discovery source version 0.1.0-experimental

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Context

Perspective Discovery specification version 1.0 is accepted. The implementation plan defines exactly three Markdown source files and disconnected static checks. The user stated, “I accept,” in response to that plan.

## Decision

Authorize creation of source version `0.1.0-experimental` at `skills/compass-installation-perspective-discovery/`, containing only:

- `SKILL.md`;
- `references/behavior-contract.md`; and
- `references/evaluation-cases.md`.

Authorize local, disconnected static inspection of those files. Do not create a `.skill` package or access Copilot Cowork, Work IQ, Microsoft 365, OneDrive, or a graph.

## Alternatives considered

- **Create and upload the package immediately:** Not selected because package and connected-test review remain separate gates.
- **Modify the received Installation Beta 1:** Not selected because received specimens remain immutable and its mixed responsibilities conflict with the accepted slice.

## Consequences

- The Skill may advance from `idea` to `developing` after source creation.
- Static checks may establish source conformance but cannot establish runtime behavior.
- Any material scope change requires review against specification version 1.0.

## Follow-up

- Inspect source and record direct static observations.
- Request separate package authorization only after static checks complete without unresolved scope defects.
