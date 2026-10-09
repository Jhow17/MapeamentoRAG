---
title: "Creating an asset using assessments"
slug: "creating-an-asset-using-assessments"
updated: 2025-12-09T07:17:53Z
published: 2025-12-09T07:17:53Z
canonical: "helpcenter.securiti.ai/creating-an-asset-using-assessments"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating an asset using assessments

You can add assets to the asset catalog using an asset discovery assessment. The process lets you maintain and monitor the asset catalog via an assessment. See [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets) for information to create an asset without assessments.

We assume you have asset attributes accurately defined in the catalog definition template. If you have not, see [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates) for more information.

> [!NOTE]
> **Note**
> 
> You must have one or more of the following roles and have access to the assessment organization:
> 
> - Super Admin
> - Org Admin
> - Operator
> - Module Owner
> - DPO
> 
> See [Understanding user roles and permissions before conducting assessments](/v1/docs/understanding-user-roles-and-permissions-before-conducting-assessments) for more information.Understanding user roles and permissions before conducting assessments

To verify if the assessment template shows you the updated fields:

1. On the Securiti Dashboard view, open **Data Mapping Automation**.
2. In the left sidebar, click **Assessments**. Securiti redirects you to the Internal Assessments list view page.
3. In the left sidebar, select **Assessments > Templates**.
4. On the following page, in the **Data Maps** section, click Options **(three vertical dots)** for your data mapping assessment template and click **Preview**.

Verify that the changes you made in the catalog definition are showing.

To create an asset using assessments:

1. On the assessment templates page, in Data Maps, from the options menu, choose **Start an Assessment**.
2. On the **Select / Add New Asset** popup, in **Choose Process**, mark the **Add New** radio button.

Then click **Create**.

Optionally, mark the **Select Existing** radio button to continue with the process you configured earlier.
3. On the **Assessment Owners & Collaborators** popup, add more owners, business process users (BPU), or any collaborators to suit.

After you have made the selections, click **Save & Invite**.
4. (Optional) Click **Assign Sections** to configure who is assigned what section.

On the assessment details page, enter the asset information such as Name, Purpose etc. via the questions in the assessment. Once you've recorded the responses, click **Submit** or **Submit All** for one or more questions, respectively. In the upper right corner of the page, click **Review & Publish**.

![Screenshot_2023-11-20_at_2_53_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b42e9fb1-82df-dc58-42db-00b7d9c11ae9.png)![Screenshot_2023-11-20_at_2_53_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74e1be89-bf89-f87a-97df-fe80c94bc72b.png)

Securiti shows your newly created data asset in the assets list under Assets section of the Data Mapping module. Click the asset to view its details page. The page shows you multiple tabs associated with that asset such as Asset Details, Assessments, and Risks, etc. Use the options on the page to edit the asset or initiate assessment.

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

A process defines the flow of data between entities and processes.

Risks help assess the criticality of an asset, and measure breaches and repercussions in the event of a breach.

## Related

- [Creating custom assessment templates in Securiti](/creating-custom-assessment-templates-in-securiti.md)
