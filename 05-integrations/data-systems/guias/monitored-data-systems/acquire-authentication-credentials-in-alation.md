---
title: "Acquire authentication credentials in Alation"
slug: "acquire-authentication-credentials-in-alation"
updated: 2026-07-04T22:12:08Z
published: 2026-07-04T22:12:08Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-alation"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Alation

Alation, data system connector, requires Base URL, User ID, and Refresh Token to activate connector in Securiti.

> [!NOTE]
> **Note**
> 
> We assume you have the instance running Alation or that you have access to its admin to obtain credentials for connector activation.

1. Log in to your Alation instance.
2. For **Base URL**, record the URL appearing on the home page for later use, as shown below.

<https://securitiaidemo.alationcatalog.com>

![base_url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb3135df-ebe3-2c37-f5ee-06a1be6c8115.png)
3. For **User ID**:
  1. Near the upper right corner of the page, select My Account > **User Profile**.

![user_profile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf15e09f-1866-5e13-023f-405e50672702.png)
  2. Record the ID appearing in the URL for later use, as shown below.

<105>

![user_id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b77142a6-3876-b210-a62c-a71da74402f0.png)
4. For **Refresh Token**:
  1. Select My Account > **Account Settings**.
  2. On the authentication tab, click **Create Refresh Token** under Access Tokens.

![create_refresh_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f9a56f3-aa68-f9ab-2f3e-bc3d26dc8539.png)
  3. Enter a name for your token on the Create Refresh Token dialog and click **Create Refresh Token**, as shown below.

![refresh_token_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d315a98-2fab-2ec5-7a2e-dd15e3fd1782.png)
  4. Record the **Token Secret Key** for later use.

![token_secret_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d578a36a-e6c5-c408-1227-96dbe3151307.png)

> [!NOTE]
> **Note**
> 
> Refresh token expires in 60 days after which you must create a new token and reconfigure the connector.
5. Proceed to [Connecting Alation with Securiti](/latest/docs/new-ui-connecting-alation-with-securiti).
