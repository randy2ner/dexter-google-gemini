# Risk-based test design

## Document control

- **Status:** living
- **Version:** 3.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-09

## Purpose

Reach complete beta learning quickly while protecting material trust and safety boundaries.

## Start with the decision

Every test plan states:

- the decision the evidence will inform;
- the accepted claims under evaluation;
- one representative complete journey through the Orchestration;
- the highest-consequence stop conditions;
- evidence needed to distinguish pass, partial, fail, and blocked; and
- when testing stops.

## Default test shape

Prefer one complete experience that:

1. starts from a recognizable user goal;
2. crosses every Skill and handoff needed for the product promise;
3. includes real user choices, corrections, cancellation paths, and visible limitations as they naturally occur;
4. independently inspects claimed durable effects; and
5. records dated observations and the current assessment in the Test Plan.

Do not create a scenario for each field, enum, prompt, Skill, permutation, or theoretical edge case. Probabilistic Skills are evaluated as an experience, not as deterministic functions. Run static package/source checks before beta only to catch malformed artifacts, missing dependencies, broken links, or obvious contract contradictions.

## Adding test cases

Add a focused Test Plan case only when at least one applies:

- failure would create material user, privacy, integrity, or operational harm;
- an observed defect needs reproduction;
- two plausible implementations would produce materially different outcomes; or
- uncertainty blocks continuation or the beta decision.

Record unexercised requirements as gaps in the Test Plan. Do not automatically turn every gap into another case.

Each case names the applicable Specification criteria and Skills. Host-surface, transport, package, dependency, and tool checks are Test Plan cases too; they do not need another document type.

## Continuous verification

Keep a compact case table in the living Test Plan. Each entry identifies the behavior worth preserving, the representative use case, the latest dated observation, and the reason it should be checked again. It is a memory aid, not an exhaustive test suite.

Revisit an entry when:

- related project behavior changes;
- a Skill, Orchestration, host, model, service, permission, or data contract it depends on changes;
- enough time has passed that current operation is uncertain;
- a user reports doubt, friction, or regression; or
- a release, redistribution, or readiness decision needs fresh evidence.

No source change is required to justify a new verification run. Prefer exercising due entries through one natural complete journey; use a focused diagnostic only under the criteria above. Add a dated observation to the Test Plan rather than creating a result file.

## Revision timing

During the complete beta journey, collect non-blocking observations without repeatedly rebuilding the candidate. Stop and patch immediately only when continuing risks unauthorized access, privacy exposure, identity corruption, destructive history loss, unrecoverable effects, or false success.

After the journey, group observations by root cause and make one coordinated rewrite across affected Specifications and Skills. Repackage the complete candidate once and rerun the full journey unless one focused diagnostic is needed first.

## Closure

Finish a beta cycle when:

- required claims have sufficient evidence for the stated scope;
- unresolved gaps are documented and do not block the decision;
- observed defects have an accepted disposition;
- the Test Plan identifies exact versions, exercised claims, gaps, and material observations; and
- additional testing has diminishing decision value.

Missing nonessential metadata becomes an explicit limitation, not an invitation to fabricate or repeat work without purpose.