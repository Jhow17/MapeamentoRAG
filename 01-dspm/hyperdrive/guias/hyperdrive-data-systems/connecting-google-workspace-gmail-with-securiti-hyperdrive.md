---
title: "Connecting the Gmail (Google Workspace) with Securiti (Hyperdrive)"
slug: "connecting-google-workspace-gmail-with-securiti-hyperdrive"
updated: 2026-09-26T19:43:43Z
published: 2026-09-26T19:43:43Z
canonical: "helpcenter.securiti.ai/connecting-google-workspace-gmail-with-securiti-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Gmail (Google Workspace) with Securiti (Hyperdrive)

Before starting the authentication and connection for Gmail (Google Workspace) using Hyperdrive mode, see the [Prerequisites](/latest/docs/gmail-google-workspace-hyperdrive#prerequisites1) and [obtaining authentication credentials](/latest/docs/obtaining-authentication-credentials-in-google-apps-for-gmail-hyperdrive) topics.

## Creating a Gmail (Google Workspace) data system connector instance

Perform the following steps to create a Data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the Integrations menu, choose **Monitored Data systems.**
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
| Hyperdrive mode | Mark the **Hyperdrive mode** checkbox to enable Dynamic Compute, used for adaptive resource scaling to optimize data scanning performance > [!NOTE] > Note > > Once the integration has been created with dynamic compute enabled, this option cannot be turned off. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Gmail (Google Workspace) (Self Hosted) connector

After creating a Gmail (Google Workspace) connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Outpost** you configured earlier in [Hyperdrive deployment](/latest/docs/hyperdrive-deployment).
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
| G Suite Domain Administrator's Email | Enter the admin email address you used when logging into the Google admin console to prepare for the connector. See the example below. `john.doe@securiti.ai` |
| Optional) Use Keyring | > [!CAUTION] > Caution > > Keyring support is not available for data systems using Hyperdrive mode. |
| Service account key file | Click **Upload File** and navigate to the key file you downloaded when configuring API client access in the [prerequisites and obtaining authentication credentials for Gmail](/latest/docs/obtaining-authentication-credentials-in-google-apps-for-gmail-hyperdrive). |
4. Click **Test** **Connection** at the bottom of the page

Securiti activates the Connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/connectors-new-ui-template-1).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-authentication-statuses-hyperdrive).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Gmail (Google Workspace) (Self-hosted):

- [Configure discovery scans in Gmail (Google Workspace) (self-hosted) (Hyperdrive)](/latest/docs/configure-discovery-scans-in-g-suite-gmail-message-body-attachments-1).
- [Configure Data Inventory Sync for Gmail (Google Workspace) (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive)
- [Configure Activity Analysis scan for Gmail (Google Workspace) (Hyperdrive)](/latest/docs/configure-activity-analysis-for-gmail-google-workspace-hyperdrive)
