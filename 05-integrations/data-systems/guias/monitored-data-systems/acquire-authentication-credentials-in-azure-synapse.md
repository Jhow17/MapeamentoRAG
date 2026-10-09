---
title: "Acquire authentication credentials in Azure Synapse"
slug: "acquire-authentication-credentials-in-azure-synapse"
updated: 2026-07-02T20:39:31Z
published: 2026-07-02T20:39:31Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-azure-synapse"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Azure Synapse

1. Log in to the Azure portal.
2. In the upper left corner of the portal, click **Create a resource**.

![Create-a-resource_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70001117-0c0d-67b8-512e-592a103e52ac.png)
3. On the New page, under **Azure Marketplace**, choose **Databases**.
4. Under **Featured**, choose **SQL Data Warehouse**.

![Select-sql-data-warehouse_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-acfcdfcc-a7f1-d54f-45ec-21285cd89cc5.png)
5. On the **SQL Data Warehouse** page, click **Create**.

![Click-create_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-051a3413-6f08-09cc-4652-936ea2f03d65.png)
6. Give your data warehouse a name. That name also becomes your Db name.
7. Create a server, following the steps below:
  1. On the **Basics** tab, click **Create New** as shown below.

![Create-new-server_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea804ddf-fa6a-4065-6336-41a63a63db89.png)
  2. Near the right side of the page, enter values for creating the "New server" then click **OK**.

![New-server_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4879591c-a677-9a46-4c40-b2d54067b758.png)

> [!NOTE]
> **Note**
> 
> This procedure assumes that you have the values available before server creation.

Apply the following values:
    - Server name or Host
    - Server Admin login or User
    - Password
    - Location

(`west US 2` preferred due to low cost)
    - Performance level

(`minimum` preferred due to low cost)
  3. Record the values for **Server name**, **User**, **Password** and **Db name** to use later.
8. Create the data warehouse:
  1. On the Basics tab, from the **Server** menu select the server.
  2. Enter the following values:

> [!NOTE]
> **Note**
> 
> This procedure assumes that you have the values available before data warehouse creation.
    - Payment method
    - Resource group (create new where applicable)
    - Database name
    - Server (Step 7 above)
  3. Review the information and click **create**.

![Reivew-and-create_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07d51826-7ce2-c4a1-8c7f-7ef181b7fb4b.png)

After successful deployment, you see the page as shown below.

![Successful-deployment-page_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cbd5f3bc-aa9e-04fd-8dae-90488e212bdc.png)
  4. Click **Go to resource** to view the data warehouse page as shown below.

![Go-to-resource_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26314edd-21ce-012e-372e-a80dadf74854.png)
  5. Click **Show database connection strings** in "Connection strings" to reveal the Port number.
  6. Record port number to use later.
9. Proceed to [Connecting Azure Synapse with Securiti](/latest/docs/activate-the-azure-synapse-connector-in-securiti) .

## Related

- [Connecting Azure Synapse with Securiti](/activate-the-azure-synapse-connector-in-securiti.md)
