---
title: "Azure Data Lake Storage Gen 2"
slug: "azure-data-lake-storage-gen-2-regular-node"
updated: 2026-02-09T12:30:09Z
published: 2026-02-09T12:30:09Z
canonical: "helpcenter.securiti.ai/azure-data-lake-storage-gen-2-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Azure Data Lake Storage Gen 2

Azure Data Lake Storage (ADLS) is a cloud storage service designed for big data analytics. It allows organizations to store vast amounts of structured and unstructured data in a cost-effective manner. ADLS integrates with analytics services like Azure HDInsight and Azure Databricks, enabling efficient data processing, analysis, and management for advanced insights.

In Securiti, the ADLS node lets you perform the following operation on the Data Lake Storage container:

**List objects:** You can fetch a list of objects from the specified container by providing the prefix path.

Refer to the [Node Configurations](/v1/docs/azure-data-lake-storage-gen-2) section to understand the node properties and working.

#### Prerequisites

You must configure the Azure Data Lake Storage Gen2 connector in Securiti platform.

For more information, see [ADLS connector documentation](/v1/docs/azure-data-lake-storage-adls-gen2-connectors).

#### Example use case

As an example, let’s consider a use case where a company stores sensitive documents in Azure Data Lake Storage Gen 2 that must be kept in compliance with industry regulations. The use case involves setting up a workflow that automatically identifies files added or modified on the current day and subsequently runs a discovery scan on these files to detect sensitive information and ensure compliance.

The workflow begins with the **ADLS Gen2 node** configured to connect to a specific container in Azure Data Lake Storage Gen 2. It lists all files in the container and retrieves metadata for each file, including the last modified date. An IF node then analyzes the list of files and their metadata. It filters out the files whose last modified date matches the current date. This step ensures that only newly added or updated files are processed further. For each file identified in the previous step as being modified or added on the current day, the discovery scan node initiates a scan. This scan is designed to detect any sensitive or regulated data update.

The following nodes are used in this use case:

1. Azure Data Lake Storage Gen 2 node
2. IF node
3. Discovery Scan node

#### Automating compliance scans for newly modified files in Azure Data Lake Storage Gen 2 node

1. Add the ADLS Gen2 node and use List operation to list all the files on the desired prefix path and in the desired container.

![image__3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52b42989-00e7-b75f-d399-0735d166927c.png)
2. Add an IF node to analyze if the files fetched from the ADLS Gen2 have modified date matching the current date.
3. Add the Discovery scan node to run scans based on files modified.
4. Connect the nodes and execute the workflow.

![image__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69f7b910-3214-dc2a-8538-9ba8e8d37f89.png)
5. Once the workflow is executed, you can view the response in table view.

![image__2_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c2319fb-924c-db0d-6f28-a875e31104de.png)

#### Node Configurations

| Parameter | Description |
| --- | --- |
| Data System Name | Select the ADLS Gen 2 instance from the dropdown. To create a new ADLS Gen 2 instance, see the [ADLS connector documentation](/v1/docs/azure-data-lake-storage-adls-gen2-connectors). |
| Container | Specify the container name where the data objects are stored. For example, workflow. |
| Path | Specify the path where the objects are stored. For example, *logs/2024/january* If no path is provided, all items from the container are returned. A maximum of 10,000 items can be returned. |
| Operation | List objects | Choose this operation to fetch the list of objects placed on the relevant path. |
| Pagination | Enable this toggle to set a page limit for the results per page. This feature is recommended for the active mode, if enabled. |
| Page Size | Specify the number of objects to show per page. This value must be between 100 to 1000.s |
