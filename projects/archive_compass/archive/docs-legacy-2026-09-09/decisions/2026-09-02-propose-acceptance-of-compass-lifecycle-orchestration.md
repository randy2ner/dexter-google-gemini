# Decision: Accept Compass lifecycle Orchestration

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Definition:** [Compass work-memory lifecycle](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)
- **Governing plan:** [Full-beta candidate assembly plan](../specifications/2026-09-02-compass-full-beta-candidate-assembly-plan.md)

## Context

The accepted five-Skill responsibility set now has one proposed coordination definition covering entry-point routing, typed handoffs, approval renewal, Graph Governor validation and verification, Daily Log coupling, cancellation, common outcomes, and synthetic-only recovery.

## Decision

Accept `compass-work-memory-lifecycle` version `0.1-beta-candidate` and close Slice C.

This decision establishes the design sequence and handoff contract for the complete beta candidate. It authorizes planning and impact analysis for Slice D, but not source implementation or candidate construction.

## Compatibility basis

- Every entry point routes to one accountable Skill.
- Evidence access, graph inspection, proposal approval, and graph modification remain distinct authorities.
- Daily Scan cannot organize Topics; Curator cannot mutate; Graph Governor cannot choose semantic meaning.
- Every mutating path includes exact authority, a typed handoff, a same-operation Daily Log effect, Graph Governor pre-write validation, post-write verification, and honest effect accounting.
- Material proposal drift renews user authority.
- Recovery remains limited to an explicitly authorized disposable synthetic graph.
- Typed conversational paths prevent required controls from depending on inaccessible Adaptive Card overflow.

## Preserved limitations

- No executable Orchestration or complete Skill source set exists.
- No package or runtime evidence supports the proposed lifecycle.
- Source Conversation ID fields still require runtime characterization.
- Last activity, item-level evidence, staleness automation, Person merge, CSP retirement, and production persistence remain deferred.

## Authorization boundary

This decision authorizes Slice D planning and impact analysis only. Skill or Orchestration implementation, package creation, connected access, graph writes, test execution, beta launch, deployment, and release require a separate explicit decision.