# Marquee Outlet Orchestration Specification

## Document control

- **Status:** draft for review
- **Version:** 0.1
- **Owner:** User / product owner
- **Created:** 2026-09-09
- **Last updated:** 2026-09-11
- **Governed by:** [Marquee Project Charter](../CHARTER.md) and [`PR-003`, `PR-004`, `PR-006`, `PR-007`, `PR-008`](../PRD.md#product-requirements-and-acceptance-signals)
- **Depends on:** [Marquee graph creation](marquee-graph-creation.md)
- **Verified by:** [Knowledge Artifact Quality](../test-plans/02-knowledge-artifact-quality.md); [Outlet Recognition and Classification](../test-plans/03-outlet-recognition-and-classification.md); [Completion Strategy and User Involvement](../test-plans/04-completion-strategy-and-user-involvement.md); [Unconfirmed Knowledge Follow-up](../test-plans/06-unconfirmed-knowledge-follow-up.md); [Outlet Guidance Value and Accuracy](../test-plans/07-outlet-guidance-value-and-accuracy.md); [CareerHub Development Plan](../test-plans/08-careerhub-development-plan.md); [Manager OneNote Questionnaire](../test-plans/09-manager-onenote-questionnaire.md)
- **Candidate implementation:** [Marquee Skill](../skills/marquee/SKILL.md) implements this draft for evaluation. Implementation and packaging do not establish acceptance or runtime success.
- **Implementation authority:** None. This Specification records intended behavior for review.

## Purpose

Marquee recognizes when a user is asking for help completing a repeatable career exercise, understands the requested Outlet, and works with the user to choose the most effective way to complete it. The approach reflects both the automation available on the AI surface and how involved the user wants to be.

An Outlet request may be explicit, such as "Help me complete my CareerHub Development Plan," or conversational, such as "My manager gave me a questionnaire" or "I need to prepare for my performance connect."

## Recognizing an Outlet request

Marquee treats a request as an Outlet when the user wants help preparing, answering, drafting, editing, or completing a recurring professional exercise for an audience or destination.

Examples include:

- development plans;
- manager questionnaires;
- performance connects and annual reviews;
- recurring manager-meeting preparation;
- LinkedIn profiles and posts; and
- other repeatable career-story exercises.

An ordinary conversation about an accomplishment, goal, feedback, or career idea is not automatically an Outlet. It contributes to career knowledge unless the user is also trying to complete a repeatable exercise.

When the request could reasonably be either, Marquee asks one natural-language question about what the user wants to accomplish rather than forcing the user to classify the request.

## Understand the request

Marquee gathers only the context needed to begin useful work. It determines:

- what the exercise is;
- what the user needs to complete;
- the intended audience and purpose;
- the destination or format, when one exists;
- any deadline or immediate priority;
- whether the user has supplied, attached, linked, or opened the source document;
- which Marquee knowledge and authorized Work IQ context may help; and
- what a useful result looks like to the user.

Marquee inspects available instructions, questions, fields, or source material before asking the user to restate information already present. It asks follow-up questions only when the answer is needed to proceed or when the user's judgment cannot be responsibly inferred.

## Determine available automation

Marquee assesses what the current AI surface can actually do for the specific Outlet. It does not assume that access to a document also permits editing or submission.

The available completion level may be:

| Level | Meaning |
| --- | --- |
| Direct completion | Marquee can work in the Outlet destination and apply user-approved content there. |
| Complete draft | Marquee can prepare the full finished content, but the user will place it in the destination. |
| Guided completion | Marquee and the user work through sections or topics, producing approved content as they go. |
| Conversational preparation | Marquee prepares the user's story, talking points, or responses for an Outlet that is primarily a conversation. |

Direct Outlet automation is best effort. Marquee's dependable fallback is a polished response the user can use in the destination themselves.

Marquee states any meaningful limitation plainly. It does not make the user troubleshoot unavailable automation when drafting the content will still accomplish the request.

## Determine preferred involvement

Marquee asks or naturally establishes how the user wants to participate in this exercise. The user may prefer Marquee to:

- take the lead and prepare a complete first draft;
- collaborate section by section;
- ask questions before drafting;
- work directly in an accessible destination with review at appropriate points; or
- prepare concise talking points for a live conversation.

Marquee may recommend an approach based on the exercise, available source material, deadline, and need for a coherent story. It briefly explains the recommendation and allows the user to choose or adjust it.

The user does not need to select from a formal menu when their preference is already clear from the request.

## Agree on the completion approach

Before substantive completion work, Marquee summarizes the plan in natural language. The summary identifies:

- the Outlet and desired result;
- whether Marquee can work directly in the destination or will provide content in conversation;
- how Marquee and the user will work together;
- the knowledge or authorized Work IQ context Marquee expects to use; and
- any material action that will still require user confirmation.

The user can accept or redirect the approach. Marquee does not repeatedly reconfirm routine steps once the working approach is understood.

## Complete the Outlet

Marquee follows the agreed approach while adapting to information learned during the conversation.

- In conversation, Marquee remains natural, friendly, curious, and encouraging.
- Outlet content is polished, concise, credible, audience-aware, and all business.
- Marquee uses relevant existing career knowledge before asking the user to reconstruct it.
- Marquee uses authorized Work IQ when it can add relevant evidence or context.
- Marquee does not invent accomplishments, outcomes, feedback, goals, or capabilities.
- Marquee makes the user's contribution and significance clear without exaggeration.
- When direct editing is unavailable or becomes blocked, Marquee continues with a usable draft or response unless the user chooses to stop.

## Outlet guidance

A recognized Outlet uses or creates Markdown guidance in the Marquee graph's `Outlets` area or another location agreed by the user and Marquee.

For an existing Outlet, Marquee uses the current guidance when planning the exercise. For a new Outlet, Marquee develops guidance from the process that proves effective during completion. The guidance may include the Outlet's purpose, audience, recurring structure, useful knowledge sources, preferred voice, and effective working approach.

Marquee tells the user when it creates or updates Outlet guidance and what it documented. Outlet guidance supports repeatable assistance; it is not an activity ledger.

## Requirements

| ID | Requirement | Acceptance criterion |
| --- | --- | --- |
| OUTLET-001 | Marquee recognizes requests to complete repeatable career exercises. | Explicit and conversational requests enter the Outlet flow without requiring the user to name the concept of an Outlet. |
| OUTLET-002 | Marquee distinguishes an Outlet request from an ordinary career-knowledge conversation. | Ordinary accomplishments, goals, and feedback do not create generic Outlet guidance unless a repeatable exercise is being completed. |
| OUTLET-003 | Marquee understands the exercise before choosing a completion method. | Marquee identifies the desired result, audience, available source material, destination or format, and relevant constraints. |
| OUTLET-004 | Marquee assesses automation for the current request. | Marquee distinguishes direct completion from drafting, guided work, or conversational preparation based on capability actually available. |
| OUTLET-005 | Direct Outlet automation is best effort. | Unavailable direct editing does not block success when Marquee can provide polished usable content to the user. |
| OUTLET-006 | Marquee establishes the user's preferred involvement. | The agreed approach reflects whether the user wants Marquee to lead, collaborate, ask first, edit directly, or prepare talking points. |
| OUTLET-007 | Marquee recommends an efficient approach when useful. | The recommendation reflects the exercise, deadline, available context, automation, and need for coherence, and the user can redirect it. |
| OUTLET-008 | Marquee explains the agreed completion approach. | Before substantive work, the user understands what Marquee will produce, how they will participate, and whether direct editing is available. |
| OUTLET-009 | Marquee adapts without creating unnecessary process. | It asks only questions needed to proceed and does not require a formal choice when the user's request already establishes the approach. |
| OUTLET-010 | Marquee produces professional Outlet content. | Finished content is credible, audience-aware, evidence-grounded, and ready for direct use or user-managed transfer. |
| OUTLET-011 | Marquee degrades gracefully when automation fails. | If direct access or editing becomes unavailable, Marquee states the limitation and offers to finish the content in conversation. |
| OUTLET-012 | Repeatable Outlet guidance is retained transparently. | Marquee creates or updates guidance from the effective process and tells the user what Markdown it changed. |

## Authority and boundaries

- The user decides the desired result and how involved they want to be.
- Marquee may inspect user-provided Outlet material and use authorized career knowledge or Work IQ for the agreed purpose.
- Agreement on a working approach does not authorize publication, submission, sharing, or messaging another person.
- Direct editing requires the destination capability and user agreement appropriate to that exercise.
- Marquee does not claim an Outlet was completed in its destination when it only produced a draft in conversation.
- The user may redirect, pause, or stop the exercise at any time.

## Failure and cancellation

- If Marquee cannot understand what the user is trying to complete, it asks one focused question and preserves the user's language.
- If source material is unavailable, Marquee explains what is missing and continues from user-provided information when useful.
- If direct automation is unavailable, Marquee offers the conversational drafting fallback.
- If the user stops, Marquee does not claim completion.
- Any Outlet guidance or career knowledge retained before the conversation ends identifies material that still needs user confirmation according to the applicable knowledge specification.

## Open questions

None are required to review this orchestration behavior. Destination-specific mechanics and prompts belong to the individual Outlet guidance developed through use.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 0.1 | 2026-09-09 | Defined how Marquee recognizes an Outlet request and agrees on an effective completion approach based on available automation and preferred user involvement. |
