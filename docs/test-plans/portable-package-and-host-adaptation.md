# Portable Package and Host Adaptation Test Plan

## Metadata

- **Owner:** Dexter product owner
- **Specifications:** [`portable-skill-packaging.md`](../specifications/portable-skill-packaging.md)
- **Candidate:** Dexter canonical layout and templates as of 2026-09-11
- **Skill host product:** Identify per packaged Skill
- **Status:** active; architecture static validation passed, package and host cases pending
- **Last updated:** 2026-09-11

## Success decision

Determine whether a project can package and share a Skill with enough concise documentation and reusable testing for another user to understand it, evaluate it on a named Skill host, predict adaptations for a different host, and verify those predictions.

## Host compatibility profile

- **Required host behavior:** Import or invoke the package and expose the capabilities required by the governing Specification.
- **User obligation:** Identify the Skill host product.
- **Additional details:** Probe and record only conditions that materially affect a behavior under test.

## Test cases

| ID | Specification behavior | Prompt or situation | Practical check and observable confirmation | Status | Latest observation |
| --- | --- | --- | --- | --- | --- |
| DEX-PACK-001 | `PACK-001`, `PACK-007` | Inspect a project prepared from the canonical layout. | Required artifacts are present, conditional directories are justified, links are project-relative, and no required Dexter-root dependency remains. | not run | None |
| DEX-PACK-002 | `PACK-002`, `PACK-003` | Build and inspect an importable `.skill` file placed directly in `skill-exchange/`. | Package contains only expected safe relative runtime files, matches the owning source, and is identified by its exact filename. | not run | None |
| DEX-PACK-003 | `PACK-004`, `PACK-005` | Hand the package and accompanying material to another tester. | Tester can identify purpose, specified behavior, practical checks, observable confirmations, host product, and known limitations. | not run | None |
| DEX-PACK-004 | `PACK-006` | Tester chooses a different Skill host. | Product identification plus focused probes produce a bounded compatibility/adaptation hypothesis that is then tested rather than assumed. | not run | None |

## Focused host capability checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| Package import or invocation | Import or invoke a non-sensitive candidate | Host accepts, rejects, or conditions the operation visibly | not run |
| Required context or tool | Use one known non-sensitive object | Required read, action, or interaction control is observed or bounded as unavailable | not run |

## Material stop conditions

- Package contains credentials, sensitive content, unsafe paths, or unexpected files.
- Guidance claims compatibility based only on a product name or documentation.
- A connected write or other external effect occurs without exact user authority.

## Execution log

### 2026-09-11 - Instruction architecture static validation

- **Cases:** Structural prerequisite for `DEX-PACK-001` through `DEX-PACK-004`; no project package or Skill host invoked.
- **Direct observation:** Checked 23 active Dexter Markdown files. All 12 required architecture and scaffold files exist, all non-placeholder relative links resolve, and all four Dexter or template `SKILL.md` files contain YAML frontmatter and a description.
- **Defects and limitations:** This check did not instantiate a new project, build or import a package, copy a project to a neutral location, involve another tester, or exercise another Skill host.
- **Assessment:** Passed for the active instruction architecture only. Package portability and host adaptation remain unestablished.

### 2026-09-11 - Flat Skill Exchange revision validation

- **Cases:** Static prerequisite for `DEX-PACK-001` and `DEX-PACK-002`; no package or Skill host invoked.
- **Direct observation:** Rechecked 23 active Dexter Markdown files after simplifying Skill Exchange. All relative links resolve, and active guidance contains no requirement for `incoming`, `ready-for-test`, or `tested` subdirectories.
- **Defects and limitations:** This check did not import a `.skill` file or establish host behavior.
- **Assessment:** Passed for the flat exchange instruction architecture.

## Current success assessment

- **Assessment:** partial
- **Supported claims:** The canonical layout, required scaffolds, active links, and Skill frontmatter statically express a consistent package boundary and host adaptation method.
- **Unresolved claims:** Usability by another tester and portability outside Dexter.
- **Next test or revision:** Apply the scaffold to the next packaged Skill and run the static and host-adaptation cases.