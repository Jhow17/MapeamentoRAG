---
title: "Retrieval Firewall"
slug: "retrieval-firewall"
updated: 2025-12-09T09:50:12Z
published: 2025-12-09T09:50:12Z
canonical: "helpcenter.securiti.ai/retrieval-firewall"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Retrieval Firewall

**Scenario**

As a Data Privacy Officer, you must ensure that only approved information is retrieved and passed to the LLM. Without control at the retrieval stage, sensitive data may surface unknowingly. With the **Retrieval Firewall** node, you apply a policy profile that evaluates retrieved records before they reach the model. It allows, blocks, or warns based on rule violations, helping you prevent accidental exposure at the source.

The Retrieval Firewall node lets you select the policy profile that you want to use in the retrieval of results from the Embeddings Retriever to the LLM. The profile contains policies and rules that evaluate the data retrieved and makes decisions to allow the response to reach the LLM or to block or warn.

The Retrieval Firewall node analyzes the data retrieved by the LLMs for RAG use cases. For example:

- Redaction of sensitive data during retrieval
- Ensuring relevance and accuracy of the retrieved data
- Monitoring retrieved data for data poisoning or indirect prompt injections

It is important to be able to implement organization-wide standards on the types of information exposed to models and LLMs for any RAG use case.

### Defining the Retrieval Firewall

To define your retrieval firewall:

1. Click **Add** (+) to enable the **Retrieval Firewall** node.
2. Select the policy profile for the firewall. You can select one policy to be configured with the firewall.

![Configuration screen for Retrieval Firewall with profile selection options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/retrieval fw.png)
3. When you are satisfied with the provided details, click **Save and Continue** to proceed to the [**LLM Selection**](/v1/docs/llm-selection) stage.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A system or component that retrieves relevant information from a large dataset or knowledge base. Retrievers play a crucial role in tasks such as question-answering systems, information retrieval, and search engines.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Embeddings Retriever](/embeddings-retriever.md)
