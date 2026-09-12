# Compass 0.4.0 participant-management candidate package set

## Document control

- **Status:** packages and schema-v2 fixture statically validated; behavioral execution not authorized
- **Version:** 0.4.0-participant-management-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-06
- **Decision basis:** [Accepted participant-management decision](../decisions/2026-09-06-accept-participant-and-topic-management.md)
- **Test plan:** [Participant-management test plan](../test-plans/2026-09-06-participant-management-test-plan.md)
- **Fixture validation:** [Schema-v2 fixture construction check](../test-results/2026-09-06-compass-participant-management-v2-fixture-validation.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-installation-interview-v0.3.0-participant-management-candidate.skill) | 7,564 bytes | `936e65cd63f4dc196595817d1315583d8f99cf1de7f92b91788b6a66c6307eff` |
| Daily Scan | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-daily-scan-v0.3.0-participant-management-candidate.skill) | 5,030 bytes | `d16dc8f4017bd3fa67309ffbfe7daf01c290059ba722547355543abe13b56087` |
| Tracking Topic Interview | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.3.0-participant-management-candidate.skill) | 4,642 bytes | `08e1a16a879a3becec522f9454d4336320b8512d1d1878b3129117d2d01dcb70` |
| Curator | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-curator-v0.3.0-participant-management-candidate.skill) | 3,798 bytes | `152ebaac902c2d04075a872c2c96f4d9548bcda80ac0edda6e83c524e03380ca` |
| Graph Governor | `0.4.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/graph-governor-v0.4.0-participant-management-candidate.skill) | 13,017 bytes | `4df11e7dec20839d2ca58ed7fa476f8fc9139d09d01812ea876943cb089b025f` |

## Package boundary

Each package contains its source `SKILL.md` and every file under its source-local `references/` directory. Entries are sorted safe relative paths, DEFLATE-compressed, mode `0644`, and timestamped `2026-09-04 00:00:00`. Independent rebuilds were byte-identical.

These packages implement the accepted source instructions for schema version 2. Static package inspection does not establish Cowork import, activation, Microsoft 365 retrieval, conversational quality, graph migration, connected writes, or runtime correctness.

## Use boundary

Do not use these packages to mutate an existing schema-version-1 graph. The planned disconnected scenario and a separately authorized migration design must precede personal-graph use. Runtime execution requires separate product-owner authorization and immutable result capture.