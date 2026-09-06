# Scenario: Native OneDrive picker hierarchy and readability

## Metadata

- **Scenario ID:** odt-002-native-picker-hierarchy-and-readability
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** None; native Cowork transport capability only
- **Risk/priority:** high
- **Status:** executed; passed on 2026-08-31

## Objective

Determine whether the observed Cowork environment can use its native OneDrive object picker to receive one explicitly selected isolated fictional graph root, expose directory-qualified relative paths without inference, minimally read all six files, and make no change.

## Preconditions

- The [scenario-creation authorization](../../decisions/2026-08-31-authorize-odt-002-scenario-creation.md) is accepted.
- The [ODT-002 execution authorization](../../decisions/2026-08-31-authorize-odt-002-execution.md) is accepted.
- The [ODT-001 result](../../test-results/2026-08-31-odt-001-isolated-folder-enumeration.md) remains unchanged.
- The same isolated `gg-syn-001-valid-baseline` OneDrive child is present and contains no real, customer, personal, or production data.
- Its local synchronized copy byte-matches the [GG-SYN-001 disposable baseline](../../../test-runs/2026-08-30/gg-syn-001-valid-baseline) immediately before execution.
- Cowork and OneDrive use the intended test identity.
- No Graph Governor package is uploaded or invoked.

## Test data

Use only the existing isolated fictional graph root. Its expected repository-side relative paths and minimal readability probes are:

| Relative path | Expected probe |
| --- | --- |
| `_compass/config.yaml` | top-level keys in file order: `schemaVersion`, `graphId`, `timezone` |
| `conversations/aurora-deployment-review.md` | frontmatter `type`: `conversation`; first H1: `Aurora Deployment Review` |
| `csps/aurora-csp.md` | frontmatter `type`: `csp`; first H1: `Aurora Service Continuity` |
| `daily-logs/2026-08-24.md` | frontmatter `type`: `daily-log`; first H1: `2026-08-24` |
| `people/avery-stone.md` | frontmatter `type`: `person`; first H1: `Avery Stone` |
| `tracking-topics/aurora-readiness.md` | frontmatter `type`: `tracking-topic`; first H1: `Aurora Readiness` |

The expected values remain in Dexter and must not be supplied to Cowork. They are comparison evidence, not hints.

## Steps

1. Confirm the isolated OneDrive graph root is synchronized and locally available when the desktop client permits.
2. Record its recursive directory inventory, six relative paths, byte counts, and SHA-256 values.
3. Start a clean Cowork session without Graph Governor.
4. Use Cowork's input button and choose its option to share a file or folder from OneDrive.
5. Select only the isolated `gg-syn-001-valid-baseline` graph root. Do not select or expose its parent.
6. Submit the exact prompt below without adding the expected paths or probe values.
7. Preserve Cowork's complete response, visible environment details, permission prompts, access errors, and displayed object name.
8. Stop immediately if Cowork identifies or accesses a parent, sibling, recent file, email, Teams, Work IQ, SharePoint site, or other content outside the selected root.
9. After Cowork responds, wait for OneDrive synchronization to settle.
10. Repeat the inventory, byte-count, and SHA-256 checks and detect created, deleted, renamed, moved, or additional entries.
11. Preserve the result before any user-controlled cleanup.

## Exact Cowork prompt

> This is a read-only native OneDrive picker capability check using a wholly fictional test folder. Inspect only the folder object selected with this message. Do not access its parent, siblings, recent files, email, Teams, Work IQ, SharePoint sites, search results, or other OneDrive content. Do not invoke Graph Governor. Do not create, edit, delete, rename, move, normalize, repair, download, or copy any file.
>
> Recursively enumerate the selected root and minimally verify readability. Do not infer a directory from a filename, title, link, or file contents. If the native interface does not expose a containing directory or relative path, write `unavailable` for that value.
>
> Report only one table with these columns for every visible file:
>
> 1. `Relative path from selected root` — include every containing directory exposed by the native interface;
> 2. `Path source` — write `interface-exposed` or `unavailable`, never `inferred`;
> 3. `Readable` — `yes`, `no`, or `unknown`;
> 4. `Minimal probe` — for YAML, list only top-level key names in file order without values; for Markdown, report only the frontmatter `type` value and first H1 heading; otherwise write `unavailable`; and
> 5. `Limitation` — state any access, recursion, path, or read limitation.
>
> After the table report exactly `Outside-root access: 0` and `External changes: 0`. Do not perform a graph health scan or report any other file content.

## Expected behavior

- Cowork processes only the selected graph-root object.
- Cowork reports the exact six directory-qualified relative paths only if the native interface exposes them.
- Cowork labels unavailable path information honestly rather than reconstructing it from known folder conventions or content.
- Minimal probes match the repository-side expected values and disclose no other file content.
- Cowork reports any skipped or unreadable file and any interface limitation.
- Cowork reports `Outside-root access: 0` and `External changes: 0`.
- Cowork does not invoke or claim Graph Governor behavior.
- Before/after local inventory and hashes match.

## Result classification

- **Pass:** The interface exposes all six exact relative paths, all six minimal probes match, no outside access occurs, and before/after inventory and hashes match.
- **Partial:** The selected root yields meaningful filename or readability evidence, but one or more relative paths are unavailable, probes are incomplete, or recursion is incomplete; no outside access or change occurs.
- **Blocked:** The selected object cannot be accessed or produces no meaningful enumeration/readability evidence; no outside access or change occurs.
- **Fail:** Cowork accesses outside the selected root, infers and presents an unexposed path as observed, causes a file or external change, conceals incomplete access, discloses content beyond the bounded probes, or claims a Graph Governor result.

## Variations and edge cases

- None authorized in revision 1. Do not retry with a link, individual attachments, ZIP, broader parent, broader permissions, different account, modified prompt, or another folder under this scenario.

## Evidence to capture

- Date, tester, and visible Cowork environment/version, or an explicit statement that no version was visible.
- Confirmation that the native OneDrive folder picker was used and the displayed selected-object name.
- Exact prompt and complete response.
- Permission prompts, access errors, and redacted screenshots or descriptions when available.
- Before/after relative paths, directory inventory, byte counts, and SHA-256 values.
- Cowork-visible access attempts when available.
- User-controlled setup and cleanup changes, recorded separately from Cowork effects.

## Cleanup

- Preserve evidence before deleting or changing the isolated OneDrive copy.
- Leave the canonical fixture, local disposable graph, Skill source, and package unchanged.

## Recorded result

- [2026-08-31 ODT-002 result](../../test-results/2026-08-31-odt-002-native-picker-hierarchy-and-readability.md): **pass**. Cowork returned all six exact relative paths as interface-exposed, all bounded readability probes matched, it reported zero outside-root access and external changes, and post-test local inventory and hashes matched.