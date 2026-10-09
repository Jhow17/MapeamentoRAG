---
title: "Using External OAuth Providers"
slug: "using-oauth-providers"
updated: 2026-04-28T02:41:51Z
published: 2026-04-28T02:41:51Z
canonical: "helpcenter.securiti.ai/using-oauth-providers"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using External OAuth Providers

**Scenario**

As a Data Security Officer, you need to ensure that users only access information they are authorized to see when querying your GenAI pipelines. Previously, when your application used only a pipeline API key, the system could not identify the user. For example, if an employee asked, “Show documents related to internal IAM policies,” entitlement checks failed and no results were returned. By passing the user’s external OAuth token with the request, the API identifies the user and applies entitlement checks correctly. Now the employee receives only the documents they are permitted to access.

The **External OAuth Providers** page lets you create OAuth providers that you can configure in your GenAI pipeline to enforce entitlements. This lets you identify the requesting user using an external OAuth token so entitlement-based access checks can be applied correctly. To open the **External OAuth Providers** page, go to **Settings > Gencore AI > External OAuth Providers**.

## Adding OAuth providers

To add your external OAuth provider, on the **External OAuth Providers** page:

1. On the upper right corner, click **+ New External OAuth Provider**.

![Create new external OAuth provider](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Oauth providers dashboard New.png)
2. On the **New OAuth Provider** popup, enter the following information:

| Field | Description |
| --- | --- |
| Provider instance name | Enter the name for your provider instance. |
| Provider URL | Enter the URL for your provider instance. |
| Client ID | Enter the client ID for your provider instance. |
| Client secret | Enter the client Secret for your provider instance. |

![Form for adding a new OAuth provider with fields for instance name, URL, and credentials.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New oauth provider popup.png)
3. To save the details, click **Add External OAuth Provider.**

To configure your OAuth provider in your pipeline, see [**Assistant API > External OAuth for entitlements**](/latest/docs/assistant-api#external-oauth-for-entitlements).

## Managing OAuth providers

You can manage your OAuth providers by clicking **Options** (three dots).

- To edit your OAuth provider:
  1. Click **Edit**.
  2. Make required changes.
  3. Click **Update**.
- To delete your OAuth provider, click **Delete**.
