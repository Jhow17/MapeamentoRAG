---
title: "Data Catalog"
slug: "data-catalog-regular-node"
updated: 2026-02-12T05:56:42Z
published: 2026-02-12T05:56:42Z
canonical: "helpcenter.securiti.ai/data-catalog-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Data Catalog

In Securiti, the Enterprise Data Catalog module (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

The Data Catalog node lets you update the data catalog entities based on the modified metadata within a workflow. Using the Data Catalog node, you can perform the following operation:

**Upsert**: The Data Catalog node lets you perform an Upsert operation on several aspects of the catalog entities such as Containers, Datasets, Glossary terms, Glossary Nodes etc.

Refer to the [Node Configuration section](/v1/docs/using-custom-filtering-for-the-data-mapping) to understand the node parameters and descriptions.

#### Example Use Case

In this use case, the workflow ensures that when an EDC user modifies any aspect of a dataset, if the modification involves changes in governance status, the dataset's domain classification is automatically updated. This process streamlines governance-related actions and ensures consistent domain assignment for datasets based on their governance status changes.

The workflow initiates through the **Data Catalog Trigger** node. This node gets triggered when an EDC user updates any aspect of the dataset. This trigger sets the stage for the entire workflow.

Upon receiving a trigger signal indicating that an aspect of a dataset has been altered, the trigger node forwards this information to the **IF Node**. Serving as a pivotal decision-making point within the workflow, the IF Node assesses whether the alteration pertains to the governance status of the dataset.

If the IF Node determines that the modification indeed concerns the governance status of the dataset, it triggers the execution of the **Data Catalog** node. Specifically, it automatically assigns the dataset the “Engineering” domain, reflecting its governance status change. The Data Catalog node thus ensures accurate and efficient management of certified datasets within the Enterprise Data Catalog.

This use case uses the following nodes:

- [Data Catalog Trigger Node](/v1/docs/data-catalog)
- [IF Node](/v1/docs/if)
- Data Catalog Node

#### Automating domain classification to the datasets

1. Add a Data Catalog Trigger node to start the workflow on the occurrence of an aspect change in the EDC.
2. Add the IF node to evaluate if that modification is about the governance status of the dataset.
3. Add the Data Catalog node at the end to assign the “Engineering” domain to datasets that undergo a governance status change.

![Data_Catalog_Node_-_Before_execution.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d993d6b-8ca7-948a-91cc-85d2ffbe9e8e.png)
4. Connect the nodes and execute the workflow.

![Workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d899ad2c-ab55-edcf-dd84-4dd58089305f.png)
5. Upon successful execution, the workflow node provides a successful response. You can access the results in two formats i.e. table view and JSON response.

![DC_Node_JSON_response.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56f5a858-780a-20fd-f146-bd98c93001d8.png)

#### Node configurations

| Parameters | Description |
| --- | --- |
| Entity Type | Choose the type of entity within the EDC that you intend to update. Examples of entity types could include datasets, glossary terms, or any other metadata entity stored within the EDC. |
| Aspect Name | Choose the specific aspect or attribute of the entity that you want to modify. In the context of a dataset, aspects could include attributes such as the dataset name, description, and domain. |
| Entity URN | URN stands for Uniform Resource Name, which is a unique identifier assigned to each entity within the EDC. The Entity URN parameter refers to the URN of the entity that you want to update. This ensures that the update is applied to the correct entity within the EDC. |
| Aspect | Specify the aspect of the entity that you want to modify. It provides additional granularity in targeting specific attributes or properties of the entity. For example, if the entity type is a dataset, the aspect could be dataset owner, or the domain that this entity belongs to. |
| Change Type | Select the type of change or action that you want to perform on the specified aspect of the entity. In this case, you can only select “Upsert”. |
