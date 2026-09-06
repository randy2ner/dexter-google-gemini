# Project Dexter

## Build Better AI Skills. Not Bigger Prompts.

**A lightweight laboratory for developing, validating, and evolving AI Skills and Orchestrations.**

---

## You're Already Building Skills

### The problem is that you are not tracking their evolution.

AI solutions often grow through a familiar loop:

```text
Idea
	↓
Build a Skill
	↓
Fix one problem
	↓
Break something else
	↓
Add another Skill
	↓
Tune an Orchestration
	↓
Wonder which change caused the behavior
	↓
Start spinning plates faster
```

The history is trapped inside conversations. Dependencies are undocumented. Testing is informal. Confidence is subjective. When a Skill changes, nobody knows what else might break.

## Enter Dexter's Laboratory

Project Dexter moves Skill development out of isolated prompting and into the durable framework of a GitHub repository. It is laboratory equipment for AI builders: folders, records, templates, and supporting tools for collecting Skills, testing ideas, documenting experiments, validating results, and understanding how changes affect an AI environment.

Dexter is intentionally lightweight. Its structure can be customized, extended, or replaced as the team's practice evolves.

## Meet the Quadroplex-T3000 Computer

The **Quadroplex-T3000 Computer** is the operating model for the repository. It oversees the laboratory by:

- tracking progress;
- recording experiments;
- measuring confidence from evidence;
- monitoring dependencies;
- documenting evolution;
- validating Orchestrations;
- preserving lessons learned;
- preparing Skills and supporting documentation for redistribution; and
- tracking release notes, version history, and packaging readiness.

It does not replace Copilot Cowork. It provides the controlled workbench around Cowork.

## What Can Dexter Do?

Do not develop only where the work happens. Step outside the AI surface and put your Skills up on the lift.

```text
Quadroplex-T3000 Computer
│
├─ Observe
├─ Test
├─ Document
├─ Validate
├─ Package
│
└─ Your next Skills project
	 ├─ Skill A
	 ├─ Skill B
	 ├─ Skill C
	 └─ Skill D
```

Dexter creates traceability from an idea to a versioned Skill, from a scenario to an observed result, and from a finding to a decision. That traceability makes regression risk visible and confidence explainable.

## Laboratory Layout

| Location | Purpose |
| --- | --- |
| [`projects/`](projects/) | Isolated, self-contained laboratory projects such as Compass |
| [`skills/`](skills/) | Reusable Skill source intentionally promoted beyond one project |
| [`orchestrations/`](orchestrations/) | Reusable Orchestration patterns intentionally promoted beyond one project |
| [`skill-exchange/`](skill-exchange/) | Shared exchange area; prefer each project's local exchange for project artifacts |
| [`docs/inventory/`](docs/inventory/) | Skill and Orchestration registry |
| [`docs/test-plans/`](docs/test-plans/) | Test scope, objectives, and acceptance criteria |
| [`docs/scenarios/`](docs/scenarios/) | Reusable and reproducible experiment definitions |
| [`docs/experiments/`](docs/experiments/) | Hypotheses, controlled changes, observations, and interpretations |
| [`docs/test-results/`](docs/test-results/) | Immutable observations from individual runs |
| [`docs/confidence/`](docs/confidence/) | Evidence-based readiness assessments |
| [`docs/findings/`](docs/findings/) | Cross-run findings, regressions, and lessons learned |
| [`docs/decisions/`](docs/decisions/) | Decisions and their rationale |
| [`docs/_templates/`](docs/_templates/) | Copyable records for consistent laboratory work |

## The Dexter Loop

1. **Register** — identify the Skill or Orchestration, its owner, purpose, version, and dependencies.
2. **Build** — develop source in the owning project's `skills/` or `orchestrations/` directory and document meaningful changes.
3. **Design** — shape one repeatable, representative experience and its material boundaries.
4. **Package** — place the exact importable artifact in the owning project's `skill-exchange/ready-for-test/` directory.
5. **Test** — execute the experience in Copilot Cowork, directly or through a [mediated rehearsal](docs/methodology/mediated-cowork-experience-rehearsals.md), and record direct observations.
6. **Assess** — compare expected and actual behavior; update confidence using linked evidence.
7. **Learn** — preserve findings and decisions, including failed experiments.
8. **Evolve** — create a new version and rerun affected scenarios rather than rewriting history.

## Quick Start

1. Create an isolated directory under [`projects/`](projects/) for the effort.
2. Establish its vision and scope charter before defining requirements or implementation.
3. Copy reusable templates from [`docs/_templates/`](docs/_templates/) into the project's documentation area.
4. Develop Skill and Orchestration source inside the project boundary.
5. Exchange, test, and retain exact artifacts inside the project's local exchange area.
6. Promote material to Dexter's root-level collections only after intentionally generalizing it for reuse.

## Core Principles

- **Evidence over intuition.** Confidence must link to observed results.
- **History over hindsight.** Preserve failed runs and superseded versions.
- **Explicit dependencies.** A changed Skill should reveal which Orchestrations and scenarios may be affected.
- **Source versus specimen.** Develop in `skills/`; test the exact packaged copy in `skill-exchange/`.
- **Small and replaceable.** The framework should help the work without becoming the work.
- **No fabricated outcomes.** Record only what was directly observed, then separate interpretation from evidence.
- **Instructions meet a medium.** Evaluate Skill source together with the AI surface, host controls, conversation, and data context that shape its behavior.

## Naming and Lifecycle

- Use lowercase kebab-case for Skill, Orchestration, and scenario names.
- Start dated records with `YYYY-MM-DD`.
- Suggested artifact name: `<skill-name>-v<version>.SKILL`.
- Suggested test result: `YYYY-MM-DD-<skill-name>-<scenario>-<environment>.md`.
- Preserve any package layout or filename required by Copilot Cowork.
- Within the owning project's exchange, move artifacts through `incoming` → `ready-for-test` → `tested` → `archive`.

## Collaboration

Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before changing shared records or artifacts. Never commit credentials, private customer data, tenant identifiers, or sensitive test prompts.
