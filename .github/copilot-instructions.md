# Copilot instructions for this workspace

- This repository is Project Dexter, a lightweight laboratory for developing, validating, packaging, and evolving Copilot Cowork Skills and Orchestrations; no build, runtime, extension, task, or launch configuration is required.
- Preserve Dexter's core model: evidence over intuition, history over hindsight, explicit dependencies, editable source separated from tested specimens, and no fabricated outcomes.
- Treat each directory under `projects/` as an isolated laboratory effort containing its own documentation, Skill and Orchestration source, test evidence, and artifact exchange.
- Keep project-specific material inside its project boundary. Treat root-level `skills/`, `orchestrations/`, `skill-exchange/`, and `docs/` as reusable Dexter scaffolding or intentionally promoted shared material.
- Establish and maintain each project's source-of-truth chain: Project Charter -> PRD -> recorded MVP scope -> Specifications -> Test Plan -> Test Results -> Confidence Assessment.
- Use the Project Charter for purpose, boundaries, authority, stakeholders, and intended outcomes; use the PRD for user problems, required capabilities, priorities, success measures, and product requirements.
- Treat MVP as a scope decision, not necessarily a standalone document. Record it explicitly in the PRD or an accepted decision so its assumptions and boundaries are traceable.
- Use Specifications for precise behavior, interfaces, constraints, dependencies, interaction qualities, and acceptance criteria. Use Test Plans to define how those claims will be evaluated, not to invent product behavior.
- Treat charters, PRDs, recorded MVP scope, specifications, and test plans as living documents that may evolve through Vibe Coding, training, findings, and user learning.
- Require living source-of-truth documents to identify their owner, status, version, and last update. Link material revisions to the finding or decision that motivated them and preserve superseded versions when their history matters.
- Distinguish present intent from observed history: revise editable source-of-truth documents when intent changes, but never rewrite completed test results to match later expectations.
- When a source of truth changes, perform impact analysis against dependent source, artifacts, scenarios, and evidence. Rerun only tests affected by the change unless broader regression is explicitly justified and authorized.
- Trace every test claim to an accepted requirement or specification. Include humanistic conversational flow, user comprehension, dignity, trust, and usability when they are part of the intended product behavior.
- Use `orchestrations/` for multi-Skill workflow definitions and `docs/inventory/` for traceable Skill and Orchestration registration.
- When an authorized project slice requires coordinated behavior across two or more Skills, tools, or human actors, create or update a project Orchestration to record the sequence, handoffs, approvals, and shared failure boundaries. Do not create one for speculative relationships or shared dependencies alone. Drafting an Orchestration does not authorize implementation, execution, connected access, or release.
- Base confidence assessments on linked test evidence; never present an untested claim as measured confidence.
- Preserve prior skill versions and completed test records; add new dated records instead of rewriting observed history.
- Use lowercase kebab-case for names and `YYYY-MM-DD` for dated records.
- Use the templates in `docs/_templates/` when creating profiles, plans, scenarios, experiments, results, confidence assessments, findings, or decisions.
- Keep direct observations separate from interpretation and never fabricate test outcomes.
- Link related scenarios, artifacts, results, findings, and decisions with repository-relative links.
- Do not commit credentials, secrets, personal data, tenant identifiers, or confidential test content.
- Preserve the package layout and filename required by Copilot Cowork when handling `.SKILL` artifacts or directories containing `SKILL.md`.
- Act as a laboratory assistant: do not implement a project, infer approval, or advance its lifecycle unless the user explicitly directs it.

## Workspace setup status

- [x] Workspace instructions verified.
- [x] Requirements clarified.
- [x] Project scaffolded and customized.
- [x] Extensions skipped because none are required.
- [x] Compilation skipped because the workspace contains Markdown and artifacts only.
- [x] VS Code task skipped because there is no build or run command.
- [x] Launch skipped because there is no executable application.
- [x] Documentation verified and scaffolding comments removed.
