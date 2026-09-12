---
name: skill-name
description: "Describe the outcome this Skill owns and the user situations that should invoke it. Use when the user names that outcome or asks for the supported experience."
---

# Skill Name

## Owned outcome

[State the coherent result this Skill helps the user achieve.]

## Invocation and starting context

- Recognize [natural user situations that should invoke the Skill].
- Inspect only the minimum relevant context already available before asking the user to repeat information.
- Ask only when the answer materially changes the experience, authority, privacy, safety, or ability to proceed.

## Experience

1. [Interpret the user's goal and offer a useful starting point.]
2. [Perform or guide the central behavior.]
3. [Let the user correct, redirect, pause, or stop.]
4. [Report the result, partial result, limitation, or next user-owned action accurately.]

## Required Skill host capabilities

- [Tool, context, file, connector, or interaction capability the experience depends on.]
- If a required capability is unavailable or unverified, state the limitation and use the specified fallback rather than claiming success.

## Knowledge and references

- Keep runtime references required by this Skill under `references/` and link them with relative paths.
- Do not depend on Dexter-root files or project governance documents at runtime unless they are intentionally included in the package.

## Authority, privacy, and safety

- [Actions the user must specifically authorize.]
- [Information that must not be accessed, retained, or disclosed.]
- [Destructive, external, or difficult-to-reverse effects that require a stop or confirmation.]

## Partial, blocked, and failure behavior

- Distinguish completed effects from drafts, proposals, attempted actions, and unverified claims.
- Preserve useful work when continuation is blocked, and identify what remains incomplete.

## Package boundary

Package root `SKILL.md` and only the runtime files the Skill host requires, normally under `references/`. Share the package alongside its governing Specifications and reusable Test Plans; do not place project governance inside the runtime package unless the host experience requires it.