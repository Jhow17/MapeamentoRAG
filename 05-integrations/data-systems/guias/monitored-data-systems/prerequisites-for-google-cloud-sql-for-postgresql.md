---
title: "Prerequisites for Google Cloud SQL for PostgreSQL"
slug: "prerequisites-for-google-cloud-sql-for-postgresql"
updated: 2026-04-28T04:21:17Z
published: 2026-04-28T04:21:17Z
canonical: "helpcenter.securiti.ai/prerequisites-for-google-cloud-sql-for-postgresql"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Google Cloud SQL for PostgreSQL

> [!NOTE]
> **Note**
> 
> You must have SQL Cloud instances running on the Google Cloud Platform (GCP) infrastructure.

To connect Google Cloud SQL for PostgreSQL with Securiti and perform data scanning, you must do the following.

- [Ensure that SQL Cloud instances are enabled](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
- *(Skip for SQL Cloud Proxy Authentication)* [Record user credentials for Basic authentication](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
- *(Skip for Basic Authentication)* [Prerequisites for SQL Cloud Proxy authentication](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
  - Enable Cloud proxy on GCP Infrastructure
  - [Create IAM User](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
  - [Create and associate Service Account](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
    - Assign roles or Permissions to the service account
  - [Enable IAM for your SQL cloud instance](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
  - [Grant DB permissions to IAM user](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)
  - [Download service account file](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql)

Follow the procedures below to acquire your Google Cloud for PostgreSQL Authentication Credentials based on the selected Authentication method.

### Enable SQL Cloud instances

You must have SQL Cloud instances running and enabled on the Google Cloud Platform (GCP) infrastructure.

![gcp_sql_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9dfbbd4-53f0-8662-2e5a-e616c44229cc(1).png)

#### Enable Cloud SQL Admin API

You must enable the Cloud SQL Admin API to create and manage SQL instances. To enable Cloud SQL Admin API.

1. On the Google Cloud dashboard, in the left sidebar, select **APIs & Services > Enabled APIs & services**.

![gcpmysql_apiandservices.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58fc559a-db27-63a2-bc77-4aeeec358624(1).png)
2. At the top of the page, click **+ Enable APIs And Services**.

![gcpmysql_enableapi_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9b49c74-65c1-75e2-952a-499a3787105f(1).png)
3. On the following page, in the search bar, enter 'Cloud SQL Admin API.' Then, click the card for it showing in the search result. ![gcpmysql_cloudapi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-576f1672-bbaf-e7a9-da90-7345e144dd95(1).png)
4. Click **Enable**

![gcpmysql_enableapi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1bbeab18-c900-60ae-4dab-9a89e2170385(1).png)

### Basic authentication

When using Basic Authentication type for your Data system Connector, enable your SQL Cloud instances and record the following values to use later.

- Record the **Public IP address**. This is the hostname to use later for Connector Activation.
- On the GCP console's **Connections** tab, record the **port** number for your SQL Instance. For PostgreSQL, the default port number is *5432*.
- Record the **username** and **password** for your Database account with administrative access. You can find this information in the **Users** tab.

Proceed to [Activate the Google Cloud SQL for PostgreSQL connector in Securiti](/v1/docs/activate-the-google-cloud-sql-for-postgresql-connector-in-securiti)

### SQL Cloud Proxy authentication

Record the following to use later.

- On the GCP console's **Overview** page for your SQL Instance, in the **Connection name** field, record the value for **Connection Identifier**. It is generated when you launch your SQL Instance.

See an example below.

*<gcpprojectname>:<region>:<Instance-name>*

![gcpmysql_connectionname.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ec22bd3-0282-25c9-1f71-ffa3540809c5(1).png)
- Record the **Public IP address**. This is the hostname to use later for Connector Activation.
- On the GCP console's **Connections** tab, record the **port** number for your SQL Instance. For MySQL, the default port number is *3306*.
- Record the **username** and **password** for your Database account with administrative access. You can find this information in the **Users** tab.

#### Create and assign the IAM user to your PostgreSQL instance

Follow the procedure below to let the service account access your PostgreSQL Instance

1. Select the GCP project that contains your PostgreSQL Instance.
2. In the left sidebar, navigate to **SQL** to view the list of SQL instances.

![gcpmysql_sql.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b263761-7b75-6726-f79b-81e963e60be1(1).png)
3. Select the PostgreSQL Instance you want to connect to.
4. In the left sidebar, click **Users** and then in the right pane, click **Add User Account**.

![gcpmysql_users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51bf58bf-74ba-2238-49aa-320cac56e0e1(1).png)
5. In the flyout menu, under **Choose how to authenticate**, select **Cloud IAM**.
6. Enter the service account email (generated earlier) into the **Principal** field.

![gcpmysql_adduseraccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41239871-8296-9e24-9119-081f556154cf(1).png)
7. Click **Add**. The IAM user now appears in the list of users for the PostgreSQL Instance.
8. Proceed to create a service account and assign roles and Permissions to it, as explained in the section below.

#### Create a service account

To connect the Google Cloud SQL for PostgreSQL Connector with Securiti, you must create a service account with appropriate roles and Permissions to securely interact with the SQL instances.

If you want to connect using the service account of a different project, see [(Optional) Connect using another service account](/v1/docs/optional-connect-using-another-service-account)

1. Log in to the Google Cloud Console and choose your Project where your Google Cloud SQL Instance is located.
2. Navigate to **IAM & Admin**.
3. From the left sidebar, select **Service Accounts**.
4. In the right pane, click **Create Service Account** and fill in the following details.

![gcpmysql_serviceaccounts.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1c772fdd-8ba2-263b-5834-35d7c182b519(1).png)
  - **Service Account Name**: Choose a name that is easily recognizable.
  - **Service Account ID:** This will be auto-generated but should be unique.
  - The **email address** for the service account will be generated in the format:

*<service-account-name>@<project-id>.iam.gserviceaccount.com*

![gcpmysql_iamprincipal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a53b401e-53ed-03bb-1f59-a1c1631d0563(1).png)

> [!NOTE]
> **Note**
> 
> The email generated during the service account creation is your IAM principal name.
  - **Service Account Description**: (Optional) Add a description for clarity.
5. Click **Create and Continue**.
6. *(Required for SQL Cloud Proxy Authentication only)* Record the value for the Database **IAM User** to use later.

![gcpmysql_allusers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae517043-76cd-7850-d6c1-37177780c2ae(1).png)
7. Assign roles to the Service Account following the procedure below.
  1. On the next page, select the following mandatory roles:

> [!NOTE]
> **Note**
> 
> When you create a service account, the associated IAM user is also created.

![select_roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4401156b-f3f6-41d5-959a-ffaa2ec55648(1).png)

![sql_client_and_sql_instance_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ef9cdb8-f9f2-cd49-5270-da59d54d04b4(1).png)
    - **Cloud SQL Client**: Lets the service account connect to Cloud SQL instances.
    - **Cloud SQL Instance User**: Enables the service account to authenticate and manage SQL instances.
  2. Click **Continue** to finish assigning roles.
  3. (Optional) If you want to grant specific users access to the resources associated with the service account, you can do so on this page by assigning specific roles to other users.

![user_access_to_resources_(optional).png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e6e1fef0-7548-13a9-cc6d-bacee97c9ce5(1).png)

![click_done.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-deb03d74-f34f-1ec4-c3eb-f833cd214a0e(1).png)
  4. Click **Done** to finish creating the service account.

#### (Optional) Verify the service account

(Optional) Follow the procedure below to check the roles and Permissions of the created service account

1. Go to **IAM & Admin > IAM**.
2. Enter the IAM principal or email address of the service account in the search bar.
3. The results display all the roles assigned to the service account.

![gcpmysql_roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ac08209-e096-3227-e873-69105c220094(1).png)

#### Enable IAM for service account

Enable the ***<cloudsql.iam_authentication (on)>*** IAM flag for existing or new instances, as shown below.

![gcp_sql_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-91d1e1cc-29cb-f758-7a92-9214c4119958(1).png)

#### Grant database permissions

> [!NOTE]
> **Note**
> 
> We recommend you proceed as the account admin or user with adequate privileges before granting DB Permissions

Follow the procedure below to grant the necessary privileges to the IAM user created for the Google Cloud SQL Connector in Securiti.

1. Record the IAM principal (service account email) in the format:

*email@iam.gserviceaccount.com*

This service account email was generated when you created the service account with the IAM roles required for Google Cloud SQL.
2. Login to the Database using any Database client (e.g., MySQL Workbench, psql) or the Cloud SQL console.
3. Connect to the Google Cloud SQL Instance where the Database resides.
4. Grant Permissions to the IAM User by executing the commands below.
  - For each Database Schema that needs to be scanned, execute the following SQL command:

```plaintext
GRANT SELECT ON ALL TABLES IN SCHEMA "<schema_name>" TO "<iam_user>";
```
  - (Optional) To verify the GRANT Permissions, use the following SQL queries:

```plaintext
select grantee, privilege_type
from information_schema.role_table_grants
WHERE grantee='<iam_username>';
```
  - To view Column-level grants:

```plaintext
select *
from information_schema.role_column_grants
where grantee='<iam_username>';
```

#### Generate and download the Service Account Key

Follow the procedure below if you to generate the service account key.

1. Under **Service Accounts**, search for the service account you just created.
2. In the **Actions** Column, click options (three dots) next to the service account and select **Manage Permissions**.

![manage_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9629bca0-a1ef-1488-ce22-b49bfae39a97(1).png)
3. Navigate to the **Keys** tab and select **Add Key > Create New Key**.

![gcpmysql_createnewkey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-011607a1-67e1-a2ac-ac2b-222945386550(1).png)
4. In the popup, select **JSON** as the key type and click **Create**.

![choose_json.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad4f443e-1c4d-7f2e-bb6f-3cbdf9dd47d1(1).png)
5. The JSON key file is automatically downloaded. The JSON file is your **Credentials File** to use for Connector Activation.

Keep this file safe, as it is required during the Connector Activation in Securiti. This file cannot be regenerated, and if lost, you must create a new key.
6. Proceed to [Activate the Google Cloud SQL for PostgreSQL connector in Securiti](/latest/docs/activate-the-google-cloud-sql-for-postgresql-connector-in-securiti) or [(New UI) Connecting Google Cloud SQL for PostgreSQL with Securiti](/latest/docs/new-ui-connecting-google-cloud-sql-for-postgresql-with-securiti).
