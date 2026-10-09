---
title: "Create an application and obtain authentication credentials for Shopify (self-hosted)"
slug: "create-an-application-and-obtain-authentication-credentials-for-shopify-self-hosted"
updated: 2026-06-20T10:19:44Z
published: 2026-06-20T10:19:44Z
canonical: "helpcenter.securiti.ai/create-an-application-and-obtain-authentication-credentials-for-shopify-self-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create an application and obtain authentication credentials for Shopify (self-hosted)

Perform the following steps to create a Shopify app and obtain Authentication Credentials.

#### Create a Shopify app

Perform the following steps to create a Shopify application

1. Log in to your [Shopify account](https://admin.shopify.com/).
2. On the Shopify **Dashboard** in bottom left sidebar, click **Settings**.

![Shopify-setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9627ce5b-0c17-da2e-2453-5c84be6865f2.png)
3. On the **Settings** page, perform the following steps to access Develop Apps page:
  1. On the left sidebar, click **App and Sales Channels**.
  2. On the **App and Sales Channels** page, click **Develop Apps**.

![sales-develop-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf5184a3-05fb-9967-2b75-94ff55f81a62.png)
4. On the **App development** page, click **Allow custom app development**.

![allow-custom.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5cd87ed-a6c7-392e-a14a-1a82ef5222a7.png)
5. On the following page, click **Allow custom app development**.

![allow-custom-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-447577a7-e734-04a2-538d-c469bf22849a.png)
6. On the following page, click **Create an app**.

![creat-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebd26bee-f021-63ea-47df-cc8b13a65e5b.png)
7. On the **Create an app** popup, configure the following parameters:

| Parameter | Description |
| --- | --- |
| App name | Enter a convenient name for Shopify app. See the example below. *Shopify-App* |
| App developer | Select the Store Admin account from the App developer menu. |

Click **Create app**.

![create-app-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-658e614e-e93d-4cbd-bd4a-496827930408.png)

#### Configure admin scopes and install the app

1. On the newly created Shopify app page, click **Configure Admin API scopes**.

![Admin-Api-scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65fac03e-1019-391a-0f24-d2a69cdf355d.png)
2. On the **Admin API Integrations** page under **All** tab, assign scopes to the newly created Shopify app.
  1. Mark the checkboxes for the following scopes:
    - read_orders
    - read_files
    - read_products
    - read_content
    - read_locations
    - read_customers
    - read_draft_orders
  2. Click **Save**.

![Shopify-scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6b447ba-1a67-bc69-ec14-54fa04490b8d.png)
3. On the top right, click **Install app**.

![install-app_copy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f07b246c-09fa-d587-1cd8-38c27853ffdc.png)
4. On the **Install Shopify-Securiti-app on My Store?** popup, click **Install**.

![install.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0abd6b0-957f-df1d-9d49-88d20c8c862d.png)

It redirects you to **API Credentials** tab.

#### Record activation credentials

Perform the following steps to record the Credentials required for Connector Activation.

1. **Record Access Token:**
  - On the **API Credentials** page under the **Admin API access Token** section, click **Reveal Token once** to record the API access Token.

![reveal-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17e70ac3-538a-2c97-35a3-2d5b61ff8037.png)
2. **Record Store Identifier:**
  1. On the top left, click **Shopify logo** to access the home page.
  2. From the URL address bar, record the Store Identifier as shown below.

If *https://admin.shopify.com/store/****1t71ww-dk*** is the URL. Your store identifier is *1t71ww-dk*.

![shopify-homepage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6dfbcddb-efc2-1678-dd64-3ea159788559.png)
3. Proceed to [Connecting Shopify with Securiti (Self-hosted)](/latest/docs/connecting-shopify-with-securiti).
