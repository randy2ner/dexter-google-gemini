# Human-centered evaluation

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Make conversational quality, comprehension, dignity, trust, and user control first-class product behavior when a Skill interacts with people.

## Required evaluation dimensions

| Dimension | Question |
| --- | --- |
| Comprehension | Can the user explain what is happening, why, and what each choice changes? |
| Natural flow | Does the interaction sound like helpful conversation rather than a form, protocol, or interrogation? |
| Agency | Can the user pause, question, revise, exclude, or stop without pressure? |
| Dignity | Does the Skill avoid profiling, judgment, surveillance language, and unsupported characterization? |
| Trust | Are access, retention, uncertainty, and consequences explained before action? |
| Proportionality | Are questions limited to meaningful ambiguity rather than mechanical confirmation? |
| Accessibility | Are labels and choices understandable without internal IDs or specialist vocabulary? |
| Privacy | Is sensitive context minimized in both runtime output and retained evidence? |

## Scenario design

- Use natural-language prompts representative of intended use.
- Test whether the user understands a proposed action before authorizing it.
- Score confusing wording, unexplained IDs, excessive confirmations, and abstract classifications as behavioral findings—not user error.
- Prefer choices such as `Yes`, `Change the wording`, `Make it more general`, and `Leave it out` over internal process terms.
- Keep machine identifiers secondary unless needed to correct ambiguity.
- Ask the user for qualitative reaction when interaction quality is an accepted requirement.
- Stop when the user expresses confusion, discomfort, loss of trust, or inability to make an informed choice.

## Evidence handling

Record the minimum safe interaction excerpt needed to support a finding. Do not retain private source content merely to prove a usability issue. Separate direct user feedback from Dexter's interpretation.

## Acceptance

Structural compliance does not compensate for an interaction that users cannot understand or willingly control. A privacy-safe workflow may still fail its human-centered acceptance criteria.