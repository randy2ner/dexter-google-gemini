# Compass Graph Governor Specification

## Document control

- **Status:** active
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-12
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-019` and `PR-041` through `PR-045`
- **Implementation authority:** Local Skill source, synthetic fixtures, disconnected validation, and packaging are authorized. Connected graph access, mutation, deployment, and release remain unauthorized.

## Purpose and applicability

Graph Governor protects the portable Compass graph contract before and after another Skill attempts a durable change. It validates structure, stable identity, relationships, preservation, paths, change indexing, and effect truth without deciding whether customer content is substantively correct.

## Scope and boundaries

- **In scope:** Configuration, YAML parsing, object schemas, IDs, references, cardinality, lifecycle invariants, filenames, folders, preservation, Daily Log entries, archive metadata, preflight proposals, and post-write verification.
- **Out of scope:** Work IQ retrieval, Activity meaning, lifecycle decisions, user intent, automatic repair, and mutation ownership.
- **Authority:** Governor is read-only. It returns validation findings and blockers; it does not grant or exercise another Skill's authority.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| GOV-001 | Validate graph configuration and required root folders. | Missing, ambiguous, or invalid configuration produces bounded blockers. | Accepted |
| GOV-002 | Parse YAML and Markdown structurally and preserve unknown fields and user-authored content. | Validation does not normalize or rewrite files as a side effect. | Accepted |
| GOV-003 | Validate canonical entity schemas, field types, required values, and timestamp syntax. | Every finding names the object, field, rule, and severity. | Accepted |
| GOV-004 | Validate unique stable IDs independently of paths, filenames, titles, and email addresses. | Duplicate or malformed identity blocks affected correlation or mutation. | Accepted |
| GOV-005 | Validate references, cardinalities, uniqueness, and disjoint participant sets. | No Effort has several CSPs and no Activity has several or missing dispositions. | Accepted |
| GOV-006 | Validate lifecycle and archive invariants. | Activity removal is invalid unless its Effort is archived and complete retained metadata is verified. | Accepted |
| GOV-007 | Validate readable filenames, object-type folders, and collision handling without treating paths as identity. | A collision or wrong folder is reported without overwrite or invented repair. | Accepted |
| GOV-008 | Validate proposed changes against a disclosed base state before mutation. | Preflight distinguishes valid operations, blockers, warnings, and unresolved intent. | Accepted |
| GOV-009 | Re-read and validate resulting files after mutation. | Postflight confirms observed state rather than trusting attempted operations. | Accepted |
| GOV-010 | Reconcile Daily Log entries with verified durable object effects. | Missing, duplicate, or false entries prevent a complete-success claim. | Accepted |
| GOV-011 | Never claim substantive factual correctness from structural validity. | Governor labels a valid Activity as structurally valid, not customer-verified or true. | Accepted |
| GOV-012 | Return a compact machine- and human-usable validation report. | The report identifies scope, base state, valid operations, blockers, warnings, observed effects, and unverified effects. | Accepted |

## Validation report contract

Governor returns:

- `scope`: graph root and objects inspected;
- `phase`: `preflight` or `postflight`;
- `validOperations`: proposed or observed operations satisfying the graph contract;
- `blockers`: rule, object ID or path, field, and required resolution;
- `warnings`: non-blocking uncertainty or preservation concern;
- `observedEffects`: postflight-only verified durable effects;
- `unverifiedEffects`: attempted or expected effects not established by read-back; and
- `result`: `valid`, `valid-with-warnings`, `blocked`, or `partial`.

## Skills and orchestration

Installation, Activity Scan, and Curator invoke Governor before and after their own graph mutations. The initiating Skill retains responsibility for purpose, user interaction, authority, mutation, and recovery. Governor receives the graph scope, proposed operations, base-state evidence, and expected Daily Log effects; it returns validation only.

## Failure and cancellation

- Unsafe YAML parsing, duplicate IDs, unresolved references, invalid cardinality, or incomplete archive metadata blocks the affected operation.
- Missing access is reported as unverified rather than valid.
- Governor never repairs a graph, invents an ID, chooses a filename, supplies an Effort disposition, or retries a write.
- Cancellation returns no mutation because Governor performs none.

## Implementation status

- **Implemented:** `compass-graph-governor` `0.1.0-local-candidate`, runtime validation contract, importable package, canonical graph schema, orchestration handoffs, and synthetic fixture.
- **Not implemented:** Verified Cowork adaptation and observed runtime behavior.

## Test Plans

- [Graph Governor Test Plan](../test-plans/graph-governor.md)
- [Customer Work Lifecycle Test Plan](../test-plans/customer-work-lifecycle.md)

## Acceptance boundary

This Specification authorizes local implementation, fixtures, disconnected validation, and packaging. It does not authorize connected graph access, mutation, deployment, or release.