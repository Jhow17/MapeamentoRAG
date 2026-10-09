---
title: "Adding and changing DSR request and DSR form owners"
slug: "adding-and-changing-dsr-request-and-dsr-form-owners"
updated: 2026-01-14T08:27:45Z
published: 2026-01-14T08:27:45Z
canonical: "helpcenter.securiti.ai/adding-and-changing-dsr-request-and-dsr-form-owners"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Adding and changing DSR request and DSR form owners

The table below describes the ownership roles that apply to DSR requests and tasks by default. These roles are separate from the Securiti system roles described in [Managing users](/v1/docs/configuring-access-management-managing-securiti-users).

| Role | Description |
| --- | --- |
| DSR Form Owner | By default, the Securiti Admin who creates a DSR form is the owner of all DSR requests that are submitted through the form. DSR form owners can add additional owners to a form. Also, Securiti admins and DPOs can change the ownership of a form. |
| DSR request owner | DSR request owners can add co-owners and also reassign ownership of their DSR requests. |
| Task owner | Each DSR request generates a series of tasks, as described in [Understanding tasks and subtasks](/v1/docs/understanding-tasks-and-subtasks). Each task is owned by the admin for the Data System. You cannot reassign tasks. |
| Subtask owner | Initially, Securiti assigns each Subtask to the admin for the Data System. The admin delegates the subtasks by reassigning them to Securiti users. See [Manually assigning DSR request subtasks](/v1/docs/manually-assigning-dsr-request-subtasks) for more information. |

To add a co-owner or change the ownership of a DSR request:

1. In Securiti, open a DSR request that you own as desribed in [Opening DSR requests in the DSR workbench](/v1/docs/opening-dsr-requests-in-the-dsr-workbench-1).
2. Near the upper right corner of the page, click **Edit** (pencil icon) and use the tools to add or remove request owners as shown below. You can search for DSR owners by their first name, last name, or full name.

![Screenshot_2025-08-05_at_2_08_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-081d5fe8-d422-0f82-c1ff-9e89aafe9b66.png)

To add a co-owner or change the ownership of a DSR form:

1. In Securiti, choose **DSR > DSR request form builder** and open a DSR request form.
2. Near the upper right corner of the page, click **Edit** (pencil icon) and use the tools to add or remove form owners.

To add a member of your organization as a new Securiti user and assign them as a DSR request:

1. Click **Add New Users** and use the Add New Users popup to specify the new user by name, email and role.

![Screenshot_2025-08-05_at_2_22_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46b758b2-2ebe-ea46-651a-b19630a90041.png)

The logged-in user can assign the following roles to a new user to be added on the DSR request:

| Logged-in user role | Roles they can assign |
| --- | --- |
| Super Admin | - Super Admin - Organization Admin - DPO - Module Owner - Operator - Module Owner DSR User Profile Role - Module Owner Self Service Portal User Profile Role |
| Org Admin | - Organization Admin |

The **Roles** menu also includes custom roles where custom access profiles with DSR module permissions were assigned to module owners or default users [before migration](/v1/docs/new-role-based-access-control-rbac-en).

> [!NOTE]
> **Note**
> 
> Logged-in users with roles such as **DPO, module owner, operator**, or **default user** cannot add a new user to the DSR request.
