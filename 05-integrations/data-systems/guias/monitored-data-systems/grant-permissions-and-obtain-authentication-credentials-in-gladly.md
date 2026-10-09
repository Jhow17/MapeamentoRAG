---
title: "Grant permissions and obtain authentication credentials in Gladly"
slug: "grant-permissions-and-obtain-authentication-credentials-in-gladly"
updated: 2026-07-01T03:38:23Z
published: 2026-07-01T03:38:23Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-in-gladly"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials in Gladly

Gladly data system requires the following minimum permissions and activation credentials to authenticate the Connector in Securiti.

- API Token
- User email

> [!NOTE]
> **Note**
> 
> We assume you have an active Gladly account or have access to that account’s admin to request necessary Permissions for Connector Activation.

1. For minimum Permissions, do the following:

> [!NOTE]
> **Note**
> 
> We recommend creating a dedicated user to make API calls so that it doesn’t conflict with any agent or organization management account. It also helps with future audits of API activity, agent activity, etc.
  1. Log in to Gladly.
  2. In the page's top-left corner, select **Settings > Users**.
  3. (Optional) if you haven’t already created a user, click **Add user** and [follow the steps to create one](https://help.gladly.com/docs/managing-users-and-roles).
  4. For existing, select your user(s) from the list and click **Edit**.

![edit_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce51872a-e615-85d3-582c-74b373934020.png)
  5. Mark the checkbox for **API User** under Roles and click **Save**.

![api_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9cd39d6-0e10-8876-dc01-a44f61eb6159.png)
2. To create an API Token:
  1. On the Gladly left-hand menu, select **Settings > API Tokens**.
  2. On the following page, click **Create Token**.
  3. Record the Token for later use.

![api_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d553ce2-df9e-dc14-f4e9-a719e34c23a9.png)
3. Proceed to [Connecting Gladly with Securiti](/latest/docs/connecting-gladly-with-securiti).
