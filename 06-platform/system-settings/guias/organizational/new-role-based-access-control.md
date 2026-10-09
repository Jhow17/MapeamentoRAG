---
title: "New Role-Based Access Control RBAC"
slug: "new-role-based-access-control"
updated: 2026-09-29T09:53:01Z
published: 2026-09-29T09:53:34Z
canonical: "helpcenter.securiti.ai/new-role-based-access-control"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# New Role-Based Access Control RBAC

## Scenario

As a Data Governance Officer, you’re responsible for ensuring that only the right people access the right data. Manually managing user permissions was time-consuming and often led to over-permissioning. With Securiti’s Role-Based Access Control (RBAC), you define fine-grained roles aligned with job functions, automate assignments via user attributes, and enforce separation of duties. This streamlines governance and ensures compliant and least-privileged access across the organization.

## Overview

Securiti's advanced **Role-Based Access Control (RBAC)** framework provides you with greater flexibility and precision in managing access. The new model moves beyond broad, predefined roles and introduces fine-grained, action-based permissions across supported modules. This framework strengthens security by ensuring users have access only to the actions they need, simplifies administration by allowing multiple roles to be assigned to a single user, and improves compliance through clearer audit trails and tighter governance.

> [!NOTE]
> Important
> 
> For modules that have not yet adopted the new RBAC framework, existing Module Owner and Module User permissions continue to function in the same way as existing Access Profiles. This ensures continuity for existing users while offering a clear path toward adopting the more advanced, fine-grained RBAC model in future releases.

## How does RBAC work?

The RBAC framework lets you assign permissions to users through roles, following a three-layer hierarchy. At the top are modules, which contain permissions, grouped into roles, and finally assigned to users, ensuring structured and secure access control.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K5BWM5AY.png)

RBAC works in three-layered components, as explained in the table below:

| Component | Explanation |
| --- | --- |
| Users | Users are the accounts for real humans accessing the Securiti platform either through the user interface or APIs, and support the following operations under new RBAC: - It lets you assign a user to a single or multiple roles that control their permissions. - It lets you assign a user to one or more organizations that control which data they can see in the tenant. |
| Roles | Roles are collections of Permissions and support the following operations under new RBAC: - It lets you assign a role to multiple users. - It lets you keep a user’s role the same across every organization they belong to. **Important** Permissions that you assign to custom roles are the individual actions that define what a user can do. Permissions can be independently assigned to a role for a high degree of freedom during configuration. |
| Organizations | The Organization is a logical division of data within the tenant. It restricts users to see only data of the organizations they are part of and supports the following operations under new RBAC: - It lets you create Data Systems, Assessments, and other data object types within organizations to segregate data visibility in the graph and other areas of the product. - It lets you assign a user to multiple organizations. - It lets you assign a data system to only one organization. For more information, see [Managing organizations](/latest/docs/system-settings-managing-organizations). |

## Roles

Roles are a set of managed permissions that you can assign to users during creation. Instead of repeatedly assigning the same permissions to new users in the same group, you can create a role with predefined permissions and assign it to multiple users. You can also create multiple roles to meet different user requirements. It provides you with two types of roles:

| Role type | Description |
| --- | --- |
| Default roles | Default roles are default roles for you. It lets you manage several use cases in different modules. The new RBAC framework also introduces the following new default roles for the Sensitive Data Intelligence module: - Data Classification Manager - SDI Evidence Analyst - SDI Analyst - SDI Classification Reviewer - Discovery Scan Manager |
| Custom roles | Custom roles are the roles that you can create to meet your use case. You can attach multiple permissions from multiple modules and assign them to the user. With the new RBAC framework update in the platform, it also supports new APIs to create roles. For more information, see [System Settings API Documentation](https://securiti-doc-router.securiti.ai/modules/system-settings/apidocs/index.html). |

## Permissions

Permissions are actual access control for the user. These are the access permissions that you select during role creation. A user can only access those functionalities and perform those certain actions that you define in the role assigned to the user.

Securiti provides the following types of permissions:

| Permission type | Description |
| --- | --- |
| Fine-grained permissions | Fine-grained permissions provide multiple levels of access for the same functionality. You can select specific permissions to assign to a user based on their role. For example, in the **Email Template** functionality under the Securiti Platform, the framework provides the following permissions: - Read Email Template - Create Email Template - Delete Email Template - Update Email Template These permissions are available in supported modules. For reviewing all permissions associated to all the supporting modules, see [RBAC permissions with custom and default roles](/latest/docs/rbac-permissions). |
| Owner and User permissions | The new RBAC framework also supports permissions from the previous RBAC version, previously managed under Access Profiles. These include: - Module Owner - Module User These permissions are available only in specific modules that do not yet support the new RBAC framework. |

The permissions inherited from Access Profiles are available when creating a role. However, you cannot assign both permission types to the same user. See the table below for details.

| Role name | Description |
| --- | --- |
| Module User | Provides read-only access to the module data |
| Module Owner | Provides administrative access to the module data |

As a user can either be a User or an Admin, you cannot apply both permissions to the same account.

The RBAC framework supports **permission dependency** within modules, based on a parent–child relationship. Some permissions act as parent permissions and automatically include their child permissions when selected. However, you can also independently select only the child permissions if needed.

For example, in the Email Template under Securiti Platform, the following permissions support child permissions:

| Permission | Dependent permission |
| --- | --- |
| Create Role | View the roles list page |
| View the roles list page | None |

## Supporting modules for fine-grained permission

Fine-grained permissions are available to the following modules:

- Assessment Automation
- Compliance
- Data Access Governance
- Data Command Center
- Data System Connectors
- Deployment
- Enterprise Data Catalog
- Gencore AI
- IaaS Connectors
- Policies
- Platform
- Privacy Notice Management
- Risk Management
- System Settings
- Sensitive Data Intelligence
- Vendor Assessments
- Workflow

## Non-supporting modules for new RBAC

From release 1.137, the new RBAC does not apply to privacy and a few other modules. These product areas are continuing to use existing roles that are similar to Access Profiles roles.

It does not support the following modules:

- Cookie Consent Management
- Data Mapping Automation
- Data Subjects Rights
- Data Breach Management
- Mobile App Consent Management
- Privacy Center
- Universal Consent Management

## User

A user is a real person using the Securiti platform using an account. A user performs the actions on the application depending on the provided permissions. The following functionalities impact a user:

| Functionality | Impact |
| --- | --- |
| Organization | An organization limits a user to its own resources and data, restricting access to resources and data from other organizations. |
| Role | A role defines the position and capabilities of a user within the Securiti application. A user can only perform the actions that their assigned role allows. |
| Permission | Permissions define the specific actions a user is allowed to perform. These can vary across modules. A user might be able to create resources in one module but not in another. |

## Organizations

An Organization helps segregate resources and data among users. If you manage multiple areas of business, you can create separate organizations and assign different users to each. A user can belong to multiple organizations, and roles can be assigned across them.

Organizations provide the following benefits:

- Isolate resources and data across different business units or groups.
- Enforce access control by restricting views and functionality within each organization.
- Enable delegated administration, allowing Organization Admins to manage only their own organizations.

## Impact on tenants

The new RBAC framework enhances access control for both Tenants and Organizations. It simplifies how you assign roles and manage permissions, so administrators can set up and maintain access more easily. The framework also preserves backwards compatibility, which means your existing roles continue to work without requiring changes.

Data visibility remains managed through the Organizations feature, allowing you to control which users can view specific resources. With these updates, you maintain consistent workflows and secure access across the Securiti platform.

### Backwards compatibility

The updated RBAC framework is built to work seamlessly with the roles and permissions you already use. You do not need to modify existing configurations, and your users continue to have the same level of access as before. This design ensures a stable upgrade experience while you explore the new capabilities. As the role of administrator, it provides you with the following features:

- Retains functionality of current roles and permissions
- Avoids interruptions to user access during the upgrade
- Let’s you adopt new RBAC options gradually
- Maintains consistency across tenants and organizations

### Organizations segregation

The new RBAC framework has not impacted the use case of organizations. It lets you separate resources and data within your Securiti tenant. By grouping users, roles, and assets under different organizations, you can isolate access and maintain stricter control across business units. This makes it easier to align access with how your company operates. It provides you with the following features:

- Segregates resources and data between groups or business units
- Restricts users to the organizations they belong to
- Allows roles to span multiple organizations when needed
