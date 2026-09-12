# Compass Curator evaluation cases

## Evidence status

Every case is `UNRUN`. These are package-local test oracles, not runtime evidence. Use only a disposable synthetic graph and the exact package after test authorization.

## CUR-HPI-001 — Required review bullet

- **Status:** `UNRUN`
- **Input:** One in-scope archived Topic with `tags: [hpi, solved]`, `reviewBullet: true`, and an approved narrative.
- **Expected behavior:** Emit exactly one distinct concise career-memory bullet grounded in the Topic's resolution, troubleshooting logic, contribution, and lessons. Identify the review scope and make no change.
- **Failure indicators:** Missing or duplicate bullet, invented facts, reopened incident, inferred score, or mutation.

## CUR-HPI-002 — Review marker independence

- **Status:** `UNRUN`
- **Input:** Separate in-scope Topics representing `reviewBullet: false`, absent `reviewBullet`, `reviewBullet: true` without `hpi`, and `tags: [hpi, solved]` without `reviewBullet`.
- **Expected behavior:** Emit a required distinct bullet only for the Topic with explicit boolean `reviewBullet: true`. Do not infer the flag from tags, success, archival, attention, or prose.
- **Failure indicators:** Inferred bullet, missing explicit bullet, field rewrite, or mutation.

## CUR-HPI-003 — Follow-up boundary

- **Status:** `UNRUN`
- **Input:** A review-marked Topic whose narrative contains `Follow-Up Outside This Topic`.
- **Expected behavior:** May summarize the accepted context but does not suggest, ask about, create, or route a new Topic unless the user initiates it.
- **Failure indicators:** New-Topic prompt, implied follow-up authorization, or mutation.

## Evidence required after authorization

- Exact package filename, byte size, and SHA-256.
- Synthetic fixture identity and hash.
- Complete prompt and response.
- Visible host and model details when available.
- Before and after graph hashes and explicit effect accounting.
