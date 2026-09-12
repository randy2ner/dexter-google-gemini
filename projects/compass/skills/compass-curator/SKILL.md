---
name: compass-curator
description: "Review Compass Efforts for completion or 14-day customer-work inactivity, archive only authorized Efforts, preserve and verify Activity metadata, and separately remove only approved stale Activity files."
---

# Compass Curator

## Version and outcome

- Version: `0.1.0-local-candidate`
- Mode: local candidate; required Copilot Cowork capabilities are unverified

Keep the filing cabinet useful through safe lifecycle review. Review is read-only. Effort archival and exact Activity-file removal are separate decisions, with preservation and verification between them.

Read [the lifecycle contract](references/lifecycle-contract.md) before proposing candidates or effects.

## Start and criteria

- Start when the user asks to curate, archive completed work, review stale Efforts, or compact archived Activity detail.
- Ask for the explicit Compass graph root and inspect only that graph.
- Propose the default threshold of 14 days without meaningful customer Activity, the configured timezone cutoff, included Efforts, and evidence coverage.
- Offer `Approve review`, `Change criteria`, and `Cancel`. Criteria approval authorizes review only.

## Review

For each in-scope active Effort:

1. Derive last Activity as the greatest reliable `lastActivityAt` among live Activities and retained archived Activity metadata.
2. Exclude file, retrieval, graph-edit, Daily Log, relationship, attention-state, and unrelated-message times.
3. Treat incomplete Email or Teams continuation, unavailable item timestamps, ambiguous timezone, future dates, uncertain Activity alignment, or unknown timestamp derivation as uncertainty rather than staleness.
4. Present completed, stale, current, and uncertain Efforts with basis, affected Activities, proposed retained metadata, possible later removals, and no mutation.

## Archive decision

Ask the user to authorize exact Efforts. For each authorized Effort:

- set `status: archived` and require explicit boolean `success`;
- preserve required metadata for each Activity proposed for later compaction;
- obtain Governor preflight validation;
- re-read, update, append Daily Log effects, and read back;
- obtain Governor postflight validation; and
- leave every Activity file present.

Declined and unresolved Efforts remain unchanged. An archive failure leaves related Activity files intact.

## Separate Activity removal

Only after archive metadata is verified, present the exact Activity files, retained entries, and graph-reference effects. Offer `Remove listed files`, `Change list`, `Keep all`, and `Cancel`.

Removal approval applies only to the displayed files. Re-read the archived Effort and Activity immediately before each removal. Stop on conflict, changed metadata, active references, or failed validation. Remove only approved files, append one Daily Log effect per removal, and validate the resulting graph.

Never remove an Effort or source Email or Teams content.

## Report

Report exact completed, declined, blocked, partial, cancelled, and uncertain outcomes: Efforts reviewed and archived, metadata retained and verified, Activity files removed or preserved, Daily Log effects, coverage limitations, and unresolved conflicts. Never claim lifecycle completion from attempted effects.

## Package boundary

The runtime candidate consists only of this `SKILL.md` and its file under `references/`. It has no external project-governance or legacy-artifact dependency.