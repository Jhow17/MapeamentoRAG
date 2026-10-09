---
title: "Obtain authentication credentials in Treasure Data CDP"
slug: "obtain-authentication-credentials-in-treasure-data-cdp"
updated: 2026-06-28T14:21:29Z
published: 2026-06-28T14:21:29Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-in-treasure-data-cdp"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials in Treasure Data CDP

> [!NOTE]
> **Note**
> 
> This procedure assumes you have a running Treasure Data Database in your environment.

To obtain Credentials for Treasure Data CDP Connector:

1. Log in to your [Treasure Data console](https://console.treasuredata.com/users/sign_in).
2. **Obtain Master API key:**
  1. On the left bottom, click on profile icon and choose **API Keys**.

![Choose-APIKey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0db7e9fe-73f1-4403-a1af-bdbb7257bf75.png)
  2. On the top left in the **API Keys** page:
    1. Click **Actions**.
    2. Choose **Create API Key** from the menu.

![Action-API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ffc6144-b2d7-b0b3-fb77-b7a821006ac9.png)
  3. On the **Create a new API Key** popup, apply the following settings:

| Setting | Description |
| --- | --- |
| Name | Enter the suitable name for master API Key. See the example below. *Securiti Master API Key* |
| Type | Select the Master key from the menu. |

Click **Save**.

![New-API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d901de9-3a98-a51a-9f48-19f291abb084.png)
  4. On the **API Keys** page:
    1. Under the **API Key** Column, hover over the newly created api key.
    2. Click on the api key to copy it.
    3. Save it for later use in Connector Activation.

![copy-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13c69ca1-829c-ffae-71d3-077a8aa1ebab.png)
3. Ensure Treasure Data user has necessary Permissions.
  - If you have set up general Permissions for your Treasure Data, perform the following steps to verify the required Permissions.
    1. On the left sidebar, click **Databases**.
    2. Make sure **General Access** permission is assigned to your Database.

![Database-access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-281d9a99-6706-d3e8-45c0-85dbf04cad81.png)
    3. Hover over the **Permission** icon to see the details of assigned Permissions.

![permi-detail.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1ec8ac5-2dae-b1dc-fd91-ed13195c152e.png)
  - If you use policy based Database Permissions for your Treasure Data, perform the following steps to verify the required Permissions.
    1. On the left sidebar, click **Databases**.
    2. Make sure **Query Only** permission is assigned to your Database. For more information, see [Database Access Control Overview](/v1/docs/securiti-pods-and-elastic-pods).
4. Obtain API Base URL.
  1. Access [Treasure Data Sites and baseURLs](/v1/docs/securiti-pods-and-elastic-pods).
  2. Scroll down to the base urls region section in which your Treasure Data server is located.

For example, if your Treasure Data server is located in United States. Choose the U.S API base URL in the next step.
  3. Copy the **Presto JDBC/ODBC URL** from the Table and save it for later use in Connector Activation.

![Presto-url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83fb584b-687b-3d1a-d6df-e25d2cd22e05.png)
5. Proceed to [Connecting Treasure Data CDP with Securiti](/latest/docs/connecting-treasure-data-cdp-with-securiti).
