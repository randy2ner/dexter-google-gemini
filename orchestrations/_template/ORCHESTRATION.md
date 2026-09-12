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

| Dependency | Type | Compatibility condition | Required | Failure impact |
| --- | --- | --- | --- | --- |
| [Name or relative link] | [Skill/tool/data/human] | [Condition] | [Yes/No] | [Impact] |

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

## Test Plans

- [Relative link to each Test Plan and the coordinated behavior it confirms]

## Revision guidance

[Identify affected Specifications, Skills, packages, and Test Plans when this coordination changes.]
