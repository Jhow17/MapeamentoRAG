---
title: "Configuring vector storage providers"
slug: "configuring-vector-storage-providers"
status: "update"
updated: 2026-01-13T06:07:41Z
published: 2026-01-13T06:07:41Z
canonical: "helpcenter.securiti.ai/configuring-vector-storage-providers"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring vector storage providers

**Scenario**

As a Data Governance Officer, you need to ensure vector data is stored securely and consistently across AI workflows. Without centralized setup, teams risk using unmanaged or siloed vector stores. On the **Vector Storage Providers** page, you configure approved providers for use in pipelines. This simplifies access control, ensures consistency, and supports compliant, scalable GenAI development.

The **Vector Storage Providers** section lets you add vector storage providers to configure vector databases in your GenAI pipelines. To open the **Vector Storage Providers** page, in Securiti, open Gencore AI, choose **Settings** and select **Vector Storage Providers**.

![List of vector storage providers with their status and creation dates displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/VSP(1).png)

The **Vector Storage Providers** page offers the following capabilities:

- Manage access to vector stores by setting up providers and API Keys.
- A widget displays the number of providers.
- Search for Vector Storage providers.
- Addition, editing and deleting a Vector Storage provider.
- Disabling or enabling a Vector Storage provider.
- Sorting and filtering vector storage providers.

> [!NOTE]
> Important
> 
> Securiti does not create or host the vector databases. The client provides their own vector database instance for the supported providers and adds the necessary connection credentials for configurations. Securiti validates those credentials and stores embeddings into the vector database specified by the client.

### Prerequisites

To add your vector database provider and configure its relevant models, you must have an active account on the provider portal.

### Adding vector storage providers

To set up a vector storage provider:

1. Click **Add Credentials**.

![Manage Vector Storage Providers and add credentials for various data services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/VSP Add Creds.png)
2. Select the provider.

![List_of_Vector_Storage_providers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2f41dc56-6cde-6154-7825-232fb04dbbdd(1).png)
3. Click **Add Credentials**.

![Pinecone-AddCredentials_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4ba33c9-eb0a-255d-c647-892ae646e9b9(1).png)
4. In the **Add Vector Storage Credentials** popup, add the credentials.

![Vector_Storage_-_Credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa68ac25-32ca-d120-0010-38a1ec5a673b(1).png)

> [!NOTE]
> **Note**
> 
> Credentials may vary for each provider.
5. In case of **ElasticSearch**, you can configure distance metrics.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(266).png)

| Distance Metric | Description |
| --- | --- |
| Euclidean | Measures how similar two vectors are based on the angle between them, ignoring magnitude. |
| Max Inner Product | Measures similarity by the dot product of two vectors—larger values mean more similarity. |
| Cosine | Measures the straight-line distance between two points in space—smaller values mean more similarity. |
6. To set this provider instance as the default selected instance in the pipeline, enable the toggle **Set as Default**.

![Vector_Storage_-_Validate_disable_Save_Creds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-612bc5fb-83af-c256-649d-74eafe650d2f(1).png)
7. To save the details:
  - To validate the credentials and save the details:
    1. Enable the **Validate Credentials** toggle.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(267).png)
    2. click Validate and Save Credentials.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(268).png)
  - To save the information without validating the credentials:
    1. Enable the **Validate Credentials** toggle.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(269).png)
    2. Click **Save Credentials**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(270).png)

> [!NOTE]
> **Note**
> 
> - To see how to configure Vertex AI as a vector storage, see [Vertex AI Vector Store Setup](/latest/docs/vertex-ai-vector-store-set-up).
> - To connect with ElasticSearch, you can connect with the ElasticSearch vector database in two ways:
>   - **Cloud-based**: This option requires a URL and API Key.
>   - **Hosted**: This option requires a URL, username, and password.
> 
> When a new vector database instance for **ElasticSearch** is created, the appliance pod on which it runs **must first have its IP allow-listed** on that instance.

### Managing vector databases

You can manage the providers as follows:

- **Edit** the vector database configuration.
- **Validate** the vector database configuration.
- **Delete** the vector database.

![VSP_Options.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b908d232-b8a3-0fda-ff9c-0f561968c0da(1).png)

### Sorting and filtering vector storage providers

You can sort Vector Storage providers based on Name and Created date.

You can filter Vector Storage providers based on Status, Name, Provider and Default.

![Vector Storage Providers filters](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/VSP filters.png)

- **Status**: To filter vector stores based on the status:
  1. Select a parameter:
    - Equals
    - Not equals
  2. Select status:
    - Active
    - Inactive
  3. Click **Apply**.
- **Name**: To filter vector stores based on the name:
  1. Select a parameter:
    - Equals
    - Not equals
    - Is one of
    - Is not one of
    - Contains
    - Not contains
    - Begins with
    - Not begins with
    - Ends with
    - Not ends with
  2. Enter keyword or phrase for the name.
  3. Click **Apply**.
- **Provider**: To filter vector stores based on the provider:
  1. Select a parameter:
    - Equals
    - Not equals
    - Is one of
    - Is not one of
  2. Select the provider. You can select multiple providers.
  3. Click **Apply**.
- **Default**: To filter vector stores based on the default status:
  1. Select a parameter:
    - Equals
    - Not equals
  2. Select:
    - True
    - False

### Supported vector storage databases

Gencore AI supports the following vector databases:

- DataStax Astra DB
- ElasticSearch
- Milvus
- OpenSearch
- Pinecone
- Qdrant
- Vertex AI
- Weaviate

### Hybrid search support for vector databases

Hybrid search lets users combine keyword-based techniques, such as BM25, with vector search methods. It improves result accuracy, even when exact keywords are missing, by using vector search to find relevant matches. Currently, Securiti supports hybrid search for the following vector databases:

- Astra
- ElasticSearch
- Milvus
- OpenSearch
- Pinecone
- Weaviate

An API key is a unique identifier used to connect to, or perform, an API call.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Vector Database](/vector-database.md)
