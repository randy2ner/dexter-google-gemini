# Test result: graph-governor / GG-SYN-004 valid baseline

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated [gg-syn-004-valid-baseline](../../test-runs/2026-08-30/gg-syn-004-valid-baseline)
- **Scenario/revision:** [GG-SYN-004 graph configuration integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-004-configuration-integrity.md), revision 2, valid-baseline run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; Graph Governor primary outcome correctly reported `Valid`

## Execution notes

The user selected only `gg-syn-004-valid-baseline`, submitted the revision 2 common scenario prompt in a clean Cowork run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-004-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Valid` after complete inspection of six exact relative paths.
2. It reported no skipped, duplicate, or unreadable file and stated that no parent, sibling, or other Microsoft 365 content was accessed.
3. It accepted configuration schema version `1` and the canonical lowercase UUID v4 graph identity.
4. It accepted the stored timezone as non-empty and IANA-name-shaped while explicitly reporting provider-backed verification as unavailable.
5. It reported that no mapping, substitution, or provisional retrieval was performed.
6. It also reported accepted structure, identities, closed values, forward relationships, and Daily Log identity and marker boundary without expanding the conclusion beyond the accepted subset.
7. It reported no corrective action and no graph change.
8. It ended with the exact line `External changes: 0`.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Valid** — Complete supplied scope was readable; no issues were found under Graph Governor’s accepted read-only subset.
>
> ## Inspected scope
>
> - **Root:** `gg-syn-004-valid-baseline`
> - **Enumeration:** Complete; six files across six folders.
> - **Inspected:**
>
> - `_compass/config.yaml`
> - `conversations/aurora-deployment-review.md`
> - `csps/aurora-csp.md`
> - `daily-logs/2026-08-24.md`
> - `people/avery-stone.md`
> - `tracking-topics/aurora-readiness.md`
> - **Skipped, duplicate, or unreadable files:** None.
> - All required fields, managed types, unique identities, source-correlation identity, closed values, and forward relationships satisfied the accepted rules.
> - `_compass/config.yaml` uses schema version `1`; `graphId` is canonical lowercase UUID v4 text; `timezone` is non-empty and IANA-name-shaped.
> - The Daily Log date identity, title, deterministic ID, and exact marker boundary were valid.
>
> ## Issues
>
> None observed under the accepted read-only subset.
>
> ## Limitations
>
> - No authoritative local timezone provider was used; provider-backed verification of the stored timezone is unavailable. No mapping, substitution, or provisional retrieval was performed.
> - This scan did not verify live Microsoft 365 identities, writes, synchronization, permissions, persistence, lifecycle behavior, staleness, or Daily Log write behavior.
> - The result applies only to the supplied folder and accepted experimental subset.
>
> ## Guidance
>
> No corrective action is indicated by this scan. No user or design judgment is currently required under the accepted subset.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: `0`
> - Graph writes: `0`
> - External access: limited to the selected attached folder; no parent, sibling, or other Microsoft 365 content was accessed.
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Accept baseline configuration schema version | Reported schema version `1` without issue | match |
| Accept canonical lowercase UUID v4 graph identity | Reported `graphId` as canonical lowercase UUID v4 text | match |
| Accept the stored IANA-name-shaped timezone without unsupported provider claim | Accepted the shape and explicitly reported provider-backed verification unavailable | match |
| Do not map or replace timezone or perform provisional retrieval | Explicitly reported none was performed | match |
| Keep conclusion bounded | Applied `Valid` only to the supplied folder and accepted experimental subset | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- Provider-backed timezone verification was unavailable. This run supports accepted shape handling, not recognition by an authoritative timezone provider.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This baseline run does not establish M-006 invalid-graph-identity or M-007 invalid-stored-timezone behavior.

## Follow-up

- Preserve this valid-baseline result as immutable evidence.
- Under the accepted sequential GG-SYN-004 authorization, run M-006 once in a separate clean Cowork conversation using only `gg-syn-004-m-006` and the unchanged revision 2 common prompt.
- Do not run M-007 until the M-006 result and post-run evidence are preserved and reviewed.

## Tester conclusion

The GG-SYN-004 valid-baseline run **passed** its expected behavior. Graph Governor accepted the configuration schema, canonical UUID v4 graph identity, and IANA-name-shaped timezone; reported provider verification honestly; remained bounded; and made no change.