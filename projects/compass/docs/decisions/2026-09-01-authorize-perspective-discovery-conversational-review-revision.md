# Decision: Authorize Perspective Discovery conversational review revision

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery candidate review is too technical](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)

## Context

The authorized Perspective Discovery connected run was paused during candidate review. The interaction exposed process terminology, a machine-like candidate ID, and abstract wording before establishing a natural explanation or question. Although the reported candidate was privacy-minimized, the user could not comfortably understand or control the review.

The accepted specification already requires a concise, respectful, curious interaction grounded in the user's language. Dexter's human-centered methodology treats comprehension, dignity, trust, and agency as product behavior.

On 2026-09-01, after reviewing Dexter's operational readiness, the user directed Dexter to proceed with the next steps in Compass development.

## Decision

Authorize the smallest corrective development slice:

- revise the three Perspective Discovery source files so candidate review leads with a short explanation, a natural question, and plain-language choices;
- keep required IDs, categories, evidence counts, and internal candidate states secondary to the conversation;
- add source version history and advance the source to `0.1.1-experimental`;
- perform disconnected static review;
- create and inspect one deterministic `0.1.1-experimental` package; and
- prepare one focused candidate-review rerun without executing connected retrieval or Cowork testing.

## Alternatives considered

- **Accept the current interaction as a limitation:** Rejected because it conflicts with the accepted interaction style and weakens meaningful user authority.
- **Redesign the full Installation Interview:** Rejected because it exceeds the observed defect and shaping-clay scope.
- **Repeat the unchanged package:** Rejected because repetition would not address the observed cause.

## Consequences

- The exact `0.1.0-experimental` package and its partial evidence remain unchanged as historical records.
- Version `0.1.1-experimental` will require a new package identity and cannot inherit runtime confidence from `0.1.0-experimental`.
- Safety, retrieval, minimization, and no-write boundaries remain unchanged.
- Connected import, retrieval, or rerun remains subject to a separate exact-package authorization after inspection.

## Follow-up

- Dexter revises and statically inspects the bounded source and package.
- Dexter updates living traceability and test-planning records for the focused candidate-review scope.
- The user reviews the new package identity and decides whether to authorize one connected rerun.