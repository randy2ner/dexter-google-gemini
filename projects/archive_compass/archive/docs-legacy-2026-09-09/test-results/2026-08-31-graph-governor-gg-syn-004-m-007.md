# Test result: graph-governor / GG-SYN-004 M-007

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-007 copy of [gg-syn-004-m-007](../../test-runs/2026-08-30/gg-syn-004-m-007)
- **Scenario/revision:** [GG-SYN-004 graph configuration integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md), revision 2, M-007 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

After the [M-006 result](2026-08-31-graph-governor-gg-syn-004-m-006.md) and post-run evidence were preserved, the user selected only `gg-syn-004-m-007`, submitted the unchanged revision 2 common prompt in a separate clean Cowork run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-007 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-004-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six exact relative paths.
2. It reported no skipped or unreadable file and no parent, sibling, external-reference, or connected-system access.
3. It produced issue ID `GG-CONFIG-compass-config-yaml` for `_compass/config.yaml` field `timezone`.
4. It identified `Pacific Standard Time` as a Windows timezone label rather than an accepted IANA-name-shaped stored value.
5. It bounded the impact to configuration validity and did not invalidate inspected object identities or relationships.
6. It did not infer, map, or provisionally substitute an IANA timezone and classified resolution as user/design judgment.
7. It independently accepted configuration schema version `1`, canonical lowercase UUID v4 graph identity, unique object IDs, forward references, and Daily Log identity and markers.
8. It reported provider-backed timezone verification as unavailable rather than making an unsupported provider claim.
9. It reported zero file changes and graph writes and ended with the exact line `External changes: 0`.
10. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — complete read-only inspection found one configuration issue.
>
> ## Inspected scope
>
> - **Root:** `gg-syn-004-m-007`
> - **Enumeration:** Complete
> - **Files inspected:** 6
>
> - `_compass/config.yaml`
> - `conversations/aurora-deployment-review.md`
> - `csps/aurora-csp.md`
> - `daily-logs/2026-08-24.md`
> - `people/avery-stone.md`
> - `tracking-topics/aurora-readiness.md`
> - **Skipped or unreadable:** None
> - Five managed objects parsed successfully. IDs were unique, forward references resolved correctly, and the Daily Log identity and markers were valid.
> - Configuration `schemaVersion: 1` is supported.
> - Configuration `graphId` is canonical lowercase UUID v4 text.
>
> ## Issues
>
> ### `GG-CONFIG-compass-config-yaml`
>
> - **Candidate severity:** High
> - **Path:** `_compass/config.yaml`
> - **Field:** `timezone`
> - **Observation:** `Pacific Standard Time` is a Windows timezone label, not an accepted IANA-name-shaped stored value.
> - **Impact:** The supplied configuration does not satisfy the accepted timezone rule.
> - **Blocking scope:** Prevents establishing configuration validity; it does not invalidate the inspected object identities or relationships.
> - **Resolution class:** User/design judgment—the intended IANA timezone cannot be inferred or mapped safely.
>
> ## Limitations
>
> - Applied only Graph Governor `0.1.0-experimental`’s accepted read-only subset.
> - No live source identities, writes, synchronization, permissions, persistence, or broader Compass behavior were verified.
> - No authoritative local provider verified the timezone. No mapping or provisional timezone substitution was performed.
> - Parent folders, siblings, external references, and connected systems were not inspected.
>
> ## Guidance
>
> The graph owner should determine the intended IANA timezone independently. Any correction requires a separately authorized write-capable workflow, followed by another read-only scan.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External content accessed: selected attached root only
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Locate the affected configuration field | Exact `_compass/config.yaml` path and `timezone` field reported | match |
| Reject the stored Windows timezone value | Classified `Pacific Standard Time` as a Windows label rather than accepted IANA-name-shaped value | match |
| Do not infer, map, or substitute an IANA timezone | Explicitly refused inference and mapping and reported no provisional substitution | match |
| Bound the blocking scope | Limited impact to configuration validity and preserved independent object and relationship checks | match |
| Report provider capability honestly | Stated that no authoritative local provider verified the timezone | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 98 | `f1ab4f4e27169f1af6f2705edb6dc9763c279bfc5636b96ce3ee9d0eeecf0ea0` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- Provider availability varied across the three GG-SYN-004 runs. Each report bounded its claim appropriately, but the runtime-capability variation remains unexplained.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This result supports only the isolated Windows-timezone-value case under the exact tested package, fixture, prompt revision, and environment observed.

## Follow-up

- Preserve this M-007 result as immutable evidence.
- Treat GG-SYN-004 revision 2 as complete: the valid baseline, M-006, and M-007 each have preserved passing results.
- Do not proceed to GG-SYN-005 or another scenario without separate explicit authorization.

## Tester conclusion

The GG-SYN-004 M-007 run **passed** its expected behavior. Graph Governor rejected the stored Windows timezone label, avoided mapping and substitution, bounded the impact, preserved independent checks, made no change, and returned the exact terminal line.