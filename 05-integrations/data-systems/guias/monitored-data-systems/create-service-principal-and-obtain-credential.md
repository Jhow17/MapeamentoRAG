---
title: "Create Service Principal and obtain credential"
slug: "create-service-principal-and-obtain-credential"
updated: 2026-07-21T05:30:36Z
published: 2026-07-21T05:30:36Z
canonical: "helpcenter.securiti.ai/create-service-principal-and-obtain-credential"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create Service Principal and obtain credential

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an active Databricks instance running. If you are not an administrator, ensure you have access to create a new Service Principal and assign the necessary permissions. This Principal details are needed later to activate the connector in Securiti.

If you want to use **Personal Access Token** authentication method, use [Grant permissions and obtain credentials in Databricks](/latest/docs/grant-permissions-and-obtain-credentials-in-databricks).

You must follow the procedures mentioned below only if you intend to connect Databricks using **OAuth 2.0** based credentials.

This topic cover the following procedures:

1. Create a Service Principal
2. Assign permissions to your Service Principal
3. Create an OAuth secret for a Service Principal
4. Assign workspace and catalogue access to Service Principal
5. Obtain other activation credentials for connector

### Create a Service Principal

1. Log in to your Databricks workspace as an admin.
2. On the top left of your workspace, click your avatar and choose **Settings**.

![Setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57d14c0e-870c-1452-9025-bd478b93c6ee.png)
3. On the left **Settings** sidebar, click **Identity and access**.

![Identity-Access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24bb8243-316b-8b89-5e56-e062f83302e7.png)
4. On the **Identity and access** page, next to **Service principals**, click **Manage**.

![Manage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea67cf88-422c-928f-6098-a823673f7717.png)
5. On the **Service principals** page, click **Add service principal**.

![Add-Service-Principal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6cf0e82d-8de0-713d-6ef1-63da1ade7bf6.png)
6. On the **Add service principal** popup, perform the following steps to add new service principal:
  1. On the right, next to the **Search Principal name** search menu, click **Add new**.

![AddNew-btn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-530d8635-538b-cebd-0708-fd5d6da12afa.png)
  2. Enter a name for the service principal.
  3. Click **Add**.

![Principal-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f2c7f94-78ef-d769-0e40-475dd6ec5a06.png)

> [!NOTE]
> **Note**
> 
> It adds service principal to both your workspace and the Databricks account.

### 2. Assign permissions to your Service Principal

1. On the **Service principals** page, click on the name of your service principal to open its details page.

![Click-SP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dbbd4e35-e916-885c-ab95-ce283327d4b1.png)
2. On the **Service principal details** page under the **Permissions** tab, locate the new Databricks Service Principal, service principals, and groups that you want to manage and use this service principal.
3. On the right side of the Principal you want to use, click options **(three dots) > Edit.**

![Edit-option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13eb3468-50de-ffed-9d14-eeeb546385c8.png)
4. On **Grant access to others** popup, remove **Service principal: Manager** and add the **Service principal: User** permission, and then click **Save**.

![Access Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7731d9be-0d8f-dd05-7e0e-44d86795177a.png)

### 3. Create an OAuth secret for a Service Principal

You must first create an OAuth secret, which can be used to generate OAuth access tokens for authentication.

> [!NOTE]
> **Important**
> 
> A service principal can have up to five OAuth secrets. OAuth secrets have a maximum lifetime of two years. Account admins and workspace admins can create an OAuth secret for a service principal.

1. On your **Service principal details** page, click the **Secrets** tab.
2. In the bottom left of the **OAuth secrets** section, click **Generate secret**.

![Generate-Secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86765c25-0492-52b9-5bb5-541c9517525e.png)
3. On the **Generate OAuth secret** popup, set the secret's lifetime in days, and click **Generate**.

![Generate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e5a1955-af87-d5c2-64d5-2e6b410a6fff.png)

> [!NOTE]
> **Note**
> 
> OAuth secrets have a maximum lifetime of 730 days (two years).
4. On the Generate secret popup, record the **Secret** and **Client ID**, and then click **Done**.

![Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1120be42-05b2-77c3-04d2-f2805fe0ee04.png)

> [!NOTE]
> **Note**
> 
> The secret is revealed once during creation. The client ID is the same as the service principal's application ID.

### 4. Assign workspace and catalogue access to Service Principal

1. To provide the Service Principal access to the required Warehouse:
  1. On the left sidebar, choose **SQL Warehouses**.
  2. On the top of the **SQL Warehouses** page, click **Permissions**.

![sql-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ff91694-650c-3d6b-63d6-3ba269203675(1).png)
  3. On the **Manage permissions** popup, assign the **Can use** permission to the Databricks Service Principal you created.

![can-use-permi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00ea055b-31c7-57f6-6825-905e1300f89c(1).png)
2. Grant the read privileges to the Service Principal for the required Catalog.
  1. On the left sidebar, choose **Catalog**.
  2. On the **Catalog Explore**r sidebar, select the desired catalog to which you want to grant the Service Principal read privileges.
  3. Under the **Permissions** tab, click **Grant**.

![catalogue-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97bbe276-1548-0676-a1a1-04edd72b8da8(1).png)
  4. On the **Grant on <your_catalog>** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Principals | Select the Service Principal from the menu that you created [above](/v1/docs/create-service-principal-and-obtain-credential). |
| Privilege presets | Select the **Data Reader** privilege from the menu to read objects in the Schema. Selecting Data Reader in the menu automatically enables the following permissions: - **USE Schema** under Prerequisite. - **EXECUTE**, **READ VOLUME**, and **SELECT** under **Read** permissions. |

Click **Grant**.

![data-reader.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93533020-c4be-7144-71d2-c5af4a5c4dd7(1).png)
3. To obtain credentials for connector activation:

### 5. Obtain other activation credentials for connector

1. On the left sidebar, choose **SQL Warehouses** > **Connection details**.
2. Record the following for connector activation.
  - Server hostname
  - Port
  - HTTP path

![connection-details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebb6ea05-fc34-2c04-c09d-de90f8da6aff(1).png)
3. Obtain **Account ID:**
  1. On the top right and click on the user profile icon.
  2. Record the **Account ID** by copying it from the user profile menu as shown below.

![account-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-796bfd75-606b-7984-1f4f-404129af128d(1).png)
4. In a separate browser tab, navigate to this Databricks driver page and download the appropriate JDBC driver files for your Databricks instance:

[https://www.databricks.com/spark/jdbc-drivers-download](https://www.databricks.com/spark/jdbc-drivers-download)
5. Proceed to [Connecting Databricks with Securiti](/latest/docs/new-ui-connecting-databricks-with-securiti)
