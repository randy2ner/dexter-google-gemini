# Experiment notes: GG-SYN-002 preflight

## Hypothesis

Two separate isolated OneDrive roots can preserve the exact registered M-001 and M-002 disposable graph bytes before the authorized GG-SYN-002 runs, while the tested Graph Governor package retains its identity.

## Variables

- **Changed:** Created isolated OneDrive copies of the existing M-001 and M-002 disposable graphs
- **Held constant:** Fixture version `1.0.0`, relative hierarchy, registered mutation bytes, all unaffected baseline bytes, and tested package bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; Cowork was not invoked during preparation

## Method

Under the [GG-SYN-002 execution authorization](../decisions/2026-08-31-authorize-gg-syn-002-execution.md), copied only the repository's `gg-syn-002-m-001` and `gg-syn-002-m-002` disposable roots into separate children of the OneDrive `Compass-Test` laboratory area. Compared recursive directory inventories, relative paths, byte counts, and SHA-256 values with their respective repository sources. Separately verified—but did not modify—the [tested Graph Governor package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill).

The initial preparation command used a .NET path API unavailable in Windows PowerShell 5.1 and stopped before completing the intended preparation. A compatible command then copied and verified exactly the two authorized roots. This setup-tool limitation is separate from future Cowork behavior.

## Direct observations

1. Both isolated destination roots contain exactly six directories and six files, with no additional entries.
2. Each destination's complete relative inventory, bytes, and SHA-256 values match its corresponding repository disposable source.
3. The M-001 Conversation replacement is 580 bytes with SHA-256 `5e2112ee0765b7d554c4478f62f30077508d44aedfc1c8e9ea0465e92d45f224`.
4. The M-002 Conversation replacement is 516 bytes with SHA-256 `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595`.
5. Every other file in each root matches the registered baseline byte count and SHA-256.
6. The tested package is 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

### M-001 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 580 | `5e2112ee0765b7d554c4478f62f30077508d44aedfc1c8e9ea0465e92d45f224` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

### M-002 before-test evidence

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

Both local isolated fixtures and the tested package satisfy the GG-SYN-002 prerequisite identity gates. This does not establish cloud synchronization or either Graph Governor outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass after one recorded compatibility-only setup error
- **Related scenario:** [GG-SYN-002 revision 1](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md), authorized and unexecuted
- **Follow-up:** Run M-001 first, preserve its response and post-run evidence, and review it before M-002