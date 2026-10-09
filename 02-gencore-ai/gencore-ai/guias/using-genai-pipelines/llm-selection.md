---
title: "LLM Selection"
slug: "llm-selection"
updated: 2026-09-14T06:36:14Z
published: 2026-09-14T06:36:14Z
canonical: "helpcenter.securiti.ai/llm-selection"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# LLM Selection

You can select and configure the models to be used for answering questions from the assistant. The LLM Selection node lets you specify a particular LLM to be used by the pipeline to answer your questions. You can select and configure the supported LLMs to be used for answering questions from the assistant.

Before configuring nodes further, Securiti lets you test your pipeline with the **Test** button. When you click the **Test** button:

- A pop-up chat displays.
- As required, interact with the Q&A Chatbot.
- The chatbot returns relevant responses.

Some of the responses may include:

- **Can't reply right now**: Possible reasons may be errors in pipeline configuration, either invalid credentials for Large Language Model (LLM) or Vector database or any other potential backend/connectivity issue.
- **Answering is not possible given the available information**: This means either the chatbot was not able to find relevant information or the answer can not be formulated from the content of ingested documents.

### Prerequisites

You must have the following predefined details:

- List of configured [LLM Providers](/latest/docs/supported-embeddings-models-and-llms).

### Defining the LLM

1. Click **Add** (+) to enable the **LLM Selection** node.

> [!NOTE]
> **Note**
> 
> The node is automatically enabled if the pipeline uses a template with this node.
2. Click **Add** (+) to select the LLM.

![Configuration settings for selecting a language model and adjusting chatbot capabilities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM selection Add.png)

> [!NOTE]
> Note
> 
> If an LLM model has been set as default in the LLM providers settings, the default model is preselected.

![Configuration options for various AI models in LLM selection interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM selection - providers and models.png)

> [!NOTE]
> **Note**
> 
> If the pipeline uses a template with LLM, the LLM is preconfigured.
3. Select the **provider** and **model**.

![Configuration options for various AI models including Azure OpenAI and Amazon Bedrock.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM selection - provider model selected.png)

> [!NOTE]
> **Note**
> 
> For preconfigured models, to show only connected models, click the toggle **Show Connected Only**. The number to the right of a model represents the number of connections against the relevant model.
4. To configure the instance:
  1. Select an existing instance.

![Selected LLM instance](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM selection - selected instance.png)
  2. To add a new instance, click **Add New**. Securiti directs you to the relevant credentials page for the selected provider where you can [configure the instance](/latest/docs/configuring-llm-providers).

![Add new model in LLM selection](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM add new.png)
5. To see the model details, select the **Model Details** tab and click **Explore**.

![Configuration options for selecting Azure OpenAI models, including GPT-3.5 Turbo details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/model details explore gpt-3.5.png)
6. When you select the model, you can view the model card showing relevant details including:

> [!NOTE]
> **Note**
> 
> To change the model, click **Edit Model**.
  - Utility, Safety and Trustworthiness metrics
  - Input and output details
  - Use cases
  - Language support
  - Token details
  - Access details
  - Costing and license information
  - Architecture and technical details
  - Training and data gathering
7. Select the **temperature**. A higher value makes the result is more diverse. A lower value indicates the result is more focused.

![temperature.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-adf1da0d-0cc1-173b-f04d-77c3299b0ec5(1).png)

For example, when asked a query “**What is Identity Access Management (IAM)?**”:
  1. The temperature setting of 0.1 results in a more focused answer.

![Example for temperature set as 0.1](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/IAM - Query-temperature-01.png)
  2. The temperature setting of 0.7 results in a more diverse answer.

![Example for temperature set as 0.7](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/IAM - Query-temperature-07.png)
8. In the **Additional Instructions** section, write the additional instructions to guide the LLM response. For example:
  - To direct the response to give answers in bullet points, write additional instructions as "Write answer in bullet points."
  - To direct the response to provide a summarized answer, write additional instructions as "Give answer as a short paragraph."
  - To direct the response to provide a friendly, conversational tone, write additional instructions as "Give a brief but friendly response in a conversational style."

![Additional_instructions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8951119-98c6-35b0-6708-7c3f06de00e4(1).png)
9. To allow references to be included in your LLM responses:

> [!NOTE]
> **Note**
> 
> References are sources or documents that offer evidence, support or validation for the information or claims presented in the text.
  - Click **Include References** toggle. The preview for the references layout displays.

![Include_References.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13008ec2-d4c8-fcbb-8765-3e2d61a6cf18(1).png)
10. When you are satisfied with the provided details, click **Save and Continue** to proceed to the [**Prompt firewall**](/latest/docs/prompt-firewall) stage.

### Reconfiguring LLM in case of deprecation

When a model in a pipeline is deprecated:

1. Securiti prompts you with alert sign on the LLM selection node title.

![Deprecated LLM alert](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deprec LLM selection node alert.png)
2. When you click the alert sign, you can view the information about replacing the deprecated model.

![Deprecated LLM selection alert hover](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deprec LLM selectio node alert hover.png)
3. When you click the LLM selection node title, Securiti prompts with a **Needs Attention** badge and a notification to update your LLM configuration.

![Warning about model availability affecting pipeline processing in the LLM selection interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deprec LLM selection node - needs attention.png)
4. When you [replace the deprecated](/latest/docs/replacing-deprecated-models) model, Securiti prompts you to reingest data into the pipeline.

![Data reingestion notification](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data reingestion notification after LLM replacement(1).png)

A large language model (LLM) represents a category of artificial intelligence (AI) programs adept at both recognizing and generating text, among other versatile tasks.

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Configuring LLM providers](/configuring-llm-providers.md)
- [Prompt Firewall](/prompt-firewall.md)
