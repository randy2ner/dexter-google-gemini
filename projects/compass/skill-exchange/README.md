# Compass Skill Exchange

This is the project-local handoff area for exact Compass artifacts. It isolates test specimens from Dexter's reusable scaffolding and from other projects.

- `incoming/`: artifacts awaiting inspection.
- `ready-for-test/`: reviewed artifacts ready for Cowork import.
- `tested/`: exact artifacts used in recorded runs.
- `archive/`: superseded artifacts retained for traceability.

## Current project artifacts

| State | Artifact | Evidence |
| --- | --- | --- |
| Tested | [Graph Governor 0.1.0-experimental](tested/graph-governor-v0.1.0-experimental.skill) | [GG-SYN-001 valid-baseline result](../docs/test-results/2026-08-31-graph-governor-gg-syn-001-valid-baseline.md) |
| Tested in authorized run; retained pending disposition | [Perspective Discovery 0.1.1-experimental](ready-for-test/compass-installation-perspective-discovery-v0.1.1-experimental.skill) | [Cancelled runtime outcome; partial laboratory result](../docs/test-results/2026-09-01-perspective-discovery-v0-1-1-pd-lean-001-cancelled.md) |
| Candidate; inspection pending | [Perspective Discovery 0.1.2-experimental](ready-for-test/compass-installation-perspective-discovery-v0.1.2-experimental.skill) | No inspection or runtime evidence recorded |
| Gate 0 candidate; disconnected inspection passed | [Installation Interview 0.1.0-beta-candidate](ready-for-test/compass-installation-interview-v0.1.0-beta-candidate.skill) | [Source and package inspection](../docs/test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md) |
| Gate 0 candidate; disconnected inspection passed | [Daily Scan 0.1.0-beta-candidate](ready-for-test/compass-daily-scan-v0.1.0-beta-candidate.skill) | [Source and package inspection](../docs/test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md) |
| Gate 0 candidate; disconnected inspection passed | [Tracking Topic Interview 0.1.0-beta-candidate](ready-for-test/compass-tracking-topic-interview-v0.1.0-beta-candidate.skill) | [Source and package inspection](../docs/test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md) |
| Gate 0 candidate; disconnected inspection passed | [Curator 0.1.0-beta-candidate](ready-for-test/compass-curator-v0.1.0-beta-candidate.skill) | [Source and package inspection](../docs/test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md) |
| Gate 0 candidate; disconnected inspection passed | [Graph Governor 0.2.0-beta-candidate](ready-for-test/graph-governor-v0.2.0-beta-candidate.skill) | [Source and package inspection](../docs/test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md) |

Artifact presence does not authorize Cowork upload, execution, connected access, or deployment. `ready-for-test` means only that disconnected source and package checks are recorded.
