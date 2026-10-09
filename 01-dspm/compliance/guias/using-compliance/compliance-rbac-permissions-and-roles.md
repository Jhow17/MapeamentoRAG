---
title: "Compliance RBAC permissions and roles"
slug: "compliance-rbac-permissions-and-roles"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/compliance-rbac-permissions-and-roles"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Compliance RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Compliance. It lets you create custom roles with specific permissions. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control. In contrast, system-generated roles automatically inherit the specific permissions defined for them.

#### Accessing Compliance permissions

To access the Compliance RBAC permissions in Securiti Platform, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Settings** from the left navigation bar.

![2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c016091-9ca2-ee04-c8c9-aa229411285e.png)
2. Under the **Organizational**, choose **Access Management > Roles**.

![3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9bcd46fb-3f27-bc1c-d1ba-68e450ae6391.png)
3. On the top right of the **Roles** page, click **+ Create Role**.

![4A.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e873b23d-de51-83ea-bba4-9825a3dfac26.png)
4. On the **Create Role** page under the **Permissions** section, click the Compliance tab to access the permissions, as shown below.

![5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d1deccb-d463-7182-3a6e-a51af884efb0.png)

#### Compliance permissions with default roles

This table shows which compliance permissions are allowed or disallowed for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | **Super Admin** | **Operator** | **DPO** | **Organization Admin** | **MODULE OWNER** | **USER** | **Data Classification Manager** | **SDI Evidence Analyst** | SDI Analyst | **SDI Classification Reviewer** | **Discovery Scan Manager** | Gencore Admin | Provider Manager | Firewall Admin | Gencore Pipe Builder | Gencore Reader | **MODULE OWNER Self Service Portal User Profile ROLE** | **GUEST Self Service Portal User Profile ROLE** | **MODULE OWNER Data map User Profile ROLE** | **USER DSR User Profile ROLE** | **MODULE OWNER Data Breach User Profile ROLE** | **DATA USER** | **GUEST Data map User Profile ROLE** | **USER Data map User Profile ROLE** | **USER Self Service Portal User Profile ROLE** | **MODULE OWNER DSR User Profile ROLE** | **GUEST DSR User Profile ROLE** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `View Compliance` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manag Compliance` | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

#### Compliance permissions with custom roles

Securiti lets you select fine-grained permission for each custom role you create in the Platform.

**Definitions**

- **Permission**: It is a parent permission that grants specific rights to perform certain actions within the system. For example, `Manage Compliance`
- **Explanation:** Explains why the permission is needed and in which context it is used. Examples: The “Manage Compliance” permission is required to provide full administrative control over compliance projects, controls, tests, and frameworks in a unified bundle.
- **Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Compliance permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | **Dependent permissions** |
| --- | --- | --- |
| `View Compliance` | This permission lets you view compliance projects, controls, tests, test findings, and frameworks in a consolidated manner. It is restricted to view-only access, including: - Read compliance projects - Read compliance controls - Read compliance tests - Read test findings - Read compliance frameworks The View Compliance permission depends on Securiti Platform and Data Command Center. | **Securiti** **Platform**: - [Create Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) **Data Command Center**: - [View Graph Explorer Page](/latest/docs/graph-reporting-dashboards-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) **Sensitive Data Intelligence**: - [View Tests](/latest/docs/sensitive-data-intelligence-roles-and-permissions#policies-findings-permissions-with-custom-roles) |
| `Manage Compliance` | This permission lets you manage complete compliance bundle with full administrative control. It grants complete authority across projects, controls, tests, test findings, and frameworks in a unified bundle, including: - Read, create, update, and delete compliance projects - Read, create, update, and delete compliance controls - Read, create, update, and delete compliance tests - Read test findings and update ownership of findings - Read, create, update, and delete compliance frameworks The Manage Compliance permission depends on Securiti Platform and Data Command Center. | **Securiti** **Platform**: - [Create Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/platform-rbac-permissions-and-roles#securiti-permissions-with-custom-roles) **Data Command Center**: - [View Graph Explorer Page](/latest/docs/graph-reporting-dashboards-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) **Sensitive Data Intelligence**: - [View Tests](/latest/docs/sensitive-data-intelligence-roles-and-permissions#policies-findings-permissions-with-custom-roles) - [Manage Tests](/latest/docs/sensitive-data-intelligence-roles-and-permissions#policies-findings-permissions-with-custom-roles) |

## Related

- [Using the Compliance dashboard](/using-the-compliance-dashboard.md)
