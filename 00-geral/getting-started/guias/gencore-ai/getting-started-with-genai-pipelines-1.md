---
title: "Getting Started with GenAI pipelines"
slug: "getting-started-with-genai-pipelines-1"
updated: 2026-10-08T05:46:29Z
published: 2026-10-08T05:46:29Z
canonical: "helpcenter.securiti.ai/getting-started-with-genai-pipelines-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with GenAI pipelines

Securiti's Gencore AI module offers several powerful capabilities with GenAI pipelines. It lets you select and ingest unstructured data, perform data extraction (including transcription and metadata tagging for security and privacy), and transform data through sanitization (masking, redaction, and anonymization) while maintaining key metadata, such as entitlements. Additionally, it enables efficient indexing and retrieval by structuring data for quick searches based on data type and context, facilitating user query responses. The module also supports configuring large language models (LLMs) to answer end-user questions. It also empowers security and governance personas to define and enforce policies, reducing risks associated with data and LLM misuse through the use of Gencore AI LLM firewalls. Furthermore, you can integrate your pipelines as web widgets, user portals or in your messaging apps.

Some of the core challenges that come with creating workflows and pipelines include:

- Access, analysis and governance of unstructured data
- Safely connecting to the array of available data systems while ensuring controls and governance throughout the workflows.

To overcome these challenges and optimize workflows, Securiti's Gencore AI comes forth as a solution to safely connect to hundreds of data systems, at the same time preserving key metadata, such as entitlements, for these controls as data is ingested into generative AI pipelines.

> [!NOTE]
> **Note**
> 
> The optional onboarding flow lets users take advantage of Securiti's frictionless onboarding. Frictionless onboarding relies on Securiti's managed pods for data ingestion and processing. In the manual flow, users need to configure their own pods using their own infrastructure.

![Gencore AI flowchart for Onboarding, GenAI pipeline flow, firewall pages and settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Gencore AI-GS.drawio.svg)

## Step 1 - Create a pipeline

Gencore AI helps you to visually design pipelines and workflows to load unstructured data from supported sources and safely transform it for use by GenAI models. The GenAI Pipeline dashboard provides a centralized interface to access information and monitor the status of these pipelines.

You can create pipelines in the following 2 ways:

- [Manual flow](/v1/docs/getting-started-with-genai-pipelines#manual-flow)
- [Onboarding flow](/v1/docs/getting-started-with-genai-pipelines#onboarding-flow)

> [!NOTE]
> **Note**
> 
> The optional onboarding flow lets users take advantage of Securiti's frictionless onboarding. Frictionless onboarding relies on Securiti's managed pods for data ingestion and processing. In the manual flow, users need to configure their own pods using their own infrastructure.

### Manual flow

In the manual flow, you can independently create GenAI pipelines and enable prerequisites including:

- Data sources
- Pods
- LLM and vector database providers

#### a - Add Data Sources, Providers and Pods

Before onboarding on Gencore AI, make sure to add and enable data sources and providers (LLM, Embeddings and Vector Storage) to your tenant. In case of manual flow, you must deploy pods beforehand.

> [!NOTE]
> **Note**
> 
> At least one LLM and one embedding provider must be configured.

| ![Monitored_DS_-_Gencore_GS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a18b63f-b966-e39c-7f4d-f78b25b70d82(2).png) | **Add data systems** In order to ingest data into your pipeline, you must connect your pipeline to a data source. In System Settings, add data systems that can be used as sources for data ingestion in the pipelines. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system. The configured data system is preselected in the [Data Loader](/v1/docs/data-loader) node. [Learn more](/v1/docs/configuring-connectors-for-monitored-data-systems) |
| --- | --- |
| ![Pods_-_Gencore_DS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-390e82f9-72fc-9598-54a8-d72d0520c7a6(2).png) | **Configure pods** A Pod is a virtual machine (VM) or a physical server provisioned by a cloud service provider to run applications or workloads. These instances typically provide CPU, memory, storage, and networking resources for running various types of software applications and services. They are located within an organization's infrastructure to safely and securely execute Gencore AI services such as data loading and sanitation. To create and authenticate connectors using the data sources, you must use pods to connect with your data systems. If you want the manual flow to create your pipelines, in the System Settings, you can use pods and elastic pods to connect with your data systems to scan your data and to classify content including identifying personal data. In case of the frictionless onboarding flow, users can make use of Securiti's managed pods. In the manual flow, users need to configure their own pods using their own infrastructure. [Learn more](/v1/docs/securiti-pods-and-elastic-pods) > [!NOTE] > **Note** > > For information on pod installation for HPE Private Cloud AI (HPE PCAI), please see [Securiti POD installation for HPE Private Cloud AI (HPE PCAI)](/v1/docs/securiti-pod-installation-for-hpe-private-cloud-ai-hpe-pcai). |
| ![LLM_Providers_-_Gencore_GS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b206f77-0cc4-d6da-a77f-a4fa7e1987ed(2).png) | **Add LLMs and embedding models** If you want to extract information and ask questions from your data sources, for example, through a chatbot, configure your LLMs and embedding models. To make use of LLMs and embedding models in your pipelines, in the Gencore AI Settings, add the relevant providers beforehand in the manual flow. In case of the onboarding flow, you can create and authenticate instances while configuring LLM providers after pipeline creation through frictionless onboarding. The configured provider is preselected in the [Embeddings Generator](/v1/docs/embeddings-generator) or [LLM Selection](/v1/docs/llm-selection) node. [Learn more](/v1/docs/configuring-llm-providers) |
| ![Vector_Storage_providers_-_Gencore_GS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2fdb4ff-81d1-a823-21a3-ead11a40bf65(2).png) | **Add** Vector **Database storage** To store your extracted data with embeddings, you must configure a vector storage provider. To make use of vector storage in your pipeline creations for your generated embeddings, add vector storage providers in the Gencore AI Settings. In case of the onboarding flow, you can configure the vector storage providers after pipeline creation through frictionless onboarding. The configured provider is preselected in the [Vector Database](/v1/docs/vector-database) node. [Learn more](/v1/docs/configuring-vector-storage-providers) |

#### b - Create GenAI pipeline

You can choose to create your pipeline with an existing template having relevant pre configured nodes or from scratch.

[Learn more about Using GenAI pipelines](/latest/docs/using-genai-pipelines)

### Onboarding flow

The optional onboarding flow lets users take advantage of Securiti's frictionless onboarding.

#### a - Create GenAI pipeline

Start by choosing to create your pipeline with an existing template having relevant pre configured nodes or from scratch.

[Learn more about Using GenAI pipelines](/latest/docs/using-genai-pipelines)

#### b - Onboarding with Gencore AI

The onboarding flow simplifies the process of getting started with Gencore AI by helping you seamlessly deploy pods and configure connectors with the added data sources. Here, you can configure your data sources, LLM providers and Vector Storage providers ready to be utilized in your pipeline.

> [!NOTE]
> **Note**
> 
> You must have the Onboarding Flow enabled.

[Learn more about Gencore AI onboarding](/latest/docs/gencore-ai-onboarding)

## Step 2 - Configure pipeline nodes

After the onboarding is complete, you can proceed to configuring individual pipeline nodes as required. The Data Loader node is mandatory. For other nodes, you can make updates and add resources to optimize your pipeline.

To add firewall nodes into your pipeline, make sure to create [firewall profiles](/v1/docs/using-firewall-profiles). A firewall profile consists of policies that determine the configuration of firewalls and their behavior in pipelines. Gencore AI lets you create firewalls along with testing capabilities to optimize data access and retrieval. This enables you to:

- Assess data before providing it to the LLM.
- Evaluate prompts and access patterns for suspicious or prohibited inputs.
- Check responses for prohibited outputs.

You can also enable your pipeline to be configured for the user to interact with through a web widget, a dedicated user portal or as a chat-bot via integration with a third party messaging application such as Slack or MS Teams.

[Learn more about configuring GenAI pipeline nodes](/v1/docs/creating-a-new-pipeline)

## Step 3 - Test your pipeline

Once you have configured the pipeline, you can test it to verify the data retrieval and access. Simply converse with your pipeline through an intuitive interface and retrieve information from the configured data sources.

## Step 4 - Interact with your pipeline

Now that you have created your pipeline and tested it, you can interact with it in real time. Based on enablement options and settings defined in your pipeline, you can interact with your pipeline as follows:

- **Web widgets embedded in your portal:** Gencore AI lets you integrate your pipeline as web widgets into your web page or application to facilitate convenient engagement and access.

Learn more about [Configuring web widgets](/v1/docs/configuring-web-widgets).
- **A dedicated user portal**: Gencore AI lets you integrate your GenAI pipelines as a user portal for centralized access, streamlining workflows and improving efficiency.

Learn more about [Configuring user portals](/latest/docs/configuring-user-portal).
- **Chat-bot integrated into your messaging application**: Gencore AI lets you connect your pipeline to a messaging app enabling real-time interaction, and convenient access. It streamlines workflows, enhances user experience, and facilitates collaboration by letting users manage processes within a familiar platform.

Securiti currently supports integration with the Slack and MS Teams messaging apps.

Learn more about [Messaging App Integrations](/latest/docs/messaging-app-integrations).

To learn more about how Gencore AI helps you create powerful and secure AI applications, see the following videos.

| [Embedded content](https://player.vimeo.com/video/938486348) | **Building Safe GenAI** Learn how utilizing your data Gencore AI creates powerful pipelines while maintaining your enterprise data controls. |
| --- | --- |
| [Embedded content](https://player.vimeo.com/video/972878951) | **Safe Enterprise AI Search with Vertex AI** Explore how you can use Vertex AI search and Vertex AI models with your data, enterprise SaaS applications, and data systems with Gencore AI. |
| [Embedded content](https://player.vimeo.com/video/998577529) | **Safe Enterprise AI Search with Amazon Bedrock and Amazon Sagemaker** Learn how Gencore AI helps you use Amazon Bedrock and Amazon Sagemaker with your data, enterprise SaaS applications, and data systems to set up enterprise AI knowledge systems. |
| [Embedded content](https://player.vimeo.com/video/1024027013) | **Safe Enterprise AI Search with NVIDIA NIM** View how Gencore AI enables you to safely use the power of NVIDIA NIM Inference microservices in your private environments with your data, data systems and enterprise applications. |
| [Embedded content](https://player.vimeo.com/video/990172088) | **Safe Enterprise AI Search with Open AI** Explore how Gencore AI helps you to use Open AI models with your data, data systems and enterprise application to set enterprise AI applications. |
| [Embedded content](https://player.vimeo.com/video/974083758) | **Data Sanitization** Learn how Securiti automatically discovers sensitive data from hundreds of unstructured and semi-structured data systems and how Gencore AI helps safely ingest the data by building masking policies for data sanitization. |
| [Embedded content](https://player.vimeo.com/video/991445634) | **Syncing Data with** Vector **Databases** View how using Gencore AI, you can synchronize your data from any source to a vector database while preserving associated metadata and safeguarding sensitive information. |

## Gencore AI API documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Gencore AI API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/gencore/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you to quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/gencore/apidocs/index.html) | ![Gencore_AI_Postman.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc0b963a-787d-e3e8-2d05-c6a3f82e4d19(2).png) |

A firewall that prevents sensitive data from being input into or leaked by LLMs. This involves checking the information going in to make sure it's not sensitive or unauthorized, controlling what the LLMs share, and making sure they follow rules to produce safe and contextually appropriate responses.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

## Related

- [Using Gencore AI](/using-gencore-ai.md)
- [Gencore AI onboarding](/gencore-ai-onboarding.md)
