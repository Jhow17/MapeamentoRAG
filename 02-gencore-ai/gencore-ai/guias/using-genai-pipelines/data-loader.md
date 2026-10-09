---
title: "Data Loader"
slug: "data-loader"
status: "update"
updated: 2026-09-02T06:37:45Z
published: 2026-09-02T06:37:45Z
canonical: "helpcenter.securiti.ai/data-loader"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Data Loader

The Data Loader Node lets you load and ingest the data into the pipeline for further Processing. In order to create an interactive chatbot to retrieve information, you must supply your Model or LLM with a Dataset (typically unstructured). To ingest this data into your pipeline, you must configure the data loader stage. This is a mandatory step. Once this stage is configured, the data can be processed in the pipeline.

Some of the challenges Securiti’s Gencore AI addressed for data ingestion include:

- **Use of existing data in VPC**: Restricting AI to pre-existing data in a controlled environment can limit its effectiveness.
- **Duplicating data for AI usage**: Moving or duplicating datasets to support RAG use cases can contribute to increased ROT (redundant, outdated, trivial) data concerns.
- **Remote access to existing data stores**: Granting unmanaged access to various data repositories may create future challenges with data access governance.

When the files are ingested, you can see the status in the [**Status**](/latest/docs/pipeline-status) page.

> [!NOTE]
> **Note**
> 
> You can ingest data into your pipelines through API as well. For more information, see [Data ingestion through API](/v1/docs/data-loader#data-ingestion-through-api) and [Securiti Portal APIs](https://securiti-doc-router.securiti.xyz/modules/gencore/apidocs/index.html).

### Prerequisites

- In the case of Self-hosted Data systems, [deploy a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- Configure [data systems and connectors for the data systems](/v1/docs/managing-data-system-connectors).

To define the Data Loader node.

1. Click **Add** (+) to enable the **Data Loader** node.

> [!NOTE]
> **Note**
> 
> Securiti automatically enables the node if the pipeline uses a template with this node.
2. To add a source:

> [!NOTE]
> **Note**
> 
> You can add multiple data sources. To add another data source, click click **+ Add a Data Source**. and continue the relevant steps.
  1. Click **+ Add a Data Source**.

> [!NOTE]
> **Note**
> 
> For more information on the list of data sources that Securiti supports, see [Supported data sources](/v1/docs/supported-data-sources).

![Data Loader showing options to add a data source and search functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Loader - Data Source Add a DS.png)
  2. In the **Data Scope**, enter the **Name**.

![DS_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05b46809-c15d-e6a2-68c8-4d6c438bc3c2(1).png)
  3. Click **Add** (+) to add a data source.
  4. Select the **Provider**.

![Selecting Amazon S3 as a data source for the pipeline configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DL-AMazonS3selected.png)
  5. To configure the instance:
    1. Select an existing instance.

![Selecting an Amazon S3 instance for data source configuration in a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DL-AmazonS3-instanceselected.png)
    2. To add a new instance, click **Add New**.

![User interface for selecting Amazon S3 data source and instance in a pipeline setup.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DL-AmazonS3-AddNew.png)

Securiti directs you to the instance creation page for the selected provider.

![Amazon S3 instance settings with fields for instance name, location, and account details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/S3 instance creation.png)

> [!NOTE]
> **Note**
> 
> You can select multiple instances.
  6. To save the selected instance, click ​**Apply**. The data source is selected.

![Selecting Amazon S3 as a data source with instance options and an apply button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DL-AmazonS3-instance-apply.png)

To edit the data source, click **Edit**.

![DL_node_DS_selected_Edit_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d8caace-338c-f1fc-8684-e4b1f8c83846(1).png)
  7. Under **Data Conditions**, where applicable, select other conditions that you want to apply to this data loading job:

Data conditions are criteria-based mechanisms used to selectively process specific data.

![Data_Conditions_-_DL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6657a8b6-a1a8-9b3a-48b1-b99820c19fde(1).png)

> [!NOTE]
> **Note**
> 
> In case of JIRA Software, Data Conditions are applied on all the issues and comments. Filter for specific tickets and issues is not supported.
    - **Object Prefix**: Enter a text or a regex prefix to match.
    - **Object Name**: Match the object name based on a regular expression.
    - **Object Tags**: Match the object name based on tags as a key:value pair format.
    - **Object Extension Category**: Match the object based on the extension category.
    - **Object Extensions**: Match the object based on the extension text.
    - **Object Size**:Match the object based on size.
    - **Last Modified**: Match the object based on when it was last updated.
  8. To add a new condition, select a condition from the drop down **Select to add new condition for the job**.

![new_conditions_-_DL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8fc9f7e2-108e-b7e6-809e-f329e115d2cb(1).png)
  9. When you are satisfied with the provided details, click **Save**.

![Save_added_DS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10f258e7-3558-aa5f-df57-c29f988fbbc2(1).png)
3. To add ​Custom Files​​, click the **​Custom Files​ toggle**. For more detail, see ​[**Adding custom files​​**](/latest/docs/adding-custom-files).
4. To select **Store Output**, click the toggle. For more detail, see [**Configuring store output**](/v1/docs/configuring-store-output).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(244).png)

1. To detect and delete stale data, enable the toggle **Delete Data**.

> [!NOTE]
> **Note**
> 
> Stale data is the data that no longer exists in the data system. For example, you have ingested a set of files and the vector storage stores the embeddings for those files. In case you delete some of the files from the data source, the embeddings still remain. In order to eliminate these from the vector storage, you must enable this toggle before executing the pipeline again with the new data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(245).png)

When you are satisfied with the provided details, click **Save and Continue** to proceed to the [**Data Sanitizer**](/v1/docs/data-sanitizer) stage.

### Testing ingested data in Data Loader

In order to perform text extraction from multiple sources, you can test if the data source is configured properly, you can click **Run** once the Data Loader node is configured.

In this case, it is mandatory to select and [configure Store Output](/v1/docs/configuring-store-output).

> [!NOTE]
> **Note**
> 
> Data sanitizer, Embeddings generator, and vector database Nodes must be disabled, because the user intent is data loading.

1. When you are satisfied with the provided details in the Data Loader node, click **Save and Continue**. The **Run** button is enabled.
2. Click **Run** to check ingested files.

### Re-ingestion of data in Data Loader

In case of **Completed** pipelines, data must be re-ingested in case of changes in the following pipeline nodes:

- Data Loader
- Data Sanitizer
- Embeddings Generator
- Vector Database

When any of the nodes is updated, a message bar displays for re-ingestion of data before processing the pipeline.

When the message bar displays for data re-ingestion:

1. Click on **Re-ingest** data. A confirmation popup displays.

![data-reingestion_128_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47e30be4-4771-c492-6c0a-9796378f7884(1).png)
2. To confirm data re-ingestion, click **Re-ingest data**.

![Data_reingestion_confirmation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aeab82dc-252c-aa35-e04d-45cdf97a718e(1).png)

### Data ingestion through API

You can ingest data into your pipelines through API using the `.jsonl` file. To ingest a custom file through API:

1. Run the relevant [data ingestion API](https://securiti-doc-router.securiti.ai/modules/gencore/apidocs/index.html).

> [!NOTE]
> **Important**
> 
> Ensure the following:
> 
> - File Extension: Must be `.jsonl`
> - Maximum size limit: The maximum size limit for the `.jsonl` file is 20 MB.
> - Content: Each line must be valid JSON representing a document chunk
> - Empty Files: Not allowed - will return 400 error
> - Empty Lines: Skipped during processing
> - Chunk Size: Maximum 256KB per chunk content
> - Minimum Content: At least one valid JSON object must be present
> - File upload: Only one file can be uploaded at a time. Multiple file upload is not supported
2. Ensure **Custom Files** toggle is enabled in the Data Loader node.
3. Select a predefined pod or add a new pod. You can see the ingested file.

![Custom_file_API_listed_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f31a9cd6-59f3-a833-0c1c-87519cab8a20.png)
4. Save the changes.
5. To execute the pipeline, click **Run**. After the file ingestion, Securiti displays it on the **Status** page with the **Custom Files Scan** label under **Data System**.

Each cluster has a primary node. You can add processing capacity to the pod by adding up to nine secondary nodes.

Data being processed that's stored by the entity, for example, an asset.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

A dataset is a structured collection of consumable data with associated metadata and features for managing, discovering, and governing data assets within an organization. Tables and files are common examples of datasets.

Self-hosted systems refer to computer systems or software applications that are hosted and operated by organizations or individuals who use them, rather than being hosted and operated by service providers or third parties. It becomes the responsibility of the organization to host, maintain, and manage the system or software.

Data systems refer to the system where your data is stored. That can be in the form of files (text, audio, video), databases (tables and schemas), and streaming data (data in motion). Securiti supported most of the structured, unstructured, and streaming data systems.

Scope defines asset types, individual assets, or asset groups, such as IaaS Cloud, assessments, data systems, or datasets within a data system.

A set of criteria that focuses your view by eliminating elements that fall outside the scope of interest. When you filter Securiti pages and dashboards, you choose criteria in the filter panel to reduce the number of elements Securiti displays to just those of interest.

A custom file is a user-provided local file (such as, a spreadsheet) containing specific data for targeted analysis or processing that you upload to run through a pipeline. Gencore AI ingests it and processes it through your configured nodes (such as Sanitization and Vectorization), alongside data from existing connectors.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Supported data sources](/supported-data-sources.md)
