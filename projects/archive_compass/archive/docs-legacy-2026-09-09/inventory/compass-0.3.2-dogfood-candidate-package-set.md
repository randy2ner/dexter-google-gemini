# Compass 0.3.2 dogfood candidate package set

## Document control

- **Status:** superseded before runtime by `0.3.3-dogfood-candidate`; protected-input avoidance rejected by product owner
- **Version:** 0.3.2-dogfood-candidate
- **Owner:** User / product owner
- **Last updated:** 2026-09-04
- **Correction basis:** [Protected-input impact assessment](../specifications/2026-09-04-protected-installation-input-impact-assessment.md)

## Exact packages

| Skill | Version | Package | SHA-256 |
| --- | --- | --- | --- |
| Installation Interview | `0.2.2-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-installation-interview-v0.2.2-dogfood-candidate.skill` | `befc99fdea10f3a96d99358f367e8d25b466eebbb0d61a73a06754b3805e399f` |
| Daily Scan | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-daily-scan-v0.2.0-dogfood-candidate.skill` | `006a08a1877eef9410edb547c13b2ebc4f4ac0d6a244a23addcff54918c6ff20` |
| Tracking Topic Interview | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.2.0-dogfood-candidate.skill` | `b5fb5cd5ecb6cda4be9628369f87112b7f6e5c03df9b51304a3ef2344feb3ad0` |
| Curator | `0.2.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/compass-curator-v0.2.0-dogfood-candidate.skill` | `ba6a2f0610b0c2e108aed7f2cfadcf44244d76a85fc2649d4bb480a0a317b8ab` |
| Graph Governor | `0.3.0-dogfood-candidate` | `../../skill-exchange/ready-for-test/graph-governor-v0.3.0-dogfood-candidate.skill` | `d5271a1fb9b14205f4eefb9d54e71bc5dc5a40967cfca53c1d919242c6201b4f` |

## Retest boundary

Begin in a new Cowork task with no attachment, linked document, imported Loop page, graph fixture, or prior conversation. Send `Help me install Compass`. Supply foundational content only by typing or pasting the needed text when asked.

Installation must disclose and complete its content-free plain-text probe before any managed subfolder or bootstrap object is created. The four unchanged packages are reused byte-for-byte from `0.3.1`.