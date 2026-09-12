---
schemaVersion: 2
type: tracking-topic
id: tracking-topic:intune-authentication-revoked-credentials
title: "Intune-managed authentication failure: revoked credentials"
createdAt: "2026-09-08T17:06:00Z"
status: archived
success: true
attentionState: waiting
cspId: csp:conditional-access-policy
participantIds:
  - person:mira-calder
  - person:nolan-reeves
  - person:tessa-ward
  - person:adrian-cole
excludedParticipantIds: []
tags:
  - hpi
  - solved
reviewBullet: true
---

# Intune-managed authentication failure: revoked credentials

## Summary

A large federal customer experienced a High Profile Incident in which thousands of users lost access to critical Microsoft 365 mobile applications. A bulk revocation of derived credentials exposed an incomplete authentication migration: affected users had enrolled their government-furnished iPhones into modern device management but had not completed passkey registration. Their revoked certificate remained their only strong-authentication method.

The immediate service-restoration effort succeeded. The incident was not caused by a Microsoft cloud platform defect and required no service-side engineering change.

## Impact

- Mobile access to Teams, Outlook, SharePoint, and OneDrive failed at scale.
- The support case opened at the highest severity with continuous follow-the-sun coverage.
- Customer help-desk volume provided the first impact estimate because persistent blast-radius telemetry was unavailable.
- Recovery had to proceed per user because the failed credential was also required by the protected self-service registration flow.

## Troubleshooting Logic

### Disproved hypothesis

The leading hypothesis was that a mass device deletion had deregistered mobile devices. An audit record appeared to support that interpretation.

Population-level evidence disproved it: device-removal volume was a very small fraction of the managed estate, the investigated device had no matching retire or remove event, and device-management commands and compliance reporting continued through the outage. The audit artifact correlated with the symptom but did not cause it.

### Confirmed causal chain

1. A third-party PKI action revoked a large set of derived credentials.
2. Certificate-based authentication correctly rejected the revoked certificates.
3. Affected users had no second strong-authentication method because passkey registration was incomplete.
4. Passkey registration required a recent MFA claim.
5. The removed credential was the only way to satisfy that requirement, creating a self-remediation deadlock.

The unaffected cohort supplied the decisive comparison: users who had completed passkey registration retained an independent method and continued authenticating.

## Evidence Considered

- Population-level device lifecycle counts
- Device-specific management and compliance history
- Authentication sign-in behavior and certificate-revocation result
- Authenticator client logs
- A screen recording of the failing registration flow
- Confirmation that the credential revocation was intentional
- Comparison of users with and without completed passkey enrollment

The minimum useful evidence package was a device identifier, authenticator client logs, and a recording of the failing flow. Each troubleshooting branch was pursued to a supported conclusion so that eliminating a non-cause remained measurable progress.

## Resolution

Affected users re-registered the authenticator application and enrolled a passkey. This was validated as the permanent recovery path rather than a temporary workaround. Security controls correctly prevented an unauthenticated bulk bypass, so recovery remained per user under the customer's compliance posture.

The case severity was reduced after the causal chain and recovery path were accepted, while monitoring and customer-side completion continued.

## Outcome and Contribution

The restoration was successful. The response combined identity and device-management analysis, a disciplined evidence package, cohort comparison, follow-the-sun handoffs, and a fixed-cadence fact base for support, account, engineering, and executive audiences.

The durable contribution was not merely identifying a revoked certificate. It was showing why only part of the population failed, disproving the attractive device-deletion theory with data, identifying the authentication deadlock, and translating those findings into a defensible recovery narrative.

## Lessons

- A strong credential remains a single point of failure until an independent second method exists.
- Recovery that requires the failed credential creates a deadlock; break-glass behavior must be designed and tested before migration.
- Audit artifacts that resemble symptoms are not causal proof. Population ratios can end a false line of investigation quickly.
- In partial-impact incidents, compare the unaffected cohort early.
- Define and obtain the minimum evidence package before speculation consumes the bridge.
- Follow-the-sun handoffs require written state and warm overlap.
- One owner and one cadence for outbound facts reduces narrative drift under executive pressure.
- Prior guidance becomes defensible incident history only when it was recorded before the trigger.
- Cause ownership and recovery leadership are different responsibilities.
- Technical correctness closes an HPI only when the explanation is evidence-backed, clear, and non-accusatory.

## Follow-Up Outside This Topic

These ideas are retained as career and troubleshooting context. They are outside this Topic's immediate-restoration scope and do not authorize or request another Topic.

- Quantify users who still have only one strong-authentication method.
- Treat enrolled-but-not-passkey-registered as an incomplete migration state with telemetry and ownership.
- Use Azure Workbooks and Authentication Enrollment resources to monitor passkey adoption across migrated government-furnished devices.
- Couple bulk credential lifecycle actions to authentication-method impact assessment, rollback planning, and communications.
- Define persona-based access standards and enforce them through Conditional Access.

## Review Bullet

- Solved HPI worth revisiting: revoked derived credentials exposed incomplete passkey enrollment and a single-method authentication deadlock. The transferable response pattern was to disprove the apparent device-management cause with population data, compare affected and unaffected cohorts, obtain a minimal client-evidence package, and maintain one evidence-backed narrative through restoration.