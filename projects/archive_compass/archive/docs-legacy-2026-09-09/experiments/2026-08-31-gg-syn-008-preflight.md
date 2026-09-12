# Experiment notes: GG-SYN-008 preflight

## Hypothesis

One isolated OneDrive root can preserve the exact registered combined M-002/M-003 disposable graph bytes before the authorized GG-SYN-008 run, while the tested Graph Governor package retains its identity.

## Variables

- **Changed:** Created an isolated OneDrive copy of the existing combined M-002/M-003 disposable graph
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, registered mutation bytes, unaffected baseline bytes, and tested package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-008 execution authorization](../decisions/2026-08-31-authorize-gg-syn-008-execution.md), verified the repository's `gg-syn-008-combined-m002-m003` source and confirmed the destination did not exist. Copied the disposable root once to a same-named isolated child in the OneDrive `Compass-Test` laboratory area. Preparation would have stopped rather than overwrite an existing destination. Read-only comparison then verified the complete recursive directory inventory, relative paths, byte counts, and SHA-256 values against the repository source. The [tested Graph Governor package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) was separately verified at its exact path.

## Direct observations

1. The source existed with exactly six recursive directories and six files.
2. The destination was absent before preparation and was newly created without overwrite.
3. The destination contains exactly six recursive directories and six files, with no extra or missing entry.
4. Every destination path, byte count, and SHA-256 value matches the repository disposable source.
5. The M-002 Conversation replacement is 516 bytes with SHA-256 `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595`.
6. The M-003 Tracking Topic replacement is 349 bytes with SHA-256 `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439`.
7. All other fixture files match their registered baseline values.
8. Exact-path verification found the tested package at 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
9. No preparation or verification anomaly was observed.

### Combined fixture before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` |

## Interpretation

The isolated fixture and tested package satisfy the local GG-SYN-008 prerequisite identity gates. This does not establish cloud synchronization, complete issue reporting, bounded health claims, or any other Graph Governor outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass
- **Related scenario:** [GG-SYN-008 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-008-bounded-honest-report.md), authorized and unexecuted
- **Follow-up:** Run the exact prompt once, preserve the complete response, and perform post-run verification