# Experiment notes: GG-SYN-004 preflight

## Hypothesis

Three separate isolated OneDrive roots can preserve the exact registered GG-SYN-004 valid baseline, M-006, and M-007 disposable graph bytes before the authorized runs, while the tested Graph Governor package retains its identity.

## Variables

- **Changed:** Created isolated OneDrive copies of the existing GG-SYN-004 valid baseline, M-006, and M-007 disposable graphs
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, registered mutation bytes, unaffected baseline bytes, and tested package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-004 execution authorization](../decisions/2026-08-31-authorize-gg-syn-004-execution.md), copied the repository's `gg-syn-004-valid-baseline`, `gg-syn-004-m-006`, and `gg-syn-004-m-007` disposable roots to same-named isolated children in the OneDrive `Compass-Test` laboratory area. The preparation failed rather than overwriting any existing destination. Read-only comparison then verified complete recursive directory inventories, relative paths, byte counts, and SHA-256 values against each repository source. The [tested Graph Governor package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) was separately verified at its exact path.

## Direct observations

1. All three destinations were newly created without overwriting another root.
2. Each isolated destination contains exactly six recursive directories and six files, with no extra or missing entry.
3. Every destination path, byte count, and SHA-256 value matches its same-named repository disposable source.
4. The valid baseline configuration is 96 bytes with SHA-256 `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1`.
5. The M-006 configuration replacement is 96 bytes with SHA-256 `c28c7fcb88ef0d9a13c79db59f5b24bff3d393c54c47ef2f7a266dd3664d8911`.
6. The M-007 configuration replacement is 98 bytes with SHA-256 `f1ab4f4e27169f1af6f2705edb6dc9763c279bfc5636b96ce3ee9d0eeecf0ea0`.
7. All non-configuration files match their registered baseline values.
8. Exact-path verification found the tested package at 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
9. No preparation or verification anomaly was observed.

### Valid-baseline before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

### M-006 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `c28c7fcb88ef0d9a13c79db59f5b24bff3d393c54c47ef2f7a266dd3664d8911` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

### M-007 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 98 | `f1ab4f4e27169f1af6f2705edb6dc9763c279bfc5636b96ce3ee9d0eeecf0ea0` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

All three isolated fixtures and the tested package satisfy the local GG-SYN-004 prerequisite identity gates. This does not establish cloud synchronization or any Graph Governor outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass
- **Related scenario:** [GG-SYN-004 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md), authorized and unexecuted
- **Follow-up:** Run the valid baseline first, preserve its response and post-run evidence, and review it before M-006