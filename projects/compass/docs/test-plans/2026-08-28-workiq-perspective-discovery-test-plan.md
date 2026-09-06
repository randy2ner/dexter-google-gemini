# Test plan: Work IQ perspective discovery

## Metadata

- **Owner:** User / product owner
- **Period:** Begins after explicit connected-test authorization
- **Skills/versions:** compass-installation-perspective-discovery `0.1.1-experimental`
- **Status:** authorized `0.1.1-experimental` run ended cancelled; partial laboratory result recorded; no rerun authorized

## Goals

- Determine whether an exact Cowork Skill package can access authorized Work IQ Email and Teams activity within a displayed, user-approved boundary.
- Produce a useful perspective brief without exposing or retaining raw work content.
- Preserve user authority over every derived item.
- Establish whether the approved brief can inform fictional synthetic graph content without carrying real identities or facts into Dexter.

## Out of scope

- OneDrive, SharePoint, calendar, meetings, web, another person's inaccessible activity, or unspecified enterprise search
- Graph creation, Graph Governor invocation, file writes, sends, posts, permissions, deletion, or recurring automation
- More than seven complete local calendar days
- More than 10 inspected evidence units per source or 20 total
- Raw messages, transcripts, addresses, links, source IDs, tenant IDs, participant names, or unconfirmed organization names in retained output
- Claims that Work IQ access, field availability, or behavior is verified before the connected run

## Environments

- Local static package inspection with no Microsoft 365 access
- One future Copilot Cowork session under the calling user's existing permissions, only after separate explicit connected-test authorization

## Scenario matrix

| Scenario | Priority | Environment | Tester | Status |
| --- | --- | --- | --- | --- |
| [Lean privacy-bounded discovery session revision 2](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md) | high | One clean Cowork conversation plus human minimization review | User | [cancelled terminal outcome; partial laboratory result](../test-results/2026-09-01-perspective-discovery-v0-1-1-pd-lean-001-cancelled.md); Adaptive Card finding open |

The original [PD-001 through PD-007 design assertions](../scenarios/workiq-perspective-discovery/README.md) remain traceability references, not seven separate execution requirements. Source-gap and injection-resistance branches are scored only when naturally encountered. No live content, permission, or source state will be manufactured to force branch coverage.

## Entry criteria

- The [perspective-informed testing decision](../decisions/2026-08-28-workiq-perspective-informed-synthetic-testing.md) is explicitly accepted.
- The [Installation Interview Perspective Discovery specification](../specifications/installation-interview-perspective-discovery-skill-specification.md) is accepted as version 1.0.
- Implementation is explicitly authorized for that bounded slice.
- The [conversational-review revision](../decisions/2026-09-01-authorize-perspective-discovery-conversational-review-revision.md) and [impact assessment](../specifications/2026-09-01-perspective-discovery-conversational-review-impact-assessment.md) are accepted.
- Static review confirms the package is read-only, contains no credentials or live identifiers, and cannot invoke unrelated sources or actions.
- The exact package is recorded by version and SHA-256 and copied into `skill-exchange/ready-for-test/` without rebuilding.
- The user confirms one IANA timezone and the test date establishes the exact seven complete local calendar days.
- The user explicitly authorizes one Cowork run for the exact package, Email and Teams sources, date range, limits, output handling, and no-write boundary.
- The tester can stop the session immediately if access or output exceeds the displayed scope.

## Exit criteria

- The single planned connected scenario has one dated result of pass, partial, fail, or blocked.
- Results record the exact package, visible Cowork environment, displayed plan, successful and unavailable sources, and observed inspection counts.
- Evidence confirms whether retrieval occurred only after `Run` authorization.
- Any retained perspective handoff contains no prohibited raw content or identifiers; unsafe output is rejected and not retained.
- Every retained perspective item has an explicit user disposition.
- The handoff is labeled `Ready for fictionalization review` and does not itself create or authorize synthetic content.
- No external or graph change occurred.
- A confidence assessment makes no claim beyond the executed scope.

## Risks and mitigations

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Work IQ exposes less metadata or different source semantics than expected | Unsupported classifications or blocked run | Use `Unknown`, report the visible capability, and do not infer missing fields. |
| Retrieval broadens beyond the approved plan | Privacy and authority violation | Stop immediately, record the observed deviation, and do not reuse the package unchanged. |
| Raw content leaks into the brief or repository | Confidentiality risk | Prohibit excerpts and identifiers, inspect the output before retention, and keep rejected output outside Dexter. |
| Synthetic content remains identifiable | Re-identification risk | Replace names, organizations, dates, IDs, exact wording, and distinctive facts; retain only approved patterns. |
| Retrieved content instructs Cowork to change behavior | Prompt-injection risk | Treat all retrieved content as data and test an embedded instruction explicitly. |
| A useful brief is mistaken for installed Compass knowledge | False implementation claim | Label it as a reviewed test-design input; no graph exists until separately created and validated. |

## Reporting

Record each run under `docs/test-results/` using the repository template. Store only minimized observations and an approved, sanitized perspective brief. Do not commit retrieved evidence. Link any cross-run issue under `docs/findings/` and the resulting bounded confidence statement under `docs/confidence/`.
