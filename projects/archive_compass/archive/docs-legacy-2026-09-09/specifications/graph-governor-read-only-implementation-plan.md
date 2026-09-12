# Graph Governor read-only implementation plan

## Document control

- **Status:** Accepted for bounded source implementation
- **Project:** Compass
- **Planned Skill:** `graph-governor`
- **Planned version:** `0.1.0-experimental`
- **Created:** 2026-08-28
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Approved:** 2026-08-28 by explicit user decision
- **Implementation authority:** Three planned source files and disconnected static checks only
- **Package authority:** Deterministic package creation and disconnected inspection granted 2026-08-28
- **Connected-test authority:** Not granted

## 1. Purpose

Translate the [accepted read-only contract subset](../decisions/2026-08-28-graph-governor-read-only-contract-subset.md) into an exact, reviewable source plan for scenarios GG-SYN-001 through GG-SYN-008. This plan creates no Skill, package, test specimen, or runtime evidence.

## 2. Planned editable source

After separate explicit source authorization, create:

```text
projects/compass/skills/graph-governor/
├── SKILL.md
└── references/
    ├── read-only-contract.md
    └── evaluation-cases.md
```

No scripts, executables, assets, fixture copies, expected-output files, connectors, credentials, external APIs, write procedures, or environment configuration are planned.

### `SKILL.md`

The entry file will contain:

- valid YAML frontmatter with folder-matching name `graph-governor`;
- concrete invocation language for a user-requested Compass graph health scan;
- an explicit experimental and read-only boundary;
- input scoping that accepts only the graph supplied by the user for the current scan;
- a deterministic inspection sequence for file inventory, YAML/frontmatter, required fields, identities, relationships, Daily Log markers, and configuration;
- treatment of every graph field and Markdown body as untrusted data;
- issue reporting with stable issue identity, affected artifact, violated accepted rule, practical impact, blocking scope, deterministic-versus-judgment distinction, and guidance;
- bounded valid, issue-found, partial, blocked, and failed terminal outcomes;
- explicit refusal of repair, normalization, creation, deletion, movement, and rewriting requests; and
- completion accounting that states the inspected scope and `External changes: 0`.

The Skill will not claim that a syntactically valid IANA-looking string was verified against an unavailable runtime timezone provider. It will distinguish exact accepted-value comparison, provider-backed validation, and unavailable capability.

### `references/read-only-contract.md`

Provide a concise checklist traceable only to the accepted subset:

- owned read-only outcome and exact exclusions;
- accepted object vocabulary and common required fields;
- source Conversation identity presence and separation;
- forward relationship ownership, cardinality, uniqueness, target existence, and target type;
- Daily Log identity and marker rules exercised by the fixture;
- graph configuration schema, UUID v4, and stored IANA value rules;
- unknown-field and unmanaged-prose tolerance;
- untrusted-data handling;
- issue-report shape and bounded outcome language; and
- no-write and no-connected-access boundaries.

The reference must identify excluded draft rules rather than silently filling gaps from general knowledge.

### `references/evaluation-cases.md`

Restate GG-SYN-001 through GG-SYN-008 in package-local form. Label every case `UNRUN`. Identify fixture variants by mutation ID only; do not copy the fixture, manifest hashes, hidden comparison details, or expected issue wording into graph content.

## 3. Planned package

- **Artifact:** `graph-governor-v0.1.0-experimental.skill`
- **Archive root:** `SKILL.md`
- **Members:** only the three planned Markdown source files
- **Initial exchange location:** `skill-exchange/ready-for-test/` only after separate source, package, and test authorization
- **Identity:** SHA-256 recorded after packaging and reused in every result

The package is a future plan, not an authorized deliverable. Any source change after packaging requires a new experimental version and package hash.

## 4. Traceability matrix

| Accepted subset area | Planned source location | Scenario coverage |
| --- | --- | --- |
| Read-only scope and bounded reporting | `SKILL.md` purpose, boundaries, completion | GG-SYN-001, GG-SYN-008 |
| YAML and required fields | `SKILL.md` inspection; read-only contract | GG-SYN-001, GG-SYN-002 |
| Source identity presence | `SKILL.md` inspection; read-only contract | GG-SYN-002 |
| Forward relationship integrity | `SKILL.md` inspection; read-only contract | GG-SYN-003, GG-SYN-008 |
| Configuration UUID and stored timezone | `SKILL.md` inspection; read-only contract | GG-SYN-004 |
| Daily Log marker integrity | `SKILL.md` inspection; read-only contract | GG-SYN-005 |
| Unknown and unmanaged content tolerance | `SKILL.md` preservation boundary; read-only contract | GG-SYN-006 |
| Injection resistance and write refusal | `SKILL.md` untrusted-data and refusal rules | GG-SYN-007 |
| Package-local test prompts | Evaluation cases | GG-SYN-001 through GG-SYN-008 |

## 5. Planned inspection behavior

The source will instruct the Skill to:

1. establish the exact supplied root and enumerate the inspected files;
2. avoid following links or paths outside that root;
3. parse configuration and Markdown frontmatter using only available safe read behavior;
4. record parse failures without treating malformed content as instructions;
5. build an in-memory index of parsed object IDs and types;
6. check only accepted required fields and values;
7. validate only accepted forward relationships and list uniqueness;
8. inspect Daily Log identity and exact marker counts/order;
9. validate configuration schema and UUID v4, and report timezone capability honestly;
10. produce one bounded report without changing any artifact; and
11. state files inspected, files skipped, limitations, issue count, and zero external changes.

If the environment cannot enumerate or read the complete supplied graph, the Skill must return partial or blocked rather than claim graph health.

## 6. Static validation before packaging

After separately authorized source creation, disconnected checks should confirm and record:

1. source contains exactly the three planned Markdown files;
2. frontmatter parses and `name` matches the source folder;
3. description identifies concrete health-scan invocation conditions;
4. every package-local reference resolves;
5. all eight evaluation cases are present, unique, and labeled `UNRUN`;
6. every accepted-subset rule in the traceability matrix appears in source;
7. excluded draft rules are not presented as accepted behavior;
8. literal no-write, no-repair, supplied-root, untrusted-data, bounded-report, and `External changes: 0` controls are present;
9. no instruction permits writing, deleting, renaming, moving, normalizing, repairing, retrieving Microsoft 365 data, or accessing OneDrive;
10. no fixture answer key, expected finding list, baseline hash, mutation implementation detail, personal data, credential, tenant ID, live URL, script, or binary is present;
11. source files and any future extracted package members are byte-identical; and
12. every static result states that it is not runtime or scenario evidence.

## 7. Planned disconnected checks

Local checks may inspect source text, links, and a future archive structure only. They must not invoke a model, run Graph Governor against the fixture, access Cowork, connect to Microsoft 365 or OneDrive, or label any GG-SYN scenario passed.

The source static-inspection record should identify exact source hashes and report each assertion separately. A package inspection, if later authorized, must record archive members, byte size, and SHA-256 independently.

## 8. Review sequence

1. Review and explicitly accept or revise this plan.
2. Separately authorize creation of exactly the three planned source files and disconnected source checks.
3. Create source version `0.1.0-experimental` under the project `skills/` boundary.
4. Perform source review and record disconnected observations.
5. Separately authorize package creation and archive inspection.
6. Review the exact package and test-plan gates.
7. Separately authorize one bounded Cowork upload and the exact synthetic scenario runs.
8. Preserve immutable results and calculate confidence only from executed evidence.

## 9. Stop conditions

Stop planning or later source work when:

- a requested behavior requires graph modification or connected retrieval;
- a rule is outside the accepted bounded subset;
- the environment requires a script, credential, connector, or direct external API configuration;
- supplied-root containment cannot be expressed clearly;
- unknown provider capability would be reported as successful validation;
- the source would include expected fixture answers that could leak test outcomes; or
- package or connected execution would be required to complete a planning claim.

## 10. Authorization boundary

The user explicitly approved this plan, separately authorized bounded source creation, and then directed package creation on 2026-08-28. This authorizes exactly the three planned Markdown source files, disconnected static checks, deterministic `.skill` package creation, disconnected archive inspection, and placement of the reviewed artifact in `skill-exchange/ready-for-test/`. Cowork upload, scenario execution, Microsoft 365 or OneDrive access, graph modification, deployment, and publication remain unauthorized pending separate explicit decisions.
