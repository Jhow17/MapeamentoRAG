---
title: "Gencore AI release notes"
slug: "gencore-ai-release-notes"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/gencore-ai-release-notes"
area: gencore-ai
modulo: gencore-ai
tipo: release
data_captura: 2026-10-08
---

# Gencore AI release notes

## 1.151

### Release updates - September 2026

#### Adding new models and model cards

Securiti has added support for new models and model cards, giving you more options when you configure AI pipelines and letting you compare model capabilities before you select one.

**Newly supported models**

Use the following table to understand the details of the newly supported **OpenAI** models:

| Model | Description |
| --- | --- |
| GPT 5.6 Sol | Advanced reasoning and problem-solving capabilities for complex coding, analysis, and knowledge-intensive use cases. |
| GPT 5.6 Terra | Balances performance and efficiency for general-purpose conversational AI, content generation, and reasoning use cases. |
| GPT 5.6 Luna | Provides fast, efficient responses for everyday conversational AI, content generation, and high-volume use cases. |

**Newly supported model cards**

Use the following table to understand the details of the newly supported model cards:

| Provider | Models |
| --- | --- |
| OpenAI | - GPT 5.5 - GPT 5.6 Sol - GPT 5.6 Terra - GPT 5.6 Luna |
| Vertex AI | - Gemini 3.1 Flash Lite - Gemini 3.5 Flash - Gemini 3.5 Flash Lite - Gemini 3.6 Flash |
| Google AI Studio | - Gemini 3.1 Flash Lite - Gemini 3.5 Flash - Gemini 3.5 Flash Lite - Gemini 3.6 Flash |

For more information, see [Configuring LLM providers](/latest/docs/configuring-llm-providers) and [Using Gencore AI Gallery](/latest/docs/using-gencore-ai-gallery).

#### API updates

Use the following table to understand the API updates made for Gencore AI in this release:

**Retrieve API**

We have introduced the following updates in the **Retrieve API**.

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/gencore/v1/retrieve` | POST | **Updates:** We have made the following changes to the response body: - `data`: This response body parameter is now an array of objects containing retrieved content and its associated metadata. Each object includes `content`, `author`, `title`, `resource_id`, `datasource_id`, and `type`. - `query_correlation_id`: We have added this response body parameter to provide the correlation ID associated with the query. > [!WARNING] > Deprecation > > Securiti has deprecated the `pipeline_terminated`, `terminate_session`, and `meta `response body parameters due to due to their irrelevance to the Retrieve endpoint, whose response is designed to be consumed by downstream applications rather than read directly. |

---

For more information, see [Gencore AI API reference](https://securiti-doc-router.securiti.ai/modules/gencore/genia_apidocs/index.html).

---

## 1.150

### Release updates - August 2026

#### Aligning the firewall module's metadata explorer with the platform-level explorer

Securiti now aligns the Firewall module's metadata explorer with the platform-level metadata explorer used across other modules, giving you a consistent view no matter which module you're working in. Opening the explorer for a firewall profile, firewall policy, or firewall rule shows the same layout and fields as elsewhere in the platform, including details, policies, pipelines, violations, creation and modification dates, integration ID, and owner.

For more information, see [Using firewall profiles](/latest/docs/using-firewall-profiles), [Using LLM firewall policies](/latest/docs/using-llm-firewall-policies), and [Using firewall rules](/latest/docs/using-firewall-rules-1).

#### Surfacing re-ingestion warnings inside the Test prompt window

Securiti now surfaces a re-ingestion warning inside the Test prompt window when you change a pipeline's embedding provider or vector store. Previously, this notice only appeared in the main pipeline builder's banner, so anyone testing from the Test prompt window had no visibility into it. The warning now appears in the status indicator across all Test prompt experiences and clears automatically once you re-ingest the pipeline's data, so you always know whether you're testing against current results.

![Warning about re-ingestion required, with session validation results displayed below.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reingestion message in test prompt expanded(1).png)

For more information, see [Creating a pipeline](/latest/docs/creating-a-new-pipeline).

#### Adding new LLMs and deprecating outdated ones

Securiti has added support for new models and deprecated select existing models, keeping the supported models list current while giving you access to newer capabilities, improved performance, and greater flexibility when configuring AI pipelines.

**Additions in LLMs**

Use the following table to understand the details of the newly supported models:

| Model | Description |
| --- | --- |
| Gemini 3.1 Flash Lite | Available through Google Vertex AI and Google AI Studio, **Gemini 3.1 Flash Lite** lets you generate fast, lightweight responses for simple, high-volume conversational AI and basic content generation use cases. |
| Gemini 3.5 Flash | Available through Google Vertex AI and Google AI Studio, **Gemini 3.5 Flash** lets you balance speed and quality for conversational AI, document summarization, and general content generation use cases. |
| Gemini 3.5 Flash Lite | Available through Google Vertex AI and Google AI Studio, **Gemini 3.5 Flash Lite** lets you generate low-latency responses for high-volume, cost-sensitive conversational AI and lightweight content generation use cases. |
| Gemini 3.6 Flash | Available through Google Vertex AI and Google AI Studio, **Gemini 3.6 Flash** lets you retrieve fast, high-quality responses for conversational AI, real-time chat, and high-throughput content generation use cases. |

**Deprecations in LLMs**

The following model is no longer available:

| Provider | Model | Action rquired |
| --- | --- | --- |
| OpenAI | GPT-3.5 | If any of your GenAI pipelines still use GPT-3.5 Turbo, switch them to a supported model to avoid disruption. |

For more information, see [Configuring LLM providers](/latest/docs/configuring-llm-providers).

#### Resolved issue

- Fixed an issue where the **Firewall rule Action** menu let you select REDACT for rules that do not support redaction, such as **Regex Pattern Match** and **Source Code** rules. This could result in a misconfigured policy that silently failed to mask sensitive data (PRIV-245353).

---

## 1.149

### Release updates - August 2026

#### Updated deployment configuration for self-hosted user portals

Securiti has updated the **Firewall** page for self-hosted user portals, which is now called **Deployment Configuration**. In addition to selecting and configuring firewall deployment, you can now optionally configure the **Ingress Controller class**, **TLS secret**, and **custom annotations** used to expose and secure the User Portal. You must also route the custom domain to the Ingress controller's IP address or hostname through DNS, and ensure a valid TLS certificate is available in the cluster.

For more information, see [Configuring user portals](/latest/docs/configuring-user-portal).

#### Support for GPT 5.5

Securiti now supports GPT 5.5 as an LLM and embedding model for pipeline workflows. Available through OpenAI, GPT 5.5 provides improved reasoning, coding, and instruction-following capabilities for enterprise AI applications. This addition expands model choice across generative AI and retrieval use cases.

For more information, see [Configuring LLM providers](/latest/docs/configuring-llm-providers).

#### Supporting pipeline validation and timestamps in Test Prompt

Securiti now validates your pipeline's mandatory steps and credentials in Test Prompt before you run a query, showing a ready or not-ready status along with the time it was last checked. Earlier, you could discover that a pipeline is misconfigured, such as missing required steps or invalid credentials, only after a test query failed. With validation, a three-dot menu next to the status reveals a per-component breakdown of what passed or failed, covering standard, streaming, and appliance-routed pipelines alike. Separately, hovering over a message in a test prompt conversation now shows the date and time it was sent, next to the username, making it easier to track timing in longer conversations.

For more information, see [Creating a new pipeline](/latest/docs/creating-a-new-pipeline#testing-the-pipeline).

#### Removing the Rule filter from Exemplars

We have simplified the **Exemplars** page by removing the Rule filter, keeping the page focused on exemplar-specific details.

For more information, see [Using Exemplars](/latest/docs/using-exemplars).

#### API updates

The following table helps you understand the API updates made for Gencore AI in this release:

**Pipeline health validation**

We have introduced the following updates in pipeline testing.

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/gencore/query/pipeline/ping` | POST | We have added this API endpoint in the current release. This API lets you validate the pipeline’s overall health and the configuration and health of the required components. |

**Configuring Ingress controller**

Securiti has introduced the following updates in the user portal deployment configuration.

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/core/v1/admin/appliance/{applianceID}` | PATCH | **New additions:** The request body now supports an `ingress` object under `genstack_appliance` for configuring how the user portal is exposed and secured through Kubernetes Ingress. The following fields have been added: - `ingress_class_name`: Specifies the Ingress Controller class, such as `nginx`. - `tls_secret_name`: Specifies the Kubernetes secret containing the TLS certificate and private key. - `annotations`: Specifies custom key-value annotations for controlling Ingress behavior. |

For more information, see [Gencore AI API reference](https://securiti-doc-router.securiti.ai/modules/gencore/apidocs/index.html).

---

## 1.148

### Release updates - July 2026

#### Improving error visibility in the Test pipeline dialog

We have improved error reporting for your GenAI pipelines in the Test pipeline dialog, making it easier to identify and troubleshoot pipeline configuration and query failures. Previously, connectivity failures could appear as generic errors in the Test pipeline dialog, making them difficult to distinguish from authentication issues. With this enhancement, Gencore AI now:

- Clearly differentiates connectivity failures from authentication errors in backend logs.
- Displays more meaningful error messages in the Test Prompt interface when queries fail.
- Provides clear feedback when an internal VectorDB endpoint is configured but accessed from the SaaS portal.

These improvements help you quickly diagnose configuration issues and reduce troubleshooting time.

For more information, see [Creating a new pipeline](/latest/docs/creating-a-new-pipeline).

#### Resetting analytics filters with the Clear Filters button

Securiti now lets you reset all applied filters on the Gencore AI **Analytics** dashboard back to their default state with a new **Clear Filters** button. Previously, you had to clear the filters by refreshing the page. The **Clear Filters** button, available directly in the dashboard toolbar, restores the default view immediately and refreshes the underlying data.

For more information, see [Using Gencore AI Analytics](/latest/docs/using-gencore-ai-analytics).

#### Additions and deprecations in LLMs

Securiti has introduced new models in Gencore AI, giving you more flexibility when selecting large language models for AI-powered workflows while continuing to enforce Gencore AI's built-in security and governance controls.

**Additions in LLMs**

Use the following table to understand the details of the newly supported models:

| Model | Description |
| --- | --- |
| GPT 5.4 | Available through OpenAI, GPT 5.4 lets you retrieve accurate and context-aware responses for conversational AI, knowledge retrieval, and content generation use cases. |
| GPT 5.4 mini | Available through OpenAI, GPT 5.4 mini provides fast, cost-efficient responses for conversational AI, knowledge retrieval, and content generation use cases. |
| GPT 5.4 nano | Available through OpenAI, GPT 5.4 nano delivers lightweight responses for high-throughput conversational AI, knowledge retrieval, and content generation use cases. |
| Claude Sonnet 4.6 | Available through Anthropic, Claude Sonnet 4.6 offers a balanced mix of speed and intelligence, ideal for conversational AI, knowledge retrieval, and content generation use cases. |
| Claude Opus 4.6 | Available through Anthropic, Claude Opus 4.6 delivers advanced reasoning and nuanced understanding for complex conversational AI, knowledge retrieval, and content generation use cases. |
| Claude Opus 4.7 | Available through Anthropic, Claude Opus 4.7 builds on the Opus line with improved reasoning and comprehension for demanding conversational AI, knowledge retrieval, and content generation use cases. |
| Claude Opus 4.8 | Available through Anthropic, Claude Opus 4.8 provides Anthropic's most capable reasoning and highest accuracy for sophisticated conversational AI, knowledge retrieval, and content generation use cases. |

**Deprecations in LLMs**

The following models are no longer available:

| Provider | Models |
| --- | --- |
| Anthropic | - Claude Opus 4 - Claude Sonnet 4 - Amazon Bedrock: - Amazon Titan Embeddings G1 - Text - Amazon Titan Text G1 - Express - Amazon Titan Text G1 - Lite - Anthropic Claude Haiku 3.5 - Anthropic Claude Sonnet 3.5 v2 - Anthropic Claude Sonnet 3 - Anthropic Claude Sonnet 3.7 - Anthropic Claude Opus 4 - Anthropic Claude Sonnet 4 - Google AI Studio: - Gemini 2.0 Flash - Latest Version - Gemini 2.0 Flash - Version 001 - Gemini 2.0 Flash Lite - Latest Version - Gemini 2.0 Flash Lite - Version 001 |
| Amazon Bedrock | - Amazon Titan Embeddings G1 - Text - Amazon Titan Text G1 - Express - Amazon Titan Text G1 - Lite - Anthropic Claude Haiku 3.5 - Anthropic Claude Sonnet 3.5 v2 - Anthropic Claude Sonnet 3 - Anthropic Claude Sonnet 3.7 - Anthropic Claude Opus 4 - Anthropic Claude Sonnet 4 |
| Google AI Studio | - Gemini 2.0 Flash - Latest Version - Gemini 2.0 Flash - Version 001 - Gemini 2.0 Flash Lite - Latest Version - Gemini 2.0 Flash Lite - Version 001 |
| NVIDIA | - DBRX Instruct - DeepSeek R1 - Llama3.1 405B Instruct - Llama 4 Maverick - Llama 4 Scout - Mistral 7B Instruct - Llama3.1 Nemotron 51B Instruct - Llama3.1 Nemotron 70B Instruct - NVIDIA Retrieval QA Mistral 7B Embedding |
| NVIDIA NIM | - Llama 3.1 405B Instruct |
| OpenAI | - GPT-4 Turbo - Model released Jan 25, 2024 - GPT-4 Turbo - Model released Nov 06, 2023 |
| Vertex AI | - Gemini 2.0 Flash - Gemini 2.0 Flash - Lite Version - GPT-4 Turbo - Model released Jan 25, 2024 - GPT-4 Turbo - Model released Nov 06, 2023 |

You can choose the model that best aligns with your performance, cost, and deployment requirements for each AI-powered workflow.

For more information, see [Configuring LLM providers](/latest/docs/configuring-llm-providers).

---

## 1.147

### Release updates - June 2026

#### Introducing new Firewall Safety Topic Analyzer for LLM Firewalls

Securiti has introduced a new **Firewall Safety Topic Analyzer** (General Malicious Intent Analyzer) in LLM Firewalls designed to identify and block a broad range of harmful, deceptive, and policy-violating prompts before they reach downstream AI systems. Powered by an **mmBERT-based classification model**, this analyzer provides enhanced detection accuracy and broader threat coverage compared to the existing exemplar-based approach. Internal evaluations show efficacy comparable to larger LLaMA 1B-based models while delivering improved performance across supported threat categories.

The analyzer helps detect prompts associated with:

- Jailbreak Instructions
- Prompt Injection
- IT Phishing
- Authentication Phishing
- PII Phishing
- Financial Data Phishing

In addition, the analyzer incorporates content safety categories aligned with the Purple LLaMA framework, including:

- Violence and Hate
- Self-Harm
- Criminal Planning
- Guns and Illegal Weapons
- Regulated or Controlled Substances

By consolidating multiple threat and safety categories into a single classifier, organizations can strengthen protection against malicious user inputs, social engineering attempts, jailbreak attacks, and unsafe content while improving detection efficiency and simplifying policy enforcement.

For more information, see [Understanding analyzers, rules and policies](/latest/docs/understanding-analyzers-rules-and-policies).

#### Additions and deprecations in Gencore AI LLMs

Gencore AI now supports additional LLMs while removing deprecated models to align with vendor support lifecycles and ensure a seamless user experience.

**Addition of LLMs**

Gencore AI has expanded its support to the following new models. These models give you additional flexibility when selecting large language models for AI-powered workflows.

| Model | Description |
| --- | --- |
| Gemini 3.0 Flash | Available through Google AI Studio and Vertex AI, Gemini 3.0 Flash delivers fast, cost-efficient inference, making it well-suited for high-volume AI applications and real-time user interactions. |
| GPT 5.2 | Available through OpenAI, GPT 5.2 provides advanced reasoning and language capabilities, enabling more sophisticated AI experiences for complex enterprise use cases. |

With this enhancement, you can choose from a broader range of supported models to meet your performance, cost, and deployment requirements while leveraging Gencore AI’s existing security, governance, and orchestration capabilities.

**Deprecation of Gemini 3.0 Pro support**

Gencore AI no longer supports Gemini 3.0 Pro following its deprecation by the model provider. Existing security, governance, and orchestration features remain available for all supported models.

For more information, see [Configuring LLM providers](/latest/docs/configuring-llm-providers).

#### Supporting Dual Triton Server deployment for user portal installation

For user portal installation, Gencore AI has enhanced the underlying AI model serving infrastructure to improve scalability, performance, and reliability as the number of supported models continues to grow. Previously, all models ran on a single GPU-backed inference server, which could lead to memory constraints; now, models are distributed across multiple GPU-backed servers with intelligent request routing for improved scalability and reliability.

Key benefits include:

- Improved platform stability by preventing GPU memory exhaustion.
- Better performance and reliability for model inference requests.
- Independent scaling of model-serving resources based on demand.
- Increased flexibility to support additional models in the future.

> [!NOTE]
> Note
> 
> This enhancement increases the GPU requirement for the Triton model-serving infrastructure from 1 GPU to 2 GPUs, with models distributed across both GPUs to optimize resource utilization and performance. Additionally, it does not require changes to existing integrations or workflows.

For more information, see [Self-hosted user portal installation](/latest/docs/self-hosted-user-portal-installation).

#### Enhanced time range filtering for Unique User Portal Logins widget

Securiti has enhanced the user experience of analytics charts displaying data for the last 30 days by improving the visibility of zero-value data points. The **No. of Unique User Portal Logins** widget now explicitly displays zero-value indicators at relevant intervals, making it easier to distinguish between periods with no activity and missing data.

This enhancement improves the consistency and reliability of portal usage analytics to track user engagement trends more accurately.

For more information, see [Using Gencore AI Analytics](/latest/docs/using-gencore-ai-analytics).

#### Known issue

- Data Sanitizer may not generate an output file when processing files larger than **5 MB** (PRIV-244291).

**Workaround:** Data Sanitizer supports output generation only for files up to **5 MB**. For supported files, Securiti generates the output as follows:

- For `CSV`, `JSON`, `NDJSON`, `XML`, and **Plain Text** files, Securiti generates the output in the same format as the source file.
- For `PDF`, `XLSX`, and **other non-text** formats, Securiti generates the output in `.txt` format.

## Related

- [Using Gencore AI](/using-gencore-ai.md)
