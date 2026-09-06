# Test result: native Cowork transport / ODT-001

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** None; native Cowork transport capability only
- **Test artifact:** Isolated OneDrive copy of the [GG-SYN-001 disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline)
- **Scenario/revision:** [ODT-001 isolated folder enumeration](../scenarios/onedrive-transport/odt-001-isolated-folder-enumeration.md), revision 1
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; clean session requested without Graph Governor
- **Input mechanism:** Cowork input button, “share a file or folder on your OneDrive” option
- **Link permission mode:** Not applicable to the observed Cowork run; the created link was not used
- **Result:** partial

## Execution notes

The user selected the graph root through Cowork's input button using its “share a file or folder on your OneDrive” option and reported Cowork's complete response. The separately created folder link was not used in Cowork. This deviates from the scenario's link-supply procedure and tests the native OneDrive object picker instead. The live link is not retained in this repository. No Graph Governor package or graph-health result was reported.

After the response, a read-only local filesystem check compared the exact isolated child with the pre-run repository reference. This check did not access the network or establish cloud synchronization state.

## Observed behavior

1. Cowork reported that the “folder link” was accessible, although the actual input was a folder selected through Cowork's native OneDrive object picker rather than a supplied link.
2. Cowork reported that recursive folder enumeration was available.
3. Cowork returned all six expected filenames, but omitted every containing directory and therefore did not preserve relative paths.
4. Cowork reported no unreadable or skipped files and no enumeration limitation.
5. Cowork reported `External changes: 0`.
6. Post-run local verification found exactly the expected recursive directory inventory and six files. Their bytes and SHA-256 values matched the pre-run reference.
7. No observation of parent, sibling, recent-file, email, Teams, Work IQ, SharePoint-site, or other OneDrive access was reported.

## Cowork response

> 1. Folder link accessible: **Yes**
> 2. Recursive folder enumeration available: **Yes**
> 3. Visible file paths:
> - `config.yaml`
> - `aurora-deployment-review.md`
> - `aurora-csp.md`
> - `2026-08-24.md`
> - `avery-stone.md`
> - `aurora-readiness.md`
> 4. Unreadable or skipped files: **None**
> 5. Permission or capability limitations: **None encountered for enumeration**
> 6. `External changes: 0`

The displayed response included Office file-type icon URLs before each filename. Those presentation-only URLs are omitted here; all returned text is preserved.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Restricted graph-root link is accessible | Not tested; Cowork accessed a graph-root object selected through its native OneDrive picker | deviation |
| Recursive enumeration preserves all six relative paths | All six basenames were returned, but directory components were omitted | mismatch |
| Files are readable or limitations are stated | Cowork reported none unreadable or skipped | match as reported |
| No access outside the supplied root | No outside access was reported | match as reported |
| No file or external change | Cowork reported zero; post-run local inventory and hashes matched | match within observed evidence |
| No Graph Governor invocation or graph-health claim | No invocation or health result was reported | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

Before-test hashes are recorded in the [OneDrive transport preflight](../experiments/2026-08-31-onedrive-transport-preflight.md). All six post-run values matched.

## Issues and risks

- **High:** Cowork's claim of recursive enumeration is not demonstrated by its output because the returned list flattened the hierarchy to basenames. Graph workflows cannot safely identify files from this result alone.
- **Medium:** The run exercised Cowork's native OneDrive object picker, not the scenario's restricted-link path. Picker selection does not establish restricted-link support or prove that Cowork's effective account permissions were limited to the selected child.
- **Medium:** The visible Cowork environment/version was not reported, limiting reproducibility.
- **Medium:** “Unreadable or skipped files: None” is Cowork's report; no returned file-content evidence independently demonstrates complete readability.
- **Low:** Local post-run hashes establish no locally synchronized byte change when checked, but do not independently audit every external action.
- A sharing URL was disclosed in conversation but was not used for the run. If creating it added a sharing grant or reusable link, that grant or link should be removed after evidence capture.

## Follow-up

- User / product owner: record the visible Cowork environment/version if still available.
- User / product owner: inspect OneDrive **Manage access** for the isolated child. Remove the unused link only if OneDrive lists it as a sharing link or added access grant; no removal is needed if no link or grant exists.
- Project Dexter: treat folder transport as partially observed; do not infer that Graph Governor can receive hierarchy-preserving graph inputs.
- Any retry that asks Cowork to prove relative paths requires a separately authorized scenario revision.

## Tester conclusion

ODT-001 is **partial with a procedure deviation**. Cowork's native OneDrive picker exposed all six expected filenames and the graph remained byte-identical after the run, but the restricted-link path was not tested and the response did not preserve required relative paths. This is native-picker transport evidence only and provides no Graph Governor, write, repair, Obsidian, or production-readiness evidence.