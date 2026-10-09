---
title: "Acquire authentication credentials in Google BigQuery"
slug: "acquire-authentication-credentials-in-google-bigquery"
updated: 2026-04-28T04:02:45Z
published: 2026-04-28T04:02:45Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-google-bigquery"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Google BigQuery

> [!NOTE]
> **Note**
> 
> This procedure assumes you have a BigQuery Instance before enabling the following prerequisites or Permissions for Connector Activation.

Perform the following steps to acquire Authentication in Google BigQuery:

### Step 1- Create a Service account in Google Cloud Platform

1. Log in to [Google Cloud Platform](/v1/docs/securiti-pods-and-elastic-pods).
2. On the left sidebar, choose **IAM & Admin** > **Service Accounts**.

![Create-Service-Ac.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dec8d842-8b43-8950-51af-36836407f30e.png)
3. On the **Service accounts** page at the top, click **+ CREATE SERVICE ACCOUNT**.

![create-S-Account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b9a237c3-e404-902d-68df-fc6aa506201b.png)
4. On the **Create service account** page, add the following information.

| Parameter | Description |
| --- | --- |
| Service account name | Enter a convenient name for the service account. See the example. *Google-BigQuery-Test-Account* |
| Service account ID | Enter an ID for your Service account. See the example below. *Test-user* > [!NOTE] > **Note** > > This Service account ID is added to the email for your service account. |
| Service account description | Enter a description to add important details for your service account. |

![Service-Account-Details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e628eb6-d7e3-60ef-d43b-f9c6170d43f1.png)
5. Under the **Grant this service account access to project** section, select the following roles from the **Role** menu by clicking **+ ADD ANOTHER ROLE**.

Click **Continue**.
  - BigQuery Data Viewer
  - BigQuery Job User
  - BigQuery Read Session User

![IAM-roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a767c18-3aed-78d3-32c9-34ec11b71275.png)
6. (Optional step) Under the **Grant users access to this service account** section, assign the following roles by entering the email of the user to whom you want to share the access.

> [!NOTE]
> **Note**
> 
> You can skip this step if you do not want to share access with the other users.
  - Service account users role
  - Service account admin role.

![Grant-user-access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7cbf778-d2fc-0e44-83d7-c5d2d2d32927.png)
  - On the **Create service account** page, Click **Done**

It creates a service account with the assigned roles.

### Step 2 - Create a key for your service account.

1. On the left sidebar, choose **Service Accounts** > **BigQuery Email** link as shown below.

![click-emaill.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95ce4881-58b0-6973-02e3-9b392b524176.png)
2. On the **Service account details** page under the **KEYS** tab, select the **Create new key** from the **ADD KEY** menu.

![Create-new-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d8ab3ad-ecc4-5457-d09c-0aa9a1ea334f.png)
3. On the **Create private key for “your service account”** popup, perform the following steps:
  1. Select the **JSON** radio button for the **Key type**.
  2. Click **CREATE**.

![JSON-Popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-911c7551-5cd8-e9b0-d185-5e2414d12550.png)

> [!NOTE]
> **Note**
> 
> It downloads the JSON file into your device. Save the file to use it for Connector Activation.
4. It shows the JSON success message popup as shown below. Click **Close**.

![success.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67c0078b-608c-ef1b-0799-dedc34778096.png)

It shows the saved key under the **KEYS** tab.

### Step 3 - Enable the APIs and Services:

> [!NOTE]
> **Note**
> 
> If your BigQuery API & Services option is already enabled, skip this step.

1. Access to the [BigQuery APIs and Service](https://console.cloud.google.com/marketplace/product/google/bigquery.googleapis.com) page.
2. On the **BigQuery API** page, click **ENABLE**.

![enable-api.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4dbd85ba-bf5f-c2e7-79d6-4f1b7e3a338e.png)

It automatically enables the BigQuery API.

### Step 4 - Obtain credentials for Google BigQuery

1. On the left side, choose **BigQuery** > **BigQuery Studio.**

![bigq-studio.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5bcdd8cb-cf0d-722d-0576-159b3d6c1879.png)
2. On the following page, click the **Project ID** and **Dataset Name** as shown in the image below.

| Parameter | Description |
| --- | --- |
| Project ID | Record the Project ID for connector activation. See the example below. `gbigquery-diagnostic-testing` |
| Dataset name | Record the Dataset name for Connector Activation. See the example below. `gbigquery_diag_testing_1` |

![Dataset-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb00785e-4802-a509-9dec-db0beffec79f.png)

### Step 5 - Create table if you are new to Google BigQuery (Optional)

> [!NOTE]
> **Note**
> 
> You can skip this step if you are an existing BigQuery with the active Table with the dataset.

1. On the top of the **Dataset info** page, click **Create Table** at the top.

![create-table.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42502225-019f-4e1d-65a8-b83a58cd0c15.png)
2. On the **Create Table** popup, do the following, as shown below:

| Parameter | Description |
| --- | --- |
| Create Table from | Select your external storage in the "Create Table from" menu, such as **Drive**. |
| Select Drive URI | Enter the file pattern per the selected external storage in the URI field. In the case of Google Drive, See the example below. <*https://drive.google.com/open?id=1IrA2fpSFR1RzSLkBhL1AZqGR5YPum7Jl*> |
| File format | Select **CSV** from the "File format" menu. |
| Project | Specify the Database (name) in the "Project" field under **Destination** section. |
| Dataset | Enter the name of your dataset. |
| Table | Enter the name of your Table. |
| Table type | Select External Table from the "Table type" menu |
| Autoselect | Under Schema, mark the **Auto detect** checkbox. |

![Import_CSV_file_from_External_storage_in_BQ.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd883a7f-0497-c3ce-1083-db32deb9f7b1.png)

Click **Create Table.**
3. In addition to Big Query API, you must enable **Google Drive API** from your Google Cloud Platform.
  1. Access the [APIs and Services library](http://APIs and Services library) in Google Cloud Platform.
  2. Search the Google Drive API in the search field.

![API_Library.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f73d5b15-ba6a-db5d-266e-d34cf7a6c619.png)
  3. Make sure Google Drive API is enabled. If it is not enabled. Click **ENABLE** ![Enable_Drive_API_in_BigQuery.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-940defd5-27db-e168-d674-3b6668e4bac7.png)
4. Proceed to [Activate the Google BigQuery connector in Securiti](/latest/docs/activate-the-google-bigquery-connector-in-securiti), [(New UI) Connecting Google BigQuery (self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-self-hosted-with-securiti) or [(New UI) Connecting Google BigQuery (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-securiti-cloud-with-securiti).
