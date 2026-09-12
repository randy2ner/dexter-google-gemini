# Test plan: Person UPN removal

## Metadata

- **Owner:** User / product owner
- **Period:** 2026-09-06 onward
- **Skills/versions:** Installation, Daily Scan, and Tracking Topic Interview `0.5.0-person-data-minimization-candidate`; Graph Governor `0.6.0-person-data-minimization-candidate`; Curator unchanged
- **Status:** active; static inspection authorized, behavioral execution not authorized

## Goals

- Verify current Person schema and proposals omit `userPrincipalName`.
- Verify Person-creating Skills do not request, infer, retrieve for retention, add, or update UPN.
- Verify Graph Governor rejects a proposed schema-version-2 effect that introduces or updates UPN.
- Verify unrelated writes preserve a pre-existing UPN as unmanaged frontmatter pending separately authorized removal.

## Out of scope

- Connected Microsoft 365 retrieval, personal-graph mutation, cleanup of existing UPN values, schema-v1 migration, deployment, promotion, and release.

## Environments

- Current documentation, Skill source, and deterministic package contents.
- Disposable fictional graph only after separate behavioral authorization.

## Check matrix

| Check | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| Current schema and source omission scan | high | repository source | Project Dexter | complete |
| Deterministic package/source equality | high | local package inspection | Project Dexter | complete |
| New Person proposal containing UPN is rejected | high | separately authorized disposable fixture | Project Dexter / product owner | planned |
| Existing unmanaged UPN survives unrelated write | high | separately authorized disposable fixture | Project Dexter / product owner | planned |
| Writer does not request or retain retrieved UPN | high | separately authorized Cowork interaction | Product owner | planned |

## Entry criteria

- Accepted decision, contracts, schema, and affected Skill sources identify exact versions.
- Runtime checks use only fictional data and separate authority.

## Exit criteria

- Static evidence covers source omission, explicit writer prohibition, validator prohibition, deterministic packaging, and historical preservation.
- Runtime behavior remains unclaimed until the three behavioral checks execute.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| A source exposes UPN and a writer retains it incidentally. | Unnecessary personal data enters the graph. | Explicitly prohibit retrieval for retention and inspect exact handoff effects. |
| Unknown-field preservation is mistaken for permission to add UPN. | New writes reintroduce removed data. | Governor distinguishes pre-existing unmanaged content from introduced or updated effects. |
| Data minimization triggers automatic cleanup. | Existing graph data changes without authority. | Require a separate disclosed cleanup proposal and test preservation first. |

## Reporting

Record dated immutable results under `docs/test-results/`. Keep static observations separate from unexecuted runtime claims.