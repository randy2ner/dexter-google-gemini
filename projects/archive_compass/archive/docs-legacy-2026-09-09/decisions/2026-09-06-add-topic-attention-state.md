# Decision: Add Topic attention state

- **Date:** 2026-09-06
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Missing structured attention distinction](../specifications/2026-09-06-topic-attention-state-impact-assessment.md)

## Context

Compass needs to distinguish Topics where the user has an action, is waiting on someone or something, or is retaining awareness without direct involvement. Lifecycle status, archival success, participant membership, and Conversation alignment do not represent that meaning.

## Decision

Add required Tracking Topic field `attentionState` under object schema version 2 with exactly three values:

- `action`: the user has a next action;
- `waiting`: progress depends on another person, event, decision, or external condition; and
- `observing`: the user is retaining awareness without direct involvement or a current action.

The field is independent of `status`, `success`, `participantIds`, `excludedParticipantIds`, `cspId`, and Conversation alignment. Installation asks for the initial value. Tracking Topic Interview owns later changes. Daily Scan may display but not infer or change it. Curator may recommend review but not derive or change it. Graph Governor validates the value and authority.

Archival retains the last accepted attention state as historical context. Reactivation requires the user to confirm or change it while removing archival `success`.

## Alternatives considered

- **Use Topic `status`:** Rejected because active/archived lifecycle is independent of the user's current relationship to the work.
- **Use `participantIds`:** Rejected because participation does not assert action ownership or direct involvement.
- **Derive from activity:** Rejected because messages, recency, and participants do not establish the user's intent.
- **Make the field optional:** Rejected because absence would preserve the ambiguity this decision resolves.

## Consequences

- All five Skills, the lifecycle Orchestration, schema, contracts, profiles, packages, and test sources require compatible revisions.
- Existing schema-v2 Topics without the field require explicit user classification before mutation under the revised contract.
- Prior packages, fixtures, and completed evidence remain unchanged and version-bound.

## Follow-up

- Statically validate all three values and lifecycle independence.
- Execute the focused conversational and validation scenario only after separate authorization.