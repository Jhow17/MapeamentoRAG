---
title: "Using GenAI pipeline templates"
slug: "using-genai-pipeline-templates"
status: "update"
updated: 2026-01-13T06:06:31Z
published: 2026-01-13T06:06:31Z
canonical: "helpcenter.securiti.ai/using-genai-pipeline-templates"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using GenAI pipeline templates

**Scenario**

As a Data Governance Officer, you need to standardize GenAI pipelines across departments. Starting from scratch each time slows teams down and leads to inconsistent setups. With the **GenAI Pipeline Templates** dashboard, you use preconfigured templates to quickly deploy pipelines that comply AI governance regulations. These templates also help you understand key pipeline stages such as the data source, the AI models or the storage configured. You save time, ensure consistency, and scale governance more effectively.

The **GenAI Pipeline Templates** dashboard lets you build your workflows using existing templates, which are preconfigured pipelines. Using templates, you can save time and effort in setting up the pipelines. Additionally, you can work with existing system templates to build an understanding about the different stages involved in building AI pipelines.

To open the **GenAI Pipeline Templates** dashboard, in Securiti, open Gencore AI, and select **Templates**. You can also access the **Templates** dashboard from the **GenAI Pipelines** dashboard.

Using the **Templates** dashboard, you can access the list of existing pipeline templates in the form of a table or a grid.

- To view the pipeline templates in the form of a table, click **Table**.

![Overview of templates with details on data systems and modification dates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Templates tbl.png)
- To view the pipeline templates in the form of a grid, click **Grid**.

![Overview of various templates including S3 and Tech Docs for project management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Templates_grid.png)

Using the **Templates** dashboard, you can access the list of existing pipeline templates in the form of a table or a grid.

> [!NOTE]
> **Note**
> 
> Securiti displays private templates with the lock icon.
> 
> ![Overview of various tech document templates with descriptions and associated services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/templates grid lock.png)

Gencore AI supports templates with multiple data sources.

- You can search for specific templates.
- You can sort the list of templates by the following columns:
  - Embeddings LLM
  - Chatbot LLM
  - Vector Storage
  - Date Modified
- You can filter the templates:

![Templates filters](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Templates filters.png)
  - **Name**: Filter the templates based on the template name.
    1. Select a parameter from:
      - Equals
      - Not equals
      - Is one of
      - Is not one of
      - Contains
      - Not contains
      - Begins with
      - Not begins with
      - Ends with
    2. Enter the keyword or phrase.
    3. Click **Apply.**
  - **Data System Type**: Filter the templates based on the type of data system name.
    1. Select a parameter from:
      - Equals
      - Is one of
    2. Select the data system(s).
    3. Click **Apply.**
  - **Embeddings LLM**: Filter the templates based on the Embeddings LLM.
    1. Select a parameter from:
      - Equals
      - Not equals
      - Is one of
      - Is not one of
    2. Select the Embeddings LLM(s).
    3. Click **Apply.**
  - **Chatbot LLM**: Filter the templates based on the Chatbot LLM.
    1. Select a parameter from:
      - Equals
      - Not equals
      - Is one of
      - Is not one of
    2. Select the Chatbot LLM(s).
    3. Click **Apply.**
  - **Vector storage**: Filter the templates based on the Vector storage.
    1. Select a parameter from:
      - Equals
      - Not equals
      - Is one of
      - Is not one of
    2. Select the Vector store(s).
    3. Click **Apply.**
  - **Owner**: Filter the templates based on the Owner.
    1. Select a parameter from:
      - Equals
      - Not equals
      - Is one of
    2. Select the email address(es) of the owner(s).
    3. Click **Apply.**
  - **System Defined**: Filter the templates based on whether the system is defined or not.
    1. Select a parameter from:
      - Equals
      - Not equals
    2. Select a parameter from:
      - True: If the system is defined.
      - False: If the system is not defined
    3. Click **Apply.**
- The widgets on the dashboard display the following information:
  - Total templates
  - LLM Models
  - Data System Types
- To view details about the data system, embeddings LLM, chatbot LLM, or vector storage, hover over the corresponding icon.

![Templates - Hover icon](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Hover icon templates.png)

### Templates Use Cases

Here are some ways you can use templates to create pipelines.

| Template | Description | Nodes |
| --- | --- | --- |
| Confluence and techdocs | Template to create pipeline for confluence and techdocs | - Data Loader - Embeddings Generator - Vector database - Embeddings Retriever - LLM Selection |
| Financial Advisor Security Settings (RAG) | Template for internal Financial Advisor Security settings | - Data Loader - Data Sanitizer - Embeddings Generator - Vector database - Embeddings Retriever - LLM Selection - Response firewall - Prompt firewall |
| Financial ETF recommendation | Financial Advisors can use this intelligent analysis engine to determine the best ETF for your clients based on their current needs. | - Data Loader - Data Sanitizer - Embeddings Generator - Vector database - Embeddings Retriever - LLM Selection - Assistant API |
| Data loading, sanitization, embeddings and loading data into a Vector database | Pipeline is preconfigured to load documents from Google Drive and store vectors in Milvus. | - Data Loader - Data Sanitizer - Embeddings Generator - Vector database |

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.

A system or component that retrieves relevant information from a large dataset or knowledge base. Retrievers play a crucial role in tasks such as question-answering systems, information retrieval, and search engines.

This firewall uses policies to assess responses for prohibited outputs.

This firewall uses policies to assess prompts and access patterns for suspicious or prohibited inputs.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Creating templates](/creating-templates.md)
- [Configuring LLM providers](/configuring-llm-providers.md)
- [Configuring vector storage providers](/configuring-vector-storage-providers.md)
