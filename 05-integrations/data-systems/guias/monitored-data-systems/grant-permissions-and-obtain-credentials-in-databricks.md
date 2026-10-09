---
title: "Grant permissions and obtain credentials in Databricks"
slug: "grant-permissions-and-obtain-credentials-in-databricks"
status: "new"
updated: 2026-07-21T05:29:55Z
published: 2026-07-21T05:29:55Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-databricks"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Databricks

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an active Databricks instance running. If you are not an administrator, ensure you have access to create a new user and assign the necessary permissions. This user's details are needed later to activate the connector in Securiti.

If you want to use **OAuth 2.0** authentication method, use [Create Service Principal and obtaining OAuth 2.0 credentials](/v1/docs/create-service-principal-and-obtain-credential).

You must follow the procedures mentioned below only if you intend to connect Databricks using **Personal Access Token** based credentials.

To obtain credentials and assign permissions to a Databricks user:

1. Log in to [Databricks](https://community.cloud.databricks.com/login.html) as admin.
2. Create a new user.
  1. On the **User management** page, click **Add user**.

For more information on providing email and personal information, see [Databricks documentation.](https://accounts.cloud.databricks.com/user-management/users)

![user-adduser.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0a64a17-ae37-4036-8ea2-88df9bf3d2f0.png)
  2. On the **Add user** page under the **User information** tab, add the following information.

Click **Add user**.

![user-adduser.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0a64a17-ae37-4036-8ea2-88df9bf3d2f0.png)
    - Email
    - First name
    - Last name
3. Assign roles and permissions to the user.
  1. On the left sidebar under the **Settings**, click **Identity and access**.
  2. Make sure the toggles are enabled for the following entitlements:

| Entitlement | Use case |
| --- | --- |
| Workspace access | It is required for data scanning. |
| Databricks SQL access | It is auto-inherited from the group if needed. |

![acceses.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a942f4dc-e812-82ee-bdd2-65e28d09c9b3.png)
  3. Provide the user access to the required Warehouse.
    1. On the left sidebar, choose **SQL Warehouses**.
    2. On the top of the **SQL Warehouses** page, click **Permissions**.

![sql-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ff91694-650c-3d6b-63d6-3ba269203675.png)
    3. On the **Manage permissions** popup, assign the **Can use** permission to the Databricks user you created.

![can-use-permi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00ea055b-31c7-57f6-6825-905e1300f89c.png)
4. Grant the read privileges to the user for the required Catalog.
  1. On the left sidebar, choose **Catalog**.
  2. On the **Catalog Explore**r sidebar, select the desired catalog to which you want to grant the user read privileges.
  3. Under the **Permissions** tab, click **Grant**.

![catalogue-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97bbe276-1548-0676-a1a1-04edd72b8da8.png)
  4. On the **Grant on <your_catalog>** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Principals | Select the user from the menu that you created [above](/v1/docs/grant-permissions-and-obtain-credentials-in-databricks). |
| Privilege presets | Select the **Data Reader** privilege from the menu to read objects in the Schema. Selecting Data Reader in the menu automatically enables the following permissions: - **USE SCHEMA** under Prerequisite. - **EXECUTE**, **READ VOLUME**, and **SELECT** under **Read** permissions. |

Click **Grant**.

![data-reader.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93533020-c4be-7144-71d2-c5af4a5c4dd7.png)
5. Obtain credentials for connector activation.
  1. On the left sidebar, choose **SQL Warehouses** > **Connection details**.
  2. Record the following for connector activation.
    - Server hostname
    - Port
    - HTTP path

![connection-details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebb6ea05-fc34-2c04-c09d-de90f8da6aff.png)
  3. Obtain **Account ID:**
    1. On the top right and click on the user profile icon.
    2. Record the **Account ID** by copying it from the user profile menu as shown below.

![account-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-796bfd75-606b-7984-1f4f-404129af128d.png)
  4. Create personal access token by logging in with the newly created user and do the following:

> [!NOTE]
> **Important**
> 
> You don't require special permissions to activate instances because the generated access token already has permissions. You can easily activate the instance.
    1. Go to **Settings** > User > **Developer** > **Access tokens**,
    2. Click **Manage**, then click **Generate new token.**
    3. On the **Generate new token** popup, click **Generate**.

![image3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7801cecb-b159-ca4b-5520-910ed697eba8.png)
    4. Record the token by copying it to use it later for connector activation.

![generate-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-687dc2ff-7b25-6e2c-264e-cb5241641414.png)
6. In a separate browser tab, navigate to this Databricks driver page and download the appropriate JDBC driver files for your Databricks instance:

[https://www.databricks.com/spark/jdbc-drivers-download](https://www.databricks.com/spark/jdbc-drivers-download)
7. Proceed to [Connecting Databricks with Securiti](/latest/docs/new-ui-connecting-databricks-with-securiti).

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

The establishment of a link or communication channel between the Securiti platform and a data system. Happens after successful authentication and activation of a data system.

Java Database Connectivity (JDBC) driver files are the set of files required for connecting Java applications to databases. These files are required where databases are selected to perform data scan on, when setting up a connector.
