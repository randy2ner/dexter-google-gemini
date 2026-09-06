# Decision: Authorize experience-led rehearsal

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Related plan:** [Experience-led rehearsal plan](../test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md)
- **Session kit:** [Cowork experience rehearsal kit](../scenarios/compass-experience-led-rehearsal.md)

## Context

The product owner selected Option B and directed the laboratory assistant to continue with the next step. Preflight confirmed that all five exact package hashes match the session kit, the disposable materialized graph matches its external baseline, and the fixed fictional input exists.

## Decision

Authorize one Cowork experience rehearsal using:

1. the five exact `.skill` packages and hashes in the session kit;
2. `compass-work-memory-lifecycle` `0.1-beta-candidate` as the coordination definition;
3. only the `compass-beta-graph-v1` materialized graph as the write target;
4. only the fixed fictional Daily Scan input as source evidence; and
5. the opening prompt and compact observation sheet in the session kit.

The laboratory assistant may import and invoke the exact packages, provide the fixed fictional input, support the user's natural conversation, inspect the disposable graph, and record direct observations. The user retains every consequential approval during the conversation.

## Explicit exclusions

This decision does not authorize:

- opening, reading, or retaining real Email, Teams, OneDrive, or other work content;
- writing to any personal, synchronized, connected, or production graph;
- substituting another package, Skill, graph, or evidence source;
- beginning development beta;
- deployment, publication, or release; or
- treating package import or a partial journey as a successful rehearsal.

## Stop conditions

Stop on any condition listed in the rehearsal plan, any mismatch in package identity or graph boundary, or any Cowork requirement to broaden connected access beyond capability visibility.

## Consequences

- The experience-led rehearsal may begin when the Cowork page is shared.
- Runtime fields and observations remain blank until directly observed.
- Completion leads to one product-owner decision: continue toward beta, run a focused follow-up, revise the candidate, or stop.