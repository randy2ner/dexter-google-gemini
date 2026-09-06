# Test result: Perspective Discovery / disconnected source inspection

## Run metadata

- **Date:** 2026-08-28
- **Tester:** Project Dexter
- **Skill/version:** compass-installation-perspective-discovery `0.1.0-experimental`
- **Test artifact:** [Editable source](../../skills/compass-installation-perspective-discovery/SKILL.md)
- **Scenario/revision:** Implementation-plan static checks, revision 1
- **Cowork environment/version:** Not used
- **Model/configuration:** Disconnected text and filesystem inspection
- **Result:** pass for bounded source inspection only

## Execution notes

The accepted implementation authorization permitted creation of exactly three Markdown source files and disconnected static checks. No package was created. No network, Copilot Cowork, Work IQ, Microsoft 365, OneDrive, or graph access occurred.

An initial long PowerShell audit entered continuation mode and was terminated without changing files. A later automated assertion reported that it did not detect the no-write boundary despite the required phrases being present. Direct exact-text search confirmed the phrases in both the entry file and behavior contract. This discrepancy is a check-harness limitation, not runtime Skill evidence.

## Observed behavior

1. The source contains exactly `SKILL.md`, `references/behavior-contract.md`, and `references/evaluation-cases.md`.
2. Frontmatter delimiters are present; the lowercase kebab-case name matches the source folder; and the description names Work IQ, Email, and Teams invocation conditions.
3. The entry file is 147 lines, below the planned 500-line limit.
4. Both package-local reference links resolve.
5. Evaluation cases PD-001 through PD-007 are unique and each is marked `UNRUN`.
6. The seven-complete-day, 10-per-source, and 20-total limits are present.
7. Exact-text inspection found `No graph writes and no external changes are permitted`, `External changes: 0`, and refusal of requests to create or modify graph content.
8. All six specified terminal outcomes are present.
9. Static pattern inspection found no obvious secret, token, tenant ID, personal email address, live URL, script, or binary content.
10. Markdown diagnostics reported no errors.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Exactly three planned Markdown files | Exactly three observed | match |
| Valid discoverable Skill frontmatter | Required name and description observed | match |
| Bounded retrieval limits | Seven complete days; 10 per source; 20 total | match |
| Explicit no-write boundary | Exact no-graph-write, no-external-change, and refusal text observed | match |
| Seven unrun evaluation cases | PD-001 through PD-007 each marked `UNRUN` | match |
| No obvious unsafe source content | No unexplained pattern hit or non-Markdown member | match |

## Evidence

| Source file | Bytes | SHA-256 |
| --- | ---: | --- |
| [SKILL.md](../../skills/compass-installation-perspective-discovery/SKILL.md) | 8,018 | `6af46fc9ce5987f98c27e392100ba0a202d03870f51fd733fbe654a5c8500c7a` |
| [Behavior contract](../../skills/compass-installation-perspective-discovery/references/behavior-contract.md) | 3,135 | `45854d78c96915ba95f38aa0d975698b38f2ae3cd71cb904cd7f40e0d342d94b` |
| [Evaluation cases](../../skills/compass-installation-perspective-discovery/references/evaluation-cases.md) | 2,189 | `6d6ceb6816fa7f33347dc5abc41988467ffb9ec906423367df2458349840c43a` |

## Issues and risks

- The static inspection does not establish `.skill` archive validity, Cowork import or activation, Work IQ access, source behavior, privacy behavior, or scenario outcomes.
- The no-write assertion should use direct literal checks in future automation to avoid a false failure from composite matching logic.
- Source hashes will change if source is revised; package evidence must use the separately computed package hash.

## Follow-up

- Review this source inspection and source content.
- Obtain separate explicit authorization before creating a `.skill` package.
- Keep every connected evaluation case `UNRUN` until the exact package receives separate Cowork and Work IQ test authorization.

## Tester conclusion

The source conforms to the bounded static requirements inspected. This supports package-review readiness only and provides no runtime confidence.
