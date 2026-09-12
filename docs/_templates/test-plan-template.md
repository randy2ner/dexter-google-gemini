# [Project] Test Plan

## Metadata

- **Owner:** [name or team]
- **Specifications:** [Links to every Specification this plan verifies]
- **Candidate:** [Skill, Orchestration, or package identity]
- **Skill host product:** [Cowork, Scout, or another host]
- **Status:** [draft, active, complete]
- **Last updated:** YYYY-MM-DD

## Success decision

[The decision this testing informs and the threshold for success.]

## Scope and environment

- **In scope:** [cases and claims]
- **Out of scope:** [exclusions]
- **AI surface:** [User-visible experience]
- **Material host conditions:** [Only capabilities, permissions, context, file handling, or controls that affect the behavior under test]
- **Privacy:** [what may and may not be retained]

## Host compatibility profile

- **Required host behavior:** [What the Skill needs the host to provide]
- **Observed conditions:** [Relevant observations on the named host]
- **Another host:** Identify its product, run the focused capability checks below, compare observed differences, and record a compatibility or adaptation hypothesis before the complete journey.

## Complete journey

| Stage | Skill or component | User decision | Observable effect or no-write outcome |
| --- | --- | --- | --- |
| [stage] | [skill] | [decision] | [effect] |

This is a shaping guide, not an exact script. Prompts, situations, checks, and confirmation criteria should be repeatable; wording, sequence, and model responses may vary.

## Test cases

| ID | Specification behavior | Prompt or situation | Practical check and observable confirmation | Status | Latest observation |
| --- | --- | --- | --- | --- | --- |
| TEST-001 | [Specification link and ID] | [Natural workflow or focused condition] | [What can vary and what must be observed] | [not run, passed, partial, failed, or blocked] | [date and concise result] |

## Focused host capability checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| [Required host behavior] | [Smallest safe operation] | [Observable result or limitation] | [not run, available, available with conditions, unavailable, blocked, or unknown] |

## Material stop conditions

- Unauthorized access, retention, or mutation.
- Privacy exposure or identity corruption.
- Destructive history loss or unrecoverable state.
- Unusable consequential approval or cancellation.
- Materially false effect reporting.

Record ordinary friction and non-blocking incompatibilities through the complete journey. Do not rebuild the candidate after each observation.

## Execution log

Append observations; do not rewrite an earlier run to match later expectations.

### YYYY-MM-DD - [candidate/run]

- **Cases:** [IDs]
- **Direct observation:** [what was visibly observed]
- **Operator-reported observation:** [only when Dexter cannot directly observe the surface]
- **Independent effect check:** [stored effect or no-write verification]
- **Defects and limitations:** [concise list]
- **Assessment:** [passed, partial, failed, or blocked, with exact scope]

## Current success assessment

- **Assessment:** [not established, partial, successful for stated scope, unsuccessful]
- **Supported claims:** [IDs]
- **Unresolved claims:** [IDs and why]
- **Next test or revision:** [next representative use, focused diagnosis, or coordinated revision]
