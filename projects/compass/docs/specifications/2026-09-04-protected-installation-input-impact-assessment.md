# Change Impact Assessment: protected installation input and write preflight

## Document control

- **Date:** 2026-09-04
- **Status:** superseded by protected-input support correction
- **Owner:** User / product owner
- **Changed source/version:** [Installation Interview Skill](../../skills/compass-installation-interview/SKILL.md) `0.2.2-dogfood-candidate`
- **Motivation:** [Protected-input finding](../findings/2026-09-04-protected-input-blocks-portable-installation.md)
- **Superseded by:** [Protected-source support impact assessment](2026-09-04-protected-source-support-impact-assessment.md)

## Change summary

Installation no longer ingests attached or linked documents for foundational setup. It stops on protection signals, proves representative plain-text write/read/delete capability before managed structure, applies an approved bootstrap config-first, and maps policy refusal to `write-blocked` / `blocked`.

The root-level probe deliberately differs from the proposed `_compass/.write-probe`: creating `_compass/` for preflight would itself create managed structure before capability was proven. A new user-confirmed empty graph root may still remain because no write probe can precede creation of its target folder.

## Impact map

| Dependent item | Current version/evidence | Impact | Required action |
| --- | --- | --- | --- |
| Installation responsibility specification | `0.2.1` | affected | Revise to `0.2.2` with protected-input, preflight, and config-first requirements. |
| Installation behavior contract and source | `0.2.1-dogfood-candidate` | affected | Revise and package as `0.2.2-dogfood-candidate`. |
| Lifecycle Orchestration | `0.2.0-dogfood-candidate` | affected | Add the installation stop and preflight ordering without changing other Skill flows. |
| Clean first-run scenario | version 1.0 | affected | Add no-document-ingestion, preflight, and policy-block expectations. |
| Compass package set | `0.3.1-dogfood-candidate` | invalidated for current dogfood | Preserve it and register a new set containing Installation `0.2.2`. |
| Prior Installation results | Exact earlier versions | none | Preserve unchanged; do not transfer their runtime claims to `0.2.2`. |
| Daily Scan, Topic, Curator, Governor packages | Exact `0.3.1` members | none | Reuse byte-identical packages; their behavior is not changed. |

## Evidence disposition

- **Still applicable:** prior results remain evidence for their exact packages and observed runs.
- **Invalidated or uncertain:** `0.3.1` is no longer the current dogfood set; no evidence yet shows that `0.2.2` avoids protected ingestion or prevents managed-folder residue in Cowork.

## Smallest justified retest set

| Test | Reason | Decision enabled |
| --- | --- | --- |
| Static `0.2.2` source/package inspection | Prove package fidelity and required instruction presence. | Admit exact package to runtime retest. |
| One clean first-run installation in a new label-free Cowork task | Exercise the changed ingestion and ordering path naturally. | Determine whether current dogfood can proceed. |

## Excluded regression

- Daily Scan, Tracking Topic Interview, Curator, and routine Graph Governor behavior are unchanged and do not require rerun before Installation retest.
- A protected-document ingestion experiment is excluded because deliberately importing protected content is unnecessary to verify the preventive instruction and may recreate avoidable tenant residue.

## Authorization required

Package inspection is authorized as part of candidate correction. Connected retest remains user-operated in the approved managed Cowork client and must begin in a new label-free task.