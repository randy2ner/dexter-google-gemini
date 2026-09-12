# Changelog

## 0.8.0-first-experience-candidate - 2026-09-09

### Changed

- Removes the disposable Installation write/read/delete probe; the approved config-first bootstrap now verifies write capability.
- Accepts reviewed normalized Person email addresses while preserving stable Compass identity and the UPN prohibition.
- Requires artifact-producing Skills to interpret direct input, graph context, and authorized Work IQ into useful editable suggestions that the user confirms or revises.
- Uses graph-root-relative path addressing for OneDrive graph writes after an operator-reported item-ID failure and successful path retry.

## 0.7.0-production-test-candidate - 2026-09-08

### Milestone

- The product owner declared this exact coordinated candidate set the baseline for production release testing, ending synthetic rehearsal as the primary release-evidence phase.
- Synthetic fixtures remain focused regression and destructive-boundary assets; a separate decision is still required for production release or deployment.
- A subsequent artifact-first shaping decision makes this orchestration an optional discovery tool and design input until the finished production graph is used to derive the controlled release-test version.

### Changed

- Designates the coordinated Skill set for production-content testing rather than synthetic rehearsal.
- Uses all relevant Work IQ source and continuation capabilities Cowork exposes within each explicitly authorized purpose, without arbitrary numeric caps or sample substitution.
- Allows Installation, Tracking Topic Interview, and Curator to use native Work IQ within their accountable purposes while keeping retrieved evidence non-authoritative until user review.
- Keeps Graph Governor evidence-neutral and removes synthetic recovery from the production-test runtime.
- Requires incomplete capability or enumeration to be disclosed and production partial writes to stop as `recovery-required`.
- Keeps any export or model-training use outside scope until separately authorized.

### Known limitations

- Static source and package inspection cannot prove which Work IQ capabilities the target Cowork surface exposes or whether complete enumeration is available.
- This version is authorized for production-content testing, not general production release.

## 0.6.0-hpi-narrative-candidate - 2026-09-08

### Changed

- Aligns Installation Interview with the current HPI baseline and Graph Governor handoff while keeping optional narrative and review metadata outside bootstrap.
- Routes optional user-offered troubleshooting evidence from Daily Scan to Tracking Topic Interview as minimized context without inherited Topic-write authority.
- Assigns detailed Topic narrative composition, `tags`, and `reviewBullet` to Tracking Topic Interview with exact user approval.
- Requires Curator to emit one distinct bullet for every in-scope `reviewBullet: true` Topic.
- Requires Graph Governor to validate review metadata shape, authority, independence, and narrative preservation without judging narrative truth.
- Preserves out-of-scope follow-up ideas without prompting for another Topic until the user initiates it.

### Dependency changes

- Depends on Shared Contracts and Graph Schema `0.7-hpi-narrative-baseline` / schema version 2.
- Advances Installation Interview to `0.6.0-hpi-narrative-compatible-candidate`, Daily Scan and Tracking Topic Interview to `0.6.0-hpi-narrative-candidate`, Curator to `0.5.0-hpi-narrative-candidate`, and Graph Governor to `0.7.0-hpi-narrative-candidate`.

### Known limitations

- No runtime evidence exists for narrative collection, Curator review bullets, or Governor metadata validation in these exact versions.
- Work IQ access remains separately authorized and surface-dependent; the sanitized HPI fixture does not establish connected retrieval.
- Prior packages, fixtures, results, and Orchestration versions remain version-bound.

## 0.5.0-person-data-minimization-candidate - 2026-09-06

### Changed

- Removes Person UPN from current schema-version-2 collection and managed persistence.
- Requires Installation, Daily Scan, and Topic Interview Person proposals to omit UPN.
- Requires Graph Governor to reject proposed effects that introduce or update UPN while preserving pre-existing unmanaged frontmatter until separately authorized removal.

### Dependency changes

- Depends on Shared Contracts and Graph Schema `0.6-person-data-minimization-baseline` / schema version 2.
- Advances the four affected Skill responsibilities; Curator remains compatible and unchanged.

### Known limitations

- No runtime prompting, retrieval-minimization, validation, write, or cleanup evidence exists for this version.
- This revision does not authorize removal of UPN from an existing graph.
- Prior packages, fixtures, evidence, and Orchestration versions remain version-bound.

## 0.4.0-attention-state-candidate - 2026-09-06

### Changed

- Requires every Tracking Topic to record whether the user has an action, is waiting, or is observing without direct involvement.
- Keeps attention state independent of lifecycle, archival success, participants, and relationships.
- Requires explicit authority for creation and changes, retains the value on archival, and confirms or changes it on reactivation.
- Coordinates Installation collection, Daily Scan preservation, Topic Interview ownership, Curator review, and Graph Governor validation.

### Dependency changes

- Depends on Shared Contracts and Graph Schema `0.5-attention-state-baseline` / schema version 2.
- Depends on the attention-state responsibility versions for all five Skills.

### Known limitations

- No runtime Orchestration evidence exists for this version.
- Prior package, fixture, and Orchestration evidence remains version-bound.

## 0.3.1-archival-success-candidate - 2026-09-06

### Changed

- Requires every archival proposal, including merge-source archival, to include the user's explicit boolean success outcome.
- Requires reactivation to remove the archived Topic's `success` field.
- Routes lifecycle-state validation through Graph Governor without inferring success from staleness, completion language, or graph content.

### Dependency changes

- Depends on Graph Schema `0.4.1-archival-success-baseline` while retaining schema version 2.
- Depends on Tracking Topic Interview `0.3.1-archival-success-candidate` and Graph Governor `0.4.1-archival-success-candidate`.

### Known limitations

- No behavioral execution evidence exists for this version.
- Prior package and Orchestration evidence remains version-bound.

## 0.3.0-participant-management-candidate - 2026-09-06

### Changed

- Coordinates complete-name Person confirmation for first-name-only mentions.
- Requires every Conversation to use a valid Topic ID or `trackingTopicId: parking-lot`.
- Carries accepted Conversation participants and deterministic non-excluded Topic participant funnel effects.
- Routes Topic participant add, remove, and explicit re-add through Tracking Topic Interview.
- Preserves Topic participants across Conversation staleness, deletion, Parking Lot movement, and reassignment.

### Dependency changes

- Depends on Shared Contracts and Graph Schema `0.4-participant-management-baseline` / schema version 2.
- Depends on the participant-management responsibility versions for all five Skills.

### Known limitations

- No runtime Orchestration evidence exists for this version.
- Schema-version-1 migration and connected recovery remain deferred.
- Prior Orchestration versions and evidence remain version-bound.

## 0.1-beta-candidate - 2026-09-02

### Added

- Initial five-Skill lifecycle definition.
- Entry-point routing for installation, daily capture, Topic organization, curation, and integrity.
- Shared handoff, approval-renewal, Daily Log, outcome, cancellation, and recovery behavior.
- Progressive typed fallback requirement for constrained host surfaces.

### Dependency changes

- Depends on Shared Contracts and Graph Schema `0.3-beta-baseline`.
- Depends on the accepted Slice B responsibility versions for all five Skills.

### Known limitations

- Definition only; no executable Orchestration or Skill source is authorized.
- Recovery is limited to an explicitly authorized disposable synthetic graph.
- Last activity, item-level evidence, staleness automation, Person merge, CSP retirement, and production persistence remain deferred.