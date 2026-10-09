---
title: "Acquire authentication credentials in Zuora"
slug: "acquire-authentication-credentials-in-zuora"
updated: 2026-06-27T07:53:49Z
published: 2026-06-27T07:53:49Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-zuora"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Zuora

Zuora uses the following Credentials to authenticate and activate the Connection with Securiti.

- Base URL
- Client ID
- Client Secret

1. Log in to Zuora.
2. Near the upper right corner, under your profile, select **Administration**.

![zuora_admin_1_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f890e6d-37d4-ac8c-2cab-598398eee941.png)
3. On the next page, click the **Manage Users** option.

![zuora_manage_users_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4df9caa7-e2ef-4033-57a1-d87c04b73728.png)
4. Select any user that is an Administrator.

![zuora_select_user_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87324d02-449e-7336-5b19-12e90c84429c.png)

If none exists, create one.
5. On the selected user profile, give a name to the OAuth Client and click **create** as shown below.

![zuora_oauth_client_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e09bf30d-22c9-b07b-c0b6-c63de6178983.png)

Zuora shows a popup screen showing the **Client Secret** and **Client ID**.
6. Record the Client Secret and Client ID to use later.
7. Record the base URL for your Zuora account based on your region. Zuora operates the following data centers.

> [!NOTE]
> **Note**
> 
> Zuora has divided the US Data Center into two regions:
> 
> - US Cloud Data Center 1: For customers whose tenants were provisioned after September 2020.
> - US Cloud Data Center 2: For customers whose tenants were provisioned before September 2020.
> 
> Following this update, connectors developed before September 2020 are not compatible with US Cloud Data Center 1.

Record the **REST API** URL for the **Production environment** as shown in the screenshot below. See [Zuora Data Centers documentation](https://knowledgecenter.zuora.com/Zuora_Environments/Zuora_Data_Centers?_gl=1*16w5prs*_gcl_au*MTkyMTc3ODMxOC4xNzI0ODMzMTk2*_ga*MTAwMzM4MTg5LjE3MjQ4MzMyMTg.*_ga_MY8CQ650DH*MTcyNDgzNTc1OS4yLjEuMTcyNDgzNzY4MC42MC4wLjIwNzM1NTA2Njk), for more information.

![zuora_baseurls.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f4df909-1333-059a-76c6-bab8ce3208d3.png)
  - US Cloud Data Center 1
  - US Cloud Data Center 2
  - EU Cloud Data Center
8. Proceed to [Connecting Zuora with Securiti](/latest/docs/connecting-zuora-with-securiti).
