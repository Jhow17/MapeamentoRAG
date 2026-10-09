---
title: "Manually assigning DSR request subtasks"
slug: "manually-assigning-dsr-request-subtasks"
updated: 2026-01-14T08:28:49Z
published: 2026-01-14T08:28:49Z
canonical: "helpcenter.securiti.ai/manually-assigning-dsr-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Manually assigning DSR request subtasks

When Securiti generates a DSR request, it initially assigns its subtasks to the primary owners and co-owners of each Data System for which it created the tasks. Data System owners can delegate their subtasks by reassigning them to others inside and outside your organization. Securiti admins and operators can also reassign subtasks.

To add or remove Subtask owners:

1. From either the DSR Dashboard or the DSR Workbench, click the DSR request to open it in the DSR workbench. For more information, see [Opening DSR requests in the DSR workbench](/v1/docs/opening-dsr-requests-in-the-dsr-workbench-1).
2. In the DSR workbench click the task to which the Subtask belongs.
3. In the Subtask list, click the Subtask you want to assign the owner. For tasks with only one Subtask, that Subtask is selected by default.
4. Near the upper right corner of the Subtask panel, next to the owner avatar click **Edit User** (pencil icon) and use the tools to add or remove Subtask owners as described below. You can search for Subtask owners by their first name, last name, or full name.

![Screenshot_2025-08-05_at_2_25_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c33ee95-b9b2-f052-95ed-da857eb4931e.png)
  - To add or remove existing Securiti users and admins as Subtask owners, use the search box and Owners tools to add or remove owners. If a Subtask has more than one owner, you can click the X next to an owner to remove them.
  - To add a member of your organization as a new Securiti user and assign them as a Subtask owner, click **Add New Users** and use the Add New Users popup to specify the new user by name and email.

You can also assign roles to the new user when adding them in a DSR Subtask. After the RBAC Migration (with release 1.120), the new RBAC feature assigns access profiles to roles in advance. These roles can then be assigned to users. For more information, see [RBAC Migration Summary](/v1/docs/new-role-based-access-control-rbac-en).

When selecting a role to assign to a new user on the DSR Subtask, the menu shows both old and new system-generated roles. Access profiles with DSR module permissions that were assigned to module owners or users before migration will now appear as new roles in the menu.

![Screenshot_2025-08-05_at_2_36_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9830616e-0500-03c8-940d-281c5a64424d.png)

The logged-in user can assign the following roles to a new user on the DSR Subtask:

| Logged-in user role | Roles they can assign |
| --- | --- |
| Super Admin | - Super Admin - Organization Admin - DPO - Module Owner - Operator - User - Module Owner DSR User Profile Role - Module Owner Self Service Portal User Profile Role - User DSR User Profile Role - User Self Service Portal User Profile Role |
| Org Admin | - Organization Admin - User - User DSR User Profile Role - User Self Service Portal User Profile Role |
| DPO | - User DSR User Profile Role - User Self Service Portal User Profile Role |

> [!NOTE]
> **Note**
> 
> Subtask owners with **GUEST DSR User Profile** or **USER DSR User Profile** may lack access to process records in the Subtask panel, preventing them from approving the Subtask .

The **Roles** menu also includes custom roles where custom access profiles with DSR module permissions were assigned to module owners or default users [before migration](/v1/docs/new-role-based-access-control-rbac-en).

> [!NOTE]
> **Note**
> 
> Logged-in users with roles such as **module owner, operator**, or **default user** are unable to add a new user to the DSR Subtask.
  - To invite a collaborator from inside or outside your organization to have ownership of a Subtask without adding them as a Securiti user:
    1. Click **Add New Collaborators**.
    2. On the Add Collaborators popup, in the Add DSR Collaborators box, type a collaborator’s email address, then press Enter to add it to the list. Repeat as necessary to build a list of collaborators. Further, choose language in which you want to send the collaborator invite. You can also add variables in the collaborative invite when adding a collaborator to a DSR Subtask. These variables act as dynamic placeholders, automatically replaced with specific values when the invite is sent.

The invite supports the following bind variables:

| Variable | Description |
| --- | --- |
| Link URL | A link to the assigned Subtask. |
| Recipient Name | The name of the collaborator, also used in the email. |
| Subtask Name | The title of the Subtask. |
| Tenant Name | The name of the tenant sending the invite to the Subtask collaborator. |

![Screenshot_2025-08-05_at_2_42_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14473246-1d01-6fd9-a969-cd476d8f2745.png)

> [!NOTE]
> **Note**
> 
> Changing the language after modifying the content of the invite results in the loss of those changes. Further, DSR Subtask collaborator invite adapts the content from the DSR collaborator notification template which means any change in the DSR collaborator notification template automatically influences content in the Subtask collaboration invite. For more information, see [Configuring DSR email notification templates](/v1/docs/configuring-dsr-email-notification-templates)
    3. (Optional) Customize the text of the invitation email using the tools on the Add Collaborators popup.
    4. When you are done, click **Assign**.
    5. Once you assign a guest user as a collaborator they receive an email containing the link to the portal.
    6. If Advanced invite control is enabled, clicking the link redirects individuals to the email verification page. For more information on Advanced Invite Control refer to [Configuring Securiti general settings](/v1/docs/system-settings-configuring-securiti-general-settings). Otherwise, they access the DSR Subtask directly.

![6e6278d1-c323-456f-b290-e1cee317a93b.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7912895c-c4a5-4f36-8891-4031949c7e37.png)
    7. Securiti sends a 6-digit verification code that the guest user enters to validate their identity to access the assigned DSR Subtask.

![validate_code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b4622b8-742a-196d-f701-b854fa7d458e.png)
