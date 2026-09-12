# Test Plan 02: Knowledge Artifact Quality

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee graph creation](../specifications/marquee-graph-creation.md), `GRAPH-002`, `GRAPH-007` through `GRAPH-009`; [Marquee Outlet orchestration](../specifications/marquee-outlet-orchestration.md), `OUTLET-012`
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instruction:** `Write Career Knowledge Artifacts`
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee, create and update Markdown in the confirmed graph, preserve YAML frontmatter and existing user content, and expose exact files for independent inspection.
- **Capability hypothesis:** Cowork may support Markdown mutation in OneDrive, but frontmatter preservation, targeted updates, and truthful reporting across partial writes remain unverified. Synthetic conversational output alone does not establish durable artifact quality.
- **Focused capability checks:** Create one synthetic Markdown file with minimal frontmatter; read it back; update one field while preserving an unknown field and body text; independently compare the durable result.
- **Another host:** Identify its product and repeat these checks. Compare file format, mutation fidelity, inspectability, and approval controls before predicting compatibility.

## Success decision

Determine whether Marquee writes accurate, useful Markdown for each graph classification. No fabricated fact, private raw-source retention, or misplaced Outlet guidance is allowed; graded behaviors must average at least 2.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Classify by future use | Charter career knowledge; `GRAPH-002` | `Write Career Knowledge Artifacts`, classification list | `2`: correct primary folder without duplication; `1`: debatable but useful; `0`: wrong or generic Outlet. |
| Use helpful frontmatter | Charter confirmed/unconfirmed contract | `Write Career Knowledge Artifacts`, frontmatter schema | `2`: valid, minimal, useful fields and status; `1`: valid but weak; `0`: invalid or misleading. |
| Preserve useful detail | Charter intended outcomes | `Write Career Knowledge Artifacts`, body criteria | `2`: contribution, significance, evidence, relevance, and focused unknowns; `1`: partially reusable; `0`: activity log or unusable summary. |
| Preserve inspectability | `GRAPH-007` | `Write Career Knowledge Artifacts`, naming and links | `2`: readable Markdown, specific name, useful links; `1`: readable with friction; `0`: opaque or inaccessible. |
| Write transparently | Charter retention contract; `GRAPH-009` | `Write Career Knowledge Artifacts`, write/report procedure | `2`: interpretation, target, changes, and confirmation state disclosed; `1`: incomplete disclosure; `0`: hidden or unauthorized write. |

## Test experience

Use privacy-safe scenarios representing a highlight, profile insight, goal, perspective, and new Outlet guidance. Ask Marquee to retain each, then inspect the files. Include one item spanning two classifications and one update containing unknown frontmatter to test primary placement and preservation.

## Evidence and stop conditions

Retain only synthetic or privacy-minimized specimens. Record proposed interpretation, resulting Markdown, placement, confirmation state, and user usefulness rating. Stop for fabricated facts, raw private source retention, overwritten user content, or an unauthorized graph change.
