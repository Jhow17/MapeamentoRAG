---
title: "Obtain authentication credentials in Azure Data Lake Storage (ADLS) Gen2"
slug: "obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2"
updated: 2026-07-30T08:12:10Z
published: 2026-07-30T08:12:10Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials in Azure Data Lake Storage (ADLS) Gen2

This topic covers the following authentication methods for obtaining credentials Azure Data Lake Storage.

- [Obtain authentication credentials for Account Key authentication method](/v1/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2)
- [Obtain authentication credentials for Azure Service Principal authentication](/v1/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2) (Applicable for Self-hosted connectors only)

### Credentials required for authentication types

The following table decribes the supported authentication types for each authentication method in Azure Dake Lake Storage.

| Authentication type | Applicable credentials |
| --- | --- |
| Account Key | - Account Name - Account Key |
| Azure Service Principal (Only applied to Self-hosted connector) | - Account Name - Tenant ID - Client ID - Client Secret |

### Obtain credentials for Account key authentication

Perform the following steps to obtain credentials for Account key authentication in Azure Data Lake Storage:

1. Log in to your Azure instance.
2. Azure Data Lake Storage (ADLS) Gen2 uses the **Account Name** and **Account Key** as activation parameters.
3. Click **Create storage account** and sign up for a free trial on the Azure portal if you don't have an existing account.

![Create_storage_account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5bbfca9f-ea97-95c9-f096-8a292de2180b.png)

> [!NOTE]
> **Note**
> 
> Follow the instructions on the [page](/v1/docs/securiti-pods-and-elastic-pods) to register your free account.
4. Configure the project and instance details and click **Next: Advanced** on the following page after registering, as shown below.

![Next_Advanced.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e416624f-b266-b811-0ca5-25b43c88c760.png)
5. Mark the checkbox for **Enable hierarchical namespace** near the bottom of the page.

![image__4_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ac64188-8c82-93a8-a59b-454520ba91e7.png)

Click **Create**
6. On the Storage accounts page, select **your account name > Security + networking > Access keys**, as shown below.

![security_networking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7392a836-21eb-b5f9-02f9-5ea52f9b3fb8.png)
7. Record the Key and Account Name to use later.

> [!NOTE]
> **Important**
> 
> You can copy any key (key1 or key2) in the example. For Account Name, you can copy it from the connection string field or at the top of the page. In the "Connection string", it appears as:
> 
> *<DefaultEndpointsProtocol=https;AccountName=azurestoragefile...>*
8. Proceed to [Connecting Azure Data Lake Storage (ADLS) Gen2 with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-with-securiti) or [Connecting Azure Data Lake Storage (ADLS) Gen2 (Securiti-Cloud) with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-securiti-cloud-with-securiti).

### Obtain credentials for Azure Service Principal authentication

Perform the following procedures in sequence to obtain credentials for Azure Service Principal authentication method for only Self-hosted connector.

#### Register an application in the Azure Portal.

1. Log in to your [Microsoft Azure](/v1/docs/securiti-pods-and-elastic-pods) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(1).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(1).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "ADLS - connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d.png)

#### Obtain OAuth based credentials

Perform the following steps to obtain OAuth based credentials.

1. **To obtain Application (Client) ID**:
  1. On the left sidebar, click **Overview**.
  2. On the Overiview page under the Essentals section, record the following credentials by clicking the **Copy to Clipboard** icon for later use.
    - **Application (Client) ID**
    - **Tenant ID**

![Client-ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a270c6ba-4c5c-df98-c0d8-5e1611722a6a.png)
2. **To configure application secret**:
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**.
  2. On the **Certificates & secrets** page, click **New client secret**.
  3. On the **Add a client secret** popup:
    - Enter a description for the secret, for example, “Azure Data Lake secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.

![secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61204a86-1124-5b8b-3e48-1ebe98fa454b.png)
  4. Under the **Client secrets** tab, copy the secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f7e429c-c469-dee0-08f8-6df35e863e98.png)
  5. Record the new client secret to use it for connector activation.

#### Grant the service principal access to Azure Data Lake Storage

1. On the left sidebar, click **Storage accounts**,
2. On the **Storage accounts** page, click on the **Storage account name** you want to provide access to Azure application you created for Azure Data Lake Storage.

> [!NOTE]
> **Note**
> 
> If you don't have a storage account, create a new one using the [procedure described above](/v1/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2).

![Click-Storage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-32fc9f6d-e275-66e9-f990-cd65871131c7.png)
3. On the Storage account sidebar, click **Access Control (IAM)**.
4. On the **Access Control (IAM)** page, choose **+ Add** > **Add role assignment** from the menu.

![click-role-assign.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-43ccf0f1-92f0-142c-9192-d8c305ef2561.png)
5. On the **Add role assignment** page under the **Role** tab, search and select the **Storage Blob Data Reader** role by clicking anywhere on the Storage Blob Data Reader row.

![data-reader.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16adebdb-2dbb-00a7-2cfb-e1160c2c5d6d.png)
6. Under the **Members** tab, apply the following settings:
  1. Mark the radio button for user, group, or service principal.
  2. Click **+ Select member**s.
  3. On the left panel under **Select Members**, search and select the Azure application you want to assign role to.
  4. Click **Select**.

![select_members.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e0cbffd-bbaa-2b3d-0f00-81511d9374b6.png)
  5. Under the **Members** tab, Click **Review + Assign**.
  6. Under the **Review + assign** tab, click **Review + Assign**.

![Review___Assign.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31e19e25-7401-66f3-7fed-562fcd8df5de.png)
    - On the **Role assignments** page, you can see the newly assigned application in the list, as shown below.

![search_-role_assignment.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-576833d2-33e4-8aaf-c3c5-700b1676693b.png)
7. Proceed to [Connecting Azure Data Lake Storage (ADLS) Gen2 with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-with-securiti) or [Connecting Azure Data Lake Storage (ADLS) Gen2 (Securiti-Cloud) with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-securiti-cloud-with-securiti).
