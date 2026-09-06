# Decision: Authorize one OneDrive transport capability experiment

- **Date:** 2026-08-30
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** None; this decision precedes the experiment

## Context

The first attempt to attach a complete local graph directory to Cowork returned `upload failed, check your connection`. Standard file attachment did not establish that Cowork can receive or recursively inspect a local folder hierarchy. The final Compass direction expects an Obsidian vault synchronized through OneDrive, but the current Graph Governor scenarios intentionally have no OneDrive evidence.

The user explicitly authorized one read-only OneDrive transport capability experiment using a copied fictional GG-SYN-001 baseline.

## Decision

Authorize exactly one experiment defined by [ODT-001](../scenarios/onedrive-transport/odt-001-isolated-folder-enumeration.md).

The experiment may:

- create one isolated OneDrive copy of the verified fictional GG-SYN-001 baseline;
- provide Cowork a restricted link to that copied folder;
- ask Cowork whether it can access the supplied root, recursively enumerate the hierarchy, preserve relative paths, and read the six fictional files; and
- compare the copied files before and after Cowork access.

Cowork may access only the explicitly supplied isolated folder. The experiment does not authorize Graph Governor package upload, activation, or scenario execution; Microsoft 365 evidence retrieval; email, Teams, Work IQ, SharePoint-site, parent-folder, sibling-folder, recent-file, or search access; file-content modification; repair; normalization; use of real data; or any production Compass or Obsidian vault.

User-controlled setup and cleanup of the isolated fictional copy must be reported separately from Cowork effects. Cowork's required effect accounting is `External changes: 0`.

## Alternatives considered

- **Continue local folder upload attempts:** Not selected because the observed upload failure did not establish hierarchy transport.
- **Attach six files individually:** Rejected because attachment may lose authoritative relative paths.
- **Use the production OneDrive or Obsidian location:** Rejected because transport capability must be established with isolated fictional data first.
- **Treat transport success as GG-SYN-001 success:** Rejected because this experiment does not invoke or evaluate Graph Governor.

## Consequences

- A successful result supports only OneDrive-folder transport and read-only enumeration in the observed Cowork environment.
- A blocked result must be preserved and must not be converted into a Graph Governor failure.
- Any access outside the supplied root or any Cowork-caused change is a safety failure and stops the experiment.
- GG-SYN-001 and every other Graph Governor scenario remain unexecuted.

## Follow-up

- User: create the isolated OneDrive copy, wait for synchronization, and provide the exact restricted folder link to Cowork using the scenario prompt.
- Project Dexter: record direct observations, visible environment details, and before/after hashes after the user supplies the result.
- Do not proceed to Graph Governor execution without a later explicit decision informed by this experiment.
