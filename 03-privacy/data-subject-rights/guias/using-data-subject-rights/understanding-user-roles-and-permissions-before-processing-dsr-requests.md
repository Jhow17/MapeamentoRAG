---
title: "Understanding user roles and permissions before processing DSR requests"
slug: "understanding-user-roles-and-permissions-before-processing-dsr-requests"
updated: 2026-07-08T07:35:12Z
published: 2026-07-08T07:35:12Z
canonical: "helpcenter.securiti.ai/understanding-user-roles-and-permissions-before-processing-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding user roles and permissions before processing DSR requests

Securiti has the following user types:

| Type | Description |
| --- | --- |
| Internal | Users within your organization who have email addresses inside your corporate domain. |
| Partner | Users from managed services partners who have email addresses outside your corporate domain. Such partners might be companies with staff members who use Securiti on your organization's behalf to process DSR requests. > [!NOTE] > **Note** > > In order for you to add a partner user: > > - The managed services organization must have a Securiti account of type "partner." > - The partner user must have an active user or admin account on the managed services organization's Securiti partner account. |
| Collaborator | Users without their own Securiti user accounts who have been invited to collaborate on DSR subtasks. Collaborators login to Securiti using links they receive via email. They have relatively limited privileges to use Securiti or make changes in it. |

Securiti has the following user roles:

| Role | Description |
| --- | --- |
| Super Admin | An administrator with access to all available Securiti functions and features for all organizations. |
| Org Admin | An administrator with access to all available Securiti functions and features for the organizations they belong to. |
| Operator | A Securiti operator with access to all functions and features except the ability to create and manage Securiti users. |
| Module Owner | A user who has privileges over a subset of Securiti modules equivalent to those held by a user with Super Admin role. To establish a user as a module owner, you assign them an access profile that gives them user privileges for the module, then set their role to “Module Owner.” |
| DSR Module Owner Role | A Securiti user with module owner permissions for the Data Subject Rights module. |
| DSR User Role | A Securiti user with user level permissions for the Data Subject Rights module. |
| DPO | A Data Protection Officer who uses Securiti to ensure the safety and security of personal data. |
| User | A Securiti user who processes DSR subtasks as required to complete DSR requests from data subjects. |

| Permissions | Super Admin | Org Admin | Operator | Module Owner | DPO | User | Collaborator |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Read DSR Tickets | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Write DSR Tickets | Yes | Yes | Yes | Yes | Yes | Yes | No |
| Update/patch on DSR ticket | Yes | Yes | Yes | Yes (If ticket Owner) | Yes | No | No |
| Delete DSR Tickets | Yes | Yes | Yes | Yes (only for DSR Owner) | Yes | No | No |
| Read DSR Audit logs | Yes | Yes | Yes | Yes | Yes (only logs of activities DPO performs on a DSR request) | Yes (only logs of activities user performs a DSR request) | No |
| Export DSR Tickets | Yes | Yes | Yes | Yes | Yes | No | No |
| Move DSR tickets across organizations | Yes | Yes | Yes | Yes | Yes | No | No |
| Read DSR Tasks | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Write DSR Tasks | Yes | Yes | Yes | Yes | Yes | No | No |
| Update/ Patch on DSR task | Yes | Yes | Yes | Yes | Yes | No | No |
| Delete DSR Tasks | Yes | Yes | Yes | Yes | Yes | No | No |
| Read DSR Sub Tasks | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Create DSR Sub Tasks | Yes | Yes | Yes | Yes (only for DSR Owner) | Yes | No | No |
| Update DSR Sub Tasks | Yes | Yes | Yes | Yes (only for DSR Owner) | Yes | Yes (if assigned) | Yes (if assigned) |
| Delete DSR Sub Tasks (internal API) | Yes | Yes | Yes | Yes | Yes | No | No |
| Create DSR Sub Task Responses | Yes | Yes | Yes | Yes | Yes | Yes (if assigned) | Yes (if assigned) |
| Read DSR Sub Task Responses | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Update DSR Sub Task Responses | Yes | Yes | Yes | Yes | Yes | Yes (if assigned) | Yes (if assigned) |
| Delete DSR Sub Task Responses - No delete for Subtask response | Yes | Yes | Yes | Yes (only for DSR Owner) | Yes | Yes (if assigned) | Yes (if assigned) |
| Read DSR Forms | Yes | Yes | Yes | Yes | Yes | Yes | No |
| Update DSR forms | Yes | Yes | Yes | Yes | Yes | No | Yes |
| Create DSR Forms | Yes | Yes | Yes | Yes | Yes | No | Yes |
| Delete DSR forms | Yes | Yes | Yes | Yes | Yes | No | Yes |
| Read DSR Universal Forms | Yes | Yes | Yes | Yes | Yes | No | No |
| Update DSR Universal Forms | Yes | Yes | Yes | Yes | Yes | No | No |
| Create DSR Universal Forms | Yes | Yes | Yes | Yes | Yes | No | No |
| Delete DSR Universal Forms | Yes | Yes | Yes | Yes | Yes | No | No |
