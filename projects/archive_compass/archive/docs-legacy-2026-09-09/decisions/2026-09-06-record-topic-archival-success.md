# Decision: Record Topic archival success

- **Date:** 2026-09-06
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** None; direct product-owner decision

## Context

Tracking Topics retain lifecycle state but previously did not distinguish whether an archived Topic achieved its intended outcome. The outcome applies only to archival and must not become stale state when a Topic is active again.

## Decision

Add the camelCase Tracking Topic YAML field `success` under object schema version 2.

- An archived Topic requires `success: true` or `success: false`.
- An active Topic may omit `success` or set it to YAML null.
- Reactivating an archived Topic removes `success` from frontmatter.
- Tracking Topic Interview asks for and previews the success choice before archival, including archival caused by merge.
- Graph Governor validates the status/success combination and exact authority. No Skill infers success from staleness, recency, completion language, merge, or graph content.

## Alternatives considered

- **Keep success in prose:** Rejected because the outcome would not be consistently queryable or structurally validated.
- **Retain success after reactivation:** Rejected because an archival outcome must not describe an active Topic's current lifecycle.
- **Add success as a third status:** Rejected because outcome and lifecycle state are independent concepts.

## Consequences

- The graph contract, Tracking Topic Interview, Graph Governor, lifecycle Orchestration, profiles, packages, and focused tests require coordinated revision.
- Existing schema-v2 active Topics remain valid when `success` is absent.
- Existing archived schema-v2 Topics without boolean `success` require an explicit user decision before they satisfy the revised living contract.
- Completed evidence and prior package bytes remain unchanged and version-bound.

## Follow-up

- Construct and statically validate a four-state fictional fixture.
- Package the revised Tracking Topic Interview and Graph Governor sources without replacing prior candidates.
- Execute the focused behavioral scenario only after separate product-owner authorization.