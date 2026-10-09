---
title: "RBAC Migration Summary"
slug: "rbac-migration-summary-en"
updated: 2026-03-31T07:52:53Z
published: 2026-03-31T07:52:53Z
canonical: "helpcenter.securiti.ai/rbac-migration-summary-en"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# RBAC Migration Summary

The new RBAC framework upgrades the previous version. Both versions provide access control for users and roles. The previous version supported Access Profiles to define permissions that applied across all modules. The new RBAC framework continues to support these permissions in specific modules where required. Users in modules that still rely on the older RBAC version can continue using these roles while gradually transitioning to new roles based on business needs.

## Comparison between the current RBAC and the new RBAC

To compare the core differences and improvements between the older versions of RBAC and the new RBAC framework, see the table below.

| Current RBAC | New RBAC |
| --- | --- |
| **Layers** It has 4 layers: - Users - Roles - Access Profiles - Organizations | **Layers** It has 3 layers: - Users - Roles - Organizations |
| **Users** Users are the accounts for real humans accessing the Securiti platform either through the user interface or APIs, and support the following operations under the current RBAC: - It supports assigning users to a single role that contains and controls the permissions. - It supports assigning users to one or more organizations that control which data a user sees in the tenant. | **Users** Users are the accounts for real humans accessing the Securiti platform either through the user interface or APIs, and support the following operations under new RBAC: - It lets you assign a user to a single role that controls their permissions. - It lets you assign a user to one or more organizations that control which data they can see in the tenant. |
| **Roles** Roles are collections of Access Profiles and support the following operations in the current RBAC: - It lets you assign a role to multiple users. - It lets you keep a user’s role the same across every organization they belong to. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/rbac-migration-summary-en-image-hhqd6hm6.png) | **Roles** Roles are collections of Permissions and support the following operations under new RBAC: - It lets you assign a role to multiple users. - It lets you keep a user’s role the same across every organization they belong to. **Important** Permissions are the individual actions that define what a user can do. Permissions can be independently assigned to a role for a high degree of freedom during configuration. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/rbac-migration-summary-en-image-ihzzwyho.png) |
| **Access Profiles** Access profiles are collections of user permissions for the modules and support the following operations under the current RBAC: - For Module Owners, it lets you have administrator access to each selected module. - For Users, it lets you have read access to each selected module. | **Access Profiles** **Important** Securiti is deprecating the **Access Profiles** with the introduction of new RBAC in release 1.137. |
| **Organizations** The Organization is a logical division of data within the tenant. It restricts users to see only data of the organizations they are part of and supports the following operations under the current RBACC V1: - It lets you create Data Systems, Assessments, and other data object types within organizations to segregate data visibility in the graph and other areas of the product. - It lets you assign a user to multiple organizations. - It lets you assign a data system to only one organization. | **Organizations** The Organization is a logical division of data within the tenant. It restricts users to see only data of the organizations they are part of and supports the following operations under new RBAC: - It lets you create Data Systems, Assessments, and other data object types within organizations to segregate data visibility in the graph and other areas of the product. - It lets you assign a user to multiple organizations. - It lets you assign a data system to only one organization. |

## Related

- [Managing Securiti users](/configuring-access-management-managing-securiti-users.md)
- [Using Roles in Securiti](/roles-in-securiti.md)
