---
title: "Restricting access to catalog item sections"
slug: "restricting-access-to-catalog-item-sections"
updated: 2025-12-09T07:26:33Z
published: 2025-12-09T07:26:33Z
canonical: "helpcenter.securiti.ai/restricting-access-to-catalog-item-sections"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Restricting access to catalog item sections

You can implement permissions-based access to sections in catalog items (asset, vendor, or institution) that restrict access to different sections of each catalog item. You can set it up so that some users can only view but not edit certain sections, and so that other users can not even see certain sections. You do this by configuring the permissions in a catalog definition, and then creating assets, vendors, or institutions using that catalog definition.

For the purpose of this feature, we have created a user type called “Business Process User.” These are users who have ownership over certain sections of a catalog item, but do not have ownership of the entire thing.

1. In Securiti, open **Data Mapping Automation** and choose **Settings >** Definitions.
2. In the Templates panel, choose an existing template that comes closest to meeting your needs, next to it choose **Options > Clone**, and click **Yes** on the confirmation popup.
3. Near the top of the cloned catalog definition, next to the name, click **Edit** (pencil icon), edit the name to suit, and click the check mark to save the new name.
4. On the card for each section in the catalog definition, click **Restrict Access**, configure the access for each user type as shown below, then click **Save**.

![RN_permission_access1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f867574-d606-74d8-4841-5239735f1187.png)

In the example above, owners can view and edit the section (you can’t change this), a business process user can view but not edit the section, and a Guest User can neither view nor edit the section.

Now that you have created a catalog definition for a certain type of catalog item, create a catalog item of that type and apply the new catalog definition, for example a new asset:

1. Choose **Catalog > Assets**, and near the upper right corner of the page click **Add Asset**.
2. On the Add New Asset popup, for Asset Type, choose the catalog definition you created earlier as shown below. Configure other settings to suit, then click **Create**.

![RN_permission_access2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aacf0726-c327-e291-8eb7-108f3133811e.png)
3. On the page for the new catalog item, next to the avatar for the Owner, click **Edit**, and use the tools on the Asset View & Access popup to add owners, business process users, and collaborators as shown below.

For owners and business process users, you can choose from among existing Securiti users. For collaborators, you can add anyone with an email address within your domain.

![RN_permission_access3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-476b02a7-0be9-2b09-9b69-e55496865cb5.png)

When the business process users and collaborators open the asset in Securiti, they can view and edit only those sections of the asset allowed by the catalog definition you used when creating the asset.

Permission-based access also applies to data map Assessments created for the catalog item. Owners can create such assessments, but business process users and collaborators cannot. Once you create such an assessment, you can only assign them to business process users and collaborators who have edit access privileges for the sections to which the questions belong.

> [!NOTE]
> **Note**
> 
> - System users who are question owners in existing assessments linked to the catalog item become business process users, and the catalog item owner becomes the owner for all assessments linked to the item.
> - Securiti synchronizes owners and collaborators between the Assessment Automation and Data Mapping Automation modules.
> - Self service portal users who are data mapping assessment owners are moved to a collaborator role and the catalog item owner takes over as the assessment owner.

A user who has not been registered in the tenant or does not have access to the current assessment organization. Also, referred to as a non-system user.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

## Related

- [Creating and customizing data mapping templates](/creating-and-customizing-data-mapping-templates.md)
- [Creating and customizing Data Mapping Automation reference lists](/creating-and-customizing-data-mapping-automation-reference-lists.md)
