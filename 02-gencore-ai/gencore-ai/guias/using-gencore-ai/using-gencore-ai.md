---
title: "Using Gencore AI"
slug: "using-gencore-ai"
status: "update"
updated: 2026-09-17T05:01:05Z
published: 2026-09-17T05:01:05Z
canonical: "helpcenter.securiti.ai/using-gencore-ai"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using Gencore AI

The constant evolution and expansion of unstructured data, has proportionately given rise to opportunities of security and privacy breach. To help customers onboard swiftly through chatbots using trained Generative Artificial Intelligence (GenAI) and Large Language Model (LLM), it has become inevitable to provide safe mechanisms for GenAI and LLM training and usage.

GenAI and LLMs must be trained on large amounts of data, especially unstructured data. It is important to train these models to ensure:

- **Security**: Generative AI and LLMs must be trained and utilized such that these cannot be exploited for fraudulent use.
- **Privacy**: Generative AI and LLMs must be utilized in alignment with existing privacy laws. For this purpose, concepts such as data privacy, purpose and entitlements must be considered.
- **Data Governance**: Data administrators must ensure that data assets are used appropriately. This includes from the perspective of security and privacy as well with terms of use (for example, copyright, licensing). Moreover, these products must be properly documented and understood.

> [!NOTE]
> Note
> 
> Gencore AI supports compliance with a range of global AI laws and regulations. For a full list of frameworks that Gencore AI supports, see the [Regulations](https://securiti.ai/solutions/) page.

The Gencore AI module is designed to easily and quickly build safe, enterprise-grade generative artificial intelligence (GenAI) systems, copilots and AI agents. It accelerates GenAI adoption in the enterprise by making it easy to build unstructured data with [GenAI pipelines](/latest/docs/using-genai-pipelines) utilizing proprietary enterprise data across hundreds of diverse data systems and applications.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Key capabilities include:

- **Build safe enterprise AI copilots**: With GenAI pipelines, implement rule-aware AI copilots across your organization's data anywhere.
- **Data vectorization and ingestion**: Convert unstructured files into AI-ready formats, syncing to Vector database.
- **Data curation and sanitization for AI**: Transform raw unstructured files into AI-ready data.
- **Context-aware LLM Firewalls**: Protect AI interactions with intelligent Retrieval firewall, Response firewall, and Prompt firewall.
- **Data selection and ingestion**: Securely ingest data with native connectors, define data scope, and apply learned enterprise controls like access entitlements at the AI usage layer.
- **Data extraction and normalization**: Extract and parse information from multiple file formats while preserving context and relationships for enhanced vector database comprehension.
- **Data classification and sanitization**: Classify, [redact](/v1/docs/data-sanitizer) or anonymize Sensitive data while maintaining privacy and compliance before ingestion of data into your selected AI model.
- **Data vectorization**: To prepare enterprise data for LLM usage, choose from multiple [embedding models](/v1/docs/configuring-llm-providers) to create Embeddings with metadata for Storage in a Vector of choice.
- **LLM selection**: Choose from various Large Language Model (LLM) to design an AI system tailored to your business goals and specific use case requirements.
- **LLM Firewalls**: Secure your AI interactions with natural language conversation-aware LLM firewalls using Policies to prevent attacks, deter data leaks, and support alignment with your objectives.
- **Efficient data retrieval**: Indexing and retrieval of data to support quick searches, enabling efficient retrieval based on user queries or search criteria.
- **Real time interaction via a variety of endpoints**: Interact with your GenAI pipeline in real-time via web widgets, a dedicated user portal, or chatbots [integrated with external messaging applications](/latest/docs/configuring-messaging-app-integrations).
- **AI system provenance**: Visualize sensitive data flow, generate audit trails, and map relationships between data, AI models, entitlements, AI agents, and governance controls.

> [!NOTE]
> **Note**
> 
> Discover how Gencore AI empowers you to rapidly develop secure, enterprise-grade AI systems, copilots, and agents swiftly by harnessing proprietary data across various systems and applications, see [Gencore AI: Building Safe, Enterprise-grade AI Systems in Minutes](/v1/docs/securiti-pods-and-elastic-pods).

A large language model (LLM) represents a category of artificial intelligence (AI) programs adept at both recognizing and generating text, among other versatile tasks.

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.

This firewall uses policies to assess queried data by the LLM before providing it to the LLM.

This firewall uses policies to assess responses for prohibited outputs.

This firewall uses policies to assess prompts and access patterns for suspicious or prohibited inputs.

Sensitive data can constitute any unit or set of data that an organization deems valuable and should have specific security controls or governance applied to it. Examples may include, but are not limited to the personal data of customers, patients, employees, or business partners.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

Entity in the storage state, for example, an asset which is storing data.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

A firewall that prevents sensitive data from being input into or leaked by LLMs. This involves checking the information going in to make sure it's not sensitive or unauthorized, controlling what the LLMs share, and making sure they follow rules to produce safe and contextually appropriate responses.

You can create data policies as a Glossary in the Enterprise Data Catalog and then relate them to the proper metadata to help data users understand how data can be used.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using firewall profiles](/using-firewall-profiles.md)
