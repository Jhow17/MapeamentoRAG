---
title: "Key concepts"
slug: "key-concepts"
updated: 2026-01-13T06:00:48Z
published: 2026-01-13T06:00:48Z
canonical: "helpcenter.securiti.ai/key-concepts"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Key concepts

A GenAI pipeline lets you get new content or data by asking questions through an AI Assistant.

In a traditional data pipelines, data is transformed and manipulated and stored in a traditional SQL database. You can query this data using SQL. These outputs are very similar to the inputs. In the context of artificial intelligence, "generative" refers to the ability of the system to produce new, original outputs rather than simply recognizing or classifying existing inputs. In order to produce such content, data must be processed and stored in a different manner.

These pipelines consist of the following distinct stages:

| Stage | Description |
| --- | --- |
| Data loading and sanitizing | The pipeline begins with the collection of relevant data. This data is then preprocessed to ensure that it is in a suitable format for training the generative models. Preprocessing may involve tasks like cleaning, normalization, and sanitation. |
| Embedding creation | During this stage, data is transformed and augmented with the help of LLMs to become compatible with generative AI. |
| Storage | The embeddings created are stored in a specialized database as vectors. These databases are called Vector Databases. You can find more information on Vector Databases below. |
| Retrieval | This stage lets the LLM retrieve embeddings from the database as requested by the LLM. |
| LLM selection | This is the ‘query engine’ that takes input from the user as a question (Prompt), interprets that question, queries the vector database (retrieval) and provides an answer to the user (response). |
| AI Assistant | This is the interphase with the user. The assistant manages the user experience and handles the prompts and responses. |

With Gencore AI, Securiti adds new stages to a traditional genpipes to preserve privacy and make it safer:

| Stage | Description |
| --- | --- |
| Enhanced data loading | Gencore AI uses Securiti’s powerful and reliable metadata extraction and classification capabilities to provide extra insights about the data. Metadata extraction includes extraction of entitlements |
| Data sanitizer | With Gencore AI, Securiti enhances how data can be sanitized and adds new stages to a traditional genpipe for increased privacy. |
| Firewalls | Firewalls add an extra layer of security to the pipeline by letting you define policies to protect the LLM from potential user abuse. This is an addition to making sure that the data retrieved and provided to the user in a response complies with privacy and security policies. |

More information on embeddings and vector databases is provided below.

#### Understanding embeddings and vector databases

Embeddings are numerical representations of objects, entities, or features, often used in machine learning and Natural Language Processing (NLP). The primary idea behind Embeddings is to transform high-dimensional data into a lower-dimensional space while preserving the essential relationships between the data points. They are particularly useful for capturing semantic relationships and similarities.

The following table describes some common embedding types.

| Embedding type | Description |
| --- | --- |
| Word embeddings | In NLP, word embeddings represent words as dense vectors in a continuous vector space. These vectors capture semantic relationships between words, letting algorithms to understand the meaning and context of words. Popular algorithms for generating word embeddings include Word2Vec, GloVe, and FastText. |
| Sentence embeddings | Sentence embeddings represent entire sentences or phrases as vectors. They aim to capture the overall meaning and context of a sentence. This is useful for tasks like text classification, sentiment analysis, and document retrieval. |
| Document embeddings | Similar to sentence embeddings, document embeddings represent entire documents (which may consist of multiple sentences or paragraphs) as vectors. They summarize the content and context of the document in a numerical format. |
| Image embeddings | In computer vision, image embeddings represent images as vectors in a continuous space. Convolutional Neural Networks (CNNs) are often used to generate image embeddings, capturing features and patterns within images. |
| Graph embeddings | For graph-structured data, such as social networks or knowledge graphs, embeddings represent nodes, edges, or entire subgraphs. Graph embeddings encode structural and relational information. |

The process of generating embeddings typically involves training a model on a large dataset to learn the optimal representations. The goal is to create embeddings that reflect meaningful relationships and patterns in the data. Once trained, you can use these embeddings as input features for various machine learning tasks, facilitating more effective learning by downstream models.

Embeddings are powerful because they provide a way to represent complex, high-dimensional data in a form that is more amenable to machine learning algorithms. They enable the algorithm to understand and generalize patterns, making them widely used in tasks like natural language understanding, image recognition, and graph analysis.

A vector database is a type of database that efficiently stores and queries vector data. Vector data refers to information that can be represented in a vector space, where each data point has a corresponding vector of numerical values. This type of database is particularly relevant in the context of machine learning, natural language processing, and other applications that involve working with vector representations.

The following table describes Vector database key characteristics and functionalities.

| Characteristic | Description |
| --- | --- |
| Efficient storage | Vector databases are optimized to store large volumes of vector data in an organized and efficient manner. This can include embeddings, feature vectors, or any other form of numerical representations. |
| Fast querying | The database is designed for fast and efficient querying of vector data. This is crucial for tasks such as similarity searches, where the goal is to find vectors that are close or similar to a given query vector. |
| Indexing | Vector databases often employ indexing techniques specifically tailored for vector data. These indexes help speed up search operations, making it quicker to find vectors that match certain criteria. |
| Support for High-Dimensional Data | Vector data can be high-dimensional, especially in the context of embeddings or feature vectors. Vector databases handle and process high-dimensional data effectively. |
| Scalability | As the volume of vector data grows, vector databases scale horizontally or vertically to accommodate increased storage and query demands. |
| Integration with Machine Learning Frameworks | Vector databases integrate seamlessly with popular machine learning frameworks, facilitating efficient storage and retrieval of model embeddings or feature vectors. |

### Understanding re-ranking

Re-ranking results in AI pipelines is the process of adjusting the order of a set of results returned by an initial ranking or search algorithm. This is done to improve the quality and relevance of the results. Re-ranking is commonly used in various applications, including search engines, recommendation systems, and natural language processing tasks. Here are the key aspects of re-ranking:

- **Initial Ranking**: The process begins with an initial ranking of results based on a primary algorithm, which could be a simple keyword search, a machine learning model, or a heuristic-based method.
- **Feature Extraction**: Additional features are extracted from the initial set of results. These features can include contextual information, user behavior data, semantic similarities, and more.
- **Secondary Model**: A secondary model, often more sophisticated than the initial ranking algorithm, is used to re-evaluate and re-rank the results. This model can be a machine learning algorithm trained specifically for the re-ranking task.
- **Optimization Objective**: The re-ranking model aims to optimize a specific objective, such as relevance, user satisfaction, or engagement metrics. This objective is often defined based on the specific needs of the application.

### Understanding entitlements

When the user asks a query to a GenAI Pipeline’s chatbot, the configured retriever retrieves the relevant documents from the configured vector store so the chatbot can provide an answer. By enabling **Entitlements Enforcement**, your GenAI pipeline’s chatbot will only reply with documents that your user is entitled to. The chatbot will not use the documents that a user does not have access to in formulating a response.

Without entitlements enabled, the chatbot retrieves all relevant docs regardless of permissions. This means that the chatbot will provide details without filtering sensitive or restricted information. To learn about the prerequisites for entitlement enforcement, see [Gencore AI onboarding prerequisites](/latest/docs/gencore-ai-onboarding).

> [!NOTE]
> **Note**
> 
> To understand how entitlements can play a critical role in your GenAI's success, see [GenAI Governance: Why Entitlements Matter More Than Ever](/v1/docs/securiti-pods-and-elastic-pods).

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

Natural Language Processing (NLP) is a specialized field within Artificial Intelligence (AI) dedicated to empowering computers to understand, generate, and manipulate human language proficiently.

Re-ranking involves refining an initial set of query results to achieve a more precise ranking through machine learning models.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

## Related

- [Embeddings Generator](/embeddings-generator.md)
- [Vector Database](/vector-database.md)
- [Supported data sources](/supported-data-sources.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
