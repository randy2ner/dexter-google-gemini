# Decision: Authorize Perspective Discovery 0.1.1 focused connected run

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery candidate review is too technical](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)

## Context

The corrective `0.1.1-experimental` source and package passed [disconnected inspection](../test-results/2026-09-01-perspective-discovery-v0-1-1-source-and-package-inspection.md). The revision changes candidate-review presentation while preserving the accepted retrieval, privacy, authority, and no-change boundaries.

The user selected `Authorize one focused run` after reviewing the exact package identity and bounded scope.

## Decision

Authorize one clean Copilot Cowork conversation using only:

- package `compass-installation-perspective-discovery-v0.1.1-experimental.skill`;
- package size 7,038 bytes;
- SHA-256 `3b563deddd98d162574d49c87e12a631d17f6a2453b7b119e92eaba8f056e6d2`;
- confirmed timezone `America/New_York`;
- previous seven complete local dates 2026-08-25 through 2026-08-31;
- Email and Teams only;
- no more than 10 inspected evidence units per source and 20 total;
- reviewed generic patterns only, with no retained raw evidence or real identities;
- no graph, file, message, permission, automation, or other external change; and
- [PD-LEAN-001 revision 2](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md).

The user must still select `Run` only after the Skill displays a complete matching plan. Any mismatch invokes the scenario stop conditions.

## Alternatives considered

- **Review source again before authorization:** Available but not selected.
- **Stop Perspective Discovery:** Available but not selected.

## Consequences

- One import and connected conversation using the exact package are authorized.
- The conversation may retrieve only within the displayed approved boundary after `Run`.
- The user may ask questions, revise wording, leave candidates out, pause, or stop.
- A pass, partial, blocked, fail, cancelled, or empty observation must be recorded honestly.
- No repeat, expanded retrieval, package change, graph action, deployment, or release is authorized.

## Follow-up

- Conduct the one focused run.
- Preserve only the privacy-bounded evidence allowed by the scenario.
- Record one dated terminal result before assessing confidence or resolving the finding.