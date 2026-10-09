---
title: "Interacting with the self-service portal as a guest user"
slug: "interacting-with-the-self-service-portal-as-a-guest-user"
updated: 2025-10-30T18:03:00Z
published: 2025-11-03T07:41:58Z
canonical: "helpcenter.securiti.ai/interacting-with-the-self-service-portal-as-a-guest-user"
area: privacy
modulo: self-service-portal
tipo: guia
data_captura: 2026-10-08
---

# Interacting with the self-service portal as a guest user

As a guest user, you can access the self-service portal using the URL published on a wiki or an internal page of your organization's website.

### Logging into the self-service portal with SSO

Securiti provides SSO-based authentication for the self-service portal so that guest users can access the portal with one set of login credentials.

1. As a guest user who visits the published URL for the first time, Securiti prompts you for your email address to access the portal, as shown below.

![login.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3c27442-2fba-69d3-afbb-660d03f9aaf1.png)

> [!NOTE]
> **Note**
> 
> If the SSP portal is unpublished, the system shows an error message on accessing the portal.
> 
> ![unpublished_self_service_portal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9484b6f9-8ec6-9133-0d53-dfd95fff5eb6.png)
2. The system redirects you to the identity provider’s (Google or Facebook) login screen, where you provide your email address and password.
3. On successful login, the system redirects you to the self-service portal.
4. In the self-service portal, you see the Home, Assessments, and Incidents tabs, respectively. To configure SSO login for assessment guest users, see [here](/v1/docs/configuring-sso-login-for-assessment-guest-users).

![SSO_SSP_login.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c0d6ebf-a094-3c93-6ae9-9d6355faa963.png)

> [!NOTE]
> **Note**
> 
> The tabs allow limited access to tools for non-Securiti users.

### Logging into the self-service portal using the link

If SSO is not active for your organization, you can access the self-service portal using the link you receive in your email.

> [!NOTE]
> **Note**
> 
> The procedure below uses fulfilling an assessment as an example.

To access the self-service portal via the invite link:

1. As a guest user who visits the published URL for the first time, Securiti prompts you for your email address to access the portal.
2. Securiti sends you an email with the OTP assuming you have the [Advanced Invite Controls](/v1/docs/system-settings-configuring-securiti-general-settings) enabled for your tenant.

> [!NOTE]
> **Note**
> 
> If you do not have MFA activated in your settings, Securiti redirects you to the assessment.

Enter the code to authenticate yourself as the intended guest user, as shown below.

![Screenshot_2025-07-07_at_12_13_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ccf78c6-e538-043f-23f0-3d89ce3337c0.png)
3. Proceed to [Start an assessment](/v1/docs/start-an-assessment).
