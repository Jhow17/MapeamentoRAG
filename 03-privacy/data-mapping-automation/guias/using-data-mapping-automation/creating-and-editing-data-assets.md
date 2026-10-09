---
title: "Creating and editing data assets"
slug: "creating-and-editing-data-assets"
status: "new"
updated: 2026-10-05T09:29:51Z
published: 2026-10-05T09:32:02Z
canonical: "helpcenter.securiti.ai/creating-and-editing-data-assets"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing data assets

**Scenario**

As a Data Compliance Officer acting as the IT administrator, you're responsible for maintaining a complete data asset inventory. Without a centralized system, tracking systems, processing activities, and data flows is fragmented and error-prone. By creating and updating the inventory in one place, you meet GDPR Article 30 requirements with accurate, up-to-date records that support audits and regulatory reporting.

You create data assets so that you can include them in data processes, and also so that Securiti can include them in DSR workflows. The data assets in your catalog are usually monitored data systems for which you have configured connectors, although you can also create data assets for unmonitored data systems for which you have not configured connectors. By default, Securiti recognizes two types of data assets:

- Data system
- SaaS application

### Prerequisites

Creating or editing data assets requires you to have one or more of the following roles and have access to the Data maps organization:

- Super Admin
- Org Admin
- Operator
- Module Owner
- DPO

### Creating a new data asset

1. In Securiti open **Data Mapping Automation**, then choose **Data Mapping > Catalog > Asset**.
2. Near the upper right corner of the Assets page, click **+ Add Asset**.
3. On the Add New Asset popup, apply the following settings, then click **Create**:

| Setting | Description |
| --- | --- |
| Asset Type | Choose from among the available data asset types defined by your data mapping templates. The default templates for data assets are **Data System** and **SaaS Application**, but you can create additional ones. See [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates) for more information about templates. |
| Technology Type | (Optional) Select or search Technology type, or you can leave the field empty. |
| Name | Enter a unique name for the asset. |

Securiti redirects you to the Asset Details page for the new asset.

See [Creating an asset using assessments](/v1/docs/creating-an-asset-using-assessments) for information on how the published assessment creates a new asset.

### Editing a new or existing data asset

1. If you have not already done so, In Securiti open **Data Mapping Automation**, then choose **Data Mapping > Catalog > Asset**.
2. Either click on an existing data asset or create a new one as described above.
3. (Existing data assets only) Near the upper right corner of the page, click **Edit**.
4. On the Asset Details tab, expand the various areas and enter information about the asset as described in the table below. The sections shown are those typically available; your templates may be different.

| Section | Description |
| --- | --- |
| Data Store Information | Configure essential information about the data asset such as description, purpose, asset type etc., along with their functions and features, responsible parties, and whether the data asset is included in DSR workflows. If you choose a role (controller/processor/subprocessor) for the asset, and later add the asset to a process, that role is reflected in the process where it is used. The Connector Status indicator at the bottom of the section shows whether there is an active connector enabled for the data asset. > [!NOTE] > **Note** > > If you enable Include in DSR Workflow for a data system but do not configure a connector for it, the data system is unmonitored. When Securiti accepts a DSR request, it uses such data systems to create and assign subtasks. However, since Securiti does not monitor these data systems, it cannot apply any automation to help you accomplish the subtasks. The subtask owners must access the data system themselves to process the subtask. |
| Retention and Disposal | Configure information about how long the asset retains data, policies regarding the retention, and subsequent data disposition. |
| Security Measures | Configure basic Information about the security measures that protect data on the asset, and information about specific security measures. Click **Add Security Measures** to add information about additional measures, for example, Data Minimization or Availability. |
| Risk | Choose a location on the risk heat map that describes both the likelihood of a security breach, and the severity of its consequences. |
| Data Elements and Types | Configure data element types detected during scans: - Data Element Type is the primary field. It populates automatically during asset scanning and classifies personal data by type (for example, a column named customerName would be classified as Data Element Type = Name). - Data Element is available as a manual reference field if you want to add notes or labels. It does not populate from scans. Click **Add or Modify Data Elements and Types** to view, edit types, or add manual reference information. See [Configuring attribute properties for data elements](/v1/docs/configuring-attribute-properties-for-data-elements) for information about editing the attribute properties for data elements. |
| Data Sets | Use this section to configure convenient sets of the available data elements and data element types, along with their properties. You can use data sets when you configure processes that use the asset. |
| Data Subjects | Use this section to configure convenient sets of the available data elements and data element types that apply to different types of data subjects. Similar to Data Sets, you can use data subjects when you configure processes that use the asset. |
| Processes | Shows you the processes that use the asset. |

> [!NOTE]
> **Note**
> 
> You can customize the fields available in each section, and even add more sections, as described in [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates).
5. When you are done, check to make sure the **Save** button near the upper right corner of the page is disabled, showing you that Securiti has already autosaved your changes. If the button is active, click it to manually save your changes.

### Deleting a single data asset

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Assets** to open the Assets page.
2. At the right end of the card for the asset, choose **Options > Delete**.
3. When Securiti prompts you to confirm, click **Delete**.

### Deleting multiple data assets at a time

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Assets** to open the Assets page.
2. Along the left end of the table of assets, mark the checkboxes for the assets you want to delete.
3. At the right end of the search box, click **Delete** (trash can icon) as shown below.

![RN_catalog_multi_delete.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc5d089d-84e6-5452-7e25-124f7c51758e.png)
4. When Securiti prompts you to confirm, click **Delete**.

> [!NOTE]
> **Note**
> 
> If any of the selected assets are ineligible for deletion because they are linked to data system connectors, Securiti warns that they cannot be deleted and offers to delete the other selected items while skipping the ineligible ones.

A Technology Type defines what type of asset or vendor an entity belongs to. These may include 101Data, ServiceNow, MySQL, and the likes thereof.

Risk is the likelihood of effects or implications that would negatively impact what you value. Risk in Securiti refers to risks that may arise when conducting internal or vendor assessments. You can track them using the risk dashboard.
