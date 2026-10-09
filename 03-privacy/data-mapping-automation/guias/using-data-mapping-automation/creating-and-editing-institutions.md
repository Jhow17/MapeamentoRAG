---
title: "Creating and editing institutions"
slug: "creating-and-editing-institutions"
updated: 2025-12-09T07:21:16Z
published: 2025-12-09T07:21:16Z
canonical: "helpcenter.securiti.ai/creating-and-editing-institutions"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing institutions

You typically use Institutions to define and identify controllers, processors, joint controllers, and data recipients when you sell data. You might also use them to identify entities that act as sources, storage locations, and destinations of data. A typical Institution record has a basic set of key properties associated with it, along with standard information tabs such as assessments, risks, workflows and activities associated with that institution.

### Prerequisites

Ensure you have one or more of the following roles and have access to the Data maps organization:

- Super Admin
- Org Admin
- Operator
- Module Owner
- DPO

### Creating an institution

1. In Securiti, choose **Data Mapping > Catalog > Institutions**.
2. Near the upper right corner of the Institutions page, click **+ Add Institution**.
3. On the Add New Institution popup, enter basic information about the new institution, then click **Create**.

| Setting | Description |
| --- | --- |
| Template | Choose from among the available templates. See [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates) for more information about templates. |
| Organization | Enter the name of the institution. |
| Name | Enter a unique name for the institution record in Securiti. |
| Short description | Enter a short description for the institution. |
| Purpose | Enter the purpose of the institution. |

Securiti redirects you to the Institution Details page for the new institution.

### Editing a new or existing institution

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Institutions** and either click on an existing institution or create a new one as described above.
2. (Existing institutions only) Near the upper right corner of the page, click **Edit**.
3. On the Institution Details tab, expand the various areas and enter information about the institution. The table below describes typical fields.

| Area | Description |
| --- | --- |
| Basic Information | Configure essential information about the institution. |
| Risk | Choose a location on the risk heat map that describes both the likelihood of a security breach, and the severity of its consequences. |
| Data Elements and Types | View and if necessary configure the data elements and types retained by the institution: - Data elements are data storage units that are used within an element. - Data Element types are the associated PD type for each element. Click **Add or Modify Data Elements and Types** to add or edit the data elements. |
| Data Sets | Use this section to configure convenient sets of the available data elements and data element types, along with their properties. You can use data sets when you configure processes that use the asset. |

> [!NOTE]
> **Note**
> 
> You can customize the fields available in each section, and even add more sections, as described in [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates).
4. When you are done, check to make sure the **Save** button near the upper right corner of the page is disabled, showing you that Securiti has already autosaved your changes. If the button is active, click it to manually save your changes.

### Deleting a single institution

1. In Securiti, open **Data Mapping Automation** and choose **Catalog > Institutions**.
2. Filter the view as necessary to focus on the institutions of interest.
3. On the institution you want to delete, choose **Options > Delete**. Then click **Delete** on the popup to confirm.

### Deleting multiple institutions

1. In Securiti, open **Data Mapping Automation** and choose **Catalog > Institutions**.
2. Filter the view as necessary to focus on the institutions of interest.
3. Mark the checkboxes at the left edge of the institutions you want to delete.
4. Next to the Search box, click **Delete** as shown below. ![RN_delete_multiple_vendor_institution.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75a70f1e-e8cb-2884-fec2-26299acf3239.png)

Institution is the same as an asset - an entity that serves a different purpose.
