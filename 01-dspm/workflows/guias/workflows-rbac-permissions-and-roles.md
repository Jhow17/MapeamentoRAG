---
title: "Workflows RBAC permissions and roles"
slug: "workflows-rbac-permissions-and-roles"
updated: 2026-09-29T13:50:50Z
published: 2026-09-29T13:50:50Z
canonical: "helpcenter.securiti.ai/workflows-rbac-permissions-and-roles"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Workflows RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Workflows. It introduces a set of system-generated roles with predefined permissions, while also allowing you to create custom roles with workflows–specific permissions. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control. In contrast, system-generated roles automatically inherit the specific permissions defined for them.

### Accessing Workflows permissions

To navigate to Workflows RBAC permissions in Securiti ​, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the ​**Jewel**​ icon, and choose ​**Settings**​​ from the left navigation bar. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(977).png)
2. Under the **​Organizational**​, choose ​**Access Management** > **Roles**​.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(978).png)
3. On the ​**Roles**​ page, select **+Create Role​**.
4. Under the ​**Permissions**​ section, click the ​**Workflows** tab to access the permissions, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(980).png)

### Workflows permissions with default roles

This table shows which data system permissions are allowed or disallowed for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Organization Admin | MODULE OWNER | DPO | USER | Operator | SDI Analyst | SDI Evidence Analyst | SDI Classification Reviewer | Discovery Scan Manager | Data Classification Manager | Gencore Reader | Provider Manager | Firewall Admin | Gencore Pipe Builder | Gencore Admin | MODULE OWNER Data Breach User Profile ROLE | MODULE OWNER Self Service Portal User Profile ROLE | GUEST Self Service Portal User Profile ROLE | MODULE OWNER Data map User Profile ROLE | USER DSR User Profile ROLE | DATA USER | GUEST Data map User Profile ROLE | USER Data map User Profile ROLE | USER Self Service Portal User Profile ROLE | MODULE OWNER DSR User Profile ROLE | GUEST DSR User Profile ROLE |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Manage Workflow Bundle` | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Workflow Bundle` | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Owned Workflows` | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Owned Workflows` | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

### Workflows permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create in the Platform.

**Permission:** It is a parent permission that grants specific rights to perform certain actions within the system. For example, `Manage Workflow Bundle` , and `View Workflow Bundle`.

**Explanation:** Describes why the permission is needed and the context in which it is used. For example, the “Manage Workflow Bundle” permission is required to manage workflow.

**Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Workflows permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permissions | Explanation | Dependent Permissions |
| --- | --- | --- |
| `Manage Workflow Bundle` | Permission to create, edit, activate, and delete workflows, regardless of owner | Securiti **Platform:** - [Delete From Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) - [View Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) |
| `View Workflow Bundle` | Permission to view workflows | Securiti **Platform:** - [View Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) |
| `View Owned Workflows` | Permission to view workflows (Owned by user) | Securiti **Platform:** - [View Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) |
| `Manage Owned Workflows` | Permission to manage owned workflows (Owned by user) | Securiti **Platform:** - [View Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) - [Delete From Private Cloud Storage](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-default-roles) |
