# Orchestration: [descriptive name]

> Template: replace every bracketed placeholder before validation.

## Identity

- **Name:** [lowercase-kebab-case]
- **Version:** [semantic or documented version]
- **Owner:** [name or team]
- **Status:** [idea, active, validating, stable, deprecated]

## Purpose

[Describe the outcome and why multiple Skills are required.]

## Trigger

[Describe how and when this Orchestration begins.]

## Dependencies

| Dependency | Type | Version/constraint | Required | Failure impact |
| --- | --- | --- | --- | --- |
| [Name or relative link] | [Skill/tool/data/human] | [Version] | [Yes/No] | [Impact] |

## Flow

1. [Skill or actor] receives [input] and produces [output].
2. [Routing or decision condition].
3. [Next Skill, tool, or human approval].

## Handoffs and contracts

| From | To | Data or artifact | Success condition |
| --- | --- | --- | --- |
| [Source] | [Destination] | [Contract] | [Observable condition] |

## Guardrails and approvals

- [Action the user must approve or perform]
- [Privacy, safety, or data boundary]

## Failure and fallback behavior

- [Failure mode]: [expected response and recovery path]

## Validation scenarios

- [Relative link to a scenario]

## Change impact

[Identify which scenarios and downstream dependencies must be revisited when this Orchestration changes.]
