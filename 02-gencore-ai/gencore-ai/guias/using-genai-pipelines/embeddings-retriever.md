---
title: "Embeddings Retriever"
slug: "embeddings-retriever"
updated: 2026-01-13T06:04:32Z
published: 2026-01-13T06:04:32Z
canonical: "helpcenter.securiti.ai/embeddings-retriever"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Embeddings Retriever

The Embeddings Retriever node defines parameters used when retrieving query results from the Vector database. The process includes:

- **Similarity search**: To retrieve similar Embeddings, you provide a query embedding as input, and the vector database performs a search to find embeddings closest to the query in the vector space.
- **Retrieval**: Following the similarity search, the Vector database retrieves embeddings most similar to the query embedding, representing data points considered related based on their vector representations.
- **Ranking**: The Vector database may also include ranking or scoring information with the retrieved Embeddings, indicating the degree of similarity or relevance between the query embedding and each result.
- **Re-ranking**: This is the process of refining the initial results retrieved based on similarity scores by applying additional criteria or models to improve the final ranking's relevance and quality. This step significantly enhances the precision of embedding-based retrieval systems.

To define this stage:

1. Click **Add** (+) to enable the **Embeddings Retriever** node.

![Settings for embeddings retriever including results and threshold configuration options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Embeddings retriever.png)
2. Select the number of **results** to return for a search or prompt.

![no_of_results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd590264-6e36-0ff8-fd5a-101929d515f4(1).png)
3. Define the **threshold**. The threshold determines the relevance and accuracy of the search results when the user's query is to match against the vector database.

![threshold.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee490721-ec70-b2fb-7433-cded8d7a01f8(1).png)
4. To re-rank the results, click the toggle **Re-rank results using AI**.

![rerank.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e25b3169-9c51-4d74-498e-1ccfe805b38e(1).png)

> [!NOTE]
> Note
> 
> To learn more about re-reranking results, see ​[Understanding re-ranking​​](/latest/docs/key-concepts#understanding-reranking).
5. To enable entitlement enforcement, click the toggle **Entitlements Enforcement Enabled**.

![entitlements_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08b7e5dd-527d-1440-7f25-f6a3d7ab3c67(1).png)

> [!NOTE]
> Note
> 
> The ​Entitlements Enforcement Enabled​ toggle is only visible if the selected data source supports entitlement. For the list of data systems supporting entitlements, see ​[Supported data sources​​](/latest/docs/supported-data-sources).
> 
> ​
> 
> To learn more about entitlements, see ​[Understanding entitlements​​](/latest/docs/key-concepts#understanding-entitlements).
6. When you are satisfied with the provided details, click **Save and Continue** to proceed to the **Retrieval firewall** stage.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A system or component that retrieves relevant information from a large dataset or knowledge base. Retrievers play a crucial role in tasks such as question-answering systems, information retrieval, and search engines.

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.

Re-ranking involves refining an initial set of query results to achieve a more precise ranking through machine learning models.

This firewall uses policies to assess queried data by the LLM before providing it to the LLM.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Embeddings Generator](/embeddings-generator.md)
- [Vector Database](/vector-database.md)
