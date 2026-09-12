# Decision: Authorize Gate 0 contract-baseline slice

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Prior Skills require reconciliation](../findings/2026-08-28-prior-skill-static-review.md); [full-beta assembly impact assessment](../specifications/2026-09-02-full-beta-candidate-assembly-impact-assessment.md)

## Context

The compact full-beta strategy requires five compatible Skills and one Orchestration. Current shared contracts and graph schema contain the needed principles but remain broader drafts with unresolved fields and a deferred persistence protocol. Authoring write-capable Skills before selecting a common baseline would duplicate decisions and risk incompatible behavior.

## Decision

Authorize Slice A of the [full-beta candidate assembly plan](../specifications/2026-09-02-compass-full-beta-candidate-assembly-plan.md): revise the shared contracts and graph schema into one minimum beta baseline for user review.

The revision may define only:

- stable graph, object, source-item, and source-Conversation identity;
- canonical relationship ownership;
- minimum graph configuration and timezone behavior;
- proposal, approval, and material-change rules;
- typed cross-Skill handoffs;
- validation before and after changes;
- Daily Log same-operation effects;
- conflict detection and a recoverable disposable-beta write protocol;
- common terminal outcomes and effect accounting; and
- preservation of unmanaged user content.

The revision must explicitly defer nonblocking last-activity semantics, item-level evidence retention, staleness automation, Person merge, CSP retirement, and production-scale transaction design.

This decision authorizes specification revision and disconnected consistency review only. It does not authorize Skill or Orchestration implementation, package creation, connected access, graph writes, test execution, beta launch, deployment, or release.

## Alternatives considered

- **Define each Skill first:** Rejected because shared identity, write, and recovery behavior would be repeated or inconsistent.
- **Accept every current draft section:** Rejected because several deferred decisions are unnecessary for the minimum beta lifecycle.
- **Implement prior packages directly:** Rejected because their responsibility and architecture assumptions conflict with current Compass sources.

## Consequences

- One compact accepted baseline can govern all five Skill specifications and the Orchestration.
- Product semantics not required for beta remain visible but do not block progress.
- No runtime or implementation risk is introduced by the specification-only slice.

## Follow-up

- Prepare one focused shared-contract and schema revision for review.
- User separately accepts, revises, or declines the resulting beta baseline.
- Do not begin Slice B until the Slice A baseline is accepted.