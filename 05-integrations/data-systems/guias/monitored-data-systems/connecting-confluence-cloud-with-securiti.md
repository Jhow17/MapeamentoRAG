---
title: "Connecting Confluence Cloud with Securiti"
slug: "connecting-confluence-cloud-with-securiti"
updated: 2026-05-25T06:49:46Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/connecting-confluence-cloud-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Confluence Cloud with Securiti

This topic covers activation of the Confluence Cloud connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating an Confluence Cloud data system instance

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

## Authenticating Confluence Cloud connector

After creating an Confluence Cloud connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
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
| (Optional) Custom Domain | Enable the **Custom Domain** toggle option if you want to use the full URL of your Atlassian site. > [!NOTE] > **Note** > > Enabling this toggle requires you to enter the full **Atlassian Site URL** instead of **Site Name**. |
| Atlassian Site URL | In case of **Custom Domain** option enabled above, enter the complete **Atlassian Site URL** of your custom domain. See an example below. `https://confluence.acme.com` |
| Site Name | In case of **Site Name**, enter the confluence site name. The site name can be extracted from the base URL in [Acquire authentication credentials in Confluence Cloud](/latest/docs/acquire-authentication-credentials-in-confluence-cloud). See an example below. `foundri_site` |
| Client ID | Enter the Client ID you recorded in [Acquire authentication credentials in Confluence Cloud](/latest/docs/acquire-authentication-credentials-in-confluence-cloud). The Client ID uses string value. See an example below. `8a7b3c9d-12e4-567f-89ab-0123456789cd` |
| Client Secret | Enter the Client Secret you recorded in [Acquire authentication credentials in Confluence Cloud](/latest/docs/acquire-authentication-credentials-in-confluence-cloud). The Client Secret uses string value, See an example below. `n3v3rU53th1s_Ke3p1tS3cur3!` |
4. Click **Test Connection** at the bottom of the page.

In the popup, select the site name from the menu corresponding to one specified in the **Site Name** field during connector activation, as shown below.

> [!WARNING]
> Important
> 
> Connector authentication fails if the site selected from the menu does not match the one specified during connector activation.

![confluence_sitename.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-335295d4-5b35-96e4-6808-869e6d79f2eb.png)

Click **Accept** to accept the Confluence permissions.

> [!NOTE]
> Note
> 
> You can only activate one connector per site.
5. Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Confluence Cloud:

- [Configure Data Inventory Sync for Confluence Cloud](/latest/docs/configure-data-inventory-sync-for-confluence-cloud)
- [Configure discovery scans in the Confluence Cloud](/latest/docs/configure-discovery-scans-in-the-confluence-cloud).
- [Viewing Confluence Cloud metadata in Securiti](/latest/docs/viewing-confluence-cloud-metadata-in-securiti).
- [Fulfilling DSR requests for Confluence Cloud](/latest/docs/fulfilling-dsr-requests-for-confluence-cloud).
