# Artifact-first production shaping plan

## Document control

- **Status:** active
- **Date:** 2026-09-08
- **Owner:** User / product owner
- **Decision:** [Adopt artifact-first production shaping](../decisions/2026-09-08-adopt-artifact-first-production-shaping.md)
- **Output:** A finished production graph and grounded requirements for the next Skill set

## Purpose

Build the target Compass graph experience before fixing the final automation design. Use real work, flexible Cowork conversation, direct inspection, and manual correction to discover which outcomes matter and which techniques reliably create them.

## Operating loop

1. **Choose an outcome.** Name the graph artifact or user-visible result to improve, without prescribing a Skill workflow unless that helps.
2. **Try an effective method.** Use ordinary Cowork conversation, a current Skill, another available Cowork capability, or a manual edit within approved access and policy boundaries.
3. **Inspect the artifact.** Check meaning, usefulness, YAML, stable identity, links, relationships, preservation, and visible effect truth.
4. **Correct freely.** Redirect Cowork or edit the graph manually until the artifact reflects the intended result. Do not preserve defects merely to keep a test pure.
5. **Record the technique.** Capture the privacy-minimized interaction pattern, what it produced, corrections required, and whether the method should be repeated.
6. **Update the instruction manual.** Revise the smallest affected requirement, specification, schema rule, or Skill behavior when the demonstrated result changes current intent.
7. **Repeat.** Continue until representative graph outcomes are useful and stable enough to define repeatable automation.

## Artifact quality review

For each material artifact, review:

| Dimension | Question |
| --- | --- |
| Meaning | Does this preserve what the user needs to remember or act on? |
| Structure | Are object type, schema version, required frontmatter, and Markdown shape correct? |
| Identity | Are object and source identities stable, explicit, and non-inferred? |
| Relationships | Do canonical links resolve with correct ownership and cardinality? |
| Narrative | Are facts, interpretation, outcome, contribution, lessons, and boundaries represented usefully where applicable? |
| Privacy | Is retained content minimized, with no unnecessary raw work evidence or identity data? |
| Authority | Did the user review and accept the durable meaning, including manual corrections? |
| Effect truth | Can created, changed, unchanged, uncertain, and failed effects be stated accurately? |
| Usefulness | Would the finished artifact support real work without explanation from its creator? |

## Provenance classes

Record one or more of these classes for material artifacts:

- `cowork-conversation-created`
- `current-skill-created`
- `manual-created`
- `cowork-corrected`
- `manual-corrected`
- `mixed-method`

Record provenance outside managed graph frontmatter unless the schema later accepts a durable provenance field. Do not invent schema fields during shaping.

## Technique record

For each reusable technique, capture only:

- date and target artifact type;
- generalized user intent;
- Cowork surface or method used;
- generalized request or conversational pattern;
- source capability types used, without work-content excerpts;
- result category and artifact-quality dimensions satisfied;
- manual or conversational corrections required;
- failure or friction pattern;
- candidate Skill behavior implied; and
- confidence and known limits.

Use the [production shaping technique ledger](../experiments/production-graph-shaping-technique-ledger.md). Do not record customer names, colleague names, message text, document titles, links, tenant details, or other identifying work content.

## Reverse-engineering handoff

When outcomes stabilize:

1. compare finished artifacts with current schema and Skill contracts;
2. identify every manual correction and successful conversational move;
3. classify each as required Skill behavior, optional assistance, user judgment, or out-of-scope manual control;
4. update the PRD and specifications before revising runtime instructions;
5. revise the smallest responsible Skill or orchestration handoff;
6. package an exact derived candidate set; and
7. run a controlled repeatability test under the production release-test plan.

## Evidence boundary

A finished production artifact is direct evidence of the desired result and the methods used to reach it. It is not evidence that the current or future Skills can create that result autonomously. Only a controlled run of exact packaged versions can support a release claim about repeatability, automation, or reduced manual effort.
