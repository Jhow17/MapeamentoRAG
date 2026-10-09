---
title: "Embeddings Generator"
slug: "embeddings-generator"
updated: 2026-01-13T06:04:02Z
published: 2026-01-13T06:04:02Z
canonical: "helpcenter.securiti.ai/embeddings-generator"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Embeddings Generator

Embeddings are data that are converted into an array of numbers called vectors and contain patterns of relationships. Embeddings measure relatedness of text strings.

To make data available to your LLM, it must be in the form of embeddings stored in a vector database. Embeddings are numerical representations of data, typically in the form of vectors, that capture the semantic meaning or relationships within the data. Embeddings are essential for tasks like search, recommendation systems, clustering, and other AI applications because they enable meaningful comparisons and operations on complex data types. The Embeddings generator stage lets you create embeddings at this stage.

Some of the challenges Securiti’s Gencore AI addresses for preprocessing data include:

- **Selecting pre-trained models**: Conducting research to document embedding models and let users compare them.
- **Integration with model providers**: Integrating with the model provider by using the model's API or framework.
- **Preprocessing text data**: Preparing source data to ensure compatibility with the embedding model. This may involve tokenization, lowercasing, punctuation removal, handling special characters, and applying any language-specific preprocessing steps.

## Prerequisites

- List of preconfigured [embedding models](/latest/docs/supported-embeddings-models-and-llms).

> [!NOTE]
> Note
> 
> You can choose to select your embedding model by selecting the type of model as ​Embedding​ while adding credentials for an LLM provider. For more information, see ​[Configuring LLM providers​​](/latest/docs/configuring-llm-providers). ![List of LLM providers with options to add credentials and select model types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM providers - add creds - model type(1).png)

## Generating embeddings

This stage displays the details for the configured provider and model. To configure your embedding model:

1. Click **Add** (+) to enable the **Embeddings Generator** Node.

> [!NOTE]
> **Note**
> 
> The node is automatically enabled if the pipeline uses a template with this node.
2. Click **Add** (+) to select the model.

![Configuration settings for an embeddings generator with text splitting options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Embeddings generator Add.png)

If the template already uses a model, it is preconfigured. To edit it, click **Edit Model**.

> [!NOTE]
> **Note**
> 
> If the pipeline uses a template, the LLM is preconfigured. For preconfigured models, to show only connected models, click the toggle **Show Connected Only**. The number to the right of a model represents the number of connections against the relevant model.
3. Select the **provider** and **model**. Securiti displays the existing created instances for the relevant model.

![Configuration settings for various AI embedding models displayed in a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/embed generator instance.png)

1. To configure the instance:
  1. Select an existing instance.

![Select embedding generator instance](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/embed generator existing instance.png)
  2. To add a new instance, click **Add New**. Securiti directs you to the relevant credentials page for the selected provider where you can [configure the model](/v1/docs/configuring-llm-providers).

![Add new embedding generator](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/embed generator instance Add New(1).png)
2. To see the model details, select the ​**Model Details**​ tab and click ​**Explore**​​.

![Embedding generator explore model](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/embed generator explore.png)

Use the **Model Details** tab to view the model card showing relevant details of the model.

1. Define the details for Text Splitting:

When you are satisfied with the provided details, click Save and Continue to proceed to the [Vector Database](/latest/docs/configuring-vector-storage-providers) stage.
  - Select the Chunk Type. You can choose from:
    - Character
    - Word
    - Sentence
    - Passage
  - Choose Chunk length which is the number of items in each chunk when splitting the text.
  - Select the range for Chunk overlap, which is the percentage or number based of the chunk type that can overlap in consecutive chunks.
    - Sentence: 1 to 25
    - Word: 20 to 500
    - Character: 100 to 2500
    - Passage: 1 to 5

### Reconfiguring Embeddings model in case of deprecation

When a model configured in a pipeline is deprecated:

1. Securiti prompts you with alert sign on the Embeddings Generator node title.

![Pinecone II pipeline overview showing data sources and processing steps for AI integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Embed model deprecated 1.png)
2. When you click the alert sign, you can view the information about replacing the deprecated model.

![Warning about discontinuation of a model affecting data pipeline processing in Pinecone II.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Embed model deprecated 2.png)
3. When you click the Embeddings Generator node title, Securiti prompts with a **Needs Attention** badge and a notification to update your Embeddings model configuration.

![Warning about model discontinuation affecting data processing in the Embeddings Generator.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Embed model deprecated 3.png)
4. When you [replace the deprecated](/latest/docs/replacing-deprecated-models) model, Securiti prompts you to reingest data into the pipeline.

![Pinecone II pipeline status with warnings about data re-ingestion and model availability.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/data reingestion after updates.png)

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

Each cluster has a primary node. You can add processing capacity to the pod by adding up to nine secondary nodes.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Configuring LLM providers](/configuring-llm-providers.md)
- [Vector Database](/vector-database.md)
