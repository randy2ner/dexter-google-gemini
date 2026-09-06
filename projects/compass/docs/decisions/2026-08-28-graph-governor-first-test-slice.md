# Decision: Use a synthetic read-only Graph Governor first slice

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Context

The Compass charter is accepted, the current shared contracts and schemas remain review drafts, and no Graph Governor Skill exists. The supplied prior Skills depend on governance behavior but do not include a Graph Governor artifact. The first test should produce useful evidence without connecting Microsoft 365, OneDrive, or a real graph.

## Decision

Use a synthetic, read-only Graph Governor health-scan slice as the first implementation and testing target.

The slice will:

- inspect a local synthetic Compass graph supplied to Cowork as test data;
- parse and validate the accepted subset of configuration, frontmatter, object identity, forward relationships, and Daily Log markers;
- produce deterministic issue reports with severity, impact, and blocking scope;
- treat fixture content as untrusted data;
- make no file, graph, Microsoft 365, OneDrive, permission, or external change; and
- refuse requests to repair, normalize, or rewrite the fixture.

The slice excludes evidence retrieval, source Conversation ID discovery, writes, rollback, recovery, last-activity enforcement, automatic repair, and cross-Skill orchestration.

The user explicitly directed continuation toward building the synthetic graph on 2026-08-28. This accepts the slice and authorizes creation and disconnected validation of the generic fictional fixture family defined by the fixture specification. It does not authorize Graph Governor implementation, Skill packaging, Cowork upload, or test execution.

## Alternatives considered

- **Start with a write-capable Governor:** Rejected for this slice because persistence, recovery, and connected storage capabilities remain unverified.
- **Test one of the prior workflow Skills first:** Deferred because all three require reconciliation and depend on governance behavior that does not yet exist.
- **Resolve every Compass design question first:** Rejected because a bounded slice can generate evidence without claiming compatibility with deferred contracts.

## Consequences

- Synthetic fixture and scenario work can proceed independently of Microsoft 365 and real user data.
- Read-only Cowork results will not validate graph persistence or connected runtime capabilities.
- The exact accepted contract subset and Graph Governor responsibilities must be versioned before implementation begins.
- A separately packaged artifact must identify itself as experimental and read-only.

## Follow-up

- Create and validate the generic fictional fixture family without Work IQ-derived content.
- Obtain separate authorization before creating Graph Governor source.
- Package and test only after entry criteria in the linked test plan are satisfied.
