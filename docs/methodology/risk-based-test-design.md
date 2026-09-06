# Risk-based test design

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Create the smallest test program that can responsibly inform the next project decision.

## Start with the decision

Every test plan states:

- the decision the evidence will inform;
- the accepted claims under evaluation;
- the highest-consequence failures;
- evidence needed to distinguish pass, partial, fail, and blocked; and
- when testing stops.

## Default first slice

Prefer three to five primary scenarios:

1. one representative successful path;
2. one representative malformed or unavailable-input path;
3. one authority, privacy, or safety-boundary path;
4. one distinctive human-interaction path when conversation is part of the product; and
5. one combined or end-to-end bounded path only when it informs closure.

Combine compatible assertions into one staged run when doing so reduces exposure and does not hide causality. Separate transport, packaging, and product behavior when a failure would otherwise be ambiguous.

## Adding tests

Add a scenario only when at least one applies:

- failure would create material user, privacy, integrity, or operational harm;
- a requirement has no meaningful evidence;
- an observed defect needs reproduction;
- two plausible implementations would produce materially different outcomes; or
- a release or scope decision depends on the result.

Do not add tests merely for every field, permutation, file order, or theoretical edge case. Use representative classes and documented gaps.

## Closure

Close a slice when:

- required claims have sufficient evidence for the stated scope;
- unresolved gaps are documented and do not block the decision;
- observed defects have an accepted disposition;
- confidence is bounded to exact versions and environments; and
- additional testing has diminishing decision value.

Missing nonessential metadata becomes an explicit limitation, not an invitation to fabricate or repeat work without purpose.