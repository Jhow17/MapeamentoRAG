---
title: "Configuring SSO Login for Assessment guest users"
slug: "configuring-sso-login-for-assessment-guest-users"
updated: 2025-10-31T13:40:49Z
published: 2025-11-03T06:12:21Z
canonical: "helpcenter.securiti.ai/configuring-sso-login-for-assessment-guest-users"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Configuring SSO Login for Assessment guest users

> [!NOTE]
> **Note**
> 
> This topic is for admins who have configured SSO (Single Sign-On) for their domain, and who manage and create users based on their IDP (Identity Provider) or AD (Application/Service Dependent Party) groups.

See the table below to learn about the entry points that are available to you as assessment guest users. This also details the experience for different use cases and access configurations.

| User type | Access via | SSO enabled | JIT (Just-In-Time) provisioning enabled | Landing page | Mapped role exist? | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Guest user | Self-service portal | Yes | Yes | User is redirected to the SSP Homepage. | Yes | The user is part of the registered domain and belongs to the AD/IDP group configured for SSO, they're authenticated as such upon login via SSO. User role is assigned based on their SAML assertion. |
| Guest user | Self-service portal | Yes | No | User is redirected to the SSP Homepage. | N/A | The user is part of the registered domain and belongs to the AD/IDP group configured for SSO, they're authenticated as such upon login via SSO. The user role is strictly guest user. |
| Guest user | Self-service portal | No | No | User is redirected to the SSP Homepage. | N/A | They login through the magic link or receive a OTP if Advanced Invite Controls are enabled in Securiti. The user role is strictly guest user. |
| Guest user | Email link | Yes | No | User is redirected to the assessment assigned to them. | N/A | The user access is authenticated via the IDP login. The user role is strictly guest user. |
| Guest user | Email link | No | No | User is redirected to the assessment assigned to them. | N/A | They login through the magic link or receive a OTP if Advanced Invite Controls are enabled in Securiti. The user role is strictly guest user. |

See these FAQs or observe the following caveats:

- *If JIT is enabled, why can we not select the Guest User role as a default role?*

The guest user via SSO with JIT provisioning no longer stays a guest user. The system therefore auto provisions roles such as User, Operator, DPO, etc.
- *Can customers enable JIT without the risk of guest users from assessments being auto provisioned as users?*

As mentioned, the guest user is no longer a guest user when they authenticate through the SSO channel with JIT active so no. Their details as to what role or responsibilities they're assigned, it's based off of their SAML assertion or default role configured in SSO.
- *If an assessment user (clicking the link from the assessment email) is not in the AD Group that SSO is configured, but they ARE part of the domain, do they get routed to SSO still, or do they get the magic link/OTP?*

The guest user is redirected towards the SSO flow as they're part of the configured domain.

For more information, see Advanced Invite Controls in [Securiti system settings](/v1/docs/system-settings-configuring-securiti-general-settings).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A user who has not been registered in the tenant or does not have access to the current assessment organization. Also, referred to as a non-system user.

## Related

- [Interacting with the self-service portal as a guest user](/interacting-with-the-self-service-portal-as-a-guest-user.md)
- [Inviting Vendors Respondents to submit assessments](/inviting-vendor-respondents-to-submit-assessments.md)
