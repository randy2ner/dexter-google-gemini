# Experiment notes: OneDrive transport preflight

## Hypothesis

A locally synchronized fictional GG-SYN-001 baseline copy can retain the exact six-file graph hierarchy and bytes before the authorized Cowork transport experiment.

## Variables

- **Changed:** User-controlled copy from the local disposable test area to an organizational OneDrive laboratory area
- **Held constant:** Fixture version `1.0.0`, all 13 disposable graph directory names, relative paths, and file bytes
- **Environment:** Local OneDrive synchronization directory on Windows; no Cowork access performed

## Method

Compared the user-provided OneDrive laboratory test-run tree with the local [disposable test-run tree](../../test-runs/2026-08-30) through read-only local filesystem inspection. The check compared child-directory inventory, relative file paths, byte counts, and SHA-256 values. It did not access the network or infer cloud synchronization status from local presence.

## Direct observations

1. The local OneDrive laboratory copy contained exactly the same 13 child graph directories as the local disposable test-run tree.
2. Each child contained exactly the expected six relative graph files.
3. All 78 corresponding files had equal byte counts and SHA-256 values.
4. The authorized ODT-001 child `gg-syn-001-valid-baseline` contained:

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

## Isolation preparation

With explicit user authorization, a new OneDrive laboratory parent named `odt-001-isolated` was created containing only a copied `gg-syn-001-valid-baseline` child. The initial copy attempt detected the nested fixture directories and copied no files. A corrected hierarchy-preserving copy then created the six expected directories and copied exactly the six expected files.

Post-copy local verification found no additional files or directories. Every destination file matched the verified source byte count and SHA-256 value listed above. The source was not modified, and no sibling mutation graph was copied into the isolated parent.

## Interpretation

The local OneDrive copy preserves the prepared fixture bytes and is suitable as a before-test reference. This does not establish that OneDrive cloud synchronization completed, that a restricted folder link prevents same-account access to siblings, or that Cowork can enumerate the folder.

Keeping all mutation folders under the same OneDrive parent is convenient for later preparation but provides weaker experimental isolation than a parent containing only the ODT-001 baseline. A link to the child does not by itself prove that a same-account Cowork environment lacks broader OneDrive permissions.

## Outcome

- **Hypothesis:** supported for local byte preservation only
- **Related results:** No Cowork result exists; [ODT-001](../scenarios/onedrive-transport/odt-001-isolated-folder-enumeration.md) remains unexecuted
- **Follow-up:** Confirm OneDrive synchronization visibly, create a restricted link to only the isolated baseline child, then perform only the authorized transport prompt and preserve the response