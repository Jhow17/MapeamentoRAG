---
title: "Connecting Microsoft Teams with Securiti"
slug: "new-ui-creating-microsoft-teams-self-hosted-connector-instance"
updated: 2026-09-25T07:30:06Z
published: 2026-09-25T07:30:06Z
canonical: "helpcenter.securiti.ai/new-ui-creating-microsoft-teams-self-hosted-connector-instance"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft Teams with Securiti

This topic covers activation of the Microsoft Teams self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

> [!NOTE]
> Note
> 
> Securiti requires these URLs to be allowlisted on the customer's firewall for the Microsoft Teams to ensure proper functionality of Sensitive data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:
> 
> - [https://graph.microsoft.com](https://graph.microsoft.com)
> - [https://login.microsoftonline.com](https://login.microsoftonline.com)

## Creating a Microsoft Teams data system instance

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

## Authenticating Microsoft Teams (Self-hosted) connector

After creating Microsoft Teams connector instance, in the **Authentication** tab, authenticate your connector:

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
3. In the **Cloud** **Configuration** section, configure the following settings:

| Setting | Credential Type | Description |
| --- | --- | --- |
| Cloud | - Client Secret - Certificate | From the menu, choose the pre-configured clouds. For most installations, you choose "Microsoft Graph global service." |
| Tenant Name | - Certificate | Enter the Tenant Name that you obtained earlier in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). |
4. In the **Credentials** section, configure the following settings:

| Setting | Credentials Type | Description |
| --- | --- | --- |
| Tenant ID | - Client Secret - Certificate | Enter your **Tenant ID** here you recorded in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). Tenant ID follows the string format. See the example below. `0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01` |
| Credential Type | — | Select from the following supported Credential types: - **Client Secret** - **Certificate** |
| (Optional) Use Keyring | - Client Secret | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select the following supported keyring: **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| Application (Client) ID | - Client Secret - Certificate | If you are not using Keyring, enter the Application ID you recorded earlier in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). The **Application (Client) ID** uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | - Client Secret | If you are not using Keyring, enter the **Client Secret** you recorded earlier in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
| Certificate Thumbprint | - Certificate | Enter the Certificate Thumbprint that you recorded earlier in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). |
| Private Key | - Certificate | Upload the Private Key that you recorded earlier in [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams). Private key supports `.pem` file type. |
5. Click **Test Connection** at the bottom of the page.

> [!NOTE]
> Note
> 
> Securiti connects to Microsoft Teams automatically using self-hosted connector, without any human intervention during connector activation.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Microsoft Teams:

- [Configuring Data Inventory Sync for Microsoft Team](/latest/docs/configuring-data-inventory-sync-for-microsoft-teams)
- [Configuring Microsoft Teams discovery scans](/latest/docs/configure-microsoft-teams-discovery-scans)
- [Fulfilling DSR requests for Microsoft Teams](/latest/docs/fulfilling-dsr-requests-for-microsoft-teams)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
