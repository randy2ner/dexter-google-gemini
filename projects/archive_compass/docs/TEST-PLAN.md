# Compass Test Plan

## Document control

- **Status:** active
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-09
- **Last updated:** 2026-09-09
- **Specification:** [SPECIFICATION.md](SPECIFICATION.md)
- **Current candidate:** Five production-test candidate Skills and Compass work-memory lifecycle Orchestration listed in the Specification

## Success decision

Testing determines whether an exact Compass candidate can reproduce accurate, useful, user-controlled work memory from authorized production evidence and is suitable for a separate product-owner release decision. Documentation and static inspection alone cannot establish success.

Success requires all material Specification claims exercised for the stated scope, no unresolved stop condition, independently verified durable effects, and a user judgment that the experience is useful, understandable, trustworthy, and controllable. Results remain bounded to the exact candidate, date, account, permissions, host capabilities, purpose, and graph state.

## Environment and privacy

- Use the user's company-approved, managed Copilot Cowork client.
- Import only the exact package set selected for the run and record package hashes.
- Use the designated Compass graph root and disclose whether it is fictional, disposable, or production.
- The user reviews work evidence privately under company security guidance.
- Dexter records only source-type names, approximate counts, continuation behavior, decisions, coverage status, interaction observations, Governor outcomes, and effect counts.
- Do not paste or describe identifying work content, raw messages, tenant details, or graph content to Dexter.

## Material stop conditions

Stop the affected run for unauthorized or broader-than-approved access; unreviewable interpretation; unsupported identity or relationship; inaccessible approval or cancellation; unexplained retrieval limits or sample substitution; UPN collection; OneDrive item-ID writes; unexpected, partial, conflicting, destructive, or unverifiable effects; privacy exposure; Curator writes; Governor Work IQ retrieval or meaning judgment; training/export without separate authority; or materially false effect reporting.

Non-blocking wording, relevance, verbosity, personality, and minor sequencing issues are recorded through the bounded journey and revised together afterward.

## Complete production journey

1. Confirm exact packages, graph root, purpose, scope, permissions, and recovery readiness.
2. Run Installation Interview. Inspect the Work IQ capabilities used and coverage disclosed, then review proposed CSPs, Topics, People, configuration, links, and YAML. Confirm, revise, reject, or cancel naturally.
3. Verify that the approved configuration is the first write and no disposable probe is created or deleted.
4. Run Daily Scan for one representative period. Review source coverage, continuation, source Conversation identity, deduplication, participants, Topic disposition, suggested content, and minimized provenance.
5. Run Tracking Topic Interview for one meaningful Topic. Review Topic-focused Work IQ, narrative, participants, attention, lifecycle, CSP alignment, and proposed effects.
6. Run Curator against a bounded review purpose. Confirm it separates graph observations, Work IQ context, and recommendations and performs no write.
7. Allow Graph Governor to validate authorized proposals and post-write state without retrieving Work IQ or choosing meaning.
8. Independently inspect the graph outside Compass and compare actual objects, paths, relationships, preserved content, and Daily Log entries with the terminal report.
9. Record privacy-minimized observations and the user's success judgment below.

## Test cases

| ID | Specification criteria | Expected observation | Status | Latest observation | Revisit trigger |
| --- | --- | --- | --- | --- | --- |
| TEST-001 | SPEC-WIQ-001, SPEC-INT-002 | Installation uses direct answers and all relevant exposed Work IQ, offers useful editable setup suggestions, discloses gaps, and writes only after confirmation. | not run | Static package inspection passed 2026-09-08; runtime unknown. | Candidate or host capability change. |
| TEST-002 | SPEC-WIQ-001, SPEC-EVID-001 | Daily Scan attempts complete relevant period coverage without arbitrary caps, continues where possible, deduplicates by source Conversation identity, and discloses gaps. | not run | Static package inspection passed 2026-09-08; runtime unknown. | Candidate, Work IQ, or source-identity change. |
| TEST-003 | SPEC-NARR-001, SPEC-PART-001, SPEC-TOPIC-001, SPEC-ATTN-001 | Topic Interview retrieves for an explicit Topic purpose and obtains exact approval for narrative, People, relationships, attention, and lifecycle. | not run | Static HPI and schema checks passed; runtime unknown. | Topic behavior or candidate change. |
| TEST-004 | SPEC-REVIEW-001, SPEC-HIGHLIGHT-001 | Curator performs the bounded review, includes each flagged Topic once, distinguishes observation from interpretation, and writes nothing. | blocked by unimplemented review requirement | Earlier static review behavior passed; current criteria-based lifecycle review is unimplemented. | Review implementation. |
| TEST-005 | SPEC-SAFE-001, SPEC-TRUTH-001 | Governor validates authority, schema, identity, paths, preservation, and effects; retrieves no Work IQ; chooses no meaning; verifies actual post-write state. | not run for current candidate | Historical read-only synthetic slice passed for `0.1.0-experimental`; no confidence transfers to current writes. | Governor, schema, or write path change. |
| TEST-006 | SPEC-AUTH-001, SPEC-INT-001, SPEC-INT-002 | The complete experience feels like one assistant, asks only material questions, and supports correction, rejection, pause, and cancellation. | not run | A 2026-09-02 automation attempt was blocked by Conditional Access; earlier proposal controls exposed usability defects. | Managed-client run or interaction change. |
| TEST-007 | SPEC-PORT-001, SPEC-GRAPH-001, SPEC-TRUTH-001 | External inspection confirms readable Markdown/YAML and exact agreement between approved, reported, and durable effects. | not run | Package and fixture inspections passed; current connected persistence is unknown. | Every durable-write candidate. |
| TEST-008 | SPEC-PRIV-001, SPEC-PRIV-002, SPEC-PERSON-001 | Retained content is minimized; reviewed email is preserved as an attribute; UPN is not requested or managed. | not run | Static package checks passed; runtime unknown. | Person schema, retrieval, or candidate change. |
| TEST-009 | SPEC-HIST-001, SPEC-HIST-002, SPEC-ATTN-001 | Archive/reactivate preserves Topic history and attention, applies/removes boolean success correctly, and never deletes the Topic. | not run | Static schema and package checks passed; runtime unknown. | Lifecycle behavior change. |
| TEST-010 | SPEC-PART-001, SPEC-TOPIC-001, SPEC-PARK-001 | Authorship and confirmed mentions qualify participants; passive membership does not; Topic funneling honors exclusions; each Conversation has one disposition. | not run | Static schema-v2 checks passed; runtime unknown. | Participant or relationship change. |
| TEST-011 | SPEC-RECENCY-001 | Creation initializes `updatedAt`; verified durable changes advance it; rejected or unrelated activity does not. | blocked by unimplemented requirement | No runtime evidence. | Recency implementation. |
| TEST-012 | SPEC-REVIEW-001 | Disclosed criteria identify candidates without changing them; purge/archive remains a separate exact user decision. | blocked by unimplemented requirement | No runtime evidence. | Lifecycle-review implementation. |
| TEST-013 | Write and effect contract | All approved creates/replaces use displayed graph-root-relative paths, not OneDrive item IDs, and preserve source Conversation identity. | not run | Path-based requirement added after item-ID addressing failed; current candidate runtime unknown. | Writer or OneDrive capability change. |
| TEST-014 | Installation responsibility | Installation verifies the approved configuration as its first write and creates no disposable setup probe. | not run | Source and package inspection passed; runtime unknown. | Installation candidate change. |
| TEST-015 | SPEC-WIQ-001 | Missing evidence yields a disclosed partial or blocked result and never sample, fixture, fictional, or synthetic production objects. | not run | Static instruction inspection passed; runtime unknown. | Retrieval or fallback behavior change. |
| TEST-016 | Product boundaries | The run creates only approved graph content and performs no automatic export, publication, or model-training submission. | not run | No export authority exists. | Integration or release change. |

## Entry criteria

- Artifact-first shaping has produced a useful target graph and reusable privacy-minimized techniques.
- The Specification and Skill source reflect the demonstrated outcomes.
- Exact packages and hashes are selected and imported into an approved managed client.
- The graph root, purpose, work scope, permissions, and recovery boundary are displayed and accepted.
- The user has separately authorized the connected retrieval and writes required for the run.

## Execution log

### 2026-09-09 - Consolidated baseline

- **Cases:** TEST-001 through TEST-016
- **Direct observation:** Repository inspection confirms current source/package baselines and prior static checks recorded in the legacy archive. No current production candidate was executed in this consolidation.
- **Operator-reported observation:** None for the current candidate.
- **Independent effect check:** Not performed; no connected action occurred.
- **Defects and limitations:** Current candidate runtime, Work IQ coverage, connected writes, path persistence, recovery, integrated interaction, and proposed recency/review behavior remain unproven. Organizational Conditional Access blocks Dexter's integrated browser from operating Cowork.
- **Assessment:** Not established for production release. Static evidence supports package structure only.

Prior dated decisions, plans, scenarios, findings, and results are preserved unchanged under [the legacy documentation archive](../archive/docs-legacy-2026-09-09/). They are historical evidence, not current governance, and Dexter does not consult or update them unless a specific question requires it.

## Current success assessment

- **Assessment:** not established
- **Supported claims:** Package structure and selected static contracts for prior exact candidates only.
- **Unresolved claims:** All current runtime claims, especially Work IQ coverage, integrated usability, path-based writes, effect truth, Person handling, participant behavior, Topic lifecycle, and persistence/recovery.
- **Blocked claims:** SPEC-RECENCY-001 and SPEC-REVIEW-001 are not implemented.
- **Next action:** Complete artifact-first shaping, revise the candidate Skills, then run the complete production journey in the approved managed Cowork client.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 1.0 | 2026-09-09 | Consolidated test strategies, cases, results, gaps, and success status into one living Test Plan to reduce Dexter documentation overhead. |