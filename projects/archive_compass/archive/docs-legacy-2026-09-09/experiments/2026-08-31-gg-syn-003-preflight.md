# Experiment notes: GG-SYN-003 preflight

## Hypothesis

Three separate isolated OneDrive roots can preserve the exact registered M-003, M-004, and M-005 disposable graph bytes before the authorized GG-SYN-003 runs, while the tested Graph Governor package retains its identity.

## Variables

- **Changed:** Created isolated OneDrive copies of the existing M-003, M-004, and M-005 disposable graphs
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, registered mutation bytes, unaffected baseline bytes, and tested package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-003 execution authorization](../decisions/2026-08-31-authorize-gg-syn-003-execution.md), prepared same-named isolated children for the repository's `gg-syn-003-m-003`, `gg-syn-003-m-004`, and `gg-syn-003-m-005` disposable roots in the OneDrive `Compass-Test` laboratory area. Read-only comparison then verified complete recursive directory inventories, relative paths, byte counts, and SHA-256 values against each repository source. The [tested Graph Governor package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) was separately verified at its exact path.

The first preparation attempt encountered a Windows PowerShell 5.1 incompatibility with `New-Item -LiteralPath`; a corrected run was interrupted after the destination roots had been populated. A subsequent read-only fixture verification passed. That verification agent incorrectly searched unrelated roots for the package and reported a package failure; an exact-path-only package verification then passed. These tooling anomalies are not Cowork or Graph Governor evidence.

## Direct observations

1. Each isolated destination contains exactly six recursive directories and six files, with no extra or missing entry.
2. Every destination path, byte count, and SHA-256 value matches its same-named repository disposable source.
3. The M-003 Tracking Topic replacement is 349 bytes with SHA-256 `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439`.
4. The M-004 Conversation replacement is 570 bytes with SHA-256 `ba5df422052063a1627d6a37f0360e9eefc74dc63a76f45beaf980a57b728b0f`.
5. The M-005 Conversation replacement is 632 bytes with SHA-256 `da9b4ec0d2951e6eaaee4c97d5d82fcc4062e7ad20bc4d10c939473d5d76331d`.
6. All other fixture files match their registered baseline values.
7. Exact-path verification found the tested package at 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

### M-003 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` |

### M-004 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 570 | `ba5df422052063a1627d6a37f0360e9eefc74dc63a76f45beaf980a57b728b0f` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

### M-005 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 632 | `da9b4ec0d2951e6eaaee4c97d5d82fcc4062e7ad20bc4d10c939473d5d76331d` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

All three isolated fixtures and the tested package satisfy the local GG-SYN-003 prerequisite identity gates. This does not establish cloud synchronization or any Graph Governor outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass after recorded preparation and verification tooling anomalies
- **Related scenario:** [GG-SYN-003 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md), authorized and unexecuted
- **Follow-up:** Run M-003 first, preserve its response and post-run evidence, and review it before M-004