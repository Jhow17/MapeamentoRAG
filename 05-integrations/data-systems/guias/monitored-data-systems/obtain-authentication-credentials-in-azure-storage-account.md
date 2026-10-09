---
title: "Obtain authentication credentials in Azure Storage account"
slug: "obtain-authentication-credentials-in-azure-storage-account"
updated: 2026-07-30T08:18:26Z
published: 2026-07-30T08:18:26Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-in-azure-storage-account"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials in Azure Storage account

> [!NOTE]
> **Note**
> 
> This procedure assumes you must have an Azure Storage account in order to facilitate the connector activation process between your Azure Files Share and the Securiti app.

Perform the following steps to obtain credentials in Azure Storage account to use them for connector activation.

1. Log in to your [Azure Portal account](/v1/docs/securiti-pods-and-elastic-pods).
2. On the **Dashboard** in the left sidebar, click **Storage accounts**.

![sidebar-Blob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cc9bacd-5b3f-21bd-b875-6dc708f89b2d(2).png)
3. On the **Storage accounts** page, click on the **Name** of the storage account you want to choose from the list.

![Storage_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c14604de-eef8-6387-560f-be452ebb008f(2).png)
4. In the Storage account sidebar, choose **Security + Networking** > **Access keys**.

![access-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-044dd868-9abc-5f50-7a41-4c247c9d2143(1).png)
5. On the **Access keys** page, record the following details to use later for connectors activation.
  - Record **Storage account name** by clicking on **Copy to clickboard** icon.
  - Record either **Key 1** or **Key 2** by copying the value from **Key** field.

![name_and_keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf82f682-919f-db67-aa2b-64762faf370d(1).png)
6. Proceed to [Connecting the Azure Files data system](/latest/docs/connecting-the-azure-files-with-securiti).

## Related

- [Using Service Principal to authenticate Azure Files](/using-service-principal-to-authenticate-azure-files.md)
