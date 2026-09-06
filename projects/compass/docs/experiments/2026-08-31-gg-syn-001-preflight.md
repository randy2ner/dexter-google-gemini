# Experiment notes: GG-SYN-001 preflight

## Hypothesis

An isolated OneDrive `Compass-Test` copy can preserve the exact GG-SYN-001 baseline hierarchy and bytes, while the separately stored ready-for-test package retains its inspected identity before the authorized Cowork run.

## Variables

- **Changed:** Created one new OneDrive laboratory parent and copied one fictional baseline into it
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, file bytes, and exact Graph Governor package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-001 execution authorization](../decisions/2026-08-31-authorize-gg-syn-001-execution.md), prepared a new OneDrive laboratory child named `Compass-Test` containing only `gg-syn-001-valid-baseline`. Compared its recursive directory inventory, relative paths, byte counts, and SHA-256 values with the [registered disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline). Separately verified—but did not copy or modify—the Graph Governor package then in `ready-for-test`; after the run, those exact bytes were moved to the [tested artifact location](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill).

The first preparation command verified the package but attempted to create the nested destination before its new `Compass-Test` parent and stopped with `FileNotFoundError`. It created and copied nothing. A corrected command created the parent first and then copied and verified the baseline. This setup history is separate from future Cowork effects.

## Direct observations

1. The new `Compass-Test` laboratory parent and its `gg-syn-001-valid-baseline` child were created.
2. The child contains exactly six expected directories and six expected files, with no additional entry.
3. Every copied file matches its repository source byte count and SHA-256 value.
4. The exact package remains 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
5. The package was not copied into OneDrive and neither source nor package was modified.

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

The local prerequisites satisfy the fixture and package identity gates for one authorized GG-SYN-001 run. This does not establish cloud synchronization, Cowork package import, Skill activation, or Graph Governor behavior.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass after one recorded no-op setup error
- **Related scenario:** [GG-SYN-001 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-001-valid-baseline.md), authorized and unexecuted
- **Follow-up:** Confirm OneDrive synchronization visibly, then use only the exact package and isolated graph root in one clean Cowork run