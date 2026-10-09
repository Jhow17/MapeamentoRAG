---
title: "Vector Database"
slug: "vector-database"
updated: 2026-01-13T06:04:15Z
published: 2026-01-13T06:04:15Z
canonical: "helpcenter.securiti.ai/vector-database"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Vector Database

A vector database indexes and stores vector embeddings for quick retrieval and similarity search. In this stage, you define the Vector database to store the embeddings generated in the earlier stage.

To efficiently search your data, you must have your embeddings stored in a vector database. A vector database is a specialized type of database designed to store, manage, and query vector embeddings efficiently. In this stage, you define the Vector database to store the Embeddings generated in the earlier stage.

Some of the ways vector stores are helpful include:

- **Embedding storage**: Vector databases store embeddings along with any related metadata and labels.
- **Fit for use**: Vector databases are highly suitable for this purpose, as they are specifically designed to efficiently store, index, and retrieve high-dimensional vector data.
- **Optimized for search**: Vector databases are optimized for similarity and nearest-neighbor (knn) searches, making them especially valuable for applications involving machine learning models that utilize vector representations, such as NLP, image search, and recommendation systems.

> [!NOTE]
> Important
> 
> Securiti does not create or host the vector databases. The client provides their own vector database instance for the supported providers and adds the necessary connection credentials for configurations. Securiti validates those credentials and stores embeddings into the vector database specified by the client.

### Prerequisites

- List of preconfigured [Vector databases](/latest/docs/configuring-vector-storage-providers).

### Defining the vector database

The Vector database stores the generated embeddings in the Embeddings Generator stage. In this stage, the details for the configured provider display. To add the database:

1. Click **Add** (+) to enable the Vector Database node.

> [!NOTE]
> **Note**
> 
> The node is automatically enabled if the pipeline uses a template with a vector database.
2. Click **Add (+)** to select the vector database. ![Configuration section for selecting a vector database with a save option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vector db add.png)

> [!NOTE]
> **Note**
> 
> If the pipeline uses a template, the database is preconfigured.
3. Select the **provider**.

![Select vector database provider](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vector database - add creds(1).png)
4. To configure the instance:
  1. Select an existing instance.

![Select vector database instance](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vector database - select instance.png)
  2. To add a new instance, click **Add New**.

![Add new vector database instance](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vector database - add new instance.png)

Securiti directs you to the instance creation page for the selected provider where you can [configure the instance](/v1/docs/configuring-vector-storage-providers).
5. To edit the database details, click **Edit Database**.

![Edit selected vector database](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vector database selected Edit.png)

> [!NOTE]
> **Note**
> 
> If the pipeline uses a template, the vector database is preconfigured. For preconfigured databases, to show only connected databases, click the toggle **Show Connected Only**.
6. When you are satisfied with the provided details, click **Save and Continue** to proceed to the **Embeddings Retriever** stage.

### Testing ingested data in Vector Database

You can enable Run in this node with the intent of storing embeddings.

> [!NOTE]
> **Note**
> 
> For enabling the Run button for vector storage, it is mandatory to configure the following nodes:
> 
> - [Data Loader](/latest/docs/data-loader)
> - [Embeddings Generator](/latest/docs/embeddings-generator)
> - Vector Database
> 
> You can optionally configure the [Data Sanitizer](/latest/docs/data-sanitizer) node as well.

1. When you are satisfied with the provided details in the Vector Database node, click **Save and Continue**. The **Run** button is enabled.
2. Click **Run** to check stored embeddings.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A system or component that retrieves relevant information from a large dataset or knowledge base. Retrievers play a crucial role in tasks such as question-answering systems, information retrieval, and search engines.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Configuring vector storage providers](/configuring-vector-storage-providers.md)
- [Embeddings Generator](/embeddings-generator.md)
- [Embeddings Retriever](/embeddings-retriever.md)
