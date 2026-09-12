# Marquee Project Charter

## Document control

- **Status:** accepted
- **Project:** Marquee
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-09
- **Last updated:** 2026-09-11
- **Approved:** 2026-09-09 by explicit user direction
- **Implementation authority:** None. This Charter establishes project direction only.

## Project documents

| Document | Purpose | Status |
| --- | --- | --- |
| [Project Charter](CHARTER.md) | Defines why Marquee exists, who it serves, its intended outcomes, initial beta scope, and boundaries. | Accepted |
| [Product Requirements Document](PRD.md) | Prioritizes Marquee outcomes, product requirements, capabilities, constraints, and acceptance signals. | Active |
| [Graph Creation Specification](specifications/marquee-graph-creation.md) | Defines creation and evolution of the user-managed Marquee graph. | Draft for review |
| [Outlet Orchestration Specification](specifications/marquee-outlet-orchestration.md) | Defines how Marquee recognizes an Outlet and agrees on its completion approach. | Draft for review |
| [Career Expertise and Advice Specification](specifications/marquee-career-expertise-and-advice.md) | Defines expert career-agent behavior and standards for useful advice. | Draft for review |
| [Marquee Skill](skills/marquee/SKILL.md) | Implements draft Specification behavior so it can be reviewed and tested without implying acceptance or runtime proof. | Test candidate implementing drafts |
| [Skill Exchange](skill-exchange/README.md) | Provides an importable copy of the test candidate; packaging does not establish behavioral acceptance or successful operation. | Importable test candidate |
| [Test Plan 01: Graph Consent and Creation](test-plans/01-graph-consent-and-creation.md) | Grades user authority, graph placement, creation, inspectability, and truthful reporting. | Ready, not run |
| [Test Plan 02: Knowledge Artifact Quality](test-plans/02-knowledge-artifact-quality.md) | Grades folder classification, frontmatter, useful detail, and transparent knowledge writes. | Ready, not run |
| [Test Plan 03: Outlet Recognition and Classification](test-plans/03-outlet-recognition-and-classification.md) | Grades recognition and understanding of explicit, conversational, ambiguous, and ordinary requests. | Ready, not run |
| [Test Plan 04: Completion Strategy and User Involvement](test-plans/04-completion-strategy-and-user-involvement.md) | Grades automation assessment, involvement, approach selection, fallback, and authority. | Ready, not run |
| [Test Plan 05: Expert Career Advice](test-plans/05-expert-career-advice.md) | Grades diagnosis, actionable recommendations, independent judgment, evidence, and boundaries. | Ready, not run |
| [Test Plan 06: Unconfirmed Knowledge Follow-up](test-plans/06-unconfirmed-knowledge-follow-up.md) | Grades visible unconfirmed status and focused resolution on a later summons. | Ready, not run |
| [Test Plan 07: Outlet Guidance Value and Accuracy](test-plans/07-outlet-guidance-value-and-accuracy.md) | Grades whether retained Outlet guidance is accurate, useful, portable, and improved through use. | Ready, not run |
| [Test Plan 08: CareerHub Development Plan](test-plans/08-careerhub-development-plan.md) | Evaluates the first complete participant journey. | Ready, not run |
| [Test Plan 09: Manager OneNote Questionnaire](test-plans/09-manager-onenote-questionnaire.md) | Evaluates the second complete participant journey. | Ready, not run |

## Vision

Marquee gives people a confident professional voice and a spotlight for work they may struggle to promote themselves. It acts as a friendly career agent that recognizes the significance of their work, helps them express it credibly, and turns accumulated career knowledge into polished material for recurring professional exercises.

Marquee is intended to make career reflection and self-advocacy more enjoyable and less of a chore. It helps the user shine without requiring them to become naturally outgoing, comfortable with self-promotion, or skilled at professional writing.

> Marquee remembers what makes you remarkable and helps you put it into words.

## Problem and opportunity

Many people do valuable work but have difficulty explaining its importance. Accomplishments become scattered across email, chats, meetings, documents, feedback, and memory. When a manager, employer, or professional network asks what they have achieved or where they want to go, they must reconstruct their story under time pressure.

This burden is especially difficult for people who are shy with words, intimidated in social settings, or uncomfortable promoting themselves. Required activities such as development plans, manager questionnaires, performance conversations, and annual reviews can become administrative chores instead of opportunities to be recognized.

Marquee can reduce that burden by helping the user recognize meaningful work as it happens, retain what the user and Copilot consider important, and turn that knowledge into a strong account suited to each recurring exercise.

## Intended users

The distributable beta is for people who:

- want their work, strengths, and potential to be more visible;
- find career writing or self-promotion difficult or uncomfortable;
- use Microsoft 365 and Copilot in their work;
- complete recurring career or performance exercises; and
- want an approachable assistant that helps them build a credible professional story over time.

Marquee begins from one user's real needs but is intended to be distributable to a larger beta group facing similar CareerHub and manager-questionnaire deadlines.

## Intended outcomes

1. **A stronger professional voice:** Help users explain what they do and why it matters in language that is confident, specific, and authentic.
2. **Visible accomplishments:** Recognize valuable work, praise, outcomes, and contributions that users may otherwise overlook or undersell.
3. **Less burdensome career exercises:** Use accumulated knowledge and relevant work context to reduce blank-page effort and repetitive reconstruction.
4. **Coherent career direction:** Connect highlights, strengths, perspectives, and aspirations into an evolving career story.
5. **Audience-ready work:** Produce polished material appropriate to the professional exercise being completed.
6. **Repeatable assistance:** Learn an effective approach while completing a recurring exercise and preserve guidance that makes the next use easier.
7. **Broader professional presence:** Eventually help users express their work through outlets such as LinkedIn as well as employer-required activities.

## Initial beta opportunity

The immediate beta focuses on two real, time-sensitive exercises shared by a larger group:

1. completing a CareerHub Development Plan; and
2. completing a manager-requested OneNote questionnaire.

The CareerHub Development Plan will be Marquee's first complete beta experience. The OneNote questionnaire provides a second outlet through which the team can learn whether Marquee adapts its process to a different audience, format, and destination.

These exercises are opportunities to discover and test Marquee with real users. This Charter does not presume how CareerHub or OneNote access works, whether direct editing is available, or what final Skill structure will be required.

## Marquee persona

Marquee belongs in the user's executive cabinet as the persona they consult for career-story work: explaining current priorities, preparing for a manager conversation, describing accomplishments, articulating goals, completing a development plan, answering a questionnaire, or building a professional presence.

Marquee has two complementary modes:

- **In conversation:** natural, friendly, curious, encouraging, and easy to talk with. It helps the user recognize significance without turning the exchange into a form or interrogation.
- **In an Outlet:** polished, concise, credible, audience-aware, and all business. Finished writing earns attention through evidence and clarity rather than exaggeration or artificial corporate language.

Marquee advocates for the user without inventing achievements, inflating claims, or making the user sound unlike themselves.

## Core experience

A user can invoke Marquee whenever something professionally meaningful happens or a career-story exercise needs attention.

Examples include:

- "Hey Marquee, I got a flattering email."
- "Hey Marquee, I was critical in fixing the HPI in this Chat ID. Who should I ask for a perspective?"
- "Help me complete my CareerHub Development Plan."
- "My manager sent me a OneNote questionnaire."
- "Help me prepare to explain what I am working on."

Marquee uses natural conversation and relevant authorized Work IQ to understand the event or exercise. It identifies what appears important, tells the user what it is documenting, and asks the user to confirm or correct its interpretation.

## Career knowledge

Ordinary Marquee conversations build useful career knowledge rather than an activity ledger. Candidate knowledge includes:

- accomplishments, praise, milestones, and problems solved;
- the user's contribution and why it mattered;
- outcomes and demonstrated strengths;
- career interests, aspirations, and goals;
- perspectives received or people who directly observed important work; and
- an evolving professional profile and career story.

This knowledge may be held in a group of user-managed Markdown artifacts. The artifacts exist to support the user's career work, not to track Marquee's activity, prove capability, or create project administration.

Marquee learns within the active conversation. It gives useful residual output to the user, who manages that output. Marquee does not maintain a separate activity or capability ledger.

## Outlets

An Outlet is a repeatable career exercise, not an ordinary conversation. Candidate Outlets include:

- CareerHub Development Plans;
- manager-requested questionnaires;
- monthly manager conversations;
- performance connects and annual reviews;
- LinkedIn profiles and posts; and
- other recurring professional narratives.

When Marquee works on an Outlet, it also creates or improves a Markdown guidance artifact describing the effective process discovered while completing that exercise. The guidance helps an AI surface handle the same Outlet more effectively in the future and may become the basis for a repeatable Skill.

Outlet guidance captures what proved useful, such as the exercise's purpose, audience, source material, preferred voice, and effective working approach. It is not an activity ledger.

## Retention contract

When invoked, Marquee is upfront about its use of files and confirms the operating contract as part of the experience:

1. Marquee identifies the user-selected OneDrive folder for Marquee knowledge or asks the user to choose one.
2. Marquee explains what career knowledge and, when applicable, Outlet guidance it expects to create or update.
3. Marquee records useful subject matter as the conversation develops.
4. Marquee tells the user specifically which Markdown files it created or changed and what each contains.
5. Marquee asks the user to confirm or correct its interpretation.
6. If the conversation ends before confirmation, retained content may remain but clearly indicates which parts are unconfirmed.

Invoking Marquee does not create a generic Outlet. Ordinary conversations build other career knowledge; Outlet guidance is created only for a recognizable repeatable exercise.

## Adaptive working method

Marquee chooses an approach suited to the request, destination, available AI-surface capabilities, and amount of personal judgment involved. It may recommend:

- editing directly when the destination permits it;
- preparing one complete artifact when the story requires coherence;
- working topic by topic when distinct questions need attention; or
- preparing the user conversationally when the Outlet is a meeting.

Marquee briefly explains the approach and allows the user to redirect it. The beta should discover what is actually possible on each AI surface rather than assume direct editing or a fixed workflow.

## Authority and user control

- The user owns their career story, knowledge, goals, and final professional representation.
- Marquee may interpret authorized information and propose what is important.
- Marquee states what it is documenting and seeks confirmation of its interpretation.
- Unconfirmed content remains distinguishable from user-confirmed knowledge.
- The user may correct, reject, redirect, or stop the experience.
- Permission to discuss, draft, or retain private Marquee knowledge does not by itself authorize submission, publication, sharing, or messaging another person.
- The user decides how and where completed material is used.

## In scope for the distributable beta

- A portable Marquee experience usable by a larger beta group.
- Friendly career-story conversation.
- Relevant, user-authorized Work IQ use when available.
- User-selected OneDrive storage for inspectable Markdown knowledge.
- Creation and refinement of career knowledge from ordinary Marquee conversations.
- Automatic Outlet guidance for repeatable exercises.
- Clear disclosure of files created or changed.
- Confirmed and visibly unconfirmed knowledge.
- Adaptive drafting or direct-edit recommendations based on the exercise and available capability.
- The CareerHub Development Plan as the first complete experience.
- A manager-requested OneNote questionnaire as the next immediate Outlet.
- Learning whether one Skill or a coordinated set of Skills best delivers the experience.

## Future opportunities

The broader vision includes:

- monthly manager-meeting preparation;
- performance connects and annual reviews;
- LinkedIn profile development and posts about things the user builds;
- professional biographies and introductions;
- perspective identification and request preparation; and
- other career-story exercises initiated by the user.

These opportunities inform the direction but do not expand the initial beta beyond what the team can build and evaluate responsibly.

## Dependencies and assumptions to verify later

- The target AI surface can invoke portable Skills and sustain the intended conversational experience.
- Work IQ can provide useful authorized context for the user's career story.
- The AI surface can create and update Markdown in a user-selected OneDrive folder.
- CareerHub and OneNote may support direct editing, or Marquee can provide an effective reviewed artifact for user-managed transfer.
- The same core experience can serve a larger beta group without embedding one user's private knowledge or preferences in the distributable package.

These are hypotheses for later verification, not established capabilities.

## Success signals

Marquee's distributable beta is promising when:

- users find it easier and more enjoyable to complete the selected career exercises;
- users recognize important accomplishments or strengths they would otherwise have omitted;
- finished Outlet writing is credible, polished, useful, and still feels true to the user;
- Marquee reduces repetitive reconstruction by using accumulated career knowledge;
- users understand what Marquee records and can correct its interpretation;
- Outlet guidance makes a repeated exercise easier without creating administrative burden;
- the experience works for multiple beta users without exposing one user's private information; and
- observed AI-surface capabilities support a practical path to distribution.

The future Test Plan will turn these signals into observable beta cases without inventing success evidence.

## Risks and open questions

- Marquee may exaggerate or flatten the user's authentic voice while trying to make them shine.
- Work IQ may omit important context or expose more information than the current purpose needs.
- Users may not understand what is retained unless file disclosure is clear and timely.
- Unconfirmed interpretations may be mistaken for accepted career facts.
- Employer exercises and destinations may vary across users or limit direct editing.
- A deadline-driven beta may encourage assumptions about AI-surface capabilities that have not been observed.
- Personalized knowledge and Outlet guidance must remain separate from distributable Skill instructions.
- The final Skill design and smallest viable beta package remain future design decisions.

## Acceptance boundary

Accepting this Charter establishes Marquee's purpose, intended users, distributable-beta direction, initial use cases, persona, and authority boundaries. It does not approve a detailed design, authorize implementation or connected access, establish that required capabilities exist, or authorize publication, submission, deployment, or release.
