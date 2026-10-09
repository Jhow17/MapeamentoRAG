---
title: "Acquire authentication credentials in Azure Cosmos DB for MongoDB"
slug: "acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb"
updated: 2026-07-01T20:04:00Z
published: 2026-07-01T20:04:00Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Azure Cosmos DB for MongoDB

> [!NOTE]
> **Note**
> 
> This procedure assumes you have:
> 
> - Azure Cosmos active subscription.
> - Active [MongoDB connection](/v1/docs/securiti-pods-and-elastic-pods).
> - MongoDB Drivers with wire protocol version 3.4 or greater.
> - Appliance IP allowlisted from [Azure Cosmos DB](/v1/docs/securiti-pods-and-elastic-pods).

1. Log in to the [Microsoft Azure portal](/v1/docs/securiti-pods-and-elastic-pods).
2. On the top-left side of the home page, click the **toggle** button to access the left sidebar, then click the **Azure Cosmos DB**.

![Step-2-select-MogoDB.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9395ffc-0c75-198f-5486-07887a6cb37c.png)
3. On the **Azure Cosmos DB** page, click **Create**.

![Step-3-create-resource.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-678cde98-5283-be01-feae-e4ea8d7ffbdc.png)
4. Under the API section, click **Create** > **Azure Cosmos DB for MongoDB**.

![Step-4-select-API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c8578dd-69e4-27de-d35f-59f7e56f9806.png)
5. Under the Request unit (RU) database account, click **Create**.

![Step-5-select-RU.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10a1fcf4-5181-1112-7bd7-16bfd381552b.png)
6. On the **Create Azure Cosmos DB for MongoDB** cluster page, under the **Basic** tab, add the following details:

| Parameters | Description |
| --- | --- |
| Resource Group | Select from the existing list in the menu or create a unique name. |
| Account name | Enter your account name which is different from the Resource Group. |
| Availability Zones | Mark the radio button for **Enable** or **Disable**. |
| Location | Select the location from the menu according to subscription access and zone support. |
| Capacity mode | Mark the radio button for the **Provisioned throughput** or **Serverless**, according to the business requirement. |
| Apply Free Tier Discount | Mark the radio button for **Apply** if you can avail of the free tier discount. |
| Limit total account throughput and Version | Leave “Limit total account throughput” and “Version” parameters with their default values. |

![Step-6-basics.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3eceeb3a-bfea-56aa-f025-1d87df7c2258.png)
7. Under the **Global Distribution** tab, keep the default values of “Geo-Redundancy and Multi-region-Writes”.

![step-7-global-distribution.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-709016e5-6885-063e-de8d-a83683a2c725.png)
8. Under the **Networking** tab in the **Network connectivity** field, mark the radio button for the preferred "Connectivity method." In the **Connection Security Setting** field, select “**Minimum Transport Layer Security"** from the menu.

![step-8-networking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-540b89d3-603c-4b0a-1657-93183ccc978c.png)
9. Under the **Backup Policy** tab in the **Backup policy** field, mark the radio button for your preferred Backup Policy. Select the time for **Backup interval** and **Backup retention** from the menus.

![Step-9-backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cca37fb7-55d4-1e2b-7725-532ee3b14fe2.png)
10. Under the **Encryption** tab in the **Data encryption** field, mark the radio button for the **Service-managed key**.

![step-10-encryption.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8113eef-fb17-e3ca-32a3-cb606c068374.png)
11. Under the **Review + create** tab, review the information selected in all tabs, then click **Create**.

> [!NOTE]
> **Note**
> 
> The Review + create process takes a few minutes to complete the deployment. After a few minutes, it redirects to the deployment success page.

![Step-11-Review.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa58d9a8-1a77-7fc3-bc7a-7cdebd6f7ea4.png)
12. On the **Deployment** page, click **Go to resource.**

![step-12-depployment.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-084fffcd-174d-d67a-ebbb-37faaca040f1.png)
13. On the **Access control** page, click **Add role assignment**, and grant full access to the resource.

![step-13-grant-access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46afe152-3157-326e-6f8e-7c238009b501.png)
14. On the left sidebar, click **Connection strings**. Record the following for later use:

![Step-14-Connector-activation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-38e3d1e0-fcc8-5cfe-44e8-ed55378b5a5c.png)
  - HOST
  - PORT
  - USERNAME
  - SSL status.
  - PRIMARY PASSWORD.
15. Proceed to [Connecting Azure Cosmos DB for MongoDB with Securiti](/latest/docs/connecting-azure-cosmos-db-for-mongodb-with-securiti).
