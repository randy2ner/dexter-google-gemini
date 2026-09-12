# Project Charter: Dexter

## Document control

- **Status:** living
- **Version:** 1.3
- **Owner:** Dexter product owner
- **Created:** 2026-09-07
- **Last updated:** 2026-09-09
- **Supersedes:** None
- **Implementation authority:** This Charter governs Dexter's design and development. It does not authorize work on a laboratory project or access to connected systems.

## Source register

| Source | Contribution | Authority treatment |
| --- | --- | --- |
| Product-owner direction, 2026-09-07 | Dexter's vision and intended outcomes | binding |
| [Project Dexter README](../../README.md) | Current repository purpose, layout, and operating loop | living implementation context |

## Vision

Dexter helps regular people develop dependable, understandable, and portable AI Skills and Orchestrations without requiring them to adopt a software team's process. It acts as a laboratory assistant: it helps shape the project, maintains its knowledge, selects appropriate development procedures, preserves evidence, and prepares the completed work to stand on its own.

## Problem and opportunity

People can create useful AI behavior conversationally, but the intent, reasoning, dependencies, and verification behind that behavior are easily lost. Documentation is often postponed, tests become tied only to source changes, development scaffolding grows beyond the user's needs, and completed work remains coupled to the environment in which it was built.

Dexter makes the durable parts of good development happen naturally during the work. It supplies governed assistance and bounded capabilities while leaving product choices and consequential authority with the user.

## Intended users and stakeholders

- People building personal or team Copilot Skills and Orchestrations, including users without conventional software-development experience.
- Project owners who decide product intent, authority, acceptable risk, readiness, and release.
- Future maintainers and collaborators who need grounded project knowledge rather than reconstructed conversation history.
- People affected by a project's connected access, retained data, or durable effects.

## Intended outcomes

- Users can move from an idea to a complete beta experience without first designing a development process.
- Each project accumulates one concise Specification and one trustworthy Test Plan as it evolves.
- Dexter can perform repeatable laboratory work under clear authority limits.
- Important features and use cases receive fresh evidence when change, drift, elapsed time, or user concern makes verification due.
- A completed project can leave Dexter with its knowledge, source, dependencies, evidence, and usable artifacts intact.

## Core Tenets

1. **Build the instruction manual alongside the project.** Maintain one Specification and one Test Plan as purpose, choices, behavior, verification needs, and results become clear.
2. **Make the project a grounded knowledge source.** Preserve current instructions with the important reasons, decisions, dependencies, evidence, and prior results behind them.
3. **Test continuously.** Maintain a compact ledger of important features and representative use cases, and revisit them when change, drift, elapsed time, user concern, or a readiness decision makes fresh evidence useful.
4. **Use the minimum helpful structure.** Add only the documentation, scaffolding, and tests needed to understand, evaluate, maintain, and advance the project.
5. **Graduate an independent project.** Keep project-specific knowledge, source, dependencies, evidence, instructions, and distributable artifacts inside the project so it remains usable after removal from Dexter.

## Scope

### In scope

- The instructions, tools, workflows, templates, and repository conventions Dexter uses to assist project development.
- Project shaping, specification, implementation support, experiential testing, evidence preservation, packaging, maintenance, and portability verification.
- The rules for user authority and for using recorded project information when Dexter chooses and uses its capabilities.

### Out of scope

- Owning the product intent of a project built through Dexter.
- Treating project-specific Skills as Dexter capabilities or as universal assets for other projects.
- Assuming authority to access connected systems, mutate durable data, accept requirements, release artifacts, or fabricate outcomes.
- Requiring developer-level infrastructure when a smaller structure can preserve intent, evidence, and portability.

## Success signals and guardrails

- A user can understand what Dexter is doing, why it selected a capability, and what decision or authorization is needed from them.
- Living project documents reflect current intent and retain links to material rationale.
- Verification evidence names the exact candidate, environment, and limitations without claiming unobserved outcomes.
- The feature and use-case ledger makes stale or missing evidence visible without becoming an exhaustive test matrix.
- Project graduation detects required dependencies outside the project boundary.
- Dexter's own operating structure remains smaller and clearer than the projects it helps users create.

## Risks and open questions

- Dexter's procedures may become overly broad, overlap, or reproduce the documentation burden its lightweight purpose rejects.
- Agent discretion may be confused with authority to make product decisions or cause connected effects.
- Repository conventions alone may not enforce every permission or portability boundary; tools and workflows may need explicit controls.
- Dexter's operating procedures still need to be specified and tested through a representative development journey.

## Related sources of truth

- **PRD:** pending
- **Specifications:** pending
- **Test Plan:** pending
- **Source-of-truth register:** pending

## Revision history

| Version | Date | Change | Motivation |
| --- | --- | --- | --- |
| 1.3 | 2026-09-09 | Restored the five Core Tenets to the Charter as authoritative product principles; workspace instructions continue to operationalize them. | Product-owner decision that Core Tenets belong in the Charter. |
| 1.2 | 2026-09-07 | Kept the Charter focused on Dexter's product vision and boundaries; moved the five agent-behavior tenets to the workspace Instruction and removed assumptions about unbuilt Dexter Skills. | Product-owner clarification that the tenets belong in Instruction and Skill design has not begun. |
| 1.1 | 2026-09-07 | Simplified the Dexter Skill model and defined grounded project knowledge in plain language. | Product-owner direction to avoid abstract, repetitive capability fields. |
| 1.0 | 2026-09-07 | Established Dexter's vision, boundaries, five core tenets, and distinction between tenets and capabilities. | Product-owner direction to make the tenets authoritative in Dexter's Charter. |

## Acceptance boundary

This Charter establishes Dexter's product purpose and boundaries. It does not define detailed operating procedures, authorize implementation of a particular project, establish connected-system permissions, or demonstrate that Dexter has achieved the intended outcomes.