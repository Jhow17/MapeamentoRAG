---
title: "Prerequisites for Azure Cosmos DB"
slug: "prerequisites-for-azure-cosmos-db"
updated: 2026-07-01T20:02:50Z
published: 2026-07-01T20:02:50Z
canonical: "helpcenter.securiti.ai/prerequisites-for-azure-cosmos-db"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Azure Cosmos DB

> [!NOTE]
> **Note**
> 
> This procedure assumes that you have a database available prior to connector activation. Also, Azure provides primary and secondary keys for Cosmos DB to query data. You only have to copy the Read-Only Primary Key from Cosmos DB and use it in connector configuration. Read-Write access is not needed.

To connect Azure Cosmos DB with Securiti and perform data scanning, you must do the following.

- Create and register an application in Microsoft Entra ID
- Acquire authentication credentials

Azure Cosmos DB supports the following authentication methods to connect and authenticate with Securiti.

| Authentication method | Authentication credentials |
| --- | --- |
| Account Key | Account Key |
| Azure Service Principal | - Tenant ID - Client ID - Client Secret |

Follow the procedures below to acquire your Azure Cosmos DB authentication credentials based on the selected authentication method.

### Creating application in Microsoft Entra ID and acquiring credentials

1. Log in to the [Azure portal](/v1/docs/securiti-pods-and-elastic-pods)
2. Go to **Microsoft Entra ID** and record the **Tenant ID** to use later.
3. Register your application by following [Microsoft Entra ID's documentation.](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id)

![azurecosmosdb_appregistration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a9dee8e-61f1-93cd-d769-6e228fe17aa4.png)
4. On the **Authentication** tab, make sure to select **Access tokens (used for implicit flows)**
5. On the selected Azure Cosmos DB account **Overview** page, record the following credentials, as shown below.
  - Storage Account name
  - Resource group
  - Subscription ID

![Overview of Azure Cosmos DB account with highlighted resource group and subscription details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azurecosmos_creds.png)
6. From the left menu, select **Browse > Containers**, and record the Resource Name which is your container’s database name, as shown below.

![Overview of Azure Cosmos DB collections with database names and throughput details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azurecosmos_containers.png)

### Acquiring Account Key for Azure Cosmos DB

> [!NOTE]
> **Note**
> 
> Skip this section if you are opting for **Azure Service Principal** authentication method.

Follow the procedure below if you are using the **Account Key** authentication method.

1. Log in to the [Azure portal](/v1/docs/securiti-pods-and-elastic-pods).
2. Near the bottom of the Azure Cosmos dashboard, click **Keys**.

![Azure-Cosmos-Keys_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be2fd753-68e5-56ed-ba29-f41154d9182f.png)
3. Under the **Read-only keys** tab, record the **URI** as Account Endpoint and **Primary Connection String** to use later.

In "Primary Connection String" record only the value after *AccountKey-* as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-25 at 14.59.42.png)

Save the account key to use later.
4. Proceed to [Connecting Azure Cosmos DB with Securiti](/latest/docs/connecting-azure-cosmos-db-with-securiti).

### Using Azure Service Principal authentication

> [!NOTE]
> **Note**
> 
> Skip this section if you are opting for **Account Key** authentication method.

See [Azure's official documentation on Service Principal](https://learn.microsoft.com/en-us/azure/managed-instance-apache-cassandra/add-service-principal), for more information.

Follow the procedure below if you are using the **Azure Service Principal** authentication method.

#### Acquiring client ID and secret values

1. In the **Overview** page, record the **Application (client) ID** to use later.

![azurecosmosdb_clientid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa92dc49-6536-6379-443d-4db7cac53367.png)
2. Navigate to the **Certificates & Secrets** section and select **New Client Secret** for the application.

![azurecosmosdb_newsecret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5cf3544f-bef8-0541-8c6d-3c48af65ad32.png)
3. Enter secret key and name.
4. Click **Add**
5. Specify the expiry duration for your client secret and save it.
6. Record the **Client Secret** to use later.

#### Assign read permission to Azure Cosmos DB

To assign read permission to Azure Cosmos DB, perform the following steps:

1. On the top middle of Microsoft Azure navigation, search and select **Azure Cosmos DB**.

![search-azure-cosmos.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f7180bb-2924-8976-6ddd-1b00d1f65ae0.png)
2. On the following page under the **Name** column, select your Azure Cosmos DB account.

![select-cosmosdb.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82bd9fa6-b5f8-e2d8-4e87-0df63e7123d8.png)
3. On the selected **Azure Cosmos DB account Overview** page, record the following credentials:
  - Account name
  - Resource group
  - Subscription ID

![Cosmos_DB.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-154ea264-c104-422a-5641-141ec7529f0e.png)
4. On the top middle of Microsoft Azure navigation, search and select **Enterprise applications**.

![search_enterrpise-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67bbc8c1-7be2-4ac4-0d0b-53eb37982aa6.png)
5. On **All applications** page, search and select the Azure Cosmos DB application you want to use for assigning role.

![select-enterprise-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d7c0f61-e933-d3ae-498d-ffa6ed488f8e.png)
6. On the **Overview** page under **Properties** section, record the **Object ID**.

![object-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cdd1fdb-ef95-2f8e-cf72-88516d41e873.png)
7. On the top middle of Microsoft Azure navigation, search and select **App registrations**.

![App-registrations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37cd6cfc-d6ff-28ef-4f5d-a93e9d12f119.png)
8. On **App registrations** page under **All applications**, search and select your Azure cosmos DB app.

![select-re-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22f6b6d2-3c72-4280-9fd9-77e749ab96b6.png)
9. On the **Overview** page, record the following:
  - Application (client) ID
  - Directory (tenant) ID

![client-teantid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63785061-45f5-40d3-aac3-782180299379.png)
10. Download Azure CLI using the following the [Azure documentation](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest).
11. Log in into Azure by using command after azure CLI installation.

```plaintext
az login
```
12. Run the following command to assign the reader role.

> [!NOTE]
> **Note**
> 
> Add the credentials to the command by replacing the example values provided in the procedure above.

```plaintext
az cosmosdb sql role assignment 
create --account-name <azure_cosmos_db_account_name> 
--resource-group <resource_group_name> --scope "/" 
--principal-id <object id as shown in the above screen shot> 
--role-definition-id 00000000-0000-0000-0000-000000000001 --subscription <subscription_id>
```

Proceed to [Connecting Azure Cosmos DB with Securiti](/latest/docs/connecting-azure-cosmos-db-with-securiti).
