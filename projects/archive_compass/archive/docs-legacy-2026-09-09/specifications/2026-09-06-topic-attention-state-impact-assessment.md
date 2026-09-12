# Change Impact Assessment: Topic attention state

## Document control

- **Date:** 2026-09-06
- **Status:** accepted
- **Owner:** User / product owner
- **Changed source/version:** [Shared Contracts and Graph Schema `0.5-attention-state-baseline`](compass-graph-schema-specification.md), object schema version 2
- **Motivation:** [Accepted Topic attention-state decision](../decisions/2026-09-06-add-topic-attention-state.md)

## Change summary

Every Tracking Topic gains required `attentionState: action|waiting|observing`. The field records the user's relationship to the Topic independently of lifecycle, archival success, participation, and relationships. This is a required schema-v2 field addition, not a schema-version migration.

## Impact map

| Dependent item | Impact | Required action |
| --- | --- | --- |
| PRD and traceability | affected | Add the accepted attention requirement and evidence path. |
| Shared Contracts and Graph Schema | affected | Define meaning, values, authority, lifecycle interaction, and validation. |
| Installation Interview | affected | Ask for one initial value per foundational Topic. |
| Daily Scan | affected | Display accepted state when useful but never infer, approve, or mutate it. |
| Tracking Topic Interview | affected | Own creation, change, merge-target selection, and reactivation confirmation. |
| Curator | affected | Use accepted state as a review lens and route user-selected changes. |
| Graph Governor | affected | Require the field, enforce the closed enum, and validate authority. |
| Lifecycle Orchestration | affected | Coordinate ownership and preserve state across archival/reactivation. |
| Prior schema-v2 fixtures and results | remain exact historical specimens | Preserve unchanged; add a separate attention-state fixture. |
| Prior packages | remain exact historical artifacts | Preserve unchanged; package all five revised Skill sources. |

## Smallest justified retest set

- Parse one Topic for each accepted value and one archived Topic retaining attention state.
- Reject missing, null, empty, and unknown values.
- Observe Installation initial-state choice and Topic Interview change/cancellation.
- Confirm Daily Scan and Curator do not infer or mutate the state.
- Confirm archival retention and reactivation confirmation or change.

## Authorization boundary

The product-owner request authorizes source, documentation, fixture, static-validation, and candidate-package updates. Runtime execution, connected access, graph migration, deployment, promotion, and release remain unauthorized.