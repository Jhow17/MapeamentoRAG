---
title: "Connecting Google Drive (Google Workspace) Self-hosted with Securiti (Hyperdrive)"
slug: "new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1"
updated: 2026-07-20T20:56:22Z
published: 2026-07-20T20:56:22Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting Google Drive (Google Workspace) Self-hosted with Securiti (Hyperdrive)

This topic covers activation of the Google Drive (Google Workspace) Self-hosted connector using Hyperdrive mode.

## Creating a Google Drive (Google Workspace) data system connector instance

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

## Authenticating Google Drive (Google Workspace) (Self-Hosted) connector

After creating a Google Drive (Google Workspace) connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, from the **Outpost** menu, choose the Hybrid Deployment with Outpost or Full SaaS deployment you configured earlier. For more information, see [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment)..
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
| User Email Address | Enter the admin email address you used when logging into the Google admin console to prepare for the Connector. > [!NOTE] > **Important** > > You can only use admin email for Google Drive connector authentication using Hyperdrive mode. > > You can't use service account email for connector activation. This is because service accounts: > > - Are not members of your Google Workspace domain. > - Don’t appear in the user directory. > - Lack access to user data unless impersonating a valid domain user. |
| (Optional) Use Keyring | > [!CAUTION] > **Caution** > > Keyring support is not available data systems using Hyperdrive mode. |
| Service account key file | Click **Choose File** and navigate to the key file you downloaded when configuring API client access in [Generating Service Account Key File](/latest/docs/prerequisites-for-g-suite-google-drive-1#5-generating-service-account-key-file) |
4. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using Data System Connectors Overview](/latest/docs/connectors-new-ui-template-1).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Google Drive (Google Workspace) (self-hosted):

- [Connecting Google Drive (Google Workspace) (Self-Hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1)
- [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted) (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1)
- [Configure discovery scans in Google Drive (Google Workspace) (Self-hosted) (Hyperdrive)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted-1)

### Additional resources

- [Troubleshooting for Google Drive (Google Workspace) (Hyperdrive)](/latest/docs/troubleshooting-for-google-drive-google-workspace)
- [Google Drive (Google Workspace) FAQs](/latest/docs/google-drive-google-workspace-faqs)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
