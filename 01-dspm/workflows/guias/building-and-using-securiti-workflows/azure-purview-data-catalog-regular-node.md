---
title: "Azure Purview Data Catalog"
slug: "azure-purview-data-catalog-regular-node"
updated: 2026-02-10T05:26:52Z
published: 2026-02-10T05:26:52Z
canonical: "helpcenter.securiti.ai/azure-purview-data-catalog-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Azure Purview Data Catalog

Azure Purview Data Catalog is a cloud-based data governance service and a vital component of Microsoft's Azure Purview. Azure Purview Data Catalog helps discover data across your organization’s data landscape that includes databases, files in Azure Data Lake, and other cloud environments. The catalog uses classifiers to automatically identify and label data based on sensitivity and content type.

In Securiti, the Azure Purview Data Catalog node performs the following set of functions:

1. List all the resources or fetch selected resources from Azure Purview Data Catalog.
2. Create new resources or delete existing resources in Azure Purview Data Catalog.
3. Populate Azure Purview Data catalog to operate on individual Azure resources.

Please refer to the [node configurations](/v1/docs/azure-purview-data-catalog) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow where the **Field Classification trigger node** is triggered whenever a classification is run and generates the results in the form of personal or sensitive information identified after the classification job.

These results are then used to populate data in the Azure Purview Data catalog node that updates the data catalog according to the newly found PD elements. This use case reduces the manual effort of updating the Azure Purview Data catalog and the workflow streamlines the data population process for the Azure Purview Data catalog.

The following nodes are used in this workflow.

- [Field Classification Trigger Node](/v1/docs/field-classification-trigger-node)
- Azure Purview Data Catalog Node

#### Populating an Azure Purview Data catalog from the FC trigger nodes results

1. Add a Field Classification Trigger node that gets triggered whenever a new classification is found in the specified data source.
2. Add Azure Purview Data Catalog node and set the fields such that the data from the results of the Field Classification Trigger node gets populated in the Azure Purview Data Catalog node.

![Screenshot_2024-05-07_at_4_00_23_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39ea553c-35b8-607a-570d-11de4583ae98.png)
3. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_3_52_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f89ccea4-2d20-af8c-3716-61855db53e44.png)
4. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Azure Instance | Specify the Name of the Azure instance to use. |
| Azure Purview Account | Azure Purview account to use for catalog operations against selected subscription |
| Populate Catalog | Whether to populate Azure Purview Data Catalog from privaci classifications or operate on individual Azure resources |
| Resource | Collection | Perform operation(s) on **Collection** (Directory) resource in the Azure Purview Data Catalog |
| Classifications | Perform operation(s) on **Classifications** (Metadata) resource in the Azure Purview Data Catalog |
| Operation | List | List selected resources from the Azure Purview Data Catalog |
| Get | Fetch selected resources from the Azure Purview Data Catalog |
| Create | Create resources in the Azure Purview Data Catalog |
| Delete | Delete resources from the Azure Purview Data Catalog |
| Collection | Collection to create the catalog in |
| Datasource Instance | Name of the Privaci Data System instance to be used with Field Classification Trigger node |
| Source Type | Add a user-specified data system such as **MySQL** and use the **connector_type** field when using it with the Field Classification Trigger node |
| Database Entity Name | Name for the database entity |
| Schema Entity Name | Name for the schema entity |
| Table Entity Name | Name for the table entity |
| Field Classification | Provide an array of objects containing columns and detections from the Privaci system and use the classifications field as raw data expression when using this node with the Field Classification Trigger node |
