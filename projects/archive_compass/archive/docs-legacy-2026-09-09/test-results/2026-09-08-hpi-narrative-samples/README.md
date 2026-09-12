# HPI narrative object samples

## Evidence status

These seven files are sanitized schema specimens prepared from the product-owner interview and the offered generic HPI case study on 2026-09-08. They are not a runtime test result, Work IQ observation, connected graph write, or claim that the supplied Chat title is a verified source Conversation ID.

All names are fictional aliases. Email domains are retained only as fictional affiliation cues requested for this test; the addresses are not verified identities and must not be contacted. The incident narrative is generalized and excludes individual identities, bridge links, phone numbers, end-user identifiers, and raw messages.

## Object chain

`Conditional Access Policy` <- `Intune-managed authentication failure: revoked credentials` <- `INT | US Dept VA | 2609020040003978 | ACE-ICM 861521539`

- The Tracking Topic owns its CSP alignment through `cspId`.
- The Conversation owns its Topic alignment through `trackingTopicId`.
- Conversation participants funnel to Topic `participantIds`.
- CSP Topic membership and Topic Conversation membership are derived; no reverse authoritative lists are stored.

## Interview decisions represented

- HPI means High Profile Incident: a major emergency affecting critical services.
- Topic scope is immediate service restoration only.
- The Topic is archived with `success: true` and retained `attentionState: waiting`.
- `tags` contains `hpi` and `solved`; `reviewBullet: true` requires Curator to surface one career-memory bullet in an applicable review.
- Follow-up ideas remain archived narrative context. Compass must not suggest, ask about, or create another Topic until the user initiates it.
- Detailed content is optional in the product behavior but was offered and approved for this specimen.

## Expected Curator bullet

- **Solved HPI — Intune-managed authentication failure: revoked credentials:** Restored access by identifying revoked derived credentials as the trigger and incomplete passkey enrollment as the single-method dependency. The durable lesson is to disprove attractive hypotheses with population data, compare affected and unaffected cohorts, and design migration telemetry before credential lifecycle changes.

## Expected Governor result

For a bounded schema-version-2 health scan of these seven managed objects: no issue under the accepted HPI narrative subset, complete ID resolution, unique participant lists, valid archived-success and attention-state combination, normalized unique tags, boolean review marker, and no direct Graph Governor changes.
