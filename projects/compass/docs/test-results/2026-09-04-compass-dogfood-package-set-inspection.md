# Test result: Compass dogfood package set inspection

## Run metadata

- **Date:** 2026-09-04
- **Tester:** Laboratory assistant
- **Candidate:** Compass `0.3.0-dogfood-candidate`
- **Result:** passed disconnected source and package inspection

## Checks

All five packages passed:

- exact expected member set against the owning source directory;
- safe relative archive paths with no absolute or parent traversal segments;
- byte equality between every package member and source file;
- fixed member timestamp `2026-09-04 00:00:00`;
- DEFLATE compression;
- effective Unix file mode `0644`;
- expected version identity in `SKILL.md`; and
- byte-identical independent rebuild with matching SHA-256.

Exact hashes and package paths are recorded in the [package-set inventory](../inventory/compass-0.3.0-dogfood-candidate-package-set.md).

## Scope limitation

This result establishes deterministic construction and static package/source fidelity only. It does not establish Cowork import, connected WorkIQ retrieval, OneDrive writes, cross-Skill continuity, archival behavior, recovery, or product usefulness. Those claims require the connected dogfood experience.