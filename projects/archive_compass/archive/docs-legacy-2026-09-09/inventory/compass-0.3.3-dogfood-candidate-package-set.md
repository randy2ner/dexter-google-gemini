# Compass 0.3.3 dogfood candidate package set

## Document control

- **Status:** ready for protected-source first-run retest
- **Version:** 0.3.3-dogfood-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-04
- **Correction basis:** [Protected-source support impact assessment](../specifications/2026-09-04-protected-source-support-impact-assessment.md)

## Exact packages

| Skill | Version | Package | SHA-256 |
| --- | --- | --- | --- |
| Installation Interview | `0.2.3-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-installation-interview-v0.2.3-dogfood-candidate.skill` | `92e96ce31fa5b609aa2665cc1b2622c969f83510f76f0cd4eb1aee3389d0c20d` |
| Daily Scan | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-daily-scan-v0.2.0-dogfood-candidate.skill` | `006a08a1877eef9410edb547c13b2ebc4f4ac0d6a244a23addcff54918c6ff20` |
| Tracking Topic Interview | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.2.0-dogfood-candidate.skill` | `b5fb5cd5ecb6cda4be9628369f87112b7f6e5c03df9b51304a3ef2344feb3ad0` |
| Curator | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-curator-v0.2.0-dogfood-candidate.skill` | `ba6a2f0610b0c2e108aed7f2cfadcf44244d76a85fc2649d4bb480a0a317b8ab` |
| Graph Governor | `0.3.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/graph-governor-v0.3.0-dogfood-candidate.skill` | `d5271a1fb9b14205f4eefb9d54e71bc5dc5a40967cfca53c1d919242c6201b4f` |

## Protected-source acceptance

Begin in a new Cowork task and send `Help me install Compass`. During the setup conversation, select the intended classified or sensitivity-labeled Microsoft 365 file or Loop page as foundational evidence. Compass must preserve native protection, retrieve only relevant content through the signed-in context, present derived CSPs and Topics as editable proposals, and never treat classification alone as a block.

After source retrieval, Installation must complete its content-free plain-text write/read/delete probe before managed structure. The four unchanged packages are reused byte-for-byte from `0.3.2`.