# Mediated Cowork experience rehearsals

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-04

## Purpose

Reach representative Skill use quickly when the laboratory assistant cannot directly operate the approved Cowork surface. The product owner operates Cowork, the laboratory assistant supplies bounded prompts and decision support, and both participants preserve a shared synthetic conversation as evidence.

This method evaluates Skills in their actual medium: probabilistic natural-language instructions interpreted by an AI inside a host surface. It complements source inspection and focused technical checks; it does not treat Skills as deterministic programs or replace evidence with intuition.

## Why the medium matters

A Skill's behavior is shaped by more than its source text:

- the model interprets natural-language instructions rather than executing every sentence as code;
- the host controls attachments, cards, permissions, context, and available actions;
- the current conversation carries user choices, corrections, and prior outputs;
- other Skills and Orchestrations affect routing and authority;
- the data medium affects identity, retention, and observable effects; and
- session variation can change wording and sequencing without changing product meaning.

Therefore Dexter evaluates both the authored instruction and the behavior produced when that instruction meets its AI surface. Exact output is required only where the project contract makes exactness consequential.

## Roles and evidence boundaries

| Participant | Responsibility | Evidence produced |
| --- | --- | --- |
| Product owner / operator | Operate Cowork in the approved client, make consequential choices, and relay displayed prompts and outcomes | First-person reports and minimal safe excerpts from the host surface |
| Laboratory assistant | Prepare exact artifacts and synthetic inputs, suggest what to type, interpret choices against accepted contracts, inspect synchronized effects, and maintain records | Local artifact inspection, external effect inspection, and clearly labeled interpretation |
| Cowork / Skill under study | Conduct the experience, present controls, invoke allowed capabilities, and report outcomes | Runtime responses relayed by the operator and durable effects available for inspection |

Do not collapse these evidence sources. An operator report establishes what the operator observed. Local inspection establishes what synchronized bytes contain. Neither alone proves hidden host behavior, cloud synchronization timing, or unobserved access.

## The shared synthetic conversation

The rehearsal conversation is a jointly tracked test instrument. It consists of:

1. the bounded user intent;
2. the exact Skill package or version;
3. fictional evidence or a disposable graph;
4. the prompt the operator sends;
5. Cowork's substantive response or decision point;
6. the operator's selected action;
7. Cowork's terminal effect report; and
8. independent inspection of observable durable effects.

The operator may relay each turn when interpretation matters, or batch routine repeated choices and provide counts plus the final report. Stop batching when a new object, authority, target, retained datum, or effect appears outside the expected experience.

Synthetic content must be visibly fictional, contain no credentials or tenant identifiers, and be treated as evidence rather than authority. Injection fixtures may appear inside synthetic evidence to evaluate whether evidence-borne instructions alter behavior.

## Fast path to a representative experience

### 1. Shape a thin experience slice

Choose one recognizable user journey with a beginning, meaningful decisions, and a useful end state. Include only the Skills, dependencies, and graph objects needed to experience that journey.

Record:

- the user outcome;
- the exact candidate versions;
- the disposable or fictional boundary;
- consequential approvals reserved for the operator;
- externally inspectable effects; and
- material stop conditions.

Do not begin by decomposing every capability into a standalone test.

### 2. Prepare the minimum runnable specimen

Inspect package structure and obvious contract prerequisites before connected use. Prepare fixed synthetic input and a known graph baseline when writes are possible. Confirm that restoration is feasible or disclose the limitation.

Static inspection establishes that the specimen is testable. It does not establish runtime success.

### 3. Rehearse through mediated turns

The laboratory assistant gives the operator one exact starting prompt. The operator relays Cowork's response when:

- a consequential choice is requested;
- the response is surprising or unclear;
- a new access request or target appears;
- the Skill proposes durable retention or mutation; or
- the experience reaches a terminal outcome.

The assistant explains the consequence of available choices and recommends a selection against accepted intent. The operator remains the authority and performs the action in Cowork.

### 4. Observe many actions in one experience

One journey may provide evidence about multiple claims, including:

- package availability and host compatibility;
- attachment and evidence transport;
- progressive conversational flow;
- user comprehension and control;
- source identity and correlation;
- cross-Skill routing and fresh approval;
- prompt-injection resistance;
- privacy minimization and retention;
- graph relationships and history;
- pre-write validation and post-write verification;
- cancellation or no-write behavior; and
- truthful effect accounting.

Maintain a claim ledger for the journey. For each claim, identify the turn or stored effect that supports it, the source of observation, and any limitation. Do not multiply scenarios merely to give each claim its own test case.

### 5. Inspect effects outside the conversation

When the Skill reports a durable effect, inspect the authorized synchronized output independently. Compare paths, object identities, canonical relationships, managed boundaries, preserved content, and unexpected files. Treat host reports and stored bytes as complementary evidence.

### 6. Classify what happened

Use four practical classes:

| Class | Meaning | Default response |
| --- | --- | --- |
| Successful variation | Different wording, timing, ordering, filename, or disclosed inference with equivalent meaning and intact control | Continue; record only when informative |
| Shaping feedback | Understandable but awkward behavior, repeated friction, unclear labels, or a theme worth improving | Continue when safe; batch recurring themes |
| Material finding | Behavior threatens authority, privacy, identity, history, recoverability, or effect truth | Stop the affected path and investigate |
| Unresolved assurance | A meaningful claim was not exercised or cannot be observed | State the limitation; run one focused check only if it blocks the next decision |

User confusion is evidence about the interaction, not operator failure. Correct the record when later clarification changes the interpretation of a selected control.

### 7. Decide the next smallest move

After the journey, choose one:

- continue shaping through representative use;
- make a focused instruction revision for a recurring theme;
- run one diagnostic for a material finding or blocking uncertainty;
- propose a bounded beta decision; or
- stop without claiming confidence beyond the evidence.

## Designing and developing Skills

Skill development is instruction design for an AI medium. Prefer instructions that communicate outcomes, boundaries, authority, and decision criteria while leaving room for natural conversational adaptation.

Use exact prescriptions for:

- allowed access and retention;
- object identity and canonical relationship ownership;
- consequential approval and cancellation;
- required handoff fields;
- protected history and user-authored content;
- effect accounting; and
- terminal outcome truth.

Use adaptive guidance for:

- conversational wording;
- reasonable question order;
- concise summaries;
- user-correctable defaults;
- presentation choices supported by the host; and
- low-consequence formatting.

Over-specifying natural language can make a Skill rigid without making it reliable. Under-specifying trust boundaries can make it fluent without making it safe. Dexter's work is to find and preserve the boundary between those concerns through observed use.

## Recording the rehearsal

Keep the durable record compact:

- one [mediated Cowork session kit](../_templates/mediated-cowork-rehearsal-template.md) or scenario defining scope and operator handoff;
- one exact candidate inventory;
- minimal operator-reported excerpts needed to support findings;
- external inspection of claimed effects;
- one result covering the complete experience;
- linked findings only for material or recurring themes; and
- a confidence statement limited to exercised claims.

Preserve completed results even when later interpretation or source intent changes. Add a correction or superseding record rather than rewriting what was directly observed. Living scenario status may advance as the experience continues.

## Origin and evidence

This method was generalized from the Compass experience-led rehearsal on 2026-09-02 through 2026-09-04. In that rehearsal, Conditional Access prevented the laboratory assistant from operating Cowork directly. The product owner operated an approved managed client, relayed Cowork responses, made approvals, and attached fictional evidence. The assistant supplied prompts, evaluated decision points, inspected synchronized OneDrive effects, and recorded results across Installation, Daily Scan, Tracking Topic Interview, and Curator.

The rehearsal demonstrated that a mediated synthetic conversation can exercise many product actions coherently while exposing medium-specific behavior such as attachment transport, Adaptive Card usability, cloud-folder identity, natural-language option ambiguity, and session variation.

Project-specific records remain the evidence; this guide is the reusable Dexter method derived from them.