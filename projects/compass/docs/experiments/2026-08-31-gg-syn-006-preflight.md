# Experiment notes: GG-SYN-006 preflight

## Hypothesis

One isolated OneDrive root can preserve the exact registered M-009 disposable graph bytes before the authorized GG-SYN-006 run, while the tested Graph Governor package retains its identity.

## Variables

- **Changed:** Created an isolated OneDrive copy of the existing M-009 disposable graph
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, registered mutation bytes, unaffected baseline bytes, and tested package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-006 execution authorization](../decisions/2026-08-31-authorize-gg-syn-006-execution.md), copied the repository's `gg-syn-006-m-009` disposable root to a same-named isolated child in the OneDrive `Compass-Test` laboratory area. Preparation failed rather than overwriting an existing destination. Read-only comparison then verified the complete recursive directory inventory, relative paths, byte counts, and SHA-256 values against the repository source. The [tested Graph Governor package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) was separately verified at its exact path.

## Direct observations

1. The destination was newly created without overwriting another root.
2. The destination contains exactly six recursive directories and six files, with no extra or missing entry.
3. Every destination path, byte count, and SHA-256 value matches the repository disposable source.
4. The M-009 Person replacement is 433 bytes with SHA-256 `5fe76f1328d77b911528c542b1fbd5c20a9a1bd085a20eed4dc8af97727c3b53`.
5. All other fixture files match their registered baseline values.
6. Exact-path verification found the tested package at 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
7. No preparation or verification anomaly was observed.

### M-009 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 433 | `5fe76f1328d77b911528c542b1fbd5c20a9a1bd085a20eed4dc8af97727c3b53` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

The isolated fixture and tested package satisfy the local GG-SYN-006 prerequisite identity gates. This does not establish cloud synchronization or any Graph Governor outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass
- **Related scenario:** [GG-SYN-006 revision 2](../scenarios/graph-governor-synthetic-read-only/gg-syn-006-unknown-content.md), authorized and unexecuted
- **Follow-up:** Run M-009 once, then preserve its response and post-run evidence