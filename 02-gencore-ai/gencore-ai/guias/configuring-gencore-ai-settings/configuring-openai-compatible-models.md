---
title: "Configuring OpenAI-Compatible models"
slug: "configuring-openai-compatible-models"
updated: 2025-12-09T10:11:25Z
published: 2025-12-09T10:11:25Z
canonical: "helpcenter.securiti.ai/configuring-openai-compatible-models"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring OpenAI-Compatible models

For OpenAI, along with selecting preconfigured models, Gencore AI also supports configuring OpenAI-compatible models.

To configure your own custom model:

1. On the LLM Providers page, click **Add Credentials**.

![Add LLM provider](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM providers Add Creds(1).png)
2. Select **Generic OpenAI-Compatible**.

![Select Custom Model](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/OpenAI model.png)
3. Click **Add Credentials**.

![Custom model - Add Credentials](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/OpenAI model add creds.png)
4. On the **Add Provider Credentials** popup, add the credentials and relevant information:
  1. Enter the **Name** for the model.

![Custom_Model_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a697f408-ec2a-5bee-38a4-05cc8f8d67e5(1).png)
  2. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(258).png)
    1. Enter **Base Endpoint URL**. For example: `https://integrate.api.openai.com/v1`, or a custom link of your own.
  3. In the **Custom Models** section, [add custom models](/v1/docs/configuring-openai-compatible-models#add-custom-models). You can add multiple models.
  4. Enter the **API Key**.
  5. To set this provider instance as the default in pipeline configuration, enable the **Set as Default** toggle.

![Set_as_default_toggle_enabled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-798d6599-67f9-eca4-c327-c72e635e59fd(1).png)
  6. Choose how you want to save the configuration:
    - To validate the credentials and save the details:
      1. Enable the toggle **Validate Credentials**.
      2. Click **Validate and Save Credentials**.

![Validate_toggle_and_save_creds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81655d08-79e8-8c24-e858-a6065130e967(1).png)
    - To save the information without validating the credentials:
      1. Disable the **Validate Credentials** toggle.
      2. Click **Save Credentials**.

![validate_disabled_and_save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34dfe0c5-7f12-532f-a300-13bfc822ffe4(1).png)

### Add custom models

To define custom models for **Generic OpenAI-Compatible** provider, in the **Custom Models** section:

1. Click **Add Custom Model**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(260).png)
2. Enter the **Name** for the model.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(261).png)
3. Enter the value for the **Context Window**. The context window specifies the maximum amount of text (tokens) the model can process at once, both input and output combined.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(262).png)

> [!NOTE]
> **Important**
> 
> Provide an accurate number for the Context Window Size.
> 
> - If the value is too low, it may truncate input unnecessarily.
> - If the value is too high, it can lead to model execution failures.
4. To add more models, click **Add Custom Model**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(263).png)
5. To set the model as the default, select **Default**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(264).png)
6. To remove a model, click Delete.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(265).png)

A provider of embeddings generator refers to a system or service that generates word or sentence embeddings.

An endpoint is a specific URL or URI (Uniform Resource Identifier) that an API exposes for communication.

An API key is a unique identifier used to connect to, or perform, an API call.

## Related

- [Configuring LLM providers](/configuring-llm-providers.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
