# Decision: Adopt compact full-beta test strategy

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery Adaptive Card controls are inaccessible](../findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md); [prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Context

Compass testing has become too cumbersome relative to the decision value of repeated narrow scenarios. Most observed Skill behavior has matched expectations, which is consistent with using simple instructions on an established Copilot Cowork surface. The remaining consequential uncertainty is concentrated in host-surface behavior, connected graph writes and recovery, cross-Skill handoffs, authority and privacy boundaries, and the quality of the complete experience.

Daily Scan and Tracking Topic Interview still require reconciliation, Curator has no Dexter source, Installation Interview is incomplete, and no Compass Orchestration exists. A full beta therefore requires completing the candidate Skill set and Orchestration before evaluating the product as a whole.

## Decision

Adopt the [Compass compact full-beta readiness and behavior strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md).

Before beta, execute no more than seven decision-oriented checks by default:

1. three quick AI-surface probes;
2. three isolated critical-operation tests; and
3. one complete synthetic Orchestration rehearsal.

Reuse applicable prior evidence. Do not repeat simple positive paths for every Skill, field, or requirement. Add or rerun a check only when its result can change beta admission, implementation, risk treatment, or a confidence claim.

After those gates pass, run the complete beta through natural use of all five Skills and the accepted Orchestration. Use beta primarily to shape usefulness, trust, interruption, conversational flow, and personality rather than to repeat scripted mechanics.

This decision accepts the strategy and authorizes planning and impact analysis for beta-candidate assembly. It does not authorize Skill or Orchestration implementation, connected retrieval, graph writes, package execution, beta launch, deployment, or release. Each implementation or connected phase still requires a concise decision identifying its scope and, when applicable, exact packages, environment, data boundary, and recovery plan.

## Alternatives considered

- **Continue one scenario per behavior or requirement:** Rejected because it produces excessive execution and review overhead with diminishing decision value.
- **Enter beta with the current partial Skill set:** Rejected because incomplete capabilities would test a different product and obscure Orchestration and personality findings.
- **Skip isolated critical operations and test only end to end:** Rejected because failures in identity, writes, conflict handling, or recovery would be difficult to diagnose and could affect durable user data.

## Consequences

- Existing immutable results remain valid within their recorded scope.
- The authorized Perspective Discovery `0.1.2` interface smoke becomes part of the first AI-surface probe rather than a separate test program.
- Pre-beta evidence is consolidated by gate instead of producing a large result set for simple checks.
- Full beta admission requires exact candidate packages for all five Skills and one versioned Compass Orchestration.
- Personality is shaped from natural beta use after critical mechanics and boundaries are demonstrated.

## Follow-up

- Reconcile or create the five beta-candidate Skills and define the complete Compass Orchestration.
- Prepare exact candidate packages and a disposable synthetic beta graph.
- Seek one concise authorization for the three surface probes when the candidate set is ready.