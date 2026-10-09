---
title: "Connecting the OneDrive (Self-hosted) data system"
slug: "create-microsoft-365-onedrive-self-hosted-connector-instance-new-ui"
updated: 2026-09-25T07:35:48Z
published: 2026-09-25T07:35:48Z
canonical: "helpcenter.securiti.ai/create-microsoft-365-onedrive-self-hosted-connector-instance-new-ui"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the OneDrive (Self-hosted) data system

This topic covers activation of the Microsoft 365 OneDrive (self-hosted) connector.

## Creating Microsoft 365 OneDrive data system connector instance

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

## Authenticating Microsoft 365 OneDrive (Self-hosted) connector

After creating a Microsoft 365 OneDrive connector instance, in the **Authentication** tab, authenticate your connector:

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
| Tenant ID | - Client Secret - Certificate | Enter your **Tenant ID** here you recorded earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted). Tenant ID follows the string format. See the example below. `0a1b01a1-ab1b-1a1a-b0b0-101010ab1a``01` |
| Tenant Name | - Certificate | Enter the Tenant Name that you obtained earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted) |
4. In the **Credentials** section, configure the following settings:

| Setting | Credential Type | Description |
| --- | --- | --- |
| Credential Type | — | Select from the following supported Credential types: - **Client Secret** - **Certificate** |
| (Optional) Use Keyring | - Client Secret | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: see [Configuring HashiCorp credential vaults](https://helpcenter.securiti.ai/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information. - **CyberArk Vault**: see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault) for more information. |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| When HashiCorp is selected as the Keyring type, the **OAuth 2.0 Secrets Engine Plugin** toggle appears. Enable the toggle for plugin to use the provided credentials to mint and access tokens automatically. Leave the toggle disabled in case you do not want to use the OAuth 2.0 plugin for HashiCorp vault. When disabled, Securiti retrieves credentials from the vault and generates an access token itself. > [!WARNING] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Application (Client) ID | - Client Secret - Certificate | If you are not using Keyring, enter the Application ID you recorded earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted). The **Application (Client) ID** uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | Client Secret | If you are not using Keyring, enter the **Client Secret** you recorded earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted). The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
| Certificate Thumbprint | Certificate | Enter the Certificate Thumbprint that you recorded earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted). |
| Private Key | Certificate | Upload the Private Key that you recorded earlier in [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted). Private key supports `.pem` file type. |
| (Optional) Use Mock Server | - Client Secret - Certificate | Enable the toggle to **Use mock server.** |
| (Optional) Allow Quarantine actions on this Data system | - Client Secret - Certificate | Enable the **Allow Quarantine actions on this Data system** toggle to use the quarantine Feature for your Microsoft 365 OneDrive Instance. This toggle is a prerequisite to creating a File Insight Policy in Sensitive Data Intelligence. For more information, see [Creating a File Insights policy to quarantine files](https://helpcenter.securiti.ai/v1/docs/configuring-file-insights-policies). > [!NOTE] > Note > > You must grant read and write Privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. > [!CAUTION] > Caution > > If any of your folder names contain a '%' symbol, the quarantine operations may not behave as expected. We recommend you avoid using the '%' symbol in folder names to ensure proper functionality. > > Files belonging to syste libraries will be excluded from the file quarantine process |
| (Optional) **Quarantine Site URL** Enter the Quarantine Site URL you recorded in [(Optional) Acquire Quarantine Policy parameters in OneDrive](/latest/docs/optional-acquire-quarantine-policy-parameters-in-onedrive) |
5. Click **Test** **Connection** at the bottom of the page

> [!NOTE]
> Note
> 
> Securiti connects to Microsoft 365 OneDrive Self-hosted automatically, without any human intervention during connector activation.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft 365 OneDrive (self-hosted):

- [Configuring Data Inventory Sync](/latest/docs/configuring-data-inventory-sync-for-onedrive-self-hosted).
- [Configuring discovery scans in Microsoft 365 OneDrive](/latest/docs/configure-discovery-scans-in-microsoft-365-onedrive).
- [Configuring General Permissions for Microsoft 365 OneDrive (Self-hosted)](/latest/docs/new-ui-configuring-general-permissions).

**Additional resources**

- [Fulfilling OneDrive Self-hosted DSR requests](/latest/docs/fulfilling-onedrive-self-hosted-dsr-requests).
- [Microsoft 365 OneDrive FAQs](/latest/docs/microsoft-365-onedrive-faqs).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
