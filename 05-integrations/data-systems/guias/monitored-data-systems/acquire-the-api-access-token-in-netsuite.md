---
title: "Acquire the API access token in NetSuite (Self-hosted)"
slug: "acquire-the-api-access-token-in-netsuite"
updated: 2025-10-31T07:51:47Z
published: 2025-11-03T06:24:48Z
canonical: "helpcenter.securiti.ai/acquire-the-api-access-token-in-netsuite"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire the API access token in NetSuite (Self-hosted)

The API Token is linked with the company data you want to access. It authorizes data retrieval. Follow these steps to acquire an API access Token:

For configuring the Netsuite app using OAuth 2.0, see [Obtain credentials in NetSuite for OAuth 2.0 authentication](/v1/docs/obtain-credentials-in-netsuite-for-oauth-20-authentication).

1. Log into NetSuite as an administrator.
2. Choose **Setup > Company > Company Information**. Record the **Account ID** to use later.

![1_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72afa7a2-92aa-4311-0dfc-fafee932872c.png)

![2_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f9f429c-8eb2-5289-a040-3778f22c63c8.png)
3. Return to **Setup**, then **Company > Enable Features > SiteCloud > Manage Authentication**.

![3_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5461738a-ac8e-0b58-e26a-e185591135b4.png)
4. Enable **Token-Based Authentication**.

![4_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9beea545-47f0-221a-d5db-d53560901d10.png)
5. Mark the **TBA: Authorization Flow** checkbox. Save the changes.
6. Record the **Consumer Key** and **Consumer Secret**:
  1. Choose **Setup > Integration > Manage Integrations > New** to create a new Integration.

![5_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-589249b7-84ac-8c2e-798d-34efd2307776.png)
  2. Select **Token-Based Authentication**. Once the Integration is created, Consumer Key and Consumer Secret are displayed.

![6_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe19b06e-61c2-c43d-a530-241a1ae9dce2.png)

![7_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7096a49e-8b91-cc56-b423-86d79ac503fe.png)
  3. Record the Consumer Key and Consumer Secret to use later.
7. Generate the API access Token:
  1. Create a Token role by choosing **Setup > User/Roles > Manage Roles**.

> [!NOTE]
> **Note**
> 
> You can create a new or edit an existing role.
  2. Under **Permissions**, the role must be listed, or you cannot activate the Connector.
  3. Add the role to a user by going to **Lists > Employees > Employees**.

![12_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d29daebd-24b4-b2b4-4f03-7568467b79d7.png)
  4. Select to edit an employee and add a new Token under **Access > Roles**.
  5. Return to **Setup > User/Roles > Access Tokens**, then create a new access Token.

![10_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e19371c-4c2f-26c0-8bf1-5a06aa570ab1.png)
  6. Select the application name as the previously created Integration and the same user and role that was updated. After the access Token is created, **Token Id** and **Token Secret** are displayed.

![8_1x.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a8de878-8dcc-7340-f536-ec0bdd6385db.png)
  7. Record the Token Id and Token Secret to use later.
8. Proceed to [Activate the NetSuite connector in Securiti](/v1/docs/activate-the-netsuite-connector-in-securiti).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
