# Test plan: Graph Governor synthetic read-only slice

## Metadata

- **Owner:** User / product owner
- **Period:** 2026-08-28 through 2026-09-01
- **Skills/versions:** graph-governor `0.1.0-experimental`
- **Fixture/version:** [gg-synthetic-graph-v1](../../test-data/gg-synthetic-graph-v1/manifest.md), `1.0.0`
- **Status:** complete and closed with limitations; see the [accepted closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)

## Goals

- Determine whether an exact Graph Governor package can inspect a fictional Compass graph in Copilot Cowork.
- Validate bounded schema, relationship, configuration, and Daily Log marker reporting.
- Verify that graph content remains data and cannot widen authority.
- Verify that the first slice makes no changes and refuses repair requests.
- Produce traceable evidence tied to exact package, fixture, scenario, and visible Cowork environment versions.

## Out of scope

- Real Microsoft 365, Work IQ, OneDrive, SharePoint, Obsidian, customer, or personal data
- Graph writes, repair, rollback, recovery, conditional persistence, and concurrency
- Source Conversation ID discovery or validation against live runtime fields
- Windows-to-IANA runtime mapping
- Last-activity enforcement
- Daily Scan, Installation, Tracking Topic Interview, Curator, or cross-Skill integration
- Deployment, release, publication, or readiness claims beyond the executed scenarios

## Environments

- Local static inspection of source, package, and fixture before upload
- One explicitly authorized Copilot Cowork test environment using only the exact synthetic fixture and exact packaged specimen

## Scenario matrix

| Scenario | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| [Valid baseline](../scenarios/graph-governor-synthetic-read-only/gg-syn-001-valid-baseline.md) | high | Local review and Cowork | User | [passed 2026-08-31](../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md) |
| [YAML and required fields](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md) | high | Cowork | User | [M-001 passed](../test-results/2026-08-31-graph-governor-gg-syn-002-m-001.md) and [M-002 passed](../test-results/2026-08-31-graph-governor-gg-syn-002-m-002.md) on 2026-08-31 |
| [Relationship integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md) | high | Cowork | User | [M-003](../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md), [M-004](../test-results/2026-08-31-graph-governor-gg-syn-003-m-004.md), and [M-005](../test-results/2026-08-31-graph-governor-gg-syn-003-m-005.md) passed on 2026-08-31 |
| [Configuration integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md) | high | Cowork | User | [valid baseline](../test-results/2026-08-31-graph-governor-gg-syn-004-valid-baseline.md), [M-006](../test-results/2026-08-31-graph-governor-gg-syn-004-m-006.md), and [M-007](../test-results/2026-08-31-graph-governor-gg-syn-004-m-007.md) passed on 2026-08-31 |
| [Daily Log markers](../scenarios/graph-governor-synthetic-read-only/gg-syn-005-daily-log-markers.md) | high | Cowork | User | [M-008 passed on 2026-08-31](../test-results/2026-08-31-graph-governor-gg-syn-005-m-008.md) |
| [Unknown content](../scenarios/graph-governor-synthetic-read-only/gg-syn-006-unknown-content.md) | medium | Cowork | User | [M-009 passed on 2026-08-31](../test-results/2026-08-31-graph-governor-gg-syn-006-m-009.md) |
| [Injection and write refusal](../scenarios/graph-governor-synthetic-read-only/gg-syn-007-injection-and-write-refusal.md) | high | Cowork | User | [M-010 two-turn run passed on 2026-08-31](../test-results/2026-08-31-graph-governor-gg-syn-007-m-010.md) |
| [Bounded honest report](../scenarios/graph-governor-synthetic-read-only/gg-syn-008-bounded-honest-report.md) | high | Cowork | User | [primary combined-fixture run passed on 2026-08-31](../test-results/2026-08-31-graph-governor-gg-syn-008-combined-m002-m003.md); file-order variation unexecuted |

## Entry criteria

- If the fixture will reflect the user's perspective, the separate Work IQ Perspective Discovery plan has completed with an approved minimized brief and reviewed fictionalization record. Perspective discovery may be skipped in favor of wholly generic fictional content.
- The proposed first-slice decision is explicitly accepted.
- The exact shared-contract, graph-schema, Graph Governor, and fixture-specification subsets exercised by these scenarios are approved and versioned.
- Synthetic fixture creation and Graph Governor implementation are explicitly authorized.
- Source review confirms the Skill is read-only and contains no credentials, live identifiers, external-data dependencies, or undisclosed tools.
- Local fixture checks confirm declared mutations, deterministic hashes, and absence of secrets or personal data.
- The package has a root `SKILL.md`, a unique experimental version, an inventory entry, and a recorded SHA-256.
- The exact package is copied—not rebuilt—into `skill-exchange/ready-for-test/`.
- Cowork upload and execution are explicitly authorized for the exact package, fixture, scenarios, environment, and no-write boundary.
- Cleanup steps are understood and no production graph is accessible to the test.

## Entry readiness as of 2026-08-28

| Gate | Status | Evidence or blocker |
| --- | --- | --- |
| Generic fictional fixture path selected | satisfied | Perspective discovery was skipped for this fixture; the manifest declares wholly generic fictional content. |
| First-slice decision accepted | satisfied | [Accepted first-slice decision](../decisions/2026-08-28-graph-governor-first-test-slice.md) |
| Fixture creation authorized and validated | satisfied for disconnected construction | [Fixture validation result](../test-results/2026-08-28-graph-governor-synthetic-fixture-validation.md) |
| Exact bounded contract subset approved | satisfied | [Accepted read-only subset](../decisions/2026-08-28-graph-governor-read-only-contract-subset.md) |
| Graph Governor implementation plan reviewed | satisfied | [Accepted implementation plan](../specifications/graph-governor-read-only-implementation-plan.md) and [acceptance decision](../decisions/2026-08-28-accept-graph-governor-read-only-implementation-plan.md) |
| Graph Governor source implementation authorized | satisfied | [Bounded source authorization](../decisions/2026-08-28-authorize-graph-governor-source-v0-1-0.md) permits exactly three Markdown files and disconnected checks. |
| Source static inspection complete | satisfied for exact source hashes | [Disconnected source inspection](../test-results/2026-08-28-graph-governor-source-static-inspection.md) |
| Package creation and disconnected inspection authorized | satisfied | [Package authorization](../decisions/2026-08-28-authorize-graph-governor-package-v0-1-0.md) |
| Exact package checks complete | satisfied | [Package inspection](../test-results/2026-08-28-graph-governor-package-inspection.md); SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1` |
| OneDrive folder transport established | satisfied for one isolated six-file baseline through the native picker | [ODT-002](../scenarios/onedrive-transport/odt-002-native-picker-hierarchy-and-readability.md) passed with all six relative paths and bounded readability probes; [ODT-001](../scenarios/onedrive-transport/odt-001-isolated-folder-enumeration.md) remains partial historical evidence. Neither is a Graph Governor scenario. |
| Cowork upload and scenario execution authorized | completed through the GG-SYN-008 primary run | The [GG-SYN-008 authorization](../decisions/2026-08-31-authorize-gg-syn-008-execution.md) is fully exercised and its result is preserved. No retry, file-order variation, or later lifecycle step is authorized. |

The readiness table records gate state only. It does not itself approve a pending gate or authorize the next lifecycle stage.

## Exit criteria

- Every scenario has one immutable dated result marked pass, partial, fail, or blocked.
- Results identify exact package hash, fixture version and hash, scenario revision, and visible Cowork environment.
- Before/after fixture hashes establish whether any file changed.
- Observations remain separate from interpretation.
- Failures and blocked runs are preserved rather than overwritten.
- A confidence assessment states only what the executed evidence supports.
- Any source or contract revision creates a new package version and reruns affected scenarios.

## Closure assessment as of 2026-09-01

| Exit criterion | Status | Evidence or limitation |
| --- | --- | --- |
| Every scenario has an immutable dated result | satisfied for all eight primary scenarios | The scenario matrix links 13 passing primary fixture-run records. The GG-SYN-008 file-order variation is optional, unmanifested, and not required by the [closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md). |
| Exact package, fixture, scenario, and visible runtime identity recorded | satisfied with documented runtime limitation | Package hash, fixture version and hashes, and scenario revision are recorded. Exact Cowork version, model, and configuration were not reported and are accepted as a reproducibility limitation rather than reconstructed. |
| Before/after hashes establish whether supplied fixture files changed | satisfied | Every primary run has post-run recursive byte and SHA-256 comparison evidence; no change was found. |
| Observations remain separate from interpretation | satisfied | Dated result records separate observed behavior, expected-versus-actual assessment, risks, and conclusions. |
| Failures and blocked records are preserved | satisfied | Historical transport limitations, provisional decisions, prompt ambiguity, and superseding decisions remain preserved. |
| Bounded confidence assessment exists | satisfied | [Graph Governor 0.1.0-experimental confidence assessment](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md) |
| Changes require reassessment and affected reruns | satisfied as a future condition | The confidence assessment defines source, package, contract, schema, fixture, runtime, and scope triggers. No rerun is authorized by closure. |

The primary synthetic read-only slice is closed. Closure supports continued controlled development only; it is not a deployment, release, production, real-graph, write, integration, or complete Compass readiness determination.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Cowork cannot inspect an attached graph hierarchy as expected | Test is blocked or tests a different interface | Record the limitation; do not simulate success or widen access. Revise packaging or fixture presentation in a new scenario revision. |
| Model reports expected answers from fixture hints | False confidence | Keep expected outputs outside the graph and use controlled mutations with hidden manifest details. |
| Skill modifies a fixture despite the boundary | Integrity failure | Use disposable copies, read-only controls where available, and before/after hashes; stop further execution. |
| Synthetic behavior is generalized to real graphs | Unsupported readiness claim | State exclusions in every result and confidence assessment. |
| Draft contract changes invalidate fixtures | Stale test evidence | Record exact contract versions and rerun affected scenarios after version changes. |
| Package activates unexpectedly or accesses unrelated context | Privacy or scope violation | Use a clean bounded session, fictional data only, explicit prompt scope, and stop on any widened access. |
| Perspective-informed fixture content remains identifiable | Privacy and reproducibility risk | Use only the approved minimized brief, replace all names and distinctive facts, and complete human fictionalization review before packaging. |

## Reporting

Create one dated result per run under `docs/test-results/` using the repository template. Link cross-run defects under `docs/findings/`, decisions under `docs/decisions/`, and the bounded readiness statement under `docs/confidence/`. Move the exact tested artifact from `ready-for-test/` to `tested/` without rebuilding it.
