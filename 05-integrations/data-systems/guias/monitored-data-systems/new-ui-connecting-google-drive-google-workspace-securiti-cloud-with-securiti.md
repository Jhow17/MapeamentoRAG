---
title: "Connecting Google Drive (Google Workspace) (Securiti cloud) with Securiti"
slug: "new-ui-connecting-google-drive-google-workspace-securiti-cloud-with-securiti"
updated: 2026-07-14T03:44:28Z
published: 2026-07-14T03:44:28Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-google-drive-google-workspace-securiti-cloud-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Google Drive (Google Workspace) (Securiti cloud) with Securiti

This topic covers activation of the Google Drive (Google Workspace) (Securiti-Cloud) connector.

## Creating a Google Drive (Google Workspace) data system connector instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, **or** **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Google Drive (Google Workspace) (Securiti cloud) connector

After creating a Google Drive (Google Workspace) connector instance, in the **Authentication** tab, authenticate your connector:

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
| G Suite Domain Administrator's Email | Enter the admin email address you used when logging into the Google admin console to prepare for the connector. > [!NOTE] > **Important** > > You can't use service account email for connector activation. You can only use admin email for cloud connectors. |
| Service account key file | Click **Choose File** and navigate to the key file you downloaded when configuring API client access in [Prerequisites for Google Drive (Google Workspace) (Securiti-Cloud) connector](/latest/docs/prerequisites-for-g-suite-google-drive-securiti-cloud-connector) |
3. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Google Drive (Google Workspace) (Securiti-Cloud):

- [Configure General permissions for Google Drive (Google Workspace) (Securiti-Cloud)](/latest/docs/configure-general-permissions-for-google-drive-google-workspace-securiti-cloud).

**Additional Resources**

- [Fulfilling DSR requests for Google Drive (Google Workspace) (Securiti-Cloud)](/latest/docs/fulfilling-dsr-requests-for-google-drive-google-workspace-securiti-cloud).
- [Troubleshooting for Google Drive (Google Workspace)](/latest/docs/troubleshooting-for-g-suite-google-drive).
- [Google Drive (Google Workspace) FAQs](/latest/docs/g-suite-google-drive-faqs-en).
