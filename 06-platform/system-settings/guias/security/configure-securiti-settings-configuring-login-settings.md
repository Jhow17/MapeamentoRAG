---
title: "Configuring login settings"
slug: "configure-securiti-settings-configuring-login-settings"
updated: 2025-12-11T10:33:03Z
published: 2025-12-11T10:33:03Z
canonical: "helpcenter.securiti.ai/configure-securiti-settings-configuring-login-settings"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring login settings

If you have a Premium account, you can configure the following settings for how users in your organization log in to Securiti:

- The minimum password length
- The number of consecutive invalid logins before Securiti takes action, and the action that Securiti takes
- The action taken after too many consecutive invalid logins
- Whether Securiti forces all users to enable MFA for their user accounts
- The number of concurrent login sessions allowed for each user, and the action Securiti takes when the value is exceeded

> [!NOTE]
> **Note**
> 
> Securiti requires each user to reset their password every 90 days. This period is not configurable.

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the System Settings menu, choose **Security > Login Settings**.
4. Near the upper right corner of the page, click **Edit** (pencil icon).
5. Edit the login settings to suit.

| Setting | Description |
| --- | --- |
| Minimum password length | Set the minimum length for a user's password. The default value is 10 characters. The valid range is 10 to 20 characters |
| Consecutive Invalid logins threshold | Set the threshold for acting on excessive consecutive invalid login attempts by a user. |
| Treatment for consecutive invalid logins | Set the action Securiti takes when a user makes an excessive number of login attempts: - **Show Capcha** - Challenges the user to correctly interpret a capcha on subsequent login attempts. - **Lock user** - Locks the user account until an admin unlocks it by opening **Organizational > Users**, and for the user choosing **Options > Unlock**. ![Unlock_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4be8135a-9adc-ee8b-c380-42abf39a6c8e(3).png) |
| Force Enable MFA | Use this toggle to enable multi-factor authentication by default for all new Securiti users as described in [Securing your account with multi-factor authentication](/v1/docs/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication). Under this setting, users cannot disable MFA. |
| Concurrent User Login Sessions | Use the [Concurrent User Login Sessions](/v1/docs/configuring-securiti-general-settings-configuring-concurraent-login-session-limits) tools to set the maximum number of concurrent sessions and the message that Securiti displays when users try to exceed the limit. If a user tries to exceed the limit, Securiti shows them an alert and denies the login. The alert has a button that lets the user force logouts for all their active sessions as shown below. ![RN_login_sessions1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad0d43af-79ba-ade3-f5ad-6010575ca537(7).png) |
6. Near the upper right corner of the page, click **Save**.
