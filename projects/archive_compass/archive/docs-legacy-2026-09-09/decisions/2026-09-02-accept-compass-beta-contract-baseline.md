# Decision: Accept Compass beta contract baseline

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Accepted sources:** [Compass Shared Contracts Specification 0.3](../specifications/compass-shared-contracts-specification.md); [Compass Graph Schema Specification 0.3](../specifications/compass-graph-schema-specification.md)
- **Preceding authority:** [Gate 0 contract-baseline slice](2026-09-02-propose-gate-0-contract-baseline-slice.md)

## Context

Slice A produced one compatible proposed baseline for the five Compass Skills and their Orchestration. It defines the minimum shared identity, relationship, configuration, authority, handoff, validation, Daily Log, conflict, recovery, and outcome behavior needed for responsibility design while preserving explicit deferrals.

## Decision

Accept the Shared Contracts Specification and Graph Schema Specification together as version `0.3-beta-baseline`.

This acceptance closes Slice A and authorizes Slice B of the [full-beta candidate assembly plan](../specifications/2026-09-02-compass-full-beta-candidate-assembly-plan.md): creation or revision of responsibility specifications for Installation Interview, Daily Scan, Tracking Topic Interview, Curator, and Graph Governor.

The accepted baseline retains these deferrals:

- final last-activity semantics;
- item-level evidence retention;
- staleness automation;
- Person merge;
- CSP retirement; and
- production-scale transaction design.

The disposable-beta recovery protocol remains limited to isolated synthetic graphs and does not establish production readiness.

## Authorization boundary

This decision authorizes responsibility-specification work and disconnected consistency review only. It does not authorize Skill source implementation, Orchestration source, package creation, connected access, graph writes, test execution, beta launch, deployment, or release.

## Consequences

- All five responsibility specifications must claim compatibility with `0.3-beta-baseline`.
- Existing Graph Governor evidence remains scoped to its exact earlier read-only contract subset and package.
- Slice C cannot begin until the five Slice B specifications are accepted as one compatible set.