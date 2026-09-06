# Experiment notes: ODT-002 preflight

## Hypothesis

The existing isolated fictional baseline still exactly matches its repository reference before the authorized ODT-002 Cowork run.

## Variables

- **Changed:** None; read-only comparison only
- **Held constant:** Existing isolated `gg-syn-001-valid-baseline`, repository reference, relative hierarchy, and file bytes
- **Environment:** Local Windows filesystem and locally synchronized OneDrive directory; no network or Cowork access performed by this check

## Method

After [ODT-002 revision 1 execution was authorized](../decisions/2026-08-31-authorize-odt-002-execution.md), compared the exact isolated child with the [GG-SYN-001 disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline). The read-only check compared recursive directory inventory, relative file paths, byte counts, and SHA-256 values. It did not inspect OneDrive siblings, access the network, or infer cloud synchronization state.

## Direct observations

1. Recursive directory inventories matched exactly.
2. Both roots contained exactly the same six relative files and no additional files.
3. Every corresponding byte count and SHA-256 value matched.

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Interpretation

The local isolated fixture satisfies ODT-002's pre-test integrity gate. This result does not establish OneDrive cloud synchronization or any Cowork capability.

## Outcome

- **Hypothesis:** supported for local fixture integrity
- **Result:** pass
- **Related scenario:** [ODT-002 revision 1](../scenarios/onedrive-transport/odt-002-native-picker-hierarchy-and-readability.md), authorized and unexecuted at the time of this check
- **Follow-up:** User executes the exact prompt once through Cowork's native OneDrive picker and returns the complete response; Project Dexter then performs the post-test check