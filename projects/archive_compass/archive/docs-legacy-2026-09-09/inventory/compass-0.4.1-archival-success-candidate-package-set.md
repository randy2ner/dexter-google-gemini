# Compass 0.4.1 archival-success candidate package set

## Document control

- **Status:** source, packages, and fixture statically validated; behavioral execution not authorized
- **Version:** 0.4.1-archival-success-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-06
- **Decision basis:** [Accepted archival-success decision](../decisions/2026-09-06-record-topic-archival-success.md)
- **Test plan:** [Topic archival-success test plan](../test-plans/2026-09-06-topic-archival-success-test-plan.md)

## Exact packages

| Skill | Version | Package | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| Installation Interview | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-installation-interview-v0.3.0-participant-management-candidate.skill) | 7,564 bytes | `936e65cd63f4dc196595817d1315583d8f99cf1de7f92b91788b6a66c6307eff` |
| Daily Scan | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-daily-scan-v0.3.0-participant-management-candidate.skill) | 5,030 bytes | `d16dc8f4017bd3fa67309ffbfe7daf01c290059ba722547355543abe13b56087` |
| Tracking Topic Interview | `0.3.1-archival-success-candidate` | [package](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.3.1-archival-success-candidate.skill) | 4,972 bytes | `b68963ade7e03a83156ec25d9db7742cc66d91c2a1c2b4e0bf467f99f493146c` |
| Curator | `0.3.0-participant-management-candidate` | [package](../../skill-exchange/ready-for-test/compass-curator-v0.3.0-participant-management-candidate.skill) | 3,798 bytes | `152ebaac902c2d04075a872c2c96f4d9548bcda80ac0edda6e83c524e03380ca` |
| Graph Governor | `0.4.1-archival-success-candidate` | [package](../../skill-exchange/ready-for-test/graph-governor-v0.4.1-archival-success-candidate.skill) | 13,312 bytes | `8b659b1f686699cb245998aa8e3667218fab405215ee09c9bcb8b8850902329e` |

## Compatibility boundary

Installation Interview, Daily Scan, and Curator source did not change: active Topic creation already omits `success`, and those Skills do not own archival outcome choice or lifecycle validation. Their exact prior candidate packages are retained in this set. Tracking Topic Interview and Graph Governor advance because they own the changed behavior.

All five packages remain schema-version-2 candidates. Prior package files and completed evidence are preserved unchanged.

## Use boundary

Static inspection does not establish conversational prompting, write application, post-write verification, Cowork activation, connected access, migration, or runtime correctness. Do not mutate a schema-version-1 or personal graph with this package set.