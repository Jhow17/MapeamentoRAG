---
title: "Connecting Google BigQuery (Securiti cloud) with Securiti"
slug: "new-ui-connecting-google-bigquery-securiti-cloud-with-securiti"
status: "update"
updated: 2026-09-22T03:48:15Z
published: 2026-09-22T03:48:15Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-google-bigquery-securiti-cloud-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Google BigQuery (Securiti cloud) with Securiti

This topic covers activation of the Google BigQuery (Securiti cloud) connector.

> [!WARNING]
> **Important**
> 
> Securiti automatically detects when a Google BigQuery table requires a partition filter and applies the necessary filter for you. This applies across discovery scans (classification, CLOB scanning, and field sampling), Exact Data Matching (EDM) indexing and scanning, and DSR request fulfillment, for both Securiti cloud and self-hosted connectors. No additional configuration is required.

## Creating a Google BigQuery data system connector instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Project ID | **Project ID** is the project identifier of the associated dataset physically present in the project. Enter the alphanumeric string you recorded in [Acquire authentication credentials in Google BigQuery](/latest/docs/acquire-authentication-credentials-in-google-bigquery). | `bigquery-project-1122334` |
| Region | Select region for the resource in GCP associated with your BigQuery Dataset | `us-west` |
| Resource Name / Instance Id | Enter the Instance ID for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) Instance, Bucket name for Cloud Storage or Dataset name for BigQuery | `GBQ-admin` |
| Managed | Enable the **Managed** toggle to help differentiate between Native and Non-Native assets (Dark assets) | - |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating the Google BigQuery connector

After creating a Google BigQuery connector instance, in the **Authentication** tab, authenticate your connector:

1. > [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as:

  - Table Training Sample files
  - Sensitive Data Intelligence protection evidence files
  - Scan Summary

> [!NOTE]
> Note
> 
> DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support.

You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another:

  1. On the activated data system instance, click on the **Reconfigure** link.
  2. From the **PCS Destination** menu, select the PCS where you want to migrate the data.
  3. Click **Reconfigure connector**.

Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete.
2. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Project ID | **Project ID** is the Unique ID of your Google Cloud project. Use the project that contains the BigQuery dataset (unless the dataset is shared from another project). In BigQuery Studio, find it by selecting the project in the Explorer. Enter the alphanumeric string you recorded in [Acquire authentication credentials in Google BigQuery](/latest/docs/acquire-authentication-credentials-in-google-bigquery). |
| (Optional) Dataset Project ID | **Dataset Project ID** is only for shared datasets. Enter the ID of the project that owns the dataset. If provided, this value overrides 'Project ID'. In BigQuery Studio, find it under the dataset's parent project in the Explorer. |
| Dataset ID | Enter the name of your Database to configure in the connector. The dataset name uses a string value. See an example below. `automation` |
| (Optional) Query Label | Provide one or more query labels to tag queries generated by this connector with labels to organize and track scan costs in Google Cloud. Enter each label as a `key:value` pair, and use commas to separate multiple labels. The `value` can also be left empty. See some examples below. - `securitiapp:scangcp` - `securitiapp:` - `securitiapp:scangcp,gcpkey:data-opps` > [!NOTE] > Note > > - Ensure each key is unique and follows BigQuery label rules. > - The keys must start with lowercase letters and contain only lowercase letters, numbers and dashes. > - The keys must be between 1-63 characters and value must be between 0-63 characters. |
| Credentials File | Upload the JSON file you downloaded earlier: - For the service account credential file, see [Acquire authentication credentials in Google BigQuery](/latest/docs/acquire-authentication-credentials-in-google-bigquery). - For the custom role credential file, see [Create a custom role and assign permissions](/latest/docs/create-a-custom-role-and-assign-permissions). The JSON file follows the *.json* format. |
| (Optional) Include Views | Enable the toggle for Include Views if you want to include the virtual tables as a part of the scan. > [!NOTE] > **Note** > > Selecting this option increases the Learning time and increase the load on the Database server. |
| (Optional) Enable Random Sampling | Enable this toggle to enable random sampling on data if your data contains blank or null values. > [!NOTE] > **Note** > > Enabling random sampling requires more resources on the Database server and may take a long time to finish Learning. |
| (Optional) Additional Connection String Options | (Optional) Specify any additional JDBC string connections. You can specify multiple options separated by a semicolon ';'. |
3. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Google BigQuery:

- [Configuring General permissions for Google BigQuery (Securiti cloud)](/latest/docs/new-ui-configuring-general-permissions-for-google-bigquery-securiti-cloud).
- [Fulfilling DSR requests for Google BigQuery](/latest/docs/fulfilling-dsr-requests-for-google-bigquery).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
