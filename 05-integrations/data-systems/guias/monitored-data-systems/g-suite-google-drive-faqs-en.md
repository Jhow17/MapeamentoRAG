---
title: "Google Drive (Google Workspace) FAQs"
slug: "g-suite-google-drive-faqs-en"
updated: 2026-07-14T03:37:48Z
published: 2026-07-14T03:37:48Z
canonical: "helpcenter.securiti.ai/g-suite-google-drive-faqs-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Drive (Google Workspace) FAQs

This article answers frequently asked questions about the Google Drive (Google Workspace) connector.

### Authentication and credentials

This section covers the FAQs related to Google Drive (Google Workspace) authentication and activation credentials.

****Why can a Service Account email address not be used to activate the connector?****

Service accounts are fundamentally different from user accounts. They exist outside your Google Workspace domain and, for security reasons, have no default access to user data, documents, or calendar events. For more information, see [Google’s documentation on service accounts](https://docs.cloud.google.com/iam/docs/service-account-overview).

To grant the necessary access, a Google Workspace administrator must implement domain-wide delegation. This process authorizes the service account to act on behalf of users, allowing the connector to function correctly.

****If you are not using a Google Workspace admin account with super admin permissions to set up the Google Drive connector, do you need to create a separate service account?****

If you do not want to use a super admin account, create a custom admin role and assign it to a regular user. The service account impersonates this user (super admin or custom admin) when connecting to Google Drive.

****How are sensitivity labels fetched for Google Drive files?****

Securiti fetches and ingests the sensitivity labels applied across Google Drive (Google Workspace) files during the Data Inventory Sync. The ingested labels can be viewed under the **Scanned Classification Label** entity in Securiti's Graph Explorer.

These labels are ingested for the self-hosted connector only, and you must fulfil the following prerequisites to enable successful ingestion of labels:

- Provide the necessary permissions in the Google Drive (Google Workspace) application, as described in Enabling APIs in a project and Assigning scopes and permissions.
- Mark the **Allow Data Labeling Policy Integration** checkbox in the **Permissions** tab.

****What is Domain-Wide Delegation (DWD), and where is it enabled?****

Domain-Wide Delegation (DWD) lets a service account act on behalf of users in your domain without requiring individual user consent.

You enable DWD in the **Google Admin console** under **Security > Access and data control > API controls > Manage Domain-Wide Delegation**.

****Does Domain-Wide Delegation let the application read everyone’s data?****

No, Domain-Wide Delegation (DWD) lets a service account impersonate users across the domain, but access is still controlled by the following:

- OAuth scopes that you authorize for the client in DWD
- Admin privileges held by the impersonated user account

DWD authorizes domain-wide impersonation. Actual data access is still bounded by the scopes you grant and the privileges of the impersonated user, and Drive content remains governed by item-level permissions.

For more information, see [Google's documentation on impersonation](https://developers.google.com/identity/protocols/oauth2/service-account#important-security-consideration:-understanding-impersonation).

****Is a service account with Domain-wide Delegation required for domain-wide Google Drive access?****

Yes. Google supports domain-wide automation only via a service account with Domain-wide Delegation (DWD), where the service account impersonates each user. Per-user OAuth authorizes only the consenting user’s content and cannot provide tenant-wide coverage. Securiti implements the DWD model and does not support per-user OAuth for the Google Drive connector.

If service accounts are disabled, such as “An Organization Policy that blocks service accounts key creation has been enforced on your organization”, then there is no alternative path to fetch and scan every user’s My Drive and shared drives.

****Can I activate the connector without a service account and still access all users’ Drive data?****

No, there is no single authorization or token that grants tenant-wide access. With DWD, the connector requests a delegated identity per user and can access only what that user is permitted to see. For Shared drives, admins can centrally view and manage shared drives, but reading files still requires the connector’s identity to be a member or have the appropriate permissions on each drive.

****Google Drive connector activation only asks for one admin email. Does the connector scan only that account’s My Drive?****

No, the said email is the delegated Workspace user with the required Admin console role (custom admin role or Super Admin). Using that admin email, the connector impersonates all users scoped in the scan from Google Directory and does not limit scanning to the admin’s **My Drive**.

****What is the difference between OAuth scopes and Admin privileges?****

OAuth scopes define which Google APIs the application calls, such as read Drive metadata, list users, or fetch audit logs. Scopes are configured in the **Google Admin console** under **Security > Access and data control > API controls > Manage Domain-Wide Delegation**.

Admin privileges define what the impersonated user is permitted to do inside those APIs, such as whether they can read user lists, organizational units, or apply labels. Privileges are configured in the **Google Admin console** under **Account> Admin roles**.

Both scopes and privileges are required for your connector. The application cannot reach the API without scopes, and the API calls fail despite being available, without the privileges.

****Where do I add OAuth scopes for my application?****

You can add the OAuth scopes in the Admin console on the DWD page under **Security > Access and data control > API controls > Manage Domain-Wide Delegation > Add new**.

Enter your OAuth client ID and paste the required scope list. This action requires a Super Admin user account.

****Which account needs Admin privileges, and where do I configure them?****

You must assign Admin privileges to the Google Workspace user you impersonate, and not the service account. Configure in **Admin console > Account > Admin roles** using a custom role or Super Admin.

****Do I need both scopes and admin roles for discovery scans, labeling, or posture scanning?****

Yes, scopes let the application call specific APIs, while Admin roles determine what the impersonated user is permitted to do with those APIs. Both are required, and having only one results in insufficient permissions.

****Can I perform discovery scans, Data inventory sync, posture scans, or data labeling in Securiti without an Admin console role for the delegated (impersonated) user?****

No, all Securiti modules depend on APIs that are considered administrator-only. In addition to granting OAuth scopes in Domain-Wide Delegation, the impersonated user must have an Admin console role with the required privileges.

This can be either a custom admin role scoped to the exact privileges needed or a Super Admin role.

**Examples of required privileges for a custom admin role:**

- Discovery scan or Data Inventory Sync: Admin SDK Directory, such as Groups > Read, Organizational Units > Read
  - Shared drives: Domain-level administration and membership management (Drive and Docs admin)
- Posture Scan: Reports or Security Center, such as Audit & Investigation privileges
- Data Labeling Policy: Drive Labels and Drive item-metadata operations (role must permit managing or applying labels)

For more information, see [Using custom role for non-admin users](/latest/docs/using-custom-role-for-non-admin-users) and [Prerequisites for Google Drive (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive).

****Do scopes change if the impersonated user is a Super Admin?****

No, scopes are granted to the OAuth client in Domain-Wide Delegation. A Super Admin only affects privileges, not the set of scopes your application can use.

****Can I access each user’s My Drive without impersonating them?****

No, Google Drive enforces item permissions. To read a user’s **My Drive**, impersonate that specific user via Domain-Wide Delegation and call the Drive API with the appropriate scopes.

****Can I configure everything in the Google Cloud console?****

No, create the service account and enable APIs in the Google Cloud console. Also, add DWD and scopes, and assign Admin roles or privileges in the Admin console.

****Do I assign admin roles to the service account?****

No, admin roles are assigned to the user account you impersonate, not the service account. The service account is only authorized through Domain-Wide Delegation.

****Is an OAuth consent screen involved for service-account DWD?****

No, end users never see a consent screen. A Super Admin authorizes the OAuth client and its scopes centrally in the Admin console.

### Discovery scan and limitations

This section covers the FAQs related to Google Drive (Google Workspace) Discovery scan and its limitations.

****Does Securiti include cloud native files in Google Workspace, such as Google Docs and Google Slides, when scanning Google Drive?****

Yes. Google Docs and Google Slides are integral components of the Google Drive ecosystem. Since these files are automatically stored and managed within Google Drive, Securiti includes them in the scanning process when you scan your Google Drive data.

****Why is the** `Move any file or folder into shared drives` **permission under Settings privilege required for read-only Google Workspace discovery scans?**?**

Securiti performs strictly read-only discovery scans and does not move or modify any files. However, to scan data across the entire Google Workspace domain (including all shared drives), we use the Google Drive API with `useDomainAdminAccess=true` parameter.

When `useDomainAdminAccess=true` parameter is enabled, it requires administrator-level privileges. In Google Workspace, these privileges are bundled under the **Drive & Docs** > **Settings** privilege group, which includes the “Move any file or folder into shared drives” permission. You must mark the **Settings** privilege checkbox otherwise the request fails with an error indicating that the user does not have sufficient administrator privileges.

Google does not provide a way to enable only read-only access for this level of domain-wide shared drive enumeration. Therefore, this permission is required solely to satisfy Google’s API authorization model, not because Securiti performs any file movement.

For more information, see [Google documentation](https://developers.google.com/workspace/drive/api/guides/manage-shareddrives#list-shared-drives).
