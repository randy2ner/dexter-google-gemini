# Test Plan: Perspective Discovery 0.1.2 interface smoke

## Document control

- **Date:** 2026-09-01
- **Status:** accepted and authorized for one exact-package run
- **Owner:** User / product owner
- **Version under test:** `0.1.2-experimental`

## Test objective

Evaluate only the corrective UI claims using the actual Cowork host and fixed synthetic preview, with no Work IQ or external source access.

## Selected scenario

| Scenario | Risk | Execution | Status |
| --- | --- | --- | --- |
| [PD-UI-001 progressive interaction smoke](../scenarios/workiq-perspective-discovery/pd-ui-001-progressive-interaction-smoke.md) | high | One clean Cowork conversation | Authorized after exact-package inspection |

## Entry criteria

- Source and package match the accepted corrective decision and impact assessment.
- Exact package name, size, hash, members, and member bytes are recorded.
- Package-local evaluation cases remain `UNRUN`.

## Exit criteria

- One terminal result is recorded as pass, partial, blocked, fail, or cancelled.
- No repeat is performed.
- The accessibility finding remains open unless the recorded evidence supports a separate resolution decision.

## Explicit exclusions

- Work IQ, Email, Teams, enterprise search, files, web, graph, and other source access.
- Real candidate content or production correctness.
- Connected retrieval, handoff, confidence, deployment, and release claims.