# Test result: Graph Governor / deterministic package inspection

## Run metadata

- **Date:** 2026-08-28
- **Tester:** Project Dexter
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact package, subsequently moved to tested](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill)
- **Scenario/revision:** Accepted implementation-plan package checks, revision 1
- **Cowork environment/version:** Not used
- **Model/configuration:** Disconnected deterministic ZIP-compatible archive creation and inspection
- **Result:** pass for bounded package construction and inspection only

## Execution notes

The user explicitly authorized package creation after the exact three-file source passed disconnected static inspection. The build checked the recorded source hashes before creating output and would have stopped if the target already existed or any source differed.

The package was created once in `skill-exchange/ready-for-test/` using DEFLATE level 9, fixed member timestamp `1980-01-01 00:00:00`, regular-file mode `100644`, no directory entries, no comments, and no extra fields. An independent temporary rebuild used the same declared algorithm, matched the package byte for byte, and was deleted.

No source or fixture file was modified. The package was not uploaded, imported, activated, or executed. No network, Copilot Cowork, Microsoft 365, Work IQ, OneDrive, SharePoint, tenant, graph, or fixture access occurred.

## Observed behavior

1. All three source SHA-256 values matched the prior source-inspection record before packaging.
2. The target did not exist before creation.
3. The archive contains exactly three regular files in the declared order: root `SKILL.md`, `references/read-only-contract.md`, and `references/evaluation-cases.md`.
4. No archive member is absolute, uses a backslash, traverses a parent, or represents a directory.
5. Every member uses DEFLATE, fixed timestamp `1980-01-01 00:00:00`, mode `100644`, no comment, and no extra field.
6. Archive CRC testing passed for every member.
7. Every member decoded as UTF-8 and was byte-identical to its reviewed source file.
8. Root `SKILL.md` frontmatter parsed and identified `graph-governor`.
9. The independent rebuild was byte-identical to the registered artifact.
10. The final package is 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Recorded reviewed source bytes | All three preflight hashes matched | match |
| Exactly three safe archive paths | Exact declared member set and order observed | match |
| Root `SKILL.md` with matching identity | Parsed name `graph-governor` | match |
| Source and archive members byte-identical | All three matched | match |
| Valid CRCs and UTF-8 Markdown | All members passed | match |
| Deterministic package construction | Independent rebuild matched byte for byte | match |
| No unexpected package metadata | Fixed timestamps and modes; no directories, comments, or extras | match |

## Evidence

### Package

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| [graph-governor-v0.1.0-experimental.skill](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill) | 9,777 | `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1` |

### Archive members

| Member | Compressed bytes | Uncompressed bytes | Timestamp | Mode | CRC-32 |
| --- | ---: | ---: | --- | --- | --- |
| `SKILL.md` | 4,568 | 11,592 | `1980-01-01 00:00:00` | `100644` | `053b6c6e` |
| `references/read-only-contract.md` | 3,155 | 7,964 | `1980-01-01 00:00:00` | `100644` | `eb7342e4` |
| `references/evaluation-cases.md` | 1,664 | 4,351 | `1980-01-01 00:00:00` | `100644` | `84539203` |

## Issues and risks

- Package inspection does not establish Cowork upload acceptance, discovery, activation, filesystem access, YAML behavior, model compliance, refusal behavior, or any GG-SYN outcome.
- `ready-for-test` records artifact review state only. It is not authorization to upload or execute the package.
- Any source or package byte change invalidates this result. Do not rebuild the tested candidate in place.
- ZIP-compatible layout is supported by prior local evidence but remains a runtime test target for this exact package.

## Follow-up

- Preserve the exact package bytes and SHA-256.
- Obtain separate explicit authorization before Cowork upload or scenario execution.
- If a connected run is authorized, copy this exact artifact without rebuilding it and record before/after fixture hashes.

## Tester conclusion

The exact package conforms to the bounded deterministic construction checks performed and is ready for package review. This result provides no runtime or Graph Governor behavior confidence.
