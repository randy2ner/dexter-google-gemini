# Installation Interview Perspective Discovery implementation plan

## Document control

- **Status:** Accepted for bounded source implementation
- **Project:** Compass
- **Planned Skill:** `compass-installation-perspective-discovery`
- **Planned version:** `0.1.0-experimental`
- **Created:** 2026-08-28
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Approved:** 2026-08-28 by explicit user decision
- **Implementation authority:** Three planned source files and disconnected static checks only
- **Package or connected-test authority:** Not granted

## 1. Purpose

Translate the accepted [Perspective Discovery specification version 1.0](installation-interview-perspective-discovery-skill-specification.md) into an exact, reviewable source and package plan. This plan creates no Skill and accesses no Cowork or Work IQ environment.

## 2. Planned editable source

After explicit implementation authorization, create:

```text
projects/compass/skills/compass-installation-perspective-discovery/
├── SKILL.md
└── references/
    ├── behavior-contract.md
    └── evaluation-cases.md
```

No scripts, executables, assets, connectors, credentials, or environment configuration are planned.

### `SKILL.md`

The entry file will contain:

- valid YAML frontmatter with folder-matching name `compass-installation-perspective-discovery`;
- a keyword-rich description covering Installation Interview, Perspective Discovery, Work IQ, Email, Teams, and fictional Compass test design;
- explicit read-only and no-installation boundaries;
- timezone confirmation and displayed-plan authorization;
- bounded retrieval procedure;
- candidate derivation and review procedure;
- output minimization and fictionalization handoff;
- source-gap, cancellation, empty, blocked, and failure behavior;
- injection resistance and unsupported-action refusal; and
- terminal accounting with `External changes: 0`.

Keep the entry file below 500 lines. Put detailed acceptance assertions and test prompts in the two reference files.

### `references/behavior-contract.md`

Provide a concise, specification-traceable checklist for:

- owned outcome;
- exact permitted context;
- authority sequence;
- allowed candidate categories;
- prohibited retained fields;
- user dispositions;
- handoff shape;
- no-write boundary; and
- terminal outcomes.

### `references/evaluation-cases.md`

Restate the seven approved scenario inputs and expected behavior in package-local form. Label every case `UNRUN`. Do not include real Work IQ data or expected answers derived from the user's environment.

## 3. Planned package

- **Artifact:** `compass-installation-perspective-discovery-v0.1.0-experimental.skill`
- **Archive root:** `SKILL.md`
- **Members:** only the three planned Markdown files
- **Initial exchange location:** `skill-exchange/ready-for-test/` only after source and package review
- **Identity:** SHA-256 recorded after packaging and reused in every test result

The package will be created from reviewed source once. The test specimen will be copied without rebuilding. Any source change requires version `0.1.1-experimental` or later and a new hash.

Observed layout of prior artifacts supports a ZIP-compatible archive with root `SKILL.md`, but current Cowork acceptance remains a test target rather than an assumed fact.

## 4. Traceability matrix

| Accepted specification area | Planned source location | Scenario coverage |
| --- | --- | --- |
| Owned outcome and boundaries | `SKILL.md` Purpose and Boundaries | PD-001, PD-007 |
| Timezone and authorization plan | `SKILL.md` Authorization | PD-001 |
| Sources, dates, permissions, and limits | `SKILL.md` Retrieval | PD-002, PD-005 |
| Candidate categories and evidence handling | `SKILL.md` Candidate Review; behavior contract | PD-003, PD-004 |
| Output minimization | `SKILL.md` Handoff; behavior contract | PD-004, PD-007 |
| Injection resistance | `SKILL.md` Safety Boundary | PD-006 |
| Terminal outcomes and no-write accounting | `SKILL.md` Completion | PD-001 through PD-007 |

## 5. Static validation before packaging

Confirm and record:

1. source contains exactly the planned files;
2. frontmatter parses and `name` matches the source folder;
3. description identifies concrete invocation conditions;
4. every package-local link resolves one level below `SKILL.md`;
5. package has no traversal path, absolute path, link, binary, script, or unexpected member;
6. source and extracted package Markdown are byte-identical;
7. secret, token, tenant-ID, personal-address, and live-link pattern scans return no unexplained hits;
8. all evaluation cases are labeled `UNRUN`;
9. instructions contain no graph write, OneDrive, send, post, delete, permission-change, or automation procedure;
10. limits remain seven complete days, 10 items per source, and 20 total;
11. output exclusions match specification version 1.0; and
12. package filename, byte size, member list, and SHA-256 are recorded.

Static success proves package construction only. It does not prove Cowork import, activation, Work IQ access, source behavior, privacy behavior, or scenario outcomes.

## 6. Planned local checks

Local checks may inspect text and archive structure only. They must not call a model, Microsoft 365, Cowork, Work IQ, OneDrive, Graph, or another external service.

The check record should report each assertion separately and fail closed on an unknown or unexpected package member. No check may label a connected scenario passed.

## 7. Review sequence

1. Authorize creation of the exact planned source and local static checks.
2. Create source version `0.1.0-experimental` under the project `skills/` boundary.
3. Review source against specification version 1.0.
4. Run local static checks and record observations.
5. Separately authorize package creation.
6. Create and inspect the exact `.skill` specimen.
7. Accept the Work IQ test plan or revise it from review findings.
8. Separately authorize one connected Cowork upload and run with exact dates and environment.
9. Preserve direct results without importing Work IQ evidence into Dexter.

## 8. Stop conditions

Stop implementation or packaging when:

- a requested change broadens accepted responsibility;
- a package requires a script, credential, connector, or direct external API configuration;
- current Cowork packaging requirements cannot be established without a connected action;
- a static check cannot distinguish source from generated specimen;
- output handling would retain raw or re-identifiable Work IQ content; or
- any instruction implies graph installation or modification.

## 9. Authorization boundary

The user explicitly accepted this plan on 2026-08-28, authorizing only creation of the three planned source files and local, disconnected static checks. Package creation, movement to `ready-for-test/`, Cowork upload, Work IQ retrieval, connected execution, graph creation, and Graph Governor implementation or testing remain separately unauthorized unless explicitly included in a later user decision.
