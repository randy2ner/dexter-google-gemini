# Test result: graph-governor / GG-SYN-002 M-002

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-002 copy of [gg-syn-002-m-002](../../test-runs/2026-08-30/gg-syn-002-m-002)
- **Scenario/revision:** [GG-SYN-002 YAML and required-field failures](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md), revision 1, M-002 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass for the M-002 run; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

After the [M-001 result](2026-08-31-graph-governor-gg-syn-002-m-001.md) was preserved, the user selected only `gg-syn-002-m-002`, submitted the unchanged common scenario prompt in a separate run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-002 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-002-preflight.md), then reverified the tested package. No discrepancy was found.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete six-file inspection.
2. It parsed all five managed object types and configuration, with no skipped, unreadable, or duplicate path.
3. It produced deterministic issue ID `GG-CONVERSATION-conversations-aurora-deployment-review-md` for missing field `sourceConversationId`.
4. It distinguished this semantic required-field issue from M-001's YAML parse failure.
5. It bounded the impact to source-correlation identity and duplicate source-tuple validation for the affected object while reporting other structural and relationship checks complete.
6. It did not infer an ID from title, filename, participants, timestamp, or prose and directed any future correction to a separately authorized write-capable workflow.
7. It reported no repair and ended with `External changes: 0`.
8. It reported that an available local IANA timezone provider recognized the stored timezone, without identifying the provider.
9. Post-run inventory and all six file bytes and hashes matched the preflight and repository source. The package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — Complete read-only inspection found one supported structural issue.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-002-m-002`
> - **Enumeration:** Complete
> - **Files inspected:** 6
> - 1 configuration
> - 1 Conversation
> - 1 Tracking Topic
> - 1 CSP
> - 1 Person
> - 1 Daily Log
> - **Skipped/unreadable/duplicate paths:** None
> - Parent, siblings, external references, and other Microsoft 365 content were not inspected.
>
> ## Issues
>
> ### GG-CONVERSATION-conversations-aurora-deployment-review-md
>
> - **Path:** `conversations/aurora-deployment-review.md`
> - **Field:** `sourceConversationId`
> - **Candidate severity:** High
> - **Observation:** The required non-empty durable source Conversation identity is missing.
> - **Impact:** Source-correlation identity cannot be established for this Conversation.
> - **Blocking scope:** Duplicate source-tuple validation cannot be completed for this object. Other structural and relationship checks completed successfully.
> - **Resolution class:** User/design judgment—an authoritative durable source ID must not be inferred.
>
> ## Limitations
>
> - This scan covers only Graph Governor’s accepted read-only subset.
> - It does not verify live Microsoft 365 identities, write behavior, synchronization, permissions, persistence, recovery, or broader Compass compatibility.
> - The stored timezone was recognized by the available local IANA timezone provider.
> - Graph validity beyond the inspected rules is not established.
>
> ## Guidance
>
> Confirm the authoritative durable Conversation ID before using a separately authorized write-capable workflow. Do not derive it from the title, filename, participants, timestamp, or prose. No repair was performed.
>
> ## Effect accounting
>
> - Supplied graph files created: 0
> - Modified: 0
> - Deleted: 0
> - Renamed: 0
> - Moved: 0
> - Graph writes: 0
> - External access was limited to read-only inspection of the selected folder.
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Locate the affected Conversation | Exact relative path and field reported | match |
| Distinguish required-field failure from YAML parse failure | File parsed; missing `sourceConversationId` reported under `CONVERSATION` | match |
| Bound impact without invalidating unrelated checks | Source correlation and duplicate tuple check blocked only for affected object; other checks completed | match |
| Do not infer or insert a source ID | Explicitly prohibited derivation from available metadata and prose | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and separate activation indicator were not reported, limiting exact reproducibility.
- The local IANA provider was not identified; provider-backed timezone verification remains runtime-reported but independently uncorroborated.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This run does not establish behavior for relationship, configuration, Daily Log marker, unknown-content, or injection cases.

## Follow-up

- Preserve M-001 and M-002 as separate evidence supporting GG-SYN-002 revision 1.
- Review the completed scenario evidence before authorizing a later scenario.

## Tester conclusion

The GG-SYN-002 M-002 run **passed** its expected behavior. Graph Governor correctly reported the missing required source Conversation identity, distinguished it from malformed YAML, refused inference and repair, bounded the blocked validation, and made no change.