---
title: "Assistant API"
slug: "assistant-api"
updated: 2026-04-28T03:14:18Z
published: 2026-04-28T03:14:18Z
canonical: "helpcenter.securiti.ai/assistant-api"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Assistant API

Once your pipeline nodes are configured, the pipeline is ready for consumption in the following ways:

- A service endpoint
- Self managed widget
- Self managed portal

In this node, you can create API Keys specific to the pipeline. API Keys are unique authentication tokens or credentials that are used to authenticate and authorize requests made to external APIs or services. You can use the API Keys as a secure way to authenticate requests between the chatbot and the external services it interacts with.

> [!NOTE]
> **Note**
> 
> To view any of the Gencore AI entities:
> 
> - Go to the Inventory page.
> - Find the pipelines on this page by searching for Gencore AI and selecting **Gencore AI Pipelines**.
> - Select your pipeline. The relevant Instance Explorer displays a complete overview of all the pipeline elements.

Click **Add (+)** to enable the **Assistant API** node.

In the Assistant API node, you can define settings for:

- [Web widgets](/v1/docs/configuring-web-widgets)
- [External OAuth for entitlements](/latest/docs/assistant-api#external-oauth-for-entitlements)
- [User portals](/latest/docs/assistant-api#user-portal)
- API Keys

## Web Widgets

Use this section to bind your pipeline to one or more web widgets so users can interact with the pipeline directly through embedded widgets.

1. Click **Enable pipeline** in Web Widget to enable the pipeline in your widget settings.
2. Select the web widget you want to bind to the pipeline. You can select multiple web widgets.

![Assistant API - Enable pipeline in web widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assistant API - web widget.png)
3. To open the Web Widget settings, click **Web Widget**.

![Configuration settings for enabling a pipeline in the Web Widget interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assistant API web widget settings.png)

> [!NOTE]
> Note
> 
> To learn more about configuring web widgets, see [Configuring Web Widgets](/latest/docs/configuring-web-widgets).

## External OAuth for entitlements

In this section, you can configure the OAuth provider for pipelines with entitlements enabled. This lets you extract user identity from external OAuth tokens provided during [Conversations API](https://securiti-doc-router.securiti.ai/modules/gencore/genia_apidocs/index.html#operation/conversation_api_genia) and Web Widget integrations.

> [!WARNING]
> Important
> 
> Ensure you have [added external OAuth providers](/latest/docs/using-oauth-providers).

1. Click **Enable External OAuth Provider**.

![Configuration settings for enabling an external OAuth provider in pipelines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Enable ext oauth for entitlements.png)
2. In **External OAuth Provider for Entitlements** field, select the your external OAuth provider from the list.

![Configuration settings for External OAuth Provider with Okta as the selected option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select ext oauth provider.jpg)

## User Portal

Use this section to make the pipeline available in the User Portal so users can interact with it directly.

1. Click **Enable pipeline in User Portals** to enable the pipeline in the portal.

![User portal interface showing option to enable pipeline in user portals.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enable pipeline in user portals.png)
2. Select user portal.

> [!WARNING]
> Important
> 
> Ensure you have created [user portals](/latest/docs/configuring-user-portal).

![User portal interface displaying various self-hosted options and details for Securiti Default.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/select user portal.png)
3. Enter a **Display Name**. This name appears for the pipeline in the user portal. If left empty, the pipeline name is used.

![Display name for the pipeline in the user portal is RAG 143 CF.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/display name for user portal.png)

### Configure Suggested Prompts

You can define suggested prompts that appear in the user portal to guide users.

1. Enable the **Configure Suggested Prompts** toggle.
2. Enter a prompt.
3. Click **Add**.

![Suggested prompts for configuring user queries about SSO and data access policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assistant API - config suggested prompts.png)

> [!NOTE]
> Note
> 
> You can configure multiple prompts.

### Configure Access Exception Rules

You can define rules to manage exceptions for pipeline access in the portal.

1. Click **Add** in Access Exception Rules.

![Access_Exception_Rules_-_Plus_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8da9480a-9859-38c7-d105-ac052e9aef16(1).png)
2. In the popup, click **Edit** to set the attribute name.

![AER_popup_Attribute_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-972db0ba-8517-0bfb-cdbe-1bf29c7b7d0d(2).png)
3. Enter the attribute name and click **Save**.

![AER_Update_Attribute_name_Email_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b53c9244-fea8-5857-c857-6f3610415747(2).png)
4. Select the operator.

![AER_-_Attribute_Email_addedAtt_Eq_To.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b19a51f2-f0bb-240c-f1ba-18c7e55c4af4(2).png)
5. Enter the attribute value.

![AER_popup_email_add.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a128f4c2-054e-18ea-2f7b-e686f6918f65(2).png)
6. Press **Enter** to add the value.

![AER_popup_email_added.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c237f4df-b799-8617-e933-bc602d76dcd7(2).png)
7. Click **Apply** to apply the rule.

![Assistan_API_Rule_added.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56c02482-1ea8-fdec-fefb-87ad36b127e7(1).png)

Securiti adds the rule for the pipeline.

> [!NOTE]
> Note
> 
> To learn more about configuring the user portal, see [Configuring User Portal](/latest/docs/configuring-user-portal).

## API Keys

Use this section to generate and manage API keys for accessing the Assistant API.

1. Enter a **name** for your Assistant API key.

![API_keys_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df85d657-711b-2190-17e8-5e11d31b6c78(1).png)
2. Click **Generate New Key** to create a unique key.

![API_keys_-_Generate_new_key_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e112b8f-ad2d-6e15-ac3f-742e37268b39(1).png)

Copy and securely store the generated key. This key is used in the **Conversations API**.

For more details, see the [Gencore AI API documentation](https://securiti-doc-router.securiti.ai/modules/gencore/apidocs/index.html).

Review the API keys generated.

- The top widget shows information on the total number of API keys.
- You can search the API keys by name.
- You can use the following API key filters:

| Filter | Description |
| --- | --- |
| Name | Filter by the name of the API key. |
| API key | Filter by the composition of the API key. |
| Created | Filter by the data and time the API is created. |
| Used | Filter by the last time the API was in use. |

![Assistant_API_-_API_keys_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-90d88336-cd69-e7e4-946d-c258e9ae771f(1).png)

When you are satisfied with the provided details in Assistant API, click **Save and Continue**.

An API key is a unique identifier used to connect to, or perform, an API call.

A set of criteria that focuses your view by eliminating elements that fall outside the scope of interest. When you filter Securiti pages and dashboards, you choose criteria in the filter panel to reduce the number of elements Securiti displays to just those of interest.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Configuring firewall APIs](/configuring-firewall-apis.md)
- [Configuring Web Widgets](/configuring-web-widgets.md)
