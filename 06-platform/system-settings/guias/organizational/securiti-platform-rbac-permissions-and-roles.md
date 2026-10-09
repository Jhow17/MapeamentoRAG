---
title: "Securiti Platform RBAC permissions and roles"
slug: "securiti-platform-rbac-permissions-and-roles"
status: "new"
updated: 2026-09-22T09:47:32Z
published: 2026-09-22T09:47:32Z
canonical: "helpcenter.securiti.ai/securiti-platform-rbac-permissions-and-roles"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Securiti Platform RBAC permissions and roles

Securiti provides an RBAC framework to manage user permissions. In the Platform module, these permissions control access to Securiti Platform-related functionalities. The fine-grained permissions provide access control from viewing the details of Securiti Platform.

RBAC includes both default roles and custom roles. You can assign a default role to a user or create a custom role with specific permissions. Each default role contains a predefined set of permissions.

## Accessing Deployment permissions

To navigate to Securiti Platform RBAC permissions, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Settings** from the left navigation bar.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-2euwd1iq.png)

1. Under the **Organizational**, choose **Access Management > Roles**.
2. On the **Roles** page, select **+ Create Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-lin49x8e.png)

1. Under the **Permissions** section, click the **Platform** tab to access the Deployment permissions, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CZEDY7YQ.png)

## Securiti Platform permissions with default roles

This table shows which data system permissions are allowed or disallowed for each system-generated role. A check mark(✅) indicates allowed access, while a cross (❌) represents no access.

| **Permission** | **Super Admin** | **Operator** | **DPO** | **Organization Admin** | **MODULE OWNER** | **USER** | **Data Classification Manager** | **SDI Evidence Analyst** | SDI Analyst | **SDI Classification Reviewer** | **Discovery Scan Manager** | **Gencore Admin** | **Gencore Pipe Builder** | **Gencore Reader** | **MODULE OWNER Self Service Portal User Profile ROLE** | **GUEST Self Service Portal User Profile ROLE** | **MODULE OWNER Data map User Profile ROLE** | **USER DSR User Profile ROLE** | **MODULE OWNER Data Breach User Profile ROLE** | **DATA USER** | **GUEST Data map User Profile ROLE** | **USER Data map User Profile ROLE** | **USER Self Service Portal User Profile ROLE** | **MODULE OWNER DSR User Profile ROLE** | **GUEST DSR User Profile ROLE** | **Provider Manager** | **Firewall Admin** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Manage Security Settings` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Tenant Settings` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Assessment Audit Logs` | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Disable Other User's MFA` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Audit Log Page` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Saved Filter` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Saved Filter` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Saved Filter` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Roles` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Roles` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Roles Access` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Roles` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Roles List Page` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Hosting Loc Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Email Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Email Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Email Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Email Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Private Cloud Storage` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Private Cloud Storage` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Custom Mail Identity` | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Custom Mail Identity` | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Custom Mail Identity` | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Custom Mail Identity` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Tenant Support Account` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Tenant Support Account` | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete From Private Cloud Storage` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Webhook` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Webhook` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Webhook` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Webhook` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View All Org Users` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage User Access` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Reassign User Resource` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Import Users` | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Users List Page` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Configure Message Digest For All` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Change User Status` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Unlock User` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Users` | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

## Securiti Platform permissions with custom roles

This table lists the Securiti Platform permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Manage Security Settings` | This permission lets you manage and view login settings, trusted devices, IP restriction and masking, and audit logs under Settings > Security. | **Securiti Platform** - `View audit logs page` **Settings** - [Update Ip Allowlist Config](/latest/docs/system-settings-rbac-permissions-and-roles#deployment-permissions-with-custom-roles1) - [Read Ip Allowlist Config](/latest/docs/system-settings-rbac-permissions-and-roles#deployment-permissions-with-custom-roles1) |
| `Update Webhook` | This permission lets you update the webhooks details. | No permission |
| `Read Webhook` | This permission lets you read the webhook details. | No permission |
| `Create Webhook` | This permission lets you create a new webhook. | No permission |
| `Delete Webhook` | This permission lets you delete the webhook. | No permission |
| `Read Custom Mail Identity` | This permission lets you view the custom mail identity. | No permission |
| `Create Custom Mail Identity` | This permission lets you create the custom mail identity. | No permission |
| `Delete Custom Mail Identity` | This permission lets you delete the custom mail identity. | No permission |
| `Update Custom Mail Identity` | This permission lets you update the existing custom mail identity. | No permission |
| `Configure message digest for all` | This permission lets you configure the message digest algorithm for signing or verification. | No permission |
| `Read Service Account` | This permission lets you view service account details, credentials, and access history. | No permission |
| `Create Users` | This permission lets you create users. | **Securiti Platform** - `View users list page` |
| `View All Org Users` | This permission lets you view all the users or organization. | No permission |
| `Import Users` | This permission lets you import users through a CSV file. | **Securiti Platform** - `View users list page` |
| `Change User Status` | This permission lets you change a user’s status to active, deactivated, or guest. | **Securiti Platform** - `Reassign User Resources` - `View users list page` |
| `Reassign User Resource` | This permission lets you reassign resources when changing a user to guest or deactivating them. | No permission |
| `View users list page` | This permission lets you view the users list page. | No permission |
| `Manage User Access` | This permission lets you manage all actions under: - **Settings > Organizational > Access Management > Users** - **Settings > Organizational > Access Management > Roles** - **Settings > Organizational > Access Management > User Groups** | **Securiti Platform** - `Configure message digest for all` - `Update User Reset Password` - `Change User Status` - `Import Users` - `Unlock User` - `Reassign User Resource` - `Create Users` - `View users list page` - `Manage Roles Access` - `Create roles` - `Delete roles` - `Update roles` - `View roles list page` |
| `Unlock User` | This permission lets you unlock a user who is locked due to invalid login attempts. | **Securiti Platform** - `View users list page` |
| `Read Tenant Support Account` | This permission lets you read Tenant Support Account resources. | No permission |
| `Manage Tenant Support Account` | This permission lets you view and modify Support Access configurations for the tenant under **Settings > Support > Support Access**. | **Securiti Platform** - `Read Tenant Support Account` |
| `Manage Tenant Settings` | This permission lets you view and modify General Settings under **Settings > Organizational > General and Support Access configurations under Settings > Support > Support Access**. | **Securiti Platform** - `Read Tenant Support Account` - `Manage Tenant Support Account` |
| `Update User Reset Password` | This permission lets you update the user details and reset the password. | **Securiti Platform** - `View users list page` |
| `Read Email Template` | This permission lets you view all email template resources. | No permission |
| `Create Email Template` | This permission lets you create a new email template. | No permission |
| `Delete Email Template` | This permission lets you delete the email template. | No permission |
| `Update Email Template` | This permission lets you update the email template details. | No permission |
| `Read Hosting Loc Metadata` | This permission lets you read the Hosting Loc metadata. | No permission |
| `View Private Cloud Storage` | This permission lets you view private cloud storage configuration. | No permission |
| `Manage Private Cloud Storage` | This permission lets you manage private cloud storage configuration. | **Securiti Platform** - `View PCS` |
| `Delete From Private Cloud Storage` | This permission lets you delete the data from the private cloud storage. | No permission |
| `Create roles` | This permission lets you create roles under **Settings > Organizational > Access Management > Roles**. | **Securiti Platform** - `View roles list page` |
| `Delete roles` | This permission lets you delete roles under **Settings > Organizational > Access Management > Roles**. | **Securiti Platform** - `View roles list page` |
| `Update roles` | This permission lets you update roles under **Settings > Organizational > Access Management > Roles**. | **Securiti Platform** - `View roles list page` |
| `View roles list page` | This permission lets you view the roles list page. | No permission |
| `Manage Roles Access` | This permission lets you view and manage roles under **Settings > Organizational > Access Management > Roles**. | **Securiti Platform** - `Create roles` - `Delete roles` - `Update roles` - `View roles list page` |
| `View Assessment Audit Logs` | This permission lets you view the audit logs of performed assessments. | No permission |
| `View audit logs page` | This permission lets you view the Audit Logs page. | No permission |
| `Disable Other User's MFA` | This permission lets you disable the multi-factor authentication for other users. | **Securiti Platform** - `View users list page` |
| `Create Saved Filter` | This permission lets you create a Saved Filter resource. | **Securiti Platform** - `Delete Saved Filter` - `Update Saved Filter` |
| `Delete Saved Filter` | This permission lets you delete saved filters. | **Securiti Platform** - `Update Saved Filter` |
| `Update Saved Filter` | This permission lets you update saved filters. | No permission |
