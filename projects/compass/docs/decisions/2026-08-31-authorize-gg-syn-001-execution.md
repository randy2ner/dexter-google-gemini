# Decision: Authorize GG-SYN-001 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [ODT-002 passed result](../test-results/2026-08-31-odt-002-native-picker-hierarchy-and-readability.md)

## Context

ODT-002 established that the observed Cowork native OneDrive picker exposed the six-file fictional baseline with directory-qualified relative paths and bounded readability probes without a reported change. The exact Graph Governor package has passed disconnected package inspection but has never been uploaded or executed. The user authorized the next test and directed Project Dexter to prepare its prerequisites in the organizational OneDrive `Compass-Test` laboratory area.

## Decision

Authorize one execution of [GG-SYN-001 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-001-valid-baseline.md) using:

- Graph Governor package `0.1.0-experimental`, exactly 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`;
- one new isolated OneDrive `Compass-Test` copy of the unchanged [GG-SYN-001 disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline);
- Cowork's native OneDrive file-or-folder picker for the graph root; and
- one clean Cowork session and one read-only health-scan request.

This authorization permits creation and local verification of the isolated fictional OneDrive test copy, upload or import of only the exact package, one GG-SYN-001 invocation, and before/after verification of the copied fixture.

It does not authorize package rebuilding, another package or fixture, mutation scenarios, retries, graph modifications, repair, normalization, parent or sibling access, search, recent files, Microsoft 365 evidence retrieval, real data, Obsidian, or production use. The fixture manifest, expected results, scenarios, and repository must not be supplied to Cowork.

## Alternatives considered

- **Proceed to a mutation scenario first:** Rejected because the exact package has no Cowork runtime evidence on the valid baseline.
- **Reuse the ODT-001 isolated copy:** Rejected to keep transport evidence separate from Graph Governor runtime evidence.
- **Authorize the full GG-SYN matrix:** Rejected because one baseline run is the next bounded lifecycle gate.

## Consequences

- A passed prerequisite check permits one exact GG-SYN-001 run.
- Upload acceptance does not itself establish Skill invocation or correct behavior.
- Any package mismatch, outside-root access, modification, invented issue, or unsupported capability claim must be preserved as observed and stops expansion to later scenarios.
- No later GG-SYN scenario is authorized by this decision.

## Follow-up

- Project Dexter: create and verify only the isolated fictional OneDrive prerequisite and record its hashes.
- User / product owner: use the exact package, selected graph root, and test prompt supplied after prerequisite verification.
- Project Dexter: verify post-run hashes and record the immutable result before proposing another scenario.