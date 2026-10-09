---
title: "Configuring LLM providers"
slug: "configuring-llm-providers"
status: "update"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-llm-providers"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring LLM providers

**Scenario**

As a Data Governance Officer, you're responsible for ensuring teams use approved LLMs and embedding models in GenAI projects. Without a central configuration, teams might use inconsistent or unvetted models. On the **LLM Providers** page, you configure approved models for use across all pipelines. This ensures alignment with organizational standards, improves traceability, and accelerates safe AI adoption.

On the **LLM Providers** page, you can manage access to LLM models by setting up providers and API keys. To open the **LLM Providers** page, in Securiti, open Gencore AI, choose **Settings** and select **LLM Providers**.

![LLM providers dashboard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM providers.png)

> [!NOTE]
> Note
> 
> Gencore AI connects directly to each LLM provider using the relevant provider's native SDK. To see the complete list of embedding models and LLMs that Gencore AI supports, see [Supported embedding models and LLMs](/latest/docs/supported-embeddings-models-and-llms).

The LLM providers page offers the following capabilities:

- A widget displays the number of providers.
- Search for LLM providers.
- Addition, editing and deleting an LLM provider.
- Disabling or enabling an LLM provider.
- Sorting and filtering LLM providers.
- Sort providers based on **Name** and **Creation date**.

## Prerequisites

To add your LLM provider and configure its relevant models, you must have an active account on the provider portal.

## Add LLM providers

To set up your LLM provider:

1. Click **Add Credentials**.

![LLM providers - Add Credentials](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM providers Add Creds.png)
2. Select the provider.

![Overview of AI models including Claude Haiku 4.5 and their features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select Anthropic provider.png)

By default, Securiti displays both embedding models and LLMs. To display embedding models or LLMs:
  1. Click **Model Type** dropdown.
  2. Select model type.

![Overview of AI models with Claude Haiku 4.5 highlighted for user selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Type.png)
3. Select the relevant model.

![Claude Haiku 4.5 highlighted as a high-speed AI model for various tasks.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select LLM.png)
4. Click **Add Credentials**.

![Overview of Claude Haiku 4.5 AI model with features and access information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLMs Add Creds.png)
5. In the **Add Provider Credentials** popup, add the credentials.

![Form to add provider credentials for Anthropic, including name and API key fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add provider creds-name-apiKey.png)
6. To set this provider instance as the default selected instance in the pipeline, enable the toggle **Set as Default**.

![Set provider as default toggle](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add provider creds-default.png)
7. Select the relevant **model(s)**.

![Selecting the active model 'Claude Haiku 4.5' in provider credentials settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add provider creds select models - active.png)
8. To save the details:
  - To validate the credentials and save the details:
    1. Enable the toggle **Validate Credentials**.

![Form to add provider credentials with options to validate model](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add provider creds-validate creds.png)
    2. Click **Validate and Save Credentials**.

![validate and save creds](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/validate and save creds.png)
  - To save the information without validating the credentials:
    1. Disable the **Validate Credentials** toggle.

![disable validate credentials](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Disable validate.png)
    2. Click **Save Credentials**.

![Save credentials](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Save Creds.png)

> [!NOTE]
> **Note**
> 
> Gencore AI also supports OpenAI-compatible LLM proxies. To configure a proxy, add it as a Generic-OpenAI Compatible provider. For more information, see [Configuring OpenAI-Compatible models](/v1/docs/configuring-openai-compatible-models).

### Adding varied credentials for providers

Different providers may require you to configure different credentials.

### **Amazon Bedrock and Amazon Sagemaker**

In case of **Amazon Bedrock** and **Amazon Sagemaker**, you can choose between the following Authentication methods:

1. Enter Name.
2. Select **Auth Method**:
  - **IAM Role based**: Requires you to create an IAM role on the AWS Console.
    1. Provide details for **Region**, **Account ID**, and **Role name**.
    2. Download the **CloudFormation** template and create the role in your AWS environment.
  - **Credentials based**: Provide details for **Access Key ID**, **Secret Access Key**, and **Region**.

### Azure OpenAI

For Azure OpenAI, enter the following credentials:

- Name
- API Key
- Endpoint

### **NVIDIA NIM**

For NVIDIA NIM, enter the following credentials:

- Name
- API Key
- Endpoint
- Additional Headers

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Vertex AI

For Vertex AI:

1. Enter the following credentials:
  - Name
  - Project
  - Location
2. Under Service Account Credentials Json, Upload your json file from your GCP portal. For more information, see [Service Account Credentials](https://cloud.google.com/iam/docs/service-account-creds) for GCP.

## Sorting and filtering LLM providers

You can sort LLM providers based on Name and Created date. You can Filter LLM providers based on Status, Name, and Provider.

![LLM providers - filters](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM providers filters.png)

- **Status**: To filter the providers based on the status:
  1. Select a parameter:
    - Equals
    - Not equals
  2. Select status:
    - Active
    - Inactive
  3. Click **Apply**.
- **Name**: To filter providers based on the name:
  1. Select a parameter:
    - Equals
    - Not equals
    - Is one of
    - Is not one of
    - Contains
    - Not contains
    - Begins with
    - Not begins with
    - Ends with
    - Not ends with
  2. Enter keyword or phrase for the name.
  3. Click **Apply**.
- **Provider**: To filter providers based on the provider name:
  1. Select a parameter:
    - Equals
    - Not equals
    - Is one of
    - Is not one of
  2. Select the provider. You can select multiple providers.
  3. Click **Apply**.
- **Default**: To filter providers based on the default status:
  1. Select a parameter:
    - Equals
    - Not equals
  2. Select:
    - True
    - False
- **Model**: To filter providers based on the model:
  1. Select a parameter:
    - Contains
    - Not contains
  2. Select LLM providers.
  3. Click **Apply**.
- **Type**: To filter providers based on the type:
  1. Select type(s):
    - LLM
    - Embedding Indexer
  2. Click **Apply**.

> [!NOTE]
> Important
> 
> In some cases, models may deprecate. To replace a deprecated mode with an updated version, see [Replacing deprecated models](/latest/docs/replacing-deprecated-models).

Authentication is a fundamental process in information security, access control, and many other contexts where security and trust are important. It is typically achieved through the presentation of credentials or evidence that establishes the identity of the party seeking access or authorization.

An API key is a unique identifier used to connect to, or perform, an API call.

An endpoint is a specific URL or URI (Uniform Resource Identifier) that an API exposes for communication.

A project is created using different frameworks and associated with categories or subcategories to track the progress of specific compliance frameworks. A project includes specific scope and controls. This helps to track progress on specific compliance goals. For instance, the data governance team may have Projects to apply the CDMC framework to various data systems. These Projects may have different owners and target specific systems. Each owner can define their own projects to track progress toward their goals.

A set of criteria that focuses your view by eliminating elements that fall outside the scope of interest. When you filter Securiti pages and dashboards, you choose criteria in the filter panel to reduce the number of elements Securiti displays to just those of interest.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using firewall profiles](/using-firewall-profiles.md)
