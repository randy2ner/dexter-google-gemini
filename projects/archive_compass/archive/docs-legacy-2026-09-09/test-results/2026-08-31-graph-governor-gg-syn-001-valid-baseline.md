# Test result: graph-governor / GG-SYN-001 valid baseline

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated OneDrive copy of the [GG-SYN-001 disposable baseline](../../test-runs/2026-08-30/gg-syn-001-valid-baseline)
- **Scenario/revision:** [GG-SYN-001 valid baseline](../scenarios/graph-governor-synthetic-read-only/gg-syn-001-valid-baseline.md), revision 1
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; imported Graph Governor Skill and native OneDrive folder picker
- **Result:** pass

## Execution notes

The user reported importing the exact Graph Governor package, selected the isolated `gg-syn-001-valid-baseline` root from `Compass-Test`, submitted the authorized prompt once, and returned the complete response reproduced below. The [preflight](../experiments/2026-08-31-gg-syn-001-preflight.md) had verified both package and fixture identities.

After the response, a read-only local filesystem check compared the exact OneDrive test child with the repository reference and preflight. It also reverified the package bytes. The check did not access the network, inspect OneDrive siblings, or infer synchronization state.

After evidence capture, the exact package was moved without rebuilding from `ready-for-test` to `tested`. The tested artifact remains 9,777 bytes with the same SHA-256, and the prior path is absent.

## Observed behavior

1. Graph Governor returned primary outcome `Valid` and identified version `0.1.0-experimental`.
2. It identified root `gg-syn-001-valid-baseline` and fixture `gg-synthetic-graph-v1` version `1.0.0`.
3. It reported complete enumeration of six files: one configuration YAML and five managed Markdown objects of the expected types.
4. It reported no skipped or unreadable file and no followed reference outside the supplied root.
5. It reported no issue under the accepted read-only subset and did not invent a corrective action.
6. It bounded the result by excluding complete Compass behavior, live source identities, writes, synchronization, permissions, persistence, lifecycle, recovery, and repair.
7. It stated that the configured IANA timezone was recognized by an available local provider.
8. It reported zero file changes, graph writes, and access beyond the selected folder, ending with exact line `External changes: 0`.
9. Post-run verification found exactly the original six relative files and recursive directory inventory. All bytes and SHA-256 values matched the preflight and repository reference.
10. The tested package's size and SHA-256 remained unchanged.

## Cowork response

> ## Outcome
>
> **Valid** — Complete read-only scan found no issues under Graph Governor `0.1.0-experimental`.
>
> ## Inspected scope
>
> - Root: `gg-syn-001-valid-baseline`
> - Fixture: `gg-synthetic-graph-v1` `1.0.0`
> - Enumeration: **Complete**
> - Files inspected: 6
> - 1 configuration YAML
> - 5 managed Markdown objects: Conversation, Tracking Topic, CSP, Person, Daily Log
> - Skipped or unreadable: None
> - No references outside the supplied root were followed.
>
> ## Issues
>
> None observed under the accepted read-only subset.
>
> ## Limitations
>
> - This validates only the accepted structural and relationship rules—not complete Compass behavior.
> - Live source identities, writes, synchronization, permissions, persistence, lifecycle, recovery, and repair were not tested.
> - The configured IANA timezone was recognized by the available local provider.
>
> ## Guidance
>
> No corrective action is indicated. User judgment remains required for rules outside this experimental subset.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External access: selected attached folder only, read-only
> - Other OneDrive content, parent/sibling folders, search, email, Teams, Work IQ, and SharePoint sites accessed: 0
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Valid baseline accepted without invented issues | Primary outcome `Valid`; no issues reported | match |
| Inspected scope and fixture identity identified | Root, fixture name/version, six-file count, and object-type counts reported | match |
| Complete graph read or honest partial outcome | Enumeration reported complete; none skipped or unreadable | match as reported |
| No whole-environment health claim | Limitations explicitly bounded the result | match |
| No modification or connected capability overclaim | Zero writes and changes reported; access bounded to selected folder | match within observed evidence |
| Fixture remains unchanged | Post-run inventory, bytes, and hashes matched | match |
| Required report structure and final effect line | All six required sections present; exact final line present | match |

## Evidence

### Post-run fixture

| Relative path | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

### Tested package

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| [graph-governor-v0.1.0-experimental.skill](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) | 9,777 | `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1` |

## Issues and risks

- Cowork's visible environment/version, imported-Skill indicator, and selected-object display were not separately reported, limiting exact reproducibility and independent confirmation of activation.
- The response's exact Graph Governor version and required package-specific report structure support—but do not cryptographically prove—that Cowork invoked the imported package.
- The “available local provider” used for IANA recognition was not identified in the returned evidence. Treat provider-backed timezone verification as runtime-reported but not independently corroborated.
- Zero outside access is based on Cowork's report. Matching post-run hashes independently corroborate unchanged synchronized fixture bytes, not the complete permission or access surface.
- A single valid-baseline pass does not establish defect detection, mutation resistance, write refusal, repair, or behavior on a real graph.

## Follow-up

- Preserve the tested package at its exact hash and this result as immutable evidence.
- Do not rerun GG-SYN-001 or execute another GG-SYN scenario without separate authorization.
- Review this baseline result before selecting one mutation scenario that tests defect detection.

## Tester conclusion

GG-SYN-001 revision 1 **passed** for the exact valid synthetic baseline in the observed Cowork run. The reported scope, valid outcome, bounded limitations, and zero-change behavior matched expectations, and post-run fixture and package verification passed. Confidence remains limited to this exact package, fixture, scenario, and observed response.