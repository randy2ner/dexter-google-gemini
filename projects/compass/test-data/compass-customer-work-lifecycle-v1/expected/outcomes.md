# Expected Disconnected Outcomes

## Activity Scan

- Update `conversation:40000000-0000-4000-8000-000000000002` through E-3 with `lastActivityAt: 2026-09-12T15:30:00Z` and both Email and Teams provenance.
- Create one separate emergency-access Activity from E-4 under `effort:20000000-0000-4000-8000-000000000002`.
- Exclude E-2 and E-5.
- Leave Conditional Access recency uncertain because E-6 has incomplete continuation.
- Require exact write approval and Governor preflight before fixture mutation.

## Governor

- Accept the baseline schemas and references.
- Block an injected second `effortId`, duplicate stable ID, overlapping Effort participant arrays, wrong folder, or missing Daily Log effect.
- Preserve unknown frontmatter and user Markdown.
- Cause no fixture mutation during validation.

## Curator

- At the fixed review instant, classify Access review remediation as stale, Passwordless pilot as current after the approved Scan update, and Conditional Access expansion as uncertain.
- Criteria approval causes no write.
- Archive only a separately authorized stale Effort with explicit `success` and retained Activity metadata.
- Keep every Activity file until retained metadata is read back and an exact removal list receives separate approval.
- Remove no uncertain, current, declined, or unlisted Activity.