# Test plan: Compass experience-led rehearsal

## Metadata

- **Owner:** User / product owner
- **Period:** First authorized Cowork session after 2026-09-02
- **Skills/versions:** Four `0.1.0-beta-candidate` Skills; Graph Governor `0.2.0-beta-candidate`; Orchestration `0.1-beta-candidate`
- **Status:** active; first automation attempt blocked by Conditional Access, compliant-client run pending
- **Decision:** [Adopt experience-led beta route](../decisions/2026-09-02-adopt-experience-led-beta-route.md)
- **Execution authority:** [Authorize experience-led rehearsal](../decisions/2026-09-02-authorize-experience-led-rehearsal.md)
- **Session kit:** [Cowork experience rehearsal kit](../scenarios/compass-experience-led-rehearsal.md)
- **Evaluation standard:** [Shaping-first vibe-coding standard](../decisions/2026-09-04-adopt-shaping-first-vibe-coding-standard.md)

## Goals

- Let the product owner experience Compass as one assistant across setup, daily memory, organization, review, and verification.
- Determine whether the exact candidate is useful and trustworthy enough for a bounded development beta.
- Observe consequential technical behavior inside the experience without turning each primitive into a separate user-facing test.

## Out of scope

- Exhaustive permutations, provider benchmarking, load testing, deployment, release, or production recovery claims.
- Repeating simple positive-path behavior unless the rehearsal exposes a defect.
- Treating static package inspection or an expected graph as runtime success.
- Development beta with real work evidence or connected storage without a later explicit decision.

## Environment

- The user's company-approved Copilot Cowork environment.
- The five exact packages named and hashed in the session kit.
- One materialized copy of `compass-beta-graph-v1`, or another explicitly designated disposable graph with an external verified backup.
- Fixed fictional evidence for the initial rehearsal. Capability visibility may be observed, but no real source content is retained.

The [first preflight attempt was blocked](../test-results/2026-09-02-compass-experience-rehearsal-preflight-blocked.md) because the integrated automation browser did not meet organizational device/client compliance policy. Continue only in an approved managed browser or client; do not bypass or weaken Conditional Access.

## Operator preflight

Before the user begins the conversation, confirm only:

1. each exact package imports and is available by its expected name;
2. the designated graph root and external backup are distinguishable;
3. the graph root is writable only if this rehearsal is separately authorized to write;
4. visible Email, Teams, and file capabilities are recorded without opening or retaining source content; and
5. restoration can be initiated by the operator if a blocking condition occurs.

A preflight failure blocks only the unavailable dependency. Fix it or record the rehearsal as blocked; do not substitute another Skill, graph, or connected source silently.

## Primary experience

The user starts with the opening prompt in the session kit and converses naturally. The desired journey is:

1. Installation Interview helps the user describe what matters and proposes a fictional graph setup.
2. Daily Scan reviews the fixed fictional activity window and proposes useful Conversations.
3. The user naturally accepts, revises, rejects, skips, pauses, or corrects suggestions.
4. Tracking Topic Interview helps organize one meaningful thread of work.
5. Curator reviews the resulting graph and offers one useful proposal without applying it.
6. Graph Governor validates consequential requests and reports whether final durable state matches reported effects.
7. The operator inspects the graph outside Compass and compares it with Compass's terminal account.

The user is not required to recite scripted phrases or exercise every control. One ordinary correction, rejection, or change of mind should arise naturally; do not manufacture a failure merely to satisfy coverage.

The fixture supplies a safe starting point, not a deterministic output oracle. Reasonable differences in wording, timestamps, timezone, filenames, operation order, or scan boundaries are shaping feedback when the user can understand and correct them and no material meaning or safety boundary is lost.

## Embedded observations

Observe these within the single journey:

| Dimension | Question |
| --- | --- |
| Usefulness | Did Compass preserve or surface context that mattered? |
| Continuity | Did the Skills feel like one assistant rather than five disconnected tools? |
| Judgment | Were proposals relevant, appropriately uncertain, and easy to correct? |
| Interruption | Did Compass ask only when a decision mattered? |
| Authority | Was approval obtained before every consequential write? |
| Trust | Was it clear what Compass read, proposed, changed, retained, or could not do? |
| Identity/history | Did repeated source identity update the intended object without destructive loss? |
| Effect truth | Did reported effects match external graph inspection? |
| Control | Could the user pause, reject, redirect, or stop naturally? |
| Recovery readiness | If a blocking write failure occurred, was unrelated state preserved and restoration possible? |

Unexercised behavior is recorded as unobserved, not failed and not silently promoted to a separate test.

## Stop conditions

Stop the rehearsal for:

- an unauthorized or unexplained write;
- source identity collision or destructive history loss;
- retention of rejected or out-of-scope source content;
- a privacy or permission boundary violation;
- graph corruption or inability to preserve the recovery state;
- false success or materially inaccurate effect reporting; or
- inaccessible interaction that prevents informed approval or cancellation.

Wording, relevance, verbosity, timezone/date drift, minor scan-window variation, awkward handoffs, and personality issues are feedback unless the user loses meaningful control, meaning, or trust.

## Exit criteria

The candidate may be proposed for development beta when:

- the user completed enough of the journey to judge usefulness, continuity, trust, and control;
- no stop condition remains unresolved;
- external graph inspection agrees with material effect reporting;
- the designated graph remains understandable and restorable; and
- the product owner explicitly chooses to proceed.

A focused follow-up test is required only for a specific observed defect or beta-blocking uncertainty. It does not reopen a broad regression suite.

## Reporting

Use one copy of the compact observation sheet in the session kit. Record direct observations separately from interpretation, omit raw work evidence and full transcripts, and conclude only `continue to beta decision`, `focused follow-up needed`, `revise candidate`, or `stop`.