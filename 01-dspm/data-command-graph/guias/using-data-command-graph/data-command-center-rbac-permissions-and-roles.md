---
title: "Data Command Center RBAC permissions and roles"
slug: "data-command-center-rbac-permissions-and-roles"
updated: 2026-09-20T21:20:56Z
published: 2026-09-20T21:20:56Z
canonical: "helpcenter.securiti.ai/data-command-center-rbac-permissions-and-roles"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Data Command Center RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Data Command Center. It introduces a set of system-generated roles with predefined permissions, while also allowing you to create custom roles with Graph or Reporting–specific permissions. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control. In contrast, system-generated roles automatically inherit the specific permissions defined for them.

- [Accessing Data Command Center permissions](/v1/docs/data-command-center-rbac-permissions-and-roles#accessing-data-command-center-permissions)
- [Data Command Center permissions with default Roles](/v1/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-default-roles)
- [Data Command Center permissions with custom roles](/v1/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles)

### Accessing Data Command Center permissions

To navigate to Data Command Center RBAC permissions in ​Securiti, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the ​**Jewel**​ icon, and choose ​**Settings**​​ from the left navigation bar. ![Settings page displaying organization information and advanced invite controls options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/settings_nav.png)
2. Under the **​Organizational**​, choose ​**Access Management** > **Roles**​. ![System settings display roles with details like role type and user count.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Roles in Access Management(2).png)
3. On the ​**Roles**​ page, select ​**+ Create Role​**.
4. Under the ​**Permissions**​ section, click the **​Data Command Center** tab to access the permissions, as shown below. ![System settings interface showing permissions for various roles and options available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcc_permissions.png)

### Data Command Center permissions with default Roles

This table shows which permissions are allowed or restricted for each default role. A tick (✔) indicates allowed access, while a cross (✖) represents disallowed access.

| **Permission** | **Super Admin** | **Operator** | **DPO** | **Organization Admin** | **MODULE OWNER** | **USER** |
| --- | --- | --- | --- | --- | --- | --- |
| View Graph Explorer Page | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| View Inventory Page | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| View Reporting and Dashboards | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Manage Reporting and Dashboards | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

### Data Command Center permissions with custom roles

Securiti lets you select fine-grained permission for each custom role you create in the Platform.

**Permission:** It is a parent permission that grants specific rights to perform certain actions within the system. For example, `View Graph Explorer Page`.

**Explanation:** Describes why the permission is needed and the context in which it is used. For example, `Manage Reporting and Dashboards` permission is required to create and edit a dashboard.

**Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Data Command Center permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `View Graph Explorer Page` | This permission lets you view the Graph Explorer page and perform the following actions: - Write queries - Filter queries - Select views - Save queries - Create widgets and dashboards - Export CSVs for query results | **Securiti Platform**: - [Create Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) - [Update Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) - [Delete Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) |
| `View Inventory Page` | This permission lets you view the Inventory page and perform the following actions: - Filter entities - Select views - Save queries | **Securiti Platform**: - [Create Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) - [Update Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) - [Delete Saved Filter](/latest/docs/rbac-permissions-with-default-roles#data-command-center-rbac-permissions-with-default-roles) |
| `View Reporting and Dashboards` | This permission lets you view both system and custom dashboards shared with you, and perform the following actions: - Refresh dashboard widgets - Sort dashboards and groups - Mark a dashboard as default - Generate and schedule reports | No dependent permission |
| `Manage Reporting and Dashboards` | This permission lets you view both system and custom dashboards shared with you, and perform the following actions: - Create custom dashboards - Edit custom dashboards - Share custom dashboards - Delete custom dashboards - Create widgets - Generate, share, and schedule reports - Manage dashboard groups - Clone dashboards - Copy widgets from another dashboards - Add rich text widgets - Change the dashboard owner and transfer ownership | `View Reporting and Dashboards` |
