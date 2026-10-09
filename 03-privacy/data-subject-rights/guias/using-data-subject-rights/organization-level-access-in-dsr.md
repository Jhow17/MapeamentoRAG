---
title: "Organization-level access in DSR"
slug: "organization-level-access-in-dsr"
updated: 2026-07-21T17:44:36Z
published: 2026-07-21T17:44:36Z
canonical: "helpcenter.securiti.ai/organization-level-access-in-dsr"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Organization-level access in DSR

Organization-level access lets you create multiple organizations within your tenant. Each organization acts as a standalone unit that is entirely independent and isolated from the rest of the organization units. When a new organization is created, three default DSR forms are also created by default in that organization. These are the same forms we source as part of Securiti tenant creation. The default forms are:

- Sample CCPA Request Intake Form
- Sample LGPD Request Intake Form
- Request Submission From (Internal)

You can migrate the DSR requests between organizations, but not the DSR forms. Migration of a DSR request transfers that DSR from one organization to another with the same name, and all tasks and subtasks associated with the migrated DSR are deleted upon DSR migration. Scanning is then initiated in the new organization based on the data systems present in that organizational unit.

> [!NOTE]
> **Note**
> 
> You can only migrate DSRs that are in **Task Created** or **Task Completed** state. DSRs in **In Progress** and **Completed** states are not allowed to migrate.
> 
> Securiti lets the following roles in your Securiti tenant migrate DSR requests across organizations:
> 
> - Super Admins
> - Module Owners

For more information on Organizations, see [Managing organizations](/latest/docs/system-settings-managing-organizations)

#### Migrating DSR(s) between organizations

To migrate Data Subject Requests from one organization to another:

1. In Securiti, go to **Data Subject Rights > Dashboard**.
2. In the DSR Dashboard, on the top right side of page, click **Migrate** icon as shown below.

![Screenshot_2024-06-09_at_12_40_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa262813-dd21-1e88-ecc3-cef1ae5f71b1.png)
3. On the popup, from the **Select DSRs** menu, choose one or more DSRs you want to migrate from your current organization to another organization.
4. From the **Select Destination Organization** menu, choose the organization where you want to migrate the selected DSRs and click **Confirm Migration** as shown below.

![Screenshot_2024-06-09_at_12_41_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dcb6e34d-17f7-cf19-0f55-b4a94815cd40.png)
