---
title: "Data Catalog"
slug: "data-catalog-trigger-node"
updated: 2025-10-31T09:21:28Z
published: 2025-11-03T06:24:48Z
canonical: "helpcenter.securiti.ai/data-catalog-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Data Catalog

In Securiti, the Enterprise Data Catalog module (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

The Data Catalog Trigger node lets you trigger workflows based on any changes made to metadata within the EDC. The Data Catalog Trigger node gets triggered on any of the following operations as per selection:

- **Asset added**: This trigger activates when a new asset is added to the EDC. An asset could be any item of metadata, like a dataset, document, or another type of resource.
- **Asset changed**: This trigger is used when an existing asset in the EDC is modified in some way. Changes could include updates to the asset’s description, metadata fields, or other properties.
- **Asset deleted**: This operation triggers a Workflow when an asset is permanently removed from the EDC.
- **Asset soft deleted**: Unlike a full deletion, a "soft delete" operation marks an asset as deleted but does not actually remove it from the database. This helps in recovery if the deletion was a mistake or premature.

Refer to the [Node Configuration section](/v1/docs/using-custom-filtering-for-the-data-mapping) to understand the node parameters and descriptions.

#### Example Use Case

In this use case, a Workflow is configured to activate whenever any modification is made to a dataset by a user in the EDC. This activation is facilitated by the **Data Catalog Trigger** node, which is specifically designed to detect changes in dataset metadata. This Workflow ensures real-time monitoring of dataset modifications. This immediate response capability guarantees that any changes are quickly recognized and addressed, maintaining the dataset’s compliance with internal and regulatory standards.

The Workflow initiates through the **Data Catalog Trigger** node. This node gets triggered when an EDC user updates any aspect of the dataset. This trigger sets the stage for the entire Workflow.

Upon receiving a trigger signal indicating that an aspect of a dataset has been altered, the trigger Node forwards this information to the IF Node. Serving as a pivotal decision-making point within the Workflow, the IF Node assesses whether the alteration pertains to the governance status of the dataset.

If the IF Node determines that the modification indeed concerns the governance status of the dataset, it triggers the execution of the Data Catalog node. Specifically, it automatically assigns the dataset the “Engineering” domain, reflecting its governance status change. The Data Catalog node ensures accurate and efficient management of certified datasets within the Enterprise Data Catalog.

This use case uses the following Nodes:

- Data Catalog Trigger Node
- [IF Node](/v1/docs/if)
- [Data Catalog Node](/v1/docs/data-catalog)

#### Streamlining metadata Updates

1. Add a Data Catalog Trigger node to start the Workflow on the occurrence of an aspect change in the EDC.

![DC_Trigger_1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3af6e54b-19d8-987f-cfdd-f306b8ceb59b.png)
2. Add the IF node to evaluate if that modification is about the governance status of the dataset.
3. Add the Data Catalog node at the end to assign the “Engineering” domain to datasets that undergo a governance status change.
4. Connect the Nodes and execute the Workflow.

![Workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d899ad2c-ab55-edcf-dd84-4dd58089305f(1).png)
5. Upon successful execution, the Workflow node provides a successful response. You can access the results in two formats i.e. table view and JSON response.

![DC_Trigger_Node_JSON_Response.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1facd62e-5978-0773-84eb-50fa64e749b3.png)

#### Node Configurations

| Parameters |
| --- |
| Name | Specify the name of data catalog trigger |
| Entity type | Specify the type of entity to trigger the Workflow on - Data Platform - Dataset - Data job - DataFlow - Chart - Dashboard - Notebook - Corpuser - CorpGroup - Domain - Container - Tag - GlossaryTerm - Assertion - GlossaryNode - SchemaField - Data Process |
| Change type | Specify the type of change to trigger the Workflow on |
| Asset Added | When an asset is added |
| Asset Changed | When an asset is updated |
| Asset deleted | When an asset is deleted |
| Asset soft deleted | When an asset is soft deleted |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
