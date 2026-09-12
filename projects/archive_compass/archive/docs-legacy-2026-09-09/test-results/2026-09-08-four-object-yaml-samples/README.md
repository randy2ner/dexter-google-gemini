# Four-object YAML samples

## Status

These files are fictional schema specimens prepared on 2026-09-08. They are not an executed test result, graph write, Skill output, or claim of runtime behavior.

The specimens target Compass Graph Schema `0.6-person-data-minimization-baseline`, object schema version `2`. They contain no personal, company, tenant, or Microsoft 365 data.

## Coverage

| File | Purpose |
| --- | --- |
| `csp-service-confidence.md` | Minimal CSP with common fields only. |
| `person-avery-stone.md` | Confirmed Person with optional normalized `emailAddresses`. |
| `person-jordan-lee.md` | Provisional Person with complete names and no email address. |
| `tracking-topic-release-readiness.md` | Active Topic with CSP alignment, included participants, and an exclusion. |
| `tracking-topic-pilot-retrospective.md` | Archived Topic with required boolean `success` and no CSP alignment. |
| `conversation-release-review.md` | Email Conversation aligned to a Topic with Person relationships. |
| `conversation-follow-up-chat.md` | Chat Conversation intentionally assigned to `parking-lot`. |

## Canonical relationships

- `conversation:sample-release-review` owns its Topic disposition through `trackingTopicId: tracking-topic:sample-release-readiness`.
- `conversation:sample-follow-up-chat` uses reserved `trackingTopicId: parking-lot`; `parking-lot` is not an object.
- Conversation and Topic `participantIds` and Topic `excludedParticipantIds` contain stable Person IDs.
- `tracking-topic:sample-release-readiness` owns its CSP alignment through `cspId: csp:sample-service-confidence`.
- Topic Conversation membership, CSP Topic membership, and Person associations are derived from these owner fields. No reverse authoritative lists are stored.

## Intended use

Use these files as readable inputs when preparing the static cases in `2026-09-08-four-object-yaml-relationship-test-plan.md`. Copy them to a separately registered disposable fixture before mutation or mediated execution. Preserve these source specimens unchanged so a future result can identify its exact starting revision and hashes.
