# Installation Interview behavior contract

## Identity

- Skill: `compass-installation-interview`
- Version: `0.7.0-production-test-candidate`
- Shared contract/schema: `0.8-production-evidence-baseline` / `0.7-hpi-narrative-baseline` / schema version 2
- Orchestration: `compass-work-memory-lifecycle` `0.7.0-production-test-candidate`

## Required invariants

1. Installation owns configuration and foundational bootstrap, not routine evidence retrieval.
2. User wording and exact displayed approval govern foundational meaning.
3. Perspective Discovery is optional, read-only, minimized, and non-authoritative.
4. Topics own `cspId`; no reverse authoritative lists are created.
5. Configuration and installation-date Daily Log form one validated bootstrap request.
6. Every durable bootstrap write uses Graph Governor pre-write validation and post-write verification. The approved, config-first bootstrap verifies write capability; Installation creates no disposable probe.
7. Existing managed and user-authored content is preserved.
8. Production partial or unverifiable writes stop as `recovery-required`; this version performs no automatic rollback or repair.
9. Setup completion requires confirmed timezone and verified effects.
10. Material proposal changes require renewed approval.
11. User-selected classified or sensitivity-labeled Microsoft 365 files and Loop pages are valid setup evidence when accessed through the signed-in Cowork context. Classification alone never blocks installation or requires declassification.
12. Protected source handling remains platform-enforced: Installation does not remove, downgrade, relabel, export, or bypass protection, and it retains only user-approved derived graph knowledge rather than raw classified source content.
13. `_compass/config.yaml` is the first approved durable write and the write-capability check. Refusal before any effect returns `write-blocked` / `blocked`; a completed or uncertain effect returns `recovery-required`. No delete-based preflight is used.
14. Approved bootstrap application writes and verifies `_compass/config.yaml` before creating remaining managed folders or objects.
15. Every Person has meaningful `firstName` and `lastName`; first-name-only input requires user confirmation before creation or binding. Reviewed normalized email addresses are retained when supplied or available for the approved purpose.
16. Installation may create reviewed initial Topic `participantIds`; `excludedParticipantIds` is present and empty unless explicitly directed otherwise.
17. Every foundational Topic has one user-selected `attentionState`: `action`, `waiting`, or `observing`; Installation never infers or defaults it.
18. Installation never requests, infers, retrieves for retention, adds, or updates Person `userPrincipalName`; existing values remain unmanaged and preserved unless separately authorized for removal.
19. Optional Topic narrative, `tags`, and `reviewBullet` remain outside bootstrap requirements. If the user offers them during installation, preserve the request and route later refinement to Tracking Topic Interview after setup; do not infer, discard, or write them during bootstrap.
20. Production setup uses direct answers and real user-authorized Work IQ evidence. It never substitutes sample, fictional, fixture, or synthetic content.
21. Within the authorized setup purpose, use all relevant Work IQ source types and continuation capabilities Cowork exposes without arbitrary numeric caps; disclose incomplete coverage and platform restrictions.
22. Every approved OneDrive file write uses its declared graph-root-relative path, never a OneDrive item ID. Folder resolution remains distinct from file-write addressing, and this rule does not concern source Conversation IDs.

## Interaction contract

- A first prompt such as `Help me install Compass` begins the installation experience without prior graph setup.
- Offer `Create a new Compass graph`, `Use an existing OneDrive folder`, and `Cancel` before requiring a graph root.
- Default new folder name is `Compass` under OneDrive Documents, subject to user confirmation.
- Ask one meaningful question per turn.
- Offer no more than three primary choices.
- Provide typed paths for every required action.
- Accept `Back`, `Pause`, and `Cancel` where meaningful.
- Explain practical effects before file mechanics.
- Interpret direct input, accepted graph context, and authorized Work IQ into a useful editable artifact suggestion before asking for confirmation.
- Render consequential previews as concise plain text, never a content-heavy Adaptive Card.
- Show every exact relative target path and each required object-type Daily Log entry.
- End the preview with directly typeable `Approve`, `Change`, `Pause`, and `Cancel` choices.
- End successful installation with ordinary product actions rather than internal Skill names.

## Forbidden behavior

- Broad Email or Teams scanning.
- Hidden profile state or raw Perspective Discovery evidence.
- Inferred customers, People, Topics, CSPs, or relationships.
- Writes outside the selected production graph.
- Silent overwrite, private persistence rules, or false success.
- Claims of runtime or connected capability without evidence.
- Retrieval from an unselected source or outside the signed-in user's platform-enforced access.
- Removal, downgrade, relabeling, export, or bypass of source protection.
- Office or PDF substitution for schema-required Markdown or YAML.
- Collection or persistence of Person UPN.
- Sample-data substitution or artificial Work IQ source and result-count restrictions.

## Normative bootstrap schema

- Configuration path is `_compass/config.yaml` with `schemaVersion`, lowercase UUID v4 `graphId`, and confirmed IANA `timezone`.
- Managed folders are `CSPs/`, `Tracking Topics/`, `People/`, `Conversations/`, and `Daily Logs/`.
- Every object requires `schemaVersion: 2`, `type`, stable `id`, `title`, and UTC `createdAt`.
- CSP has no `status`. Tracking Topic requires `status: active` or `archived`, `attentionState: action|waiting|observing`, optional `cspId`, and unique `participantIds` and `excludedParticipantIds`. Person requires `firstName`, `lastName`, and `identityState`.
- Daily Log uses deterministic `daily-log:<date>` identity and exactly one `compass:daily-log-index` marker pair around `## Compass Activity`.
- Populated Daily Log sections contain linked object labels, stable IDs, local action time, accepted operation label, concise summary, and initiating Skill/version.
