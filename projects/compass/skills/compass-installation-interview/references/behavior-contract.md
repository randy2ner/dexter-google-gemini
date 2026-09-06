# Installation Interview behavior contract

## Identity

- Skill: `compass-installation-interview`
- Version: `0.2.3-dogfood-candidate`
- Shared contract/schema: `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`

## Required invariants

1. Installation owns configuration and foundational bootstrap, not routine evidence retrieval.
2. User wording and exact displayed approval govern foundational meaning.
3. Perspective Discovery is optional, read-only, minimized, and non-authoritative.
4. Topics own `cspId`; no reverse authoritative lists are created.
5. Configuration and installation-date Daily Log form one validated bootstrap request.
6. Every durable bootstrap write uses Graph Governor pre-write validation and post-write verification. The disclosed content-free capability probe is operational preflight, not graph content or bootstrap authority.
7. Existing managed and user-authored content is preserved.
8. Connected partial writes stop as `recovery-required`; automatic rollback remains synthetic-only.
9. Setup completion requires confirmed timezone and verified effects.
10. Material proposal changes require renewed approval.
11. User-selected classified or sensitivity-labeled Microsoft 365 files and Loop pages are valid setup evidence when accessed through the signed-in Cowork context. Classification alone never blocks installation or requires declassification.
12. Protected source handling remains platform-enforced: Installation does not remove, downgrade, relabel, export, or bypass protection, and it retains only user-approved derived graph knowledge rather than raw classified source content.
13. One representative disposable plain-text write and read-back in the current post-retrieval session context precedes every managed structural change. Actual refusal stops installation as `write-blocked` / `blocked`; successful cleanup must be verified before bootstrap proceeds.
14. Approved bootstrap application writes and verifies `_compass/config.yaml` before creating remaining managed folders or objects.

## Interaction contract

- A first prompt such as `Help me install Compass` begins the installation experience without prior graph setup.
- Offer `Create a new Compass graph`, `Use an existing OneDrive folder`, and `Cancel` before requiring a graph root.
- Default new folder name is `Compass` under OneDrive Documents, subject to user confirmation.
- Ask one meaningful question per turn.
- Offer no more than three primary choices.
- Provide typed paths for every required action.
- Accept `Back`, `Pause`, and `Cancel` where meaningful.
- Explain practical effects before file mechanics.
- Render consequential previews as concise plain text, never a content-heavy Adaptive Card.
- Show every exact relative target path and each required object-type Daily Log entry.
- End the preview with directly typeable `Approve`, `Change`, `Pause`, and `Cancel` choices.
- End successful installation with ordinary product actions rather than internal Skill names.
- Explain the plain-text probe before executing it and report its cleanup state.

## Forbidden behavior

- Broad Email or Teams scanning.
- Hidden profile state or raw Perspective Discovery evidence.
- Inferred customers, People, Topics, CSPs, or relationships.
- Writes outside the supplied disposable fixture.
- Silent overwrite, private persistence rules, or false success.
- Claims of runtime or connected capability without evidence.
- Retrieval from an unselected source or outside the signed-in user's platform-enforced access.
- Removal, downgrade, relabeling, export, or bypass of source protection.
- Office or PDF substitution for schema-required Markdown or YAML.

## Normative bootstrap schema

- Configuration path is `_compass/config.yaml` with `schemaVersion`, lowercase UUID v4 `graphId`, and confirmed IANA `timezone`.
- Managed folders are `CSPs/`, `Tracking Topics/`, `People/`, `Conversations/`, and `Daily Logs/`.
- Every object requires `schemaVersion`, `type`, stable `id`, `title`, and UTC `createdAt`.
- CSP has no `status`. Tracking Topic requires `status: active` or `archived` and optional `cspId`. Person requires `identityState`.
- Daily Log uses deterministic `daily-log:<date>` identity and exactly one `compass:daily-log-index` marker pair around `## Compass Activity`.
- Populated Daily Log sections contain linked object labels, stable IDs, local action time, accepted operation label, concise summary, and initiating Skill/version.
