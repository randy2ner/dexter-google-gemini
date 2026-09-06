# Decision: Authorize lean Perspective Discovery connected run

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery package inspection](../test-results/2026-09-01-perspective-discovery-package-inspection.md), [lean-scope decision](2026-09-01-reduce-perspective-discovery-to-one-connected-run.md)

## Context

The exact Perspective Discovery package passed disconnected inspection. The user reduced the seven-scenario plan to one staged, privacy-bounded conversation and confirmed `America/New_York` as the IANA timezone. For a run on 2026-09-01, the previous seven complete local calendar days are 2026-08-25 through 2026-08-31 inclusive.

Connected authorization remains necessary because the run may inspect real Email and Teams activity exposed through the signed-in user's existing Cowork permissions. Raw or identifying work content must not be retained in Dexter or returned as test evidence.

## Decision

Authorize one execution of [PD-LEAN-001 revision 1](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md) using only the exact reviewed package:

- artifact: `compass-installation-perspective-discovery-v0.1.0-experimental.skill`;
- size: 5,972 bytes;
- SHA-256: `0dfa685330afabe0d3e3e31ad1b5beaf3211c0d275dc1aaac845c92896bfb56f`;
- conversation count: one clean Cowork conversation;
- timezone: `America/New_York`;
- date window: 2026-08-25 through 2026-08-31 inclusive;
- sources: signed-in user's authorized Email and Teams activity only;
- inspection limits: no more than 10 evidence units per source and 20 total; and
- external changes: none.

The authorization would permit:

1. importing the exact package into Cowork;
2. submitting the scenario's exact invocation prompt once;
3. confirming `America/New_York` once;
4. reviewing the complete displayed plan before retrieval;
5. selecting `Run` once only if the displayed plan exactly matches this decision;
6. allowing the bounded retrieval to reach one honest terminal outcome;
7. confirming, editing, generalizing, or excluding naturally produced candidates according to user judgment;
8. reviewing the minimized handoff before retaining any generic content; and
9. recording only the privacy-bounded evidence allowed by the scenario.

Do not select `Run` if the displayed plan differs from the authorized timezone, dates, sources, limits, retention rule, or no-change boundary. A mismatch produces a blocked result without retrieval.

The authorization would not permit another conversation, retry, source substitution, wider dates, more evidence units, OneDrive, SharePoint, files, calendar, meetings, web, enterprise search, another person's activity, permission changes, creation of test messages, deliberate injection seeding, raw-content retention, complete transcript retention, screenshots containing work content, graph access or writes, another Skill, external action, package revision, deployment, or release.

If unsafe or identifying output appears, stop and do not copy it into Dexter or this chat. Record only the stage, stop category, whether retrieval may have occurred, safe terminal accounting if available, and `rejected—not retained`.

## Alternatives considered

- **Authorize the original seven runs:** Rejected by the accepted lean-scope decision.
- **Retain complete Cowork responses:** Rejected because they may contain confidential, personal, tenant-specific, or re-identifiable work context.
- **Permit an automatic retry after a blocked plan:** Rejected because a changed scope requires review and new authorization.

## Consequences

- One run can establish bounded runtime evidence while limiting repeated access to real work context.
- Honest source gaps, an empty result, or a correct block may be valid evidence without forcing additional retrieval.
- Naturally unobserved source-gap or injection branches remain confidence gaps rather than automatic reasons for another run.
- Any unsafe access, retention, authority expansion, or external change stops progression.

## Follow-up

- Project Dexter: verify the exact package locally, then provide only the pre-retrieval stage instructions.
- User / product owner: import the exact package, submit the invocation, confirm the timezone, and return only the displayed plan before selecting `Run`.
- Project Dexter: compare the displayed plan with this authorization before any retrieval proceeds.