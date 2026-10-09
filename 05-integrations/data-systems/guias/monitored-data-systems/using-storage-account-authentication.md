---
title: "Using Storage Account authentication"
slug: "using-storage-account-authentication"
status: "update"
updated: 2026-07-30T07:57:54Z
published: 2026-07-30T07:57:54Z
canonical: "helpcenter.securiti.ai/using-storage-account-authentication"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using Storage Account authentication

> [!NOTE]
> **Note**
> 
> This procedure assumes you must have an Azure Storage account in order to facilitate the connector activation process between your Azure Blob Containers and the Securiti app.

Perform the following steps to obtain credentials in Azure Storage account to use them for connector activation.

1. Log in to your [Azure Portal account](https://portal.azure.com/).
2. On the **Dashboard** in the left sidebar, click **Storage accounts**.

![sidebar-Blob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cc9bacd-5b3f-21bd-b875-6dc708f89b2d.png)
3. On the **Storage accounts** page, click on the **Name** of storage account you want to choose from the list.

![Storage_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c14604de-eef8-6387-560f-be452ebb008f.png)
4. Record the **Subscription ID** for your storage account. This ID serves as the Account ID and lets you track which assets are associated with specific accounts.

![azureblobstorage_accountID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4a083a4-8dfb-95b7-a4e5-24805e6e67bc.png)
5. In the Storage account sidebar, choose **Security + Networking** > **Access keys**.

![access-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-044dd868-9abc-5f50-7a41-4c247c9d2143.png)
6. On the **Access keys** page, record the following details to use later for connectors activation.
  - Record **Storage account name** by clicking on **Copy to clickboard** icon.
  - Record either **Key 1** or **Key 2** by copying the value from **Key** field.

![name_and_keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf82f682-919f-db67-aa2b-64762faf370d.png)
7. Proceed to [Connecting Azure Blob Storage (Self-hosted) with Securiti](/latest/docs/connecting-azure-blob-storage-self-hosted-with-securiti).
