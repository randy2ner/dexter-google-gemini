# Decision: Declare the production release-testing milestone

- **Date:** 2026-09-08
- **Status:** accepted
- **Decider:** User / product owner
- **Milestone:** Transition from synthetic testing to production release testing
- **Applies to:** Compass production-content candidate set and lifecycle orchestration
- **Sequencing update:** [Artifact-first production shaping](2026-09-08-adopt-artifact-first-production-shaping.md) now precedes the controlled exact-package release test

## Context

Compass has completed the synthetic and disconnected work needed to establish its graph schema, YAML and relationship rules, Skill responsibility boundaries, production evidence contract, deterministic packages, and privacy-minimized test method. The exact five-Skill production-content candidate set has passed static source and package validation.

The next useful evidence must come from real, user-authorized production work context on the target Cowork surface. Continuing to treat synthetic fixtures as the primary release signal would not test native Work IQ coverage, production object quality, conversational review, durable writes, persistence, or the complete lifecycle under actual permissions.

## Decision

1. Compass has reached the milestone that ends synthetic testing as the primary product-validation phase.
2. The current project stage is **production release testing** using the exact registered production-content candidate packages.
3. Production release testing uses real user-authorized work evidence and builds real Compass production content; it does not substitute sample, fictional, fixture, or synthetic data.
4. Synthetic fixtures remain retained regression assets for focused defect diagnosis, schema checks, and destructive-boundary tests. They are supporting evidence, not substitutes for production release-test outcomes.
5. The active release-test route is the mediated production-content journey in `PROD-WIQ-001` through `PROD-WIQ-008`, with the user operating Cowork in an approved company-managed environment.
6. Work content remains private on the managed surface. Dexter receives only privacy-minimized capability observations, counts, decisions, coverage status, interaction findings, Governor outcomes, and effect accounting.
7. This milestone authorizes the release-testing phase. It does not declare Compass released, approve deployment, prove runtime behavior, authorize automatic export, or authorize submission to a model-training system.
8. A production release decision requires observed evidence from the exact packages, independent inspection of durable effects, resolution or explicit acceptance of material findings, and a separate user decision.

## Milestone evidence

- Accepted Charter and current PRD.
- Shared Contracts `0.8-production-evidence-baseline` and Graph Schema `0.7-hpi-narrative-baseline` / schema version 2.
- Five production-test candidate Skills and lifecycle orchestration `0.7.0-production-test-candidate`.
- Deterministic package validation, exact hashes, and exclusion of evaluation fixtures from runtime packages.
- Production-content and native Work IQ test plan with privacy-minimized evidence handling.

## Consequences

- Project status, package inventory, Skill Exchange, and test-plan language identify the current phase as production release testing.
- Future readiness claims prioritize evidence from real production journeys over broad synthetic scenario accumulation.
- Focused synthetic checks may still be run when a production finding needs safe reproduction or when a destructive boundary cannot be tested against production state.
- Prior synthetic results remain immutable and version-bound.
