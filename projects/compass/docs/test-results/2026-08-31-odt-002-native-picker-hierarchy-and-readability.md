# Test result: native Cowork transport / ODT-002

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** None; native Cowork transport capability only
- **Test artifact:** Existing isolated OneDrive copy of the [GG-SYN-001 disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline)
- **Scenario/revision:** [ODT-002 native picker hierarchy and readability](../scenarios/onedrive-transport/odt-002-native-picker-hierarchy-and-readability.md), revision 1
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; clean session requested without Graph Governor
- **Input mechanism:** Cowork native OneDrive file-or-folder picker
- **Selected object name:** Not separately reported; response identified content relative to the selected root
- **Permission prompts or errors:** None reported
- **Result:** pass

## Execution notes

The [ODT-002 preflight](../experiments/2026-08-31-odt-002-preflight.md) passed before execution. The user selected the existing isolated fictional baseline through Cowork's native OneDrive picker and submitted the exact revision 1 prompt once. The user then supplied the complete response reproduced below.

After Cowork responded, a read-only local filesystem comparison checked the exact isolated child against the repository reference and preflight evidence. The post-test check did not access the network, inspect sibling content, or infer cloud synchronization state.

## Observed behavior

1. Cowork returned all six expected directory-qualified relative paths.
2. Cowork labeled every path `interface-exposed`; no path was labeled or presented as inferred.
3. Cowork labeled every file readable.
4. The YAML top-level key probe matched the repository-side expectation in file order.
5. All five Markdown frontmatter-type and first-H1 probes matched repository-side expectations.
6. Cowork reported no limitation for any file.
7. Cowork reported `Outside-root access: 0` and `External changes: 0`.
8. No Graph Governor invocation, graph-health result, permission prompt, error, or outside-root content was reported.
9. Post-test local verification found the same recursive directory inventory and exactly six files, with all byte counts and SHA-256 values matching the preflight and repository reference.

## Cowork response

| Relative path from selected root | Path source | Readable | Minimal probe | Limitation |
| --- | --- | --- | --- | --- |
| `_compass/config.yaml` | `interface-exposed` | yes | Top-level keys: `schemaVersion`, `graphId`, `timezone` | none |
| `conversations/aurora-deployment-review.md` | `interface-exposed` | yes | type: `conversation`; H1: `Aurora Deployment Review` | none |
| `csps/aurora-csp.md` | `interface-exposed` | yes | type: `csp`; H1: `Aurora Service Continuity` | none |
| `daily-logs/2026-08-24.md` | `interface-exposed` | yes | type: `daily-log`; H1: `2026-08-24` | none |
| `people/avery-stone.md` | `interface-exposed` | yes | type: `person`; H1: `Avery Stone` | none |
| `tracking-topics/aurora-readiness.md` | `interface-exposed` | yes | type: `tracking-topic`; H1: `Aurora Readiness` | none |

> Outside-root access: 0
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Only the selected graph root is processed | Cowork reported zero outside-root access; no outside content was reported | match within observed evidence |
| Six exact interface-exposed relative paths | All six expected directory-qualified paths returned as `interface-exposed` | match |
| Honest unavailable labeling instead of inference | No path was unavailable; all were explicitly labeled interface-exposed | match as reported |
| Six bounded readability probes | Every probe matched its repository-side expected value | match |
| Limitations and skipped files disclosed | Every row reported no limitation; all six were marked readable | match as reported |
| Zero external changes | Cowork reported zero; post-test inventory and hashes matched | match within observed evidence |
| No Graph Governor behavior | No Graph Governor invocation or result reported | match |

## Evidence

| Relative path | Post-test bytes | Post-test SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

All post-test paths, directory entries, bytes, and hashes matched the [preflight record](../experiments/2026-08-31-odt-002-preflight.md) and repository reference.

## Issues and risks

- The visible Cowork environment/version and displayed selected-object name were not separately reported, which limits exact environment reproducibility.
- `interface-exposed`, readability, and outside-root access are Cowork-reported observations. The matching bounded probes corroborate file readability, while local hashes corroborate unchanged synchronized bytes; neither independently audits Cowork's complete permission surface.
- This single valid-baseline run does not establish native-picker behavior for mutation folders, larger vaults, duplicate basenames, hidden files, unsupported formats, writes, repairs, or Obsidian.
- This result does not test the Graph Governor package.

## Follow-up

- Preserve this result and ODT-001 as separate historical evidence.
- Treat the native OneDrive picker as established for one six-file fictional baseline in the observed environment only.
- Reassess the Graph Governor test-plan gate using this result, but obtain separate explicit authorization before package upload or any GG-SYN execution.
- Preserve or delete the isolated OneDrive copy only through a separately reported user-controlled cleanup action.

## Tester conclusion

ODT-002 revision 1 **passed**. In the observed run, Cowork's native OneDrive picker supplied all six exact relative paths and bounded readability probes without a reported outside-root access or external change, and post-test local inventory and hashes matched. This is transport evidence only; it provides no Graph Governor, write, repair, Obsidian, or production-readiness evidence.