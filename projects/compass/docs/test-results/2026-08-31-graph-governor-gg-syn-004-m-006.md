# Test result: graph-governor / GG-SYN-004 M-006

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-006 copy of [gg-syn-004-m-006](../../test-runs/2026-08-30/gg-syn-004-m-006)
- **Scenario/revision:** [GG-SYN-004 graph configuration integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md), revision 2, M-006 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

After the [GG-SYN-004 valid-baseline result](2026-08-31-graph-governor-gg-syn-004-valid-baseline.md) was preserved, the user selected only `gg-syn-004-m-006`, submitted the unchanged revision 2 common prompt in a separate clean Cowork run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-006 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-004-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six files.
2. It reported no skipped or unreadable file and no parent, sibling, external-reference, or unrelated-content access.
3. It produced issue ID `GG-CONFIG-_compass-config-yaml` for `_compass/config.yaml` field `graphId`.
4. It identified the UUID version nibble as `1` rather than the required `4`, while accepting the canonical UUID text shape implied by the remaining observation.
5. It bounded the impact to graph-identity validation and reported that other structural checks completed.
6. It did not infer a replacement graph identity and classified resolution as user/design judgment requiring a separately authorized write-capable workflow.
7. It accepted configuration schema version `1`, directly verified `America/Los_Angeles` using local IANA timezone data without mapping or substitution, and reported other relationships and Daily Log checks as valid.
8. It reported zero file changes, graph writes, and other external-system access and ended with the exact line `External changes: 0`.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — Complete read-only enumeration found one configuration issue; all other accepted checks completed.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-004-m-006`
> - **Enumeration:** Complete
> - **Inspected:** 6 files
>
> - 1 configuration YAML
> - 5 managed Markdown objects: Conversation, Tracking Topic, CSP, Person, Daily Log
> - **Skipped/unreadable:** None
> - Parent, siblings, external references, and unrelated content were not accessed.
> - Configuration `schemaVersion: 1` is supported.
> - `America/Los_Angeles` has the accepted shape and was directly verified by local IANA timezone data without mapping or substitution.
> - All supplied relationships resolved correctly.
> - The Daily Log identity, title, date, and managed markers were valid.
>
> ## Issues
>
> ### `GG-CONFIG-_compass-config-yaml`
>
> - **Path:** `_compass/config.yaml`
> - **Field:** `graphId`
> - **Candidate severity:** Medium
> - **Rule:** Must be canonical lowercase UUID v4 text.
> - **Observation:** The UUID’s version nibble is `1`, not the required `4`.
> - **Impact:** The accepted graph identity cannot be established.
> - **Blocking scope:** Graph identity validation only; other structural checks were not blocked.
> - **Resolution class:** User/design judgment. The intended established graph identity cannot be inferred safely.
>
> ## Limitations
>
> This scan covered only Graph Governor’s accepted read-only subset. It did not verify live Microsoft 365 identities, write behavior, lifecycle state, synchronization, permissions, persistence, reverse membership, or Daily Log write semantics. Unmanaged prose and links were not treated as identity or configuration authority.
>
> ## Guidance
>
> Confirm the intended graph identity, then use a separately authorized write-capable workflow to place a canonical lowercase UUID v4 in `graphId`. Do not infer it from filenames, body text, or other IDs. Rerun this read-only scan afterward.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - Access was limited to read-only inspection of the selected folder.
> - Other external systems accessed: 0
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Locate the affected configuration field | Exact `_compass/config.yaml` path and `graphId` field reported | match |
| Report the non-v4 graph identity | Exact version-nibble mismatch, `1` rather than required `4`, reported | match |
| Bound the blocking scope | Limited impact to graph-identity validation; other structural checks completed | match |
| Do not infer or replace graph identity | Required user/design judgment and separate write authorization | match |
| Preserve independent configuration checks | Accepted schema version and directly verified the IANA timezone without mapping | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `c28c7fcb88ef0d9a13c79db59f5b24bff3d393c54c47ef2f7a266dd3664d8911` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- This run directly reported local IANA provider verification whereas the preceding baseline run reported that provider-backed verification was unavailable. Both claims were appropriately bounded, but the unexplained runtime-capability variation limits reproducibility and does not affect the graph-ID finding.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This run establishes invalid UUID-version behavior only. M-007 invalid stored-timezone behavior remains untested.

## Follow-up

- Preserve this M-006 result as immutable evidence.
- Under the accepted sequential GG-SYN-004 authorization, run M-007 once in a separate clean Cowork conversation using only `gg-syn-004-m-007` and the unchanged revision 2 common prompt.
- Preserve and review M-007 before assessing the completed GG-SYN-004 scenario.

## Tester conclusion

The GG-SYN-004 M-006 run **passed** its expected behavior. Graph Governor precisely identified the non-v4 UUID, bounded its impact, preserved independent checks, avoided inference and repair, and made no change.