# Decision: Authorize Graph Governor source version 0.1.0-experimental

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Synthetic fixture construction validation](../test-results/2026-08-28-graph-governor-synthetic-fixture-validation.md)

## Context

The bounded read-only contract subset and implementation plan are accepted. The plan defines exactly three Markdown source files, disconnected static checks, and an explicit no-package and no-connected-test boundary. When asked whether to authorize that bounded source creation, the user selected “Authorize bounded source creation.”

## Decision

Authorize creation of source version `0.1.0-experimental` at `skills/graph-governor/`, containing only:

- `SKILL.md`;
- `references/read-only-contract.md`; and
- `references/evaluation-cases.md`.

Authorize local, disconnected static inspection of those files. Do not create a `.skill` package; execute Graph Governor against a fixture; access Copilot Cowork, Microsoft 365, Work IQ, OneDrive, or a real graph; or modify any graph.

## Alternatives considered

- **Stop with the accepted plan:** Not selected by the user.
- **Create and run a package immediately:** Not selected because package construction and connected execution remain separate gates.
- **Add scripts or fixture data to the source:** Rejected because the accepted plan permits only three Markdown files and keeps test answers outside the Skill.

## Consequences

- Graph Governor may advance to `developing` after source creation.
- Static inspection may establish source conformance only; it cannot establish runtime or scenario behavior.
- Any material responsibility or file-set change requires renewed review and authorization.

## Follow-up

- Create only the authorized source files and record exact static observations and hashes.
- Request separate package authorization only after source inspection completes without unresolved scope defects.
