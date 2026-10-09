---
title: "GCP Data Catalog"
slug: "gcp-data-catalog-regular-node"
updated: 2026-01-12T08:27:08Z
published: 2026-01-12T08:27:08Z
canonical: "helpcenter.securiti.ai/gcp-data-catalog-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# GCP Data Catalog

Google Cloud Platform (GCP) Data Catalog is a fully managed and scalable metadata management service that allows organizations to quickly discover, manage, and understand all their data in Google Cloud. It's designed to help teams quickly find and understand datasets that are stored across the various data storage options within Google Cloud, such as BigQuery, Pub/Sub, and Cloud Storage.

In Securiti's Workflows module, a GCP Data Catalog node allows you to:

- Create, delete and fetch entry groups in GCP data catalog.
- Create, delete and fetch entries in GCP data catalog.
- Create, delete or fetch tag templates from GCP Catalog.
- Populate GCP Data catalog to operate on individual GCP resources.

Please refer to the [node configurations section](/v1/docs/gcp-data-catalog) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow where the **Field Classification trigger node** is triggered whenever a classification is run and generates the results in the form of personal or sensitive information identified after the classification job.

These results are then used to populate data in the GCP Data catalog node. This use case reduces the manual effort of updating the GCP Data catalog and the workflow streamlines the data population process for the GCP Data catalog.

The following nodes are used in this workflow.

1. [Field Classification Trigger Node](/v1/docs/field-classification-trigger-node)
2. GCP Data Catalog Node

#### Populating a GCP data catalog from the FC trigger nodes results

1. Add a Field Classification Trigger node that gets triggered whenever a new classification is found in the specified data source.
2. Add the GCP Data Catalog and set the fields such that the data from the results of the Field Classification Trigger node gets populated in the GCP Data Catalog node.

![Screenshot_2024-05-07_at_4_06_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-06e68185-87cb-fa8c-3c16-6697bb5300e8.png)
3. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_4_08_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d67d886-4350-8500-a3d3-c23db03494fb.png)
4. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| GCP Instance | Specify the name of the GCP Instance to use |
| Populate Catalog | Whether to populate the GCP Data Catalog from privaci classifications or operate on individual GCP resources |
| Resource | Entry Group | Perform operation(s) on an Entry Group within an instance |
| Entry | Perform operation(s) on a single Entry within an Entry Group |
| Tag Template | Create tags to associate with different entities |
| Operation | List | Lists down the selected resources from the GCP catalog |
| Get | Fetches a selected resource from the CCP catalog |
| Create | Creates a new resource in the GCP catalog |
| Delete | Deletes an existing resource from the GCP catalog |
| Location | Provide the location of the resource |
| Tag Template ID | Provide the ID of the tag template |
| Entry Group | Provide the Privaci Data System as the Entry Group |
| Data System Type | Provide the name of the user-specified Data System |
| Entry Name | Provide the name of the entry from an Entry Group to perform an operation on |
| Entry ID | Provide the ID of the entry from an Entry Group to perform an operation on |
| Description | Provide the description of the operation |
| Field Classifications | Provide an array of objects containing columns and detections from the privaci system or use the classifications field as raw data expression when using this node with the Field Classification Trigger node |
| Tag Options | Row Count | Provide the desired number of rows to add to the resulting table |
| Column Count | Provide the desired number of columns to add to the resulting table |
| Entry Group ID | Provide the ID of the Entry Group to use in the operation |
