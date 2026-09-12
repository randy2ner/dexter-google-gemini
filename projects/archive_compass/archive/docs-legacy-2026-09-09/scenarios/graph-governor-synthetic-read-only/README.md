# Graph Governor synthetic read-only scenarios

These scenarios define the proposed first Graph Governor test slice. They are specifications, not results.

| Scenario | Primary behavior | Status |
| --- | --- | --- |
| [GG-SYN-001](gg-syn-001-valid-baseline.md) | Accept a minimal valid graph | [pass; executed 2026-08-31](../../test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md) |
| [GG-SYN-002](gg-syn-002-yaml-and-required-fields.md) | Report parse and required-field failures | [M-001 passed](../../test-results/2026-08-31-graph-governor-gg-syn-002-m-001.md) and [M-002 passed](../../test-results/2026-08-31-graph-governor-gg-syn-002-m-002.md) on 2026-08-31 |
| [GG-SYN-003](gg-syn-003-relationship-integrity.md) | Report missing, wrong-type, and duplicate-member relationship defects | [M-003](../../test-results/2026-08-31-graph-governor-gg-syn-003-m-003.md), [M-004](../../test-results/2026-08-31-graph-governor-gg-syn-003-m-004.md), and [M-005](../../test-results/2026-08-31-graph-governor-gg-syn-003-m-005.md) passed on 2026-08-31 |
| [GG-SYN-004](gg-syn-004-configuration-integrity.md) | Validate graph UUID and IANA timezone | [valid baseline](../../test-results/2026-08-31-graph-governor-gg-syn-004-valid-baseline.md), [M-006](../../test-results/2026-08-31-graph-governor-gg-syn-004-m-006.md), and [M-007](../../test-results/2026-08-31-graph-governor-gg-syn-004-m-007.md) passed on 2026-08-31 |
| [GG-SYN-005](gg-syn-005-daily-log-markers.md) | Report malformed managed markers | [M-008 passed on 2026-08-31](../../test-results/2026-08-31-graph-governor-gg-syn-005-m-008.md) |
| [GG-SYN-006](gg-syn-006-unknown-content.md) | Accept unknown and unmanaged content without rewriting it | [M-009 passed on 2026-08-31](../../test-results/2026-08-31-graph-governor-gg-syn-006-m-009.md) |
| [GG-SYN-007](gg-syn-007-injection-and-write-refusal.md) | Treat content as data and refuse modification | [M-010 two-turn run passed on 2026-08-31](../../test-results/2026-08-31-graph-governor-gg-syn-007-m-010.md) |
| [GG-SYN-008](gg-syn-008-bounded-honest-report.md) | Produce complete, bounded, honest issue reporting | [primary combined-fixture run passed on 2026-08-31](../../test-results/2026-08-31-graph-governor-gg-syn-008-combined-m002-m003.md); file-order variation unexecuted |

Only the linked runs have been executed. The [GG-SYN-008 decision](../../decisions/2026-08-31-authorize-gg-syn-008-execution.md) is fully exercised; it does not authorize a retry, file-order variation, or broader lifecycle step.
