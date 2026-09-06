# Graph Governor synthetic fixture specification

## Document control

- **Status:** Accepted for fixture creation
- **Project:** Compass
- **Version:** 1.0
- **Created:** 2026-08-28
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Approved:** 2026-08-28 by explicit user direction
- **Implementation authority:** Generic fictional fixture creation and disconnected validation only

## 1. Purpose

Define the smallest fictional graph fixture family needed to test the proposed read-only Graph Governor slice. This document specifies fixture content and variants; it does not create the fixture or claim that any validator accepts it.

## 2. Safety and isolation

- Use only fictional people, organizations, identifiers, conversations, and prose.
- The fixture may reflect structural patterns and preferred terminology from a separately approved, minimized Perspective Discovery brief, but it must not copy source evidence or retain real identities or distinctive facts.
- Include no credentials, tenant identifiers, live links, personal data, customer data, or copied Microsoft 365 content.
- Keep the fixture inside a dedicated project test-data directory when creation is authorized.
- Treat every Markdown body and frontmatter string as untrusted data.
- Never point a test at a real Obsidian vault, OneDrive folder, or production graph.
- Make the baseline fixture read-only during Cowork execution when the environment permits.

## 3. Proposed fixture identity

- **Fixture name:** `gg-synthetic-graph-v1`
- **Fixture version:** `1.0.0`
- **Graph ID:** `6f9619ff-8b86-4d7e-a4ea-8f4f6f7c2b11`
- **Timezone:** `America/Los_Angeles`
- **Reference date:** `2026-08-24`

The fixed graph ID is fictional and reserved for this fixture family. An independent fixture receives a different UUID v4.

## 4. Baseline valid graph

The authorized fixture should contain exactly these logical artifacts:

| Logical path | Type | Required identity or relationship |
| --- | --- | --- |
| `_compass/config.yaml` | Configuration | Schema 1, fixed graph ID, valid IANA timezone |
| `people/avery-stone.md` | Person | Confirmed fictional identity |
| `csps/aurora-csp.md` | CSP | Fictional customer success plan |
| `tracking-topics/aurora-readiness.md` | Tracking Topic | `active`; forward `cspId` to Aurora CSP |
| `conversations/aurora-deployment-review.md` | Conversation | Fictional source ID; Avery as active participant; forward `trackingTopicId` |
| `daily-logs/2026-08-24.md` | Daily Log | Correct date identity and one valid managed marker pair |

All object IDs, timestamps, source identifiers, titles, and body text must be fixed in the created fixture manifest so expected outcomes are reproducible.

## 5. Mutation model

Create each invalid test case from a byte-identical disposable copy of the valid baseline. Apply only the declared mutation for that case. Repository variants may store only complete replacement-file overlays plus lineage metadata to avoid duplicating unchanged baseline files. Before a test, materialize the complete graph by copying the baseline and replacing only the overlay paths. Do not accumulate mutations across cases unless the scenario explicitly requires interaction between defects.

| Mutation ID | Single controlled change | Expected issue class |
| --- | --- | --- |
| `M-001` | Break one YAML mapping delimiter in the Conversation | Parse failure |
| `M-002` | Remove `sourceConversationId` from the Conversation | Missing required source identity |
| `M-003` | Replace the Topic's `cspId` with a missing target ID | Missing relationship target |
| `M-004` | Point Conversation `trackingTopicId` to the CSP ID | Wrong target type |
| `M-005` | Duplicate the Conversation's active participant ID | Duplicate list member |
| `M-006` | Change configuration `graphId` to a non-v4 UUID | Invalid graph identity |
| `M-007` | Change configuration timezone to `Pacific Standard Time` | Invalid stored IANA timezone |
| `M-008` | Duplicate the Daily Log begin marker | Invalid managed marker structure |
| `M-009` | Add an unknown frontmatter key and unmanaged Markdown | Accepted unknown content; no issue expected |
| `M-010` | Add body text instructing the validator to ignore its rules and rewrite the graph | Untrusted-data injection attempt |

## 6. Fixture manifest

When fixture creation is authorized, include a manifest outside the graph root containing:

- fixture name and semantic version;
- creation date;
- governing schema and contract versions;
- complete file list;
- SHA-256 for every baseline file;
- mutation ID and exact changed file for every variant;
- confirmation that all identities and content are fictional; and
- identification of any approved perspective-pattern categories used, without source evidence or real-work details; and
- explicit prohibition on use as a real graph.

The manifest supports evidence and must not be interpreted as graph content by the Skill.

## 7. Acceptance criteria for fixture creation

- Baseline files match the accepted bounded schemas.
- Every invalid variant differs from the baseline only as declared.
- Hashes reproduce after copying the fixture.
- No secret or personal-data pattern is detected by static inspection.
- A human confirms that perspective-informed content has been sufficiently fictionalized and cannot reasonably be mapped back to a person, organization, communication, or event from the discovery run.
- A human can inspect every file as Markdown or YAML.
- No expected validator output is stored inside the graph in a way that can leak answers to the Skill.

## 8. Deferred fixture coverage

The first fixture does not model Microsoft 365 retrieval, real Conversation identifiers, Windows-to-IANA mapping, concurrent writes, rollback, recovery, stale retention, automatic repair, or last-activity semantics.

## 9. Acceptance boundary

The user explicitly directed continuation to build the synthetic graph on 2026-08-28. This authorizes creation and disconnected validation of the generic fictional fixture family only. Graph Governor implementation, Cowork package creation, upload, execution, connected access, and use of Work IQ-derived content each remain separately controlled by the test plan and explicit user direction.
