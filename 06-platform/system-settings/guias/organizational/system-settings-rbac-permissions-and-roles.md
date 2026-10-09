---
title: "System Settings RBAC permissions and roles"
slug: "system-settings-rbac-permissions-and-roles"
status: "new"
updated: 2026-09-22T09:47:50Z
published: 2026-09-22T09:47:50Z
canonical: "helpcenter.securiti.ai/system-settings-rbac-permissions-and-roles"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# System Settings RBAC permissions and roles

Securiti provides an RBAC framework to manage user permissions. In the System Settings module, these permissions control access to Securiti-related functionalities. The fine-grained permissions provide access control related to Securiti settings.

RBAC includes both default roles and custom roles. You can assign a default role to a user or create a custom role with specific permissions. Each default role contains a predefined set of permissions from the System Settings.

## Accessing System Settings permissions

To navigate to Deployment RBAC permissions in Securiti Platform, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Settings** from the left navigation bar.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-2euwd1iq.png)

1. Under the **Organizational**, choose **Access Management > Roles**.
2. On the **Roles** page, select **+ Create Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-lin49x8e.png)

1. Under the **Permissions** section, click the **Settings** tab to access the Deployment permissions, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-11W48DS4.png)

## Deployment permissions with default roles

This table shows which data system permissions are allowed or disallowed for each system-generated role. A check mark(✅) indicates allowed access, while a cross (❌) represents no access.

| **Permission** | **Super Admin** | **Operator** | **DPO** | **Organization Admin** | **MODULE OWNER** | **USER** | **Data Classification Manager** | **SDI Evidence Analyst** | SDI Analyst | **SDI Classification Reviewer** | **Discovery Scan Manager** | **MODULE OWNER Self Service Portal User Profile ROLE** | **GUEST Self Service Portal User Profile ROLE** | **MODULE OWNER Data map User Profile ROLE** | **USER DSR User Profile ROLE** | **MODULE OWNER Data Breach User Profile ROLE** | **DATA USER** | **GUEST Data map User Profile ROLE** | **USER Data map User Profile ROLE** | **USER Self Service Portal User Profile ROLE** | **MODULE OWNER DSR User Profile ROLE** | **GUEST DSR User Profile ROLE** | **Gencore Admin** | **Provider Manager** | **Firewall Admin** | **Gencore Pipe Builder** | **Gencore Reader** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Create Service Account API Key` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Organizations` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read IP Allow-List Config` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update IP Allow-List Config` | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Service Accounts` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Service Account` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

## Deployment permissions with Custom roles

This table lists the System Settings permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Create Service Account API Key` | This permission allows the user to create API keys under **Settings > Integrations > Credentials > API Keys**. | No dependent permission |
| `Manage Organizations` | This permission allows the user to view and manage organizations. | No dependent permission |
| `Read IP Allow-List Config` | This permission allows the user to read the IP allowlist configuration for the tenant under **Settings > Security > IP Restriction > Masking**. | No dependent permission |
| `Update IP Allow-List Config` | This permission allows the user to update the IP allowlist configuration for the tenant under **Settings > Security > IP Restriction > Masking**. | No dependent permission |
| `Manage Service Account` | This permission lets you view and manage organizations. | **Settings** - `View Service Account` - `Create Service Account API Key` |
| `View Service Accounts` | This permission lets you view the Service Account. | No dependent permission |
