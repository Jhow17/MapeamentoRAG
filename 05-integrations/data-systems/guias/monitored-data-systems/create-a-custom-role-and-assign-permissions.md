---
title: "Create a custom role and assign permissions"
slug: "create-a-custom-role-and-assign-permissions"
updated: 2026-08-28T07:44:00Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/create-a-custom-role-and-assign-permissions"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a custom role and assign permissions

Perform the following steps to create a custom role in Google BigQuery:

1. Log in to [Google Cloud Platform](https://console.cloud.google.com/).
2. On the left sidebar, choose **IAM & Admin** > **Roles**.
3. On top of the **Roles** page, click **+ Create role**. ![Roles management interface displaying various roles and their statuses for the IaaS project.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-role.png)
4. On the **Create role** page, add the following information:

| Paramter | Description |
| --- | --- |
| Title | Add a convenient title for the role. See the example below. *Custom role for Securiti* |
| Description | Add a suitable description for the custom role. |
| ID | It suggests an automatic ID based on the title. You can also update the ID to make it unique. See the example below. *CustomRole910* |
| Role launch stage | From the menu, select the Role launch stage, such as Alpha. |
| Add permissions | Click **Add permissions.** On the **Add permissions** popup, mark the checkboxes for the following permissions: - `bigquery.tables.getData`: Lets the actual retrieval of row-level data. - `bigquery.tables.get`: Lets the user see the table schema/metadata (required for the query engine to parse the SQL). - `bigquery.datasets.get`: Lets access to the dataset metadata. - `bigquery.tables.list`: Lets the user see the list of tables in the BigQuery sidebar. - `bigquery.jobs.get`: Lets you view the status and statistics of your specific jobs. - `bigquery.readsessions.getData` Lets you stream data directly from BigQuery storage using the BigQuery Storage Read API. - `bigquery.readsessions.create`: Lets you create a read session, which is required before you can stream data using the BigQuery Storage Read API. - `bigquery.jobs.create`: Lets a principal (user, service account, or group) start a job. |

![Creating a custom role with title, description, and permissions in IAM settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Role-popup.png)
5. Click **Create**. It creates a new custom role
6. To create a new Service Account to link the custom role:
  1. On the left sidebar, choose **IAM & Admin** > **Service Accounts**. ![Create-Service-Ac.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dec8d842-8b43-8950-51af-36836407f30e.png)
  2. On the **Service accounts** page at the top, click **+ CREATE SERVICE ACCOUNT**. ![create-S-Account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b9a237c3-e404-902d-68df-fc6aa506201b.png)
  3. On the **Create service account** page, add the following information.

| Parameter | Description |
| --- | --- |
| Service account name | Enter a convenient name for the service account. See the example. *Google-BigQuery-Account* |
| Service account ID | Enter an ID for your Service account. See the example below. *Test-user* > [!NOTE] > **Note** > > This Service account ID is added to the email for your service account. |
| Service account description | Enter a description to add important details for your service account. |

![Creating a service account with required fields and options for permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Service-Account.png)
  4. Click **Done**. It redirects you to the Service Accounts page, where you can see the newly created Service Account.
  5. From the list of service accounts, click on the newly created service account link under the **Email** column.
  6. On the Service Account details page, click the **Permissions** tab.
  7. Under the **Permissions** tab, click **Manage access**. ![Manage service account permissions and access settings in the Google Cloud console.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Manage Access.png)
  8. On the Edit access left pane under **Assign roles**, click **+ Add role**. ![Editing service account permissions in Google Cloud, including adding roles and saving changes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add-custom-role.png)
  9. In the **Select a role** menu, choose **Custom** > newly created custom role that you created in step 4 above. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assign role.png)
  10. Click **Save.**
7. To create a private key for your newly created service account:
  1. On your newly created custom role, click the **Keys** tab.
  2. Under the **Keys** tab, click the **Add key** menu.
  3. From the **Add key** menu, select the **Create new key** option. ![Service account key management interface with options to add or create new keys.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create key.png)
  4. On the **Create private key for <your service account>** popup, mark the **JSON** radio button as **Key type**.
  5. Click **Create**. ![Creating a private key for the BigQuery service account in Google Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-key-popup.png)

> [!NOTE]
> Note
> 
> It downloads the JSON file into your device. Save the file to use it as **Credential File** in the connector activation.
8. To record the Project ID and Dataset Name:
  1. On the left side, choose **BigQuery** > **BigQuery Studio.**

![bigq-studio.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5bcdd8cb-cf0d-722d-0576-159b3d6c1879.png)
  2. On the following page, click the **Project ID** and **Dataset Name** as shown in the image below.

| Parameter | Description |
| --- | --- |
| Project ID | Record the Project ID for connector activation. See the example below. `gbigquery-diagnostic-testing` |
| Dataset name | Record the Dataset name for Connector Activation. See the example below. `gbigquery_diag_testing_1` |

![Dataset-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb00785e-4802-a509-9dec-db0beffec79f.png)
9. Proceed to [Connecting Google BigQuery (self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-self-hosted-with-securiti) or [Connecting Google BigQuery (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-securiti-cloud-with-securiti).
