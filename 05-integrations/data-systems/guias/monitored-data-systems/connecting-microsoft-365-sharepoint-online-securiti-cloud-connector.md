---
title: "Connecting Microsoft 365 SharePoint Online (Securiti-Cloud) with Securiti"
slug: "connecting-microsoft-365-sharepoint-online-securiti-cloud-connector"
updated: 2026-06-23T06:25:27Z
published: 2026-06-23T06:25:27Z
canonical: "helpcenter.securiti.ai/connecting-microsoft-365-sharepoint-online-securiti-cloud-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft 365 SharePoint Online (Securiti-Cloud) with Securiti

This topic covers activation of the Microsoft 365 SharePoint Online Securiti-Cloud connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating Microsoft 365 Online SharePoint data system instance

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

## Authenticating the Microsoft 365 SharePoint Online data system instance

After creating a Microsoft 365 SharePoint Online connector instance, in the **Authentication** tab, authenticate your connector:

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
2. In the **Cloud** **Configuration** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Cloud | From the menu, choose the pre-configured clouds. For most installations, you choose "Microsoft Graph global service." |
| Tenant Name | Enter your Microsoft 365 tenant name you recorded earlier. See the examples below: If *testdomain.onmicrosoft.com* is the domain. *testdomain* is the Tenant Name. |
| Tenant ID | Enter your Tenant ID here. Tenant ID follows the string format. See the example below. `0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01` |
3. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Client ID | If you are not using Keyring, enter the Application ID you recorded earlier in [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud) The **Client ID** uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | If you are not using Keyring, enter the **Client Secret** you recorded earlier in [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud) The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
4. Click **Test** **Connection** at the bottom of the page.
5. Securiti redirects you to the Microsoft login window, as shown below. Log in with your admin Credentials.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MS 1(2).png)
6. Microsoft prompts you to accept the permissions requested by the Securiti app in Azure, click **Accept** as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MS 2(2).png)

Microsoft redirects you back to Securiti. You have finished activating the Connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft 365 SharePoint Online (Securiti-Cloud)

- [Fulfilling SharePoint Online Cloud DSR requests](/latest/docs/fulfilling-sharepoint-online-cloud-dsr-requests)
- [Configuring General permissions for Microsoft 365 SharePoint Online (Securiti-Cloud)](/latest/docs/configuring-general-permissions-for-microsoft-365-sharepoint-online-securiti-hosted)
