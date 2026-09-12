# Portable Skill Packaging Specification

## Document control

- **Status:** active
- **Owner:** Dexter product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-11
- **Charter:** [`../CHARTER.md`](../CHARTER.md)
- **PRD requirements:** `PR-TEST-001`, `PR-HOST-001`, `PR-PACK-001`, `PR-PORT-001`

## Purpose and applicability

Define the project structure and accompanying material needed to package, test, share, adapt, and graduate a Skill without making project governance part of the runtime package by default.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| PACK-001 | Every project follows one canonical layout. | [`../../projects/README.md`](../../projects/README.md) is the only repository-wide layout contract. | implemented |
| PACK-002 | Runtime source remains distinct from importable package files. | Editable source is under `skills/`; `.skill` files in the flat exchange are never edited in place. | implemented |
| PACK-003 | The runtime package contains only host-required files. | Root `SKILL.md` and required runtime references are packaged; governance remains alongside it unless required at runtime. | implemented |
| PACK-004 | Accompanying documentation explains and tests the Skill. | Governing Specifications and reusable Test Plans travel alongside the package. | implemented |
| PACK-005 | Test Plans include a reusable host profile. | The host product is recorded and only behaviorally material conditions are probed. | implemented |
| PACK-006 | Another host is treated as a compatibility hypothesis. | A user identifies the product, runs focused probes, predicts adaptation needs, and verifies behavior. | implemented |
| PACK-007 | Graduated projects are independent. | Required links, source, references, packages, and knowledge remain inside the project directory. | implemented |

## Package and sharing contract

| Material | Location | Purpose |
| --- | --- | --- |
| Editable Skill source | `skills/<skill-name>/` | Development source and runtime references |
| Importable package | `skill-exchange/<descriptive-name>.skill` | Exact package available for host import or testing |
| Governing behavior | `specifications/` | Intended Skill and interaction contracts |
| Reusable evaluation | `test-plans/` | Host profile, practical checks, observations, and assessment |
| Native fixtures | `test-data/` | Only test inputs that require native files |

## Constraints and dependencies

- Preserve the package layout and filename required by the target Skill host.
- Do not embed credentials, sensitive production content, tenant identifiers, or unnecessary project administration.
- Package integrity and links may be checked deterministically; behavioral success requires host experience.

## Implementation status

- **Implemented:** Canonical layout, artifact templates, Skill scaffold, Orchestration guidance, exchange guidance, and contributor guidance.
- **Not implemented:** No neutral-location graduation check or different-host experience has validated the revised structure.

## Test Plans

- [`../test-plans/portable-package-and-host-adaptation.md`](../test-plans/portable-package-and-host-adaptation.md): `PACK-001` through `PACK-007`.

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Created to define the approved shareable Skill package and cross-host test pattern. |
| 2026-09-11 | Static validation confirmed active links, required architecture files, and Skill frontmatter; portability and host behavior remain untested. |
| 2026-09-11 | Simplified `skill-exchange/` to a flat location for importable `.skill` files; candidate state and observations remain in filenames and Test Plans rather than lifecycle subdirectories. |

## Acceptance boundary

Acceptance establishes the packaging contract. It does not establish importability or behavioral compatibility on an untested Skill host.