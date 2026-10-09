---
title: "Security Posture Management RBAC permissions and roles"
slug: "security-posture-management-rbac-permissions-and-roles-1"
updated: 2026-10-05T08:01:31Z
published: 2026-10-05T08:01:31Z
canonical: "helpcenter.securiti.ai/security-posture-management-rbac-permissions-and-roles-1"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Security Posture Management RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Security Posture Management. It introduces a set of system-generated roles with predefined permissions, while also allowing you to create custom roles with Security Posture Management specific permissions. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control. In contrast, system-generated roles automatically inherit the specific permissions defined for them.

### Accessing Security Posture Management permissions

To navigate to Security Posture Management RBAC permissions in ​Securiti, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the ​**Jewel**​ icon, and choose ​**Settings**​​ from the left navigation bar. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(999).png)
2. Under the **​Organizational**​, choose ​**Access Management** > **Roles**​. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(1000).png)
3. On the ​**Roles**​ page, select ​**+Create Role​**.
4. Under the ​**Permissions**​ section, click the ​**Policy Engine** tab to access the permissions, as shown below.

![System settings interface showing roles and permissions for access management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/spm-rbac.png)

### Security Posture Management permissions with default roles

Security Posture Management permissions are part of the **Policy Engine** permission set. These include `View Security Posture Policies`, `Manage Security Posture Polices`, `View Posture Rule`, and `Manage Posture and Test Rule`. System-generated roles, such as Super Admin, Organization Admin, and Operator, automatically inherit a predefined set of these permissions.

To see which permissions each system-generated role has, see [Policy Engine permissions with default Roles](https://helpcenter.securiti.ai/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-default-roles).

### Security Posture Management permissions with custom roles

When you create a custom role, you can pick the Security Posture Management permissions from the **Policy Engine** tab. Some permissions have dependent permissions. When you select a parent permission, its dependent permissions are applied automatically, so the role has everything it needs for that action. For example, when you select **Manage Security Posture Policies**, **View Security Posture Policies** and **View Posture Rule** are applied too.

For the full list of Policy Engine permissions and their dependent permissions, see [Policy Engine permissions with custom roles](https://helpcenter.securiti.ai/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-custom-roles).
