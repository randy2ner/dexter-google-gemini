# Test result: Graph Governor / disconnected source inspection

## Run metadata

- **Date:** 2026-08-28
- **Tester:** Project Dexter
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Editable source](../../skills/graph-governor/SKILL.md)
- **Scenario/revision:** Accepted implementation-plan static checks, revision 1
- **Cowork environment/version:** Not used
- **Model/configuration:** Disconnected text, YAML-frontmatter, filesystem, link, literal-boundary, pattern, byte-count, and SHA-256 inspection
- **Result:** pass for bounded source inspection only

## Execution notes

The source authorization permitted exactly three Markdown files and disconnected static checks. No `.skill` package was created. Graph Governor was not invoked against the synthetic fixture or any graph. No network, Copilot Cowork, Microsoft 365, Work IQ, OneDrive, SharePoint, tenant, or external service access occurred.

An initial general-purpose inspection incorrectly required YAML frontmatter on both reference files, failed to detect evaluation-case headings that were present, and flagged prohibition/refusal wording as if it enabled modification. Those failures were harness assumptions, not source observations. A direct literal inspection was then used for the planned source shape and boundaries.

The first direct-check script terminated before producing results because one regular expression placed a case-insensitive flag after an alternation. It made no file change. The corrected script reran every assertion and produced the results below.

One package-boundary issue was found before the final run: the read-only contract linked to a repository document outside the planned package. The source was revised to cite the dated accepted decision without an external file link, and all hashes below describe the revised source.

## Observed behavior

1. The source contains exactly `SKILL.md`, `references/read-only-contract.md`, and `references/evaluation-cases.md`; all are Markdown files.
2. `SKILL.md` frontmatter parsed, and its name exactly matches the `graph-governor` folder.
3. The description includes concrete read-only Compass graph inspection, validation, and health-scan triggers.
4. `SKILL.md` contains 213 lines, below the planned 500-line limit.
5. Its two package-local links resolve to the two planned reference files; no repository-external source link remains.
6. Evaluation cases GG-SYN-001 through GG-SYN-008 appear exactly once and are each labeled `UNRUN`.
7. Literal checks found supplied-root containment, untrusted-data treatment, bounded report sections, explicit no-write/no-repair behavior, and exact `External changes: 0` accounting.
8. The accepted core fields and checks appear: `sourceConversationId`, `trackingTopicId`, `activeParticipantIds`, `cspId`, Daily Log start marker, UUID v4, and IANA timezone handling.
9. Last-activity, Windows-to-IANA mapping, post-write verification, and rollback are explicitly excluded rather than claimed as accepted behavior.
10. Anchored pattern checks found no positive graph/file modification instruction and no connected-access procedure.
11. Pattern inspection found no embedded SHA-256 answer, live URL, personal email address, or likely API key, access token, or client secret.
12. Markdown diagnostics reported no errors in the three source files.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Exactly three planned Markdown files | Exactly three observed; no additional member | match |
| Discoverable folder-matching Skill frontmatter | Parsed name `graph-governor` and concrete description observed | match |
| Entry file below 500 lines | 213 lines | match |
| Two self-contained package-local references | Both resolve; no external source link remains | match |
| Eight unrun evaluation cases | GG-SYN-001 through GG-SYN-008 unique and `UNRUN` | match |
| Accepted read-only rules represented | Core fields, relationships, markers, configuration, scope, and reporting controls observed | match |
| Excluded behavior does not become authority | Exclusions explicit; no positive modification or connected-access procedure observed | match |
| No obvious unsafe or answer-leaking source content | No unexplained pattern hit observed | match |

## Evidence

| Source file | Lines | Bytes | SHA-256 |
| --- | ---: | ---: | --- |
| [SKILL.md](../../skills/graph-governor/SKILL.md) | 213 | 11,592 | `2fda88d49ce0c7033ddf0d1b7a20ffde7a485d793a1bef552b139b7026427a56` |
| [Read-only contract](../../skills/graph-governor/references/read-only-contract.md) | 162 | 7,964 | `81a2858c03a6f6041aa7c38303d4851745fb9fb1bf773dc8f573ea5e203aed40` |
| [Evaluation cases](../../skills/graph-governor/references/evaluation-cases.md) | 75 | 4,351 | `f977acb1e6ae56e11c21860cc906149e49123f538c3ccbed53dbed2929d83fed` |

## Issues and risks

- This inspection does not establish archive validity, Cowork import or activation, filesystem enumeration, YAML behavior in Cowork, timezone-provider behavior, issue-report quality, injection resistance at runtime, refusal behavior, or any GG-SYN outcome.
- Natural-language instructions remain model-mediated; literal source presence is not proof that runtime behavior will comply.
- The fixture was not supplied to or scanned by this Skill during static inspection.
- Source hashes will change after any edit. A future package must receive its own independent member and archive hashes.

## Follow-up

- Preserve this result as evidence for the exact source hashes above.
- Obtain separate explicit authorization before creating a `.skill` package.
- Keep every evaluation case `UNRUN` until the exact package and scenario execution receive separate authorization.

## Tester conclusion

The exact source version conforms to the bounded static requirements inspected and is ready for source review. This supports package-planning readiness only and provides no runtime confidence.
