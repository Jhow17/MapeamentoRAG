---
title: "Configuring Securiti general settings"
slug: "system-settings-configuring-securiti-general-settings"
status: "update"
updated: 2026-09-24T12:06:28Z
published: 2026-09-24T12:06:28Z
canonical: "helpcenter.securiti.ai/system-settings-configuring-securiti-general-settings"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring Securiti general settings

1. In Securiti, click **Settings**, then choose **Organizational > General**.
2. Near the upper right corner of the page, click **Edit** (pencil icon).
3. Configure the following settings to suit:

| Field | Description |
| --- | --- |
| Organization Name | Enter your organization name. This name appears to all users. |
| Primary domain | Your primary domain, set during signup, is auto-populated here and you cannot edit it. Securiti uses it to identify internal users by matching the domain. |
| Secondary Domain(s) | Enter your secondary domain to let Securiti identify internal users when you have multiple domains. Use the tools to [add secondary domains](/v1/docs/adding-secondary-domains). |
| Tenant | The value is a unique identifier for your tenant. Use it to make API calls with **X-TIDENT** header. |
| Organization Address | Enter your organization's physical address. |
| Advanced Invite Controls | Enable Advanced Invite control to restrict guest users from sharing invites for accessing assigned resources. This includes sending a 6-digit verification code to guests, who must use it to confirm their identity before accessing assigned assessments, DSR subtasks, data mapping assets, etc. The verification code expires 5 minutes after Securiti sends it. > [!NOTE] > **Note** > > This option remains disabled by default. Enabling it applies to all organizations within the tenant. Enabling this setting affects various workflows in different modules, such as: - Guest users accessing SSP via magic link - Guest users accessing assigned DSR Subtasks - Guest users accessing assigned Data Mapping assets - Guest users accessing assessments > [!NOTE] > **Note** > > For Securiti to redirect the Guest User to the SSO login, you must configure SSO redirect for your domain and enable Advanced Invite Controls in Securiti Settings. Otherwise, Securiti continues to send them magic links. Observe these caveats for Assessments: \| Advanced Invite Controls \| SSO Enabled \| Guest User is Redirected to \| \| --- \| --- \| --- \| \| Enabled \| Enabled \| SSO Login page \| \| Enabled \| Disabled \| OTP page \| \| Disabled \| Enabled \| Assessment directly \| \| Disabled \| Disabled \| Assessment directly \| |
| Advanced Invite Controls | SSO Enabled | Guest User is Redirected to |
| Enabled | Enabled | SSO Login page |
| Enabled | Disabled | OTP page |
| Disabled | Enabled | Assessment directly |
| Disabled | Disabled | Assessment directly |
| Default Homepage | If you are using New Navigation, change the default landing homepage so that it redirects you to when you log in to the platform. To update the default homepage, proceed with the following steps. 1. Under the **Default Homepage** area, click **Change Homepage**. It opens **Set Your Default Homepage** popup covering the whole page. 2. Choose any platform services or application as the default landing page. On the right side of the platform service or application name, click the home icon. 3. Once done, click **Set Homepae & Continue**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Change_Default_homepage_generalsettings.png) It sets the selected page as new default page and displays the **General Settings** page again. For more information regarding New Navigation, see [Opening Securiti applications](/latest/docs/securiti-platform-opening-securiti-applications). |
| Admin Contact Email & Phone | Enter the administrator contact details to which users can contact. It includes: - Email - Phone |
| Securiti Contact | Enter the contact details for the Securiti team to contact and announce security incidents and breaches. It includes: - Email - Phone number - Language (that Securiti defaults to for new users who have not set their language yet, as described in [Managing your Securiti user profile](/v1/docs/managing-your-securiti-user-profile). |
| Idle User Session Timeout | Set the idle session timeout duration for all users. This forces users to log out automatically if the application is idle for a specific time duration set by the administrator. However, users with access to modify the general settings can update the time of their account, which doesn’t affect other accounts. To enforce the idle session timeout for all tenant users, which doesn’t let any users modify it except tenant administrators, enable **Enforce Session Timeout** for all users. It sets a session timeout for the tenant, and users can not modify it. |
| Audit log Retention | Set the time duration to retain audit logs for this tenant. This lets you store logs automatically for the defined period, which some audits might require. |
| Enforce Signed Headers For Evidence Validation | Enable the toggle to generate a random value used in the signed headers of the URLs used for evidence retrieval. When enabled: - Securiti validates evidence access using signed headers. - Direct browser downloads from PCS are blocked. - Only in-application validation is permitted. If you attempt to download evidence while signed headers are enforced, Securiti displays a message indicating that download is incompatible with Private Cloud Storage when signed headers are enabled. To enable direct downloads, you must disable signed headers. |
| Evidence Download | Enable the toggle to access evidence files from scans when needed. You cannot download the files if disabled. |
| Default Export Settings | Choose the default export file format for all users. The supported options are: - .GZ - .Zip |
| Organization Logo | Click **Change Logo** and use the tools to upload a logo. Choose a PNG (preferred), GIF, or JPG file ranging in size from 96 x 96 to 480 x 480 pixels. |
| Advanced Settings | Click **Delete your tenant** to delete your Securiti tenant and all of the data associated with it. Do this only if you are absolutely sure you do not want to use Securiti again. |

1. When you are done, near the upper right corner of the page click **Save**.

In Securiti, an organization is a functional grouping that lets some group within your company to have their own Securiti account, separate from the Securiti accounts of all other organizations within your Securiti tenant, each with its own set of Securiti elements. For example, each organization has its own data systems and connectors, its own assessments, its own DSR forms and DSR requests, its own workflows, and its own data maps and data catalog.

A user who has not been registered in the tenant or does not have access to the current assessment organization. Also, referred to as a non-system user.

Data elements are associated with different languages that depend on different global localities. Securiti is continuously adding support for different languages for the detection/classification of sensitive data.

The log that Securiti maintains of all actions taken by various users, and by the Securiti system. Different users have different levels of access to the audit log. For users of type Super Admin, DPO, and Operator, the audit log shows all log entries. For users of type User or Module Owner, the audit log only shows log entries directly related to the user and their activities.

## Related

- [Adding secondary domains](/system-settings-adding-secondary-domains.md)
- [Adding admin and security contact emails and phone numbers](/configuring-securiti-general-settingsadding-admin-and-security-contact-emails-and-phone-numbers.md)
- [Managing organizations](/system-settings-managing-organizations.md)
