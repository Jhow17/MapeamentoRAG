---
title: "Securiti Settings release notes"
slug: "platform-release-notes"
updated: 2026-09-24T09:49:12Z
published: 2026-09-24T09:49:12Z
canonical: "helpcenter.securiti.ai/platform-release-notes"
area: platform
modulo: system-settings
tipo: release
data_captura: 2026-10-08
---

# Securiti Settings release notes

## 1.151

### Release updates - September 2026

#### Enforcing authenticator application MFA across your tenant

Securiti now lets you enforce an authenticator application as the sole multi-factor authentication (MFA) method for all users or for privileged users only. This closes the gap where an attacker with access to a user's mailbox could both reset the password and collect the MFA code from the same inbox. Previously, a tenant-wide MFA policy enforced email-based verification alone, and email MFA could not be turned off. You can now remove email verification entirely and enforce authenticator factor only.

For more information, see [Securing your Securiti account with multi-factor authentication](/latest/docs/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication).

#### Introducing new RBAC permissions for Sensitive Data Intelligence

Securiti has introduced new Role-Based Access Control (RBAC) permissions for AI Tuning of document types. These permissions let you control who can view and manage document type tuning sessions independently, without requiring access to broader AI Tuning configuration settings.

> [!NOTE]
> Note
> 
> To manually update or revert a document type classification for individual files, you must have the Update Unstructured Data permission.

Use the following table to understand the RBAC permissions for AI Tuning of document types:

| Permissions | Explanation | Dependent Permissions |
| --- | --- | --- |
| `Create Document Type AI Feedback` | Lets you submit AI tuning feedback for document types via in-product AI Tuning modal. | Sensitive Data Intelligence: - `View Document Type AI Feedback` - `View Document Type AI Tuning Settings` |
| `Delete Document Type AI Feedback` | Lets you delete document type AI tuning feedback entries on the **Tuning History** page. | Sensitive Data Intelligence: - `View Document Type AI Feedback` - `View Document Type AI Tuning Settings` |
| `View Document Type AI Feedback` | Lets you view document type AI tuning feedback entries on the **Tuning History** page. | Sensitive Data Intelligence: - `View Document Type AI Tuning Settings` |
| `Manage Document Type AI Tuning Settings` | Lets you manage access to the document type **Tuning Configuration** resource. | Sensitive Data Intelligence: - `View Document Type AI Tuning Settings` Securiti Platform: - `View Private Cloud Storage` |
| `View Document Type AI Tuning Settings` | Lets you view document type AI tuning configuration on the **Tuning Configuration** page. | No dependent permissions |

For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions-1).

#### Introducing new RBAC for Privacy Notice Management

Securiti has introduced new Role-Based Access Control (RBAC) v2 for Privacy Notice Management, moving from access profiles to fine-grained, role-based permissions. You can create custom roles with specific permissions that match users’ responsibilities, preventing unauthorized access to module features and actions.

With the new RBAC v2 framework, you can:

- Create custom roles with fine-grained, action-based permissions.
- Assign multiple roles to users or user groups based on their access and responsibilities.
- Control which users can view, create, edit, approve, publish, and manage privacy notices and templates.
- Control access to custom metadata with specific permissions to view, create, update, and upload custom metadata attachments.
- Grant read-only access to notices, custom metadata, fonts, settings, and templates without providing modification permissions.
- Provide administrative permissions to manage notice settings, module settings, templates, and approval workflows.
- Apply conditional permissions to restrict access to notices and templates based on whether a user is an owner or approver.

> [!NOTE]
> Note
> 
> - Certain RBAC permissions depend on other permissions. When you assign a permission to a user, Securiti automatically grants the dependent permissions.
> - You can also assign Privacy Notice Management roles and permissions to **Service Accounts**.

For more information, see [Privacy Notice Management RBAC permissions](/latest/docs/privacy-notice-management-rbac-permissions-and-roles-1).

#### Temporarily disabling the "Open the article" on the Help sidebar

Securiti has temporarily disabled the **Open the article** icon on the Help sidebar as a part of ongoing testing and improvements to the Help Center.

![Dashboard displaying DSR requests, resolution times, and calendar for tracking deadlines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-24 at 12.42.41 PM.png)

Previously, you could click this icon to open the full Help Center in a new tab outside the Help sidebar. While this icon is temporarily disabled, you can still access the Help Center in new tab using one of the following methods:

- Click on the main menu (jewel icon) and select **Help Center**.

![Dashboard displaying DSR requests, resolution time, and Help Center navigation options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-24 at 12.38.03 PM.png)
- From the module navigation side bar, click the **Help Center** icon and select the relevant option:

![Dashboard displaying DSR requests, progress, and help center options for user assistance.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-24 at 12.38.14 PM.png)
- Bookmark the following URL: [https://helpcenter.securiti.ai/](https://helpcenter.securiti.ai/)
  - Use the AI-powered search bar to ask questions and get quick answers.
  - Search by keyword to find the topic you need.

---

## 1.150

### Release updates - August 2026

#### Enhancing PCS migration audit logs and emails

Securiti has enhanced the System Settings audit log to show additional details for Private Cloud Storage (PCS) migration activities. It lets you trace and verify individual migration events more precisely. Each Migration event under PCS now includes:

- Source and destination storage ID
- Name and type
- Migration type

Securiti has also updated the migration status email to display the same source and destination storage details and the type of change made. This update improves migration traceability and helps administrators validate PCS related activities.

For more information, see [Using Private Cloud Storage page](/latest/docs/using-private-cloud-storage-page-en#audit-logs).

#### Introducing RBAC v2 for Assessment Automation, Vendor Assessment, and Risk Management

Securiti has introduced Role-Based Access Control (RBAC) v2 for Assessment Automation, Vendor Assessment, and Risk Management. This replaces hardcoded role checks with fine-grained, action-based permissions, so you can build custom roles scoped to exactly what each job needs. The new permissions cover assessment templates, questions, responses, and risk settings. Previously, only Access Profiles governed access to these modules. You can now select granular permissions for actions such as viewing, creating, or approving assessments and risks.

For more information, see [Assessment RBAC permissions](/latest/docs/rbac-permissions-with-custom-roles#accessing-the-permissions), [Vendor RBAC permissions](/latest/docs/rbac-permissions-with-custom-roles#vendor-assessment), and [Risk RBAC permissions](/latest/docs/rbac-permissions-with-custom-roles#risk-management).

---

## 1.149

### Release updates - August 2026

#### Permanently deleting partner users from Securiti

Securiti now lets you permanently delete partner users from your tenant. As with internal users, you must migrate the partner users' permissions and ownerships to another internal user. This gives administrators full control over the user lifecycle when a partner user no longer requires access to the tenant.

For more information, see [Deleting a user in Managing Securiti users](/latest/docs/configuring-access-management-managing-securiti-users).

#### Introducing User Group RBAC permissions

Securiti has introduced new Role-Based Access Control (RBAC) permissions for **User Groups** in System Settings. Securiti automatically applies the required User Group permissions to the custom role when you add the **Manage User Access** permission to it. This ensures users with Manage User Access can manage User Groups without requiring separate User Group permission configuration.

For more information, see [User Groups](/latest/docs/user-groups).

---

## 1.148

### Release updates - July 2026

No updates

---

## 1.147

### Release updates - June 2026

#### Introducing Help Center links for Apps in Navigation subsections

Securiti has introduced the Help Center option in the navigation menu to include dedicated subsections for each available resource within the application. You can now directly access the following documentation resources of any application or supporting Platform Service from the navigation menu without navigating through the Help Center landing page first:

- Documentation
- Release Notes
- Videos
- API Reference

This update makes it faster to find and access the specific resource you need regarding the application.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4IABZHLK.png)

For more information, see [Opening Securiti applications](/latest/docs/securiti-platform-opening-securiti-applications#edit-the-navigation-settings1).

#### Restricting API key creation for Partner users

Securiti has restricted Partner user types from creating or regenerating API keys in customer’s tenants. This enhancement reduces a security gap where these keys might grant persistent access to the platform. This could bypass the temporary session-based authentication used for partner access. To run automated workflows on a customer's behalf, you must use a Service Account and its own API key.

For more information, see [Managing Securiti API keys](/latest/docs/managing-credentials-managing-securiti-api-keys).
