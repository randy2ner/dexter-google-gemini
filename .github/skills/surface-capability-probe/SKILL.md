---
name: surface-capability-probe
description: "Run small, harmless tests of Skill host tools, data access, actions, and interaction controls, and discover effective natural-language invocation. Use when a specified experience depends on a host capability that is unknown or needs verification."
---

# Surface Capability Probe

Learn quickly what the target AI surface can actually do and how to ask it. Test prerequisites, not the complete product experience.

## Procedure

1. Read the relevant PRD requirements, Specifications, Test Plans, and Skill host profile. Choose the smallest unresolved host capability that blocks Skill design or the first experience.
2. Define one harmless operation against a known, non-sensitive object. Test read or discovery before write, and prefer disposable or reversible targets for any mutation.
3. Give the user one short natural-language prompt to send through the target AI surface. Ask the user to return the surface's response and any visible tool, permission, sign-in, or confirmation behavior.
4. Treat the returned response as operator-reported evidence. Record only the minimum safe excerpt needed to understand the behavior.
5. If the result is ambiguous, vary the natural-language request once at a time to learn what wording, object reference, attachment, or context invokes the operation. Stop when the behavior is understood well enough to support or block design; do not optimize endless prompt variants.
6. Classify the capability:
   - `available`: the required operation was observed;
   - `available with conditions`: it works with stated wording, context, permissions, or controls;
   - `unavailable`: the surface does not offer the required operation;
   - `blocked`: access, policy, identity, or configuration prevented a conclusive operation; or
   - `unknown`: the probe did not establish behavior.
7. Update the affected PRD capability status or Specification dependency and append the dated observation to the relevant Test Plan case and host profile. Include the classification, shortest effective invocation, materially relevant conditions, Skill host product, and limitations. Do not create a separate probe or result record.
8. Recommend the smallest design consequence: proceed using the capability, adapt the project design, select another supported mechanism, or resolve a blocker. Do not build a project Skill around unobserved access or actions.

## Limits

- Never infer capability from documentation, a connector name, or the presence of a button.
- Do not test broad access when one known object is enough.
- Do not perform a write without the user's explicit approval of the exact target and change.
- A successful probe establishes one operation under observed conditions on the named Skill host; it does not prove the complete experience or behavior on another host.