# Decision: Authorize Perspective Discovery 0.1.2 progressive interaction slice

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Adaptive Card controls are inaccessible](../findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md); [candidate review is too technical](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)

## Context

The exact `0.1.1-experimental` connected run respected the observed retrieval and no-change boundaries but ended `cancelled` when a long Cowork Adaptive Card made required candidate-review controls inaccessible. The user also decided that an explicit UTC fallback is preferable to blocking when Cowork exposes no reliable IANA timezone.

## Decision

Authorize a `0.1.2-experimental` corrective slice that:

- presents one short candidate per ordinary conversational turn;
- offers exactly `Keep`, `Change`, and `Leave out` as the first three choices;
- follows `Change` with `Edit wording`, `Make more general`, and `Back`;
- accepts questions in normal typed conversation;
- accepts typed `Pause`, `Stop`, and `Cancel` fallbacks;
- makes candidate ID, category, counts, and internal state available only on request;
- does not depend on Adaptive Card scrolling, resizing, or overflow;
- proposes a Cowork-exposed IANA timezone when available and otherwise visibly proposes `UTC` as a fallback;
- offers `Use <timezone>`, `Change timezone`, and `Cancel` before displaying the authorization plan; and
- preserves the accepted sources, limits, minimization, authorization, handoff, and no-change boundaries.

This decision authorizes source revision, deterministic package creation, disconnected package inspection, and one actual Cowork package-import smoke test using only the package's fixed synthetic interface preview. The smoke test may not access Work IQ, Email, Teams, a graph, files, or any external source or perform any external change.

## Alternatives considered

- **Depend on a scrollable container:** Not selected because Cowork host support is unverified.
- **Keep all choices in one card:** Not selected because the observed surface made required controls inaccessible.
- **Block when timezone is unavailable:** Not selected because a disclosed UTC fallback is adequate for this bounded discovery use.

## Consequences

- `0.1.0` and `0.1.1` packages and evidence remain unchanged.
- A successful smoke test can establish only interface operability for the observed synthetic branch.
- No Work IQ retrieval, connected discovery rerun, confidence assessment, deployment, or release is authorized.

## Follow-up

- Implement and inspect `0.1.2-experimental`.
- Run PD-UI-001 once using the exact package.
- Record the terminal smoke-test result before deciding whether any connected retrieval rerun is justified.