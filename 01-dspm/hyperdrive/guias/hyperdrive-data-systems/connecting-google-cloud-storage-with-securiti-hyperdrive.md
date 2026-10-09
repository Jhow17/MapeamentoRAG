---
title: "Connecting Google Cloud Storage with Securiti (Hyperdrive)"
slug: "connecting-google-cloud-storage-with-securiti-hyperdrive"
updated: 2026-05-25T21:06:24Z
published: 2026-05-25T21:06:24Z
canonical: "helpcenter.securiti.ai/connecting-google-cloud-storage-with-securiti-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting Google Cloud Storage with Securiti (Hyperdrive)

This topic covers activation of the Google Cloud Storage (self-hosted) connector.

## Creating a Google Cloud Storage data system connector instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating the Google Cloud Storage connector

After creating a Google Cloud Storage connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Outpost** you configured earlier in [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment).
2. > [!WARNING]
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
3. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Project ID | Enter the project name you recorded in [Prerequisites for Google Cloud Storage connector (Hyperdrive)](/latest/docs/prerequisites-for-google-cloud-storage-connector-hyperdrive). See the example below. `john-doe-project` |
| Bucket(s) | Securiti automatically sets the bucket name to the Data system Instance name. > [!NOTE] > **Note** > > - To update the bucket name, deactivate the Connector and modify the Data system Instance name. > - Use the Sensitive data Intelligence dashboard to link multiple buckets to a single Connector. See an example below for the bucket name. `bucket-identity-testing,va_securiti_bucket` |
| Authentication Type | Select **Credentials File** or **IAM Service Account** as the authentication method for your Connector. |
| (Optional) Use Keyring | **Use Keyring** support is not available for data systems that use Hyperdrive mode for authenticating the connector. |
| (**Credentials File** Authentication only) Credentials | In case you are not using a Keyring, upload the Credentials file as described in [Using Credentials File authentication (Hyperdrive)](/latest/docs/using-credentials-file-authentication-1). Click **Upload File** to upload the Credentials stored as key file in JSON format. *Credentials are provided in the form of a service account key, and the key is represented as a JSON* |
| (**IAM Service Account** Authentication only) IAM Service Account | Enter the complete email address of your GCP Target Service Account that can be delegated by the service account assigned to Pod, as described in [Using IAM Service Account authentication](/latest/docs/using-iam-service-account-authentication-hyperdrive) See an example below. `john.doe@devproject.iam.gserviceaccount.com` |
| Evaluate Data system size | Mark the checkbox to enable resource size evaluation of the GCP buckets. This calculates the total storage size and objects count. Securiti calculates resource size on a weekly basis to keep the data size value up to date. > [!NOTE] > **Important** > > - You must provide the `monitoring.timeSeries.list` permission to your GCP service account to enable bucket size evaluation. > - Resource size metrics for Google Cloud Storage (GCS) update every 24 hours. When objects are added to storage buckets, their sizes are reflected in Securiti only during the next weekly evaluation cycle, provided the Cloud provider has updated its metrics since your previous evaluation. |
| (Optional) Use Native Inventory | Enable the toggle to use the built-in feature to create a GCS inventory, enabling efficient analysis of GCS object contents. > [!NOTE] > **Note** > > Before enabling the toggle, you must review the differences between the two available Data Inventory Sync methods. For more information, see [Configuring Data Inventory Sync for Google Cloud Storage (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage-1). You must provide values for the following parameters in case you enable the toggle. - **Inventory Report Configuration**: Enter the inventory report Configuration name that you acquired in [Inventory report configuration for Google Cloud Storage (Hyperdrive)](/latest/docs/inventory-report-configuration-for-blob-hyperdrive). `projects/12345678/locations/us/reportConfigs/hvhgvhtf-12ehgfch` |
4. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using Data System Connectors Overview](/latest/docs/connectors-new-ui-template-1).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Google Cloud Storage:

- [Configuring Data Inventory Sync for Google Cloud Storage (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage-1).
- [Configure discovery scans in Google Cloud Storage (Hyperdrive)](/latest/docs/configure-discovery-scans-in-google-cloud-storage-1).
- [Troubleshooting for Google Cloud Storage connector (Hyperdrive)](/latest/docs/troubleshooting-for-google-cloud-storage-connector-1).
