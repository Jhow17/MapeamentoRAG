---
title: "Project overview"
slug: "project-overview"
status: "update"
updated: 2025-12-01T07:59:21Z
published: 2025-12-01T07:59:21Z
canonical: "helpcenter.securiti.ai/project-overview"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Project overview

**Scenario**

As a data governance officer, you have to ensure compliance efforts across multiple cloud systems. Without a clear structure, tracking initiatives and timelines becomes disjointed. Using the Project feature, you define the scope, assign relevant frameworks, and launch initiatives tied to specific controls and deadlines. This keeps your compliance work organized, measurable, and aligned to strategic goals.

Project helps to create and implement initiatives to achieve compliance goals through frameworks. An initiative is a directive to implement a certain set of controls within a specific scope in a certain timeline.

To access the list of projects created:

- In Securiti, open **Compliance**, and at the upper right corner of the compliance dashboard click **Projects**.
- Or from the left navigation bar, select **Projects > Compliance Projects**.

![Main_Compliance_db_Projects_hl.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29999394-7cd7-d2c3-0a5a-c2043688195c.png)

The list shows you all the projects created in the compliance module.

**Automated projects**

The automated projects are displayed on the Projects dashboard. It consists of all the available assets of the IaaS connected account. This project enables reporting on all running tests on all assets under the scope. You view the status of newly connected IaaS accounts and their identified assets in Compliance.

By automatically generating a compliance project upon IaaS account connection, Securiti helps you efficiently monitor and assess the security and regulatory status of their assets from the moment you are onboarded.

Currently, the supported frameworks for the automated projects are as follows:

- ISO/IEC 27001:2022
- Securiti Controls
- SOC2 Type 2

You have the following options with the automated project:

- Edit
- View
- Duplicate
- View compliance
- Delete

You can disable the automated project by marking the **Active** toggle (located at the left side of the Name column) inactive.

**Projects dashboard**

The Search bar at the top of the list lets you search for the created project by its name or description.

![Compliance_Project_Search.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-62011ecd-ed7a-ac2a-321f-73d052769b78.png)

On the right side of the listed project, you can click the metadata explorer to view the information relevant to the project.You can click **Explore** to view the graphical representation of the metadata.

> [!NOTE]
> **Note**
> 
> You must have created and configured frameworks to be added to the project.

> [!NOTE]
> **Important**
> 
> Before adding a new project, make sure the Data Command Center (DCC) is enabled on your tenant. Otherwise, reach out to support@securiti.ai.

**Creating project**

> [!NOTE]
> Note
> 
> Only users with [read permissions](/v1/docs/compliance-rbac-permissions-and-roles) for projects can be associated with those projects.

1. In Securiti open Compliance, then at the upper right corner of the Compliance dashboard click **Projects**.

> [!NOTE]
> **Note**
> 
> An alternative way to create a project is:
> 
> - From the left navigation bar, select **Projects > Create Project**.
2. On the Projects list, in the upper right corner, click **Create.**

![Compliance_Project_hl_Projects_Create_Project.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5131d376-9459-2be2-2eeb-e3ae41d9040a.png)
3. In the "General Information" section of the form, enter the **Project Name**, **Description**, and Tags and choose the project owner from the menu.
4. In the “Scope and Status” section, define the scope associated with the evaluation logic. You can select all data systems or a specific data system as a part of the scope. Select the governance status of the project.
5. Further, select frameworks to be added. Click on **Configure** against each framework added and expand it to include required categories, subcategories, and controls.
6. Once done, click **Create Project**.

![4-createprojectform.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67a1def9-693f-8f05-aed4-3a9c45403ad5.png)

> [!NOTE]
> **Important**
> 
> Before adding a new project, make sure the Data Command Center (DCC) is enabled on your tenant. Otherwise, reach out to support@securiti.ai

To enable a project, click locate the card for the project you want to enable. At the right end of the card, choose **Options** (three dots) > **Enable**.

#### Default projects

When an IaaS connector is created, a default compliance project is automatically generated. This project is linked to the IaaS connector, with its name and ID derived from the connector details.

Example: GCP-0x61060cf563562

> [!NOTE]
> **Note**
> 
> if the IaaS connector is updated and new accounts are added, the associated default project will not be updated to include those new accounts.

### Enabled system frameworks

By default, the following system frameworks are activated within the project:

- ISO/IEC 27001:2022
- Securiti's Data Security Framework
- SOC 2 Type 2

#### Creating widgets

You can see the **Create Widget** button on the right side of the **Create Project** button. This option lets you display project-specific widgets on the projects dashboard to track metrics, trendlines, and more.

1. Click **Create Widget**.
2. Enter relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).

A project is created using different frameworks and associated with categories or subcategories to track the progress of specific compliance frameworks. A project includes specific scope and controls. This helps to track progress on specific compliance goals. For instance, the data governance team may have Projects to apply the CDMC framework to various data systems. These Projects may have different owners and target specific systems. Each owner can define their own projects to track progress toward their goals.

## Related

- [Managing categories](/managing-categories.md)
- [Managing sub-categories](/managing-sub-categories.md)
- [Controls overview](/controls-overview.md)
