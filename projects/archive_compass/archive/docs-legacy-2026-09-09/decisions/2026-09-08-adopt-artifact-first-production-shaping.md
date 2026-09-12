# Decision: Adopt artifact-first production shaping

- **Date:** 2026-09-08
- **Status:** accepted
- **Decider:** User / product owner
- **Stage:** Production graph artifact construction and outcome discovery
- **Applies to:** Immediate Compass development sequence
- **Related milestone:** [Production release testing](2026-09-08-declare-production-release-testing-milestone.md)

## Context

The current Compass packages encode the best available design, but the finished production graph experience has not yet been demonstrated. Requiring those Skills to control the next journey could constrain discovery to assumptions embedded in the current implementation.

The product owner intends to build the desired graph artifacts first using effective Cowork conversations, direct review, and manual edits where useful. Successful techniques and the resulting graph can then reveal the behavior future Skills must reproduce reliably.

## Decision

1. The immediate development stage is **artifact-first production shaping**.
2. The primary objective is a finished, useful production Compass graph that demonstrates the intended end results across CSPs, Tracking Topics, People, Conversations, Daily Logs, YAML frontmatter, links, relationships, narratives, and review behavior.
3. The product owner may use any authorized and policy-compliant method that effectively advances the graph, including ordinary Cowork conversation, direct prompts, current Compass Skills, other available Cowork capabilities, and manual graph edits.
4. Valid direct edits are authoritative after review. Manual work is an intentional product-discovery instrument in this stage, not a failure of automation.
5. Cowork may be redirected, corrected, or given explicit examples and desired outcomes during shaping. The objective is to learn what produces the right graph, not to preserve a blind test of the current Skills.
6. The product owner will share successful techniques as privacy-minimized operational patterns. Dexter records the request form, interaction pattern, correction strategy, and observed result category without retaining identifying work content.
7. Every material artifact records enough provenance to distinguish Cowork-created, Skill-created, manually created, and manually corrected content. Provenance does not reduce the authority of a reviewed final artifact.
8. Artifact quality and usefulness are evaluated independently from automation quality. A correct finished artifact proves a target outcome; it does not prove that a Skill can reproduce it.
9. After the target graph and successful techniques stabilize, Compass specifications and Skills will be reverse engineered from the demonstrated outcomes, then packaged and tested for repeatability with less manual effort.
10. The current production-test package set remains a design input and optional shaping tool. It is not presumed to be the final release candidate during this stage.
11. Identity accuracy, source protection, user authority, privacy minimization, effect truth, and no unapproved export or model-training submission remain mandatory. "Any means necessary" means any effective method within these boundaries, not bypassing them.
12. Production release still requires a later controlled test of exact derived Skill versions. Shaping evidence and controlled Skill evidence remain separate.

## Superseded sequencing

This decision supersedes the immediate exact-package sequencing in items 2 and 5 of the [production release-testing milestone](2026-09-08-declare-production-release-testing-milestone.md), while preserving production release testing as the overall phase. The mediated `PROD-WIQ-001` through `PROD-WIQ-008` journey remains the later repeatability and release gate after artifact-first shaping and Skill revision.

## Completion signals

Artifact-first shaping is complete when:

- the production graph is useful enough for ongoing work;
- required object types, frontmatter, links, and relationships are present and reviewable;
- representative target narratives and Curator outputs are satisfactory;
- material manual corrections and their causes are known;
- successful Cowork techniques are recorded as reusable patterns; and
- there is enough evidence to specify the Skill behavior needed to reproduce the results.

## Consequences

- Development optimizes first for demonstrated outcomes, then for repeatable automation.
- Manual intervention is expected and measured rather than hidden.
- The technique ledger becomes a grounded source for specification and Skill revisions.
- Current package runtime results gathered during shaping are experiential observations, not clean release-validation evidence unless a separately controlled run satisfies the release test plan.
