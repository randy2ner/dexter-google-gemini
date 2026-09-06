# Test result: Perspective Discovery / deterministic package inspection

## Run metadata

- **Date:** 2026-09-01
- **Tester:** Project Dexter
- **Skill/version:** compass-installation-perspective-discovery `0.1.0-experimental`
- **Test artifact:** [Exact package ready for test authorization](../../skill-exchange/ready-for-test/compass-installation-perspective-discovery-v0.1.0-experimental.skill)
- **Scenario/revision:** Accepted implementation-plan package checks, revision 1
- **Cowork environment/version:** Not used
- **Model/configuration:** Disconnected deterministic ZIP-compatible archive creation and inspection
- **Result:** pass for bounded package construction and inspection only

## Execution notes

The user directed Project Dexter to proceed to the next lifecycle step after Graph Governor closure. The [accepted package authorization](../decisions/2026-09-01-authorize-perspective-discovery-package-v0-1-0.md) permitted one deterministic package creation after requiring exact identity with the three previously inspected source files.

The build failed closed if the target already existed, checked the complete source inventory and recorded hashes before construction, and created the package once using DEFLATE level 9, fixed member timestamp `1980-01-01 00:00:00`, regular-file mode `100644`, no directory entries, no comments, and no extra fields. An independent temporary rebuild used the same declared algorithm, matched the package byte for byte, and was deleted.

No source file was modified. The package was not uploaded, imported, activated, or executed. No network, Copilot Cowork, Work IQ, Microsoft 365, OneDrive, graph, or fixture access occurred.

## Observed behavior

1. The source directory contained exactly the three authorized regular files and no unexpected member.
2. All three source byte counts and SHA-256 values matched the disconnected source-inspection record before packaging.
3. The target did not exist before package creation.
4. The archive contains exactly three regular files in declared order: root `SKILL.md`, `references/behavior-contract.md`, and `references/evaluation-cases.md`.
5. No archive member is absolute, uses a backslash, traverses a parent, represents a directory, or is a symbolic link.
6. Every member uses DEFLATE, fixed timestamp `1980-01-01 00:00:00`, mode `100644`, no comment, and no extra field.
7. Archive CRC testing passed, every member decoded as UTF-8, and every member was byte-identical to its reviewed source file.
8. Root `SKILL.md` frontmatter identified `compass-installation-perspective-discovery`.
9. The independent rebuild was byte-identical to the retained package and was deleted.
10. The package is 5,972 bytes with SHA-256 `0dfa685330afabe0d3e3e31ad1b5beaf3211c0d275dc1aaac845c92896bfb56f`.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Exact previously reviewed source bytes | All source sizes and hashes matched | match |
| Exactly three safe archive paths | Exact authorized member set and order observed | match |
| Root `SKILL.md` with matching identity | Parsed name `compass-installation-perspective-discovery` | match |
| Source and package members byte-identical | All three members matched | match |
| Valid CRCs and UTF-8 Markdown | All members passed | match |
| Deterministic package construction | Independent rebuild matched byte for byte | match |
| No unexpected package metadata | Fixed timestamps and modes; no directories, links, comments, or extras | match |

## Evidence

### Source prechecks

| Source file | Bytes | SHA-256 |
| --- | ---: | --- |
| [SKILL.md](../../skills/compass-installation-perspective-discovery/SKILL.md) | 8,018 | `6af46fc9ce5987f98c27e392100ba0a202d03870f51fd733fbe654a5c8500c7a` |
| [Behavior contract](../../skills/compass-installation-perspective-discovery/references/behavior-contract.md) | 3,135 | `45854d78c96915ba95f38aa0d975698b38f2ae3cd71cb904cd7f40e0d342d94b` |
| [Evaluation cases](../../skills/compass-installation-perspective-discovery/references/evaluation-cases.md) | 2,189 | `6d6ceb6816fa7f33347dc5abc41988467ffb9ec906423367df2458349840c43a` |

### Package

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| [compass-installation-perspective-discovery-v0.1.0-experimental.skill](../../skill-exchange/ready-for-test/compass-installation-perspective-discovery-v0.1.0-experimental.skill) | 5,972 | `0dfa685330afabe0d3e3e31ad1b5beaf3211c0d275dc1aaac845c92896bfb56f` |

### Archive members

| Member | Compressed bytes | Uncompressed bytes | Timestamp | Mode | CRC-32 |
| --- | ---: | ---: | --- | --- | --- |
| `SKILL.md` | 3,160 | 8,018 | `1980-01-01 00:00:00` | `100644` | `240ff662` |
| `references/behavior-contract.md` | 1,430 | 3,135 | `1980-01-01 00:00:00` | `100644` | `87f6b40c` |
| `references/evaluation-cases.md` | 994 | 2,189 | `1980-01-01 00:00:00` | `100644` | `528f8d05` |

## Issues and risks

- Package inspection does not establish Cowork import, discovery, activation, Work IQ availability, Email or Teams retrieval, privacy behavior, authorization sequencing, output minimization, or any PD scenario outcome.
- `ready-for-test` records package-review state only. It is not authorization to upload, import, or execute the package.
- Connected testing may expose sensitive work context. Its exact sources, date window, retrieval limits, output handling, stop conditions, and lean scenario scope require explicit review and authorization.
- Any source or package byte change invalidates this package result. Do not rebuild or replace the reviewed candidate in place.

## Follow-up

- Preserve the exact package bytes and SHA-256.
- Review and reduce the connected test plan to the smallest risk-based run that can establish the next decision.
- Obtain separate explicit authorization before Cowork import, Work IQ access, or connected execution.

## Tester conclusion

The exact package conforms to the authorized deterministic construction and disconnected inspection checks. It is ready for connected-test scope review, but no connected action or behavior is authorized or validated.