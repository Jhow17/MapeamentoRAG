---
title: "Response Firewall"
slug: "response-firewall"
updated: 2025-12-09T09:50:51Z
published: 2025-12-09T09:50:51Z
canonical: "helpcenter.securiti.ai/response-firewall"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Response Firewall

**Scenario**

As a Data Security Officer, you need to ensure that LLM responses in RAG workflows never expose sensitive or unauthorized information. Reviewing outputs manually is impractical and unreliable. By configuring the **Response Firewall** node, you automatically enforce policies on every response before it reaches the user. It detects and blocks disallowed content, helping you prevent data leaks while keeping AI interactions safe and controlled.

You can configure the Response Firewall node to enforce policies on the LLM responses. As with retrieval firewall, the response firewall node evaluates the information shared with the end users for Retrieval-Augmented Generation (RAG) use cases.

### Defining the Response firewall

To define your response firewall:

1. Click **Add** (+) to enable the **Response Firewall** node.
2. Select the relevant response profile.

![Response profile selected](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Response profile selected.png)

Securiti displays the profile attributes. To view the details, click ​**Details**​​.

![Response profile details](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Response profile details.png)
3. When you have selected the response profiles, click **Save and Continue** to proceed to the [**Assistant API**](/v1/docs/assistant-api) node.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

Retrieval-Augmented Generation (RAG) is an architectural approach designed to enhance the performance of large language model (LLM) applications by incorporating custom data. It achieves this by retrieving relevant data or documents related to a given question or task and supplying them as context to the LLM.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using firewall profiles](/using-firewall-profiles.md)
