---
title: "Creating and editing vendors"
slug: "creating-and-editing-vendors"
updated: 2025-12-09T07:19:41Z
published: 2025-12-09T07:19:41Z
canonical: "helpcenter.securiti.ai/creating-and-editing-vendors"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing vendors

You use vendors to capture relationships with suppliers and vendors who offer assets and services or act as sub-processors for your organization. A typical vendor record has a basic set of key properties associated with it, along with standard information tabs such as assessments, risks, workflows, and associate activities.

![Screenshot_from_2024-05-07_13-19-02.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-525f6c4d-fc9e-6749-b34d-5005a451e195.png)

If you are also subscribed to the Vendor Assessments module, creating a vendor in Data Mapping Automation also creates a vendor in Vendor Assessments. Any assessment related to a vendor in the Vendor Assessments module also shows up under the Assessments tab for that vendor in the Data Mapping Automation module.

> [!NOTE]
> **Note**
> 
> No difference from before is observed if you're not subscribed to both modules. However, if you opt for one and afterward add another, you can see vendors created in either module and in the other.

### Prerequisites

Creating and editing vendors require you to have one or more of the following roles and have access to the Data maps organization:

- Super Admin
- Org Admin
- Operator
- Module Owner
- DPO

### Creating a vendor

1. In Securiti, choose **Data Mapping > Catalog > Vendors**.
2. Near the upper right corner of the Vendors page, click **+ Add Vendor**.
3. On the Add New Vendor popup, enter basic information about the new vendor, then click **Create**.

| Setting | Description |
| --- | --- |
| Template | Choose from among the available templates. See Creating and customizing data catalog templates for more information about templates. |
| Technology Type | (Optional) Select or search Technology Type, or you can leave the field empty. |
| Name | Enter a unique name for the vendor. |
| Short description | Enter a short description for the vendor. |
| Purpose | Enter the purpose of the vendor. |

Securiti redirects you to the Vendor Details page for the new vendor.

### Editing a new or existing vendor

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Vendors** and either click on an existing vendor or create a new one as described above.
2. (Existing vendors only) Near the upper right corner of the page, click **Edit**.
3. On the Vendor Details tab, expand the various areas and enter information about the vendor. The table below describes typical fields.

| Area | Description |
| --- | --- |
| Basic Information | Configure essential information about the vendor. |
| Risk | Choose a location on the risk heat map that describes both the likelihood of a security breach, and the severity of its consequences. |
| Data Elements and Types | View and if necessary configure the data elements and types retained on the asset: - Data elements are data storage units that are used within a data system. For example, in structured data systems these would be all the column names for tables in a schema. - Data Element types are the associated PD type for each element. For example a column customerName could hold First Name and therefore be classified as Data.Element Type = Name. Click **Add or Modify Data Elements and Types** to add or edit the data elements. |
| Data Sets | Use this section to configure convenient sets of the available data elements and data element types, along with their properties. You can use data sets when you configure processes that use the asset. |

> [!NOTE]
> **Note**
> 
> You can customize the fields available in each section, and even add more sections, as described in Creating and customizing data catalog templates.
4. When you are done, check to make sure the **Save** button near the upper right corner of the page is disabled, showing you that Securiti has already autosaved your changes. If the button is active, click it to manually save your changes.

### Deleting a single vendor

1. In Securiti, open **Data Mapping Automation** and choose **Catalog > Vendors**.
2. Filter the view as necessary to focus on the vendors of interest.
3. On the vendor you want to delete, choose **Options > Delete**. Then click **Delete** on the popup to confirm.

> [!NOTE]
> **Note**
> 
> If there are any vendor assessments associated with the vendor, Securiti shows you a warning message as shown below, and does not delete the vendor. If this happens, open the Vendor Assessments module, delete any vendor assessments associated with the vendor, then try again.

### Deleting multiple vendors

1. In Securiti, open **Data Mapping Automation** and choose **Catalog > Vendors**.
2. Filter the view as necessary to focus on the vendors of interest.
3. Mark the checkboxes at the left edge of the vendors you want to delete.
4. Next to the Search box, click **Delete**.

> [!NOTE]
> **Note**
> 
> If there are vendor assessments associated with any of the selected vendors, Securiti shows you a warning message as shown below, and does not delete any of the vendors. If this happens, open the Vendor Assessments module, delete any vendor assessments associated with the vendors, then try again.

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

A Technology Type defines what type of asset or vendor an entity belongs to. These may include 101Data, ServiceNow, MySQL, and the likes thereof.
