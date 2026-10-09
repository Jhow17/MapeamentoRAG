---
title: "Connecting Microsoft 365 SharePoint Online (Self-hosted) with Securiti"
slug: "connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti"
updated: 2026-09-25T07:32:12Z
published: 2026-09-25T07:32:12Z
canonical: "helpcenter.securiti.ai/connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft 365 SharePoint Online (Self-hosted) with Securiti

This topic covers activation of the Microsoft 365 SharePoint Online (self-hosted) connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating Microsoft 365 SharePoint Online data system connector instance

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

## Authenticating the data system instance

After creating a Microsoft 365 SharePoint Online connector instance, in the **Authentication** tab, authenticate your connector:

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
| Tenant Name | - Client Secret - Certificate | Enter your Microsoft 365 tenant name you recorded earlier. See the examples below: If `testdomain.onmicrosoft.com` is the domain, `testdomain` is the Tenant Name. |
| Tenant ID | - Client Secret - Certificate | Enter your **Tenant ID** here you recorded earlier in [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted) or [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access). Tenant ID follows the string format. See the example below. `0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01` > [!WARNING] > **Important** > > The Tenant ID must be a GUID, not a domain name or an email address. |
4. In the **Credentials** section, configure the following settings:

| Setting | Credential Type | Description |
| --- | --- | --- |
| Credential Type | — | Select from the following supported Credential types: - **Client Secret** - **Certificate** |
| (Optional) Use Keyring | - Client Secret | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **Azure Key Vault:** For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). - **CyberArk:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| (Optional) Use the **OAuth 2.0 Secrets Engine Plugin** toggle to control whether this connector requires the OAuth plugin for HashiCorp Vault keyrings. - Disabled: Keeping the toggle disabled means the connector does not require the OAuth plugin integration. In this case, Securiti retrieves vault credentials and generates an access token, removing the dependency on the OAuth 2.0 plugin. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) and [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp). - Enabled: Enabling the toggle means the connector requires the OAuth plugin integration. In this case, the plugin retrieves credentials and generates an access token to authenticate with Securiti For more information, see [Installing and setting up the OAuth 2.0 secrets engine plugin with HashiCorp](/latest/docs/installing-and-setting-up-oauth2-secrets-engine). > [!WARNING] > Important > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Application (Client) ID | - Client Secret - Certificate | If you are not using Keyring, enter the Application ID you recorded earlier in [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted) or [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access). The **Application (Client) ID** uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | - Client Secret | If you are not using Keyring, enter the **Client Secret** you recorded earlier in [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted) or [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access) The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
| (Optional for Client Secret) Certificate Thumbprint | - Client Secret - Certificate | Provide the **Certificate Thumbprint** you recorded earlier. The Certificate Thumbprint uses an alphanumeric string value. See the example below. `34F34D57A1233EAB12345F67ABC89012D34EF5AB` > [!WARNING] > Important > > Activating the SharePoint (self-hosted) connector with a Certificate Thumbprint is required to enable the following capabilities: > > - Scoping Inventory Sync: > - Retrieval of site and hub-site properties > - Retrieval of hub-site relationships > - Data Inventory Sync: > - GenCore entitlements > - Data Access Intelligence: > - Privilege Analysis |
| Private Key | - Client Secret - Certificate | Upload the private key (.pem) file you generated earlier. The private key file uses a .pem file extension usually. See the example below. `securiti_private_key.pem` > [!WARNING] > Important > > The parameter is mandatory for Data Inventory Sync and Entitlement Scan. |
| (Optional) Scan only selected sites | - Client Secret - Certificate | Enable the **Scan only selected sites** toggle if you need to scan only the selected SharePoint Sites only. > [!NOTE] > Note > > This option requires you to create two separate Azure applications are required because the Permissions serve different purposes: > > - Selective Sites Access application with: > > Sites.Selected permission > - Full Control application (Provisioning application) with: > > Sites.FullControl.Allpermission > [!WARNING] > Important > > Enabling this option restricts important functionalities of Securiti platform. For more information, see Selective Sites Access limitations. |
| Upload **SharePoint Sites** using a single-column CSV file you created in [Creating a CSV file for sites generated from Postman](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access). Securiti displays the CSV file name post Activation of the SharePoint Online Connector |
| (Optional) Multi-geo root domains | - Client Secret - Certificate | If you are not Scanning only selective site, and your tenant spans multiple Microsoft 365 geographies, enable **Multi-geo root domains.** List additional root domains here, separated by commas. See the example below of the format you must follow. <*request.sharepoint.com*, *datasubjectrequest.sharepoint.com*> > [!NOTE] > Tip > > Leave the field blank if you do not want to use root site collections for your account and instead want to scan the default site collection, AKA "default geo. |
| (Optional) Allow Quarantine actions on this Data System | - Client Secret - Certificate | Enable the **Allow Quarantine actions on this Data System** toggle to use the quarantine Feature for your Microsoft 365 SharePoint Online Instance. This toggle is a prerequisite to creating a File Insight Policy in Sensitive Data Intelligence. For more information, see [Creating a File Insights policy](/latest/docs/creating-a-file-insights-policy). > [!NOTE] > Note > > You must grant read and write Privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. > [!CAUTION] > Caution > > If any of your folder names contain a '%' symbol, the quarantine operations may not behave as expected. We recommend you avoid using the '%' symbol in folder names to ensure proper functionality. > > Files belonging to syste libraries will be excluded from the file quarantine process |
| (Optional) **Quarantine Site URL** Enter the Quarantine Site URL you recorded in [(Optional) Acquire Quarantine Policy parameters in SharePoint Online](/latest/docs/optional-acquire-quarantine-policy-parameters-in-sharepoint-online). > [!CAUTION] > Warning > > Securiti does not scan sites configured as the quarantine destination. If the SharePoint Online site specified in the Quarantine Site URL field is also included in the scan scope, it is automatically skipped during the scanning process. To scan files in that site, remove the site URL from the Quarantine Site URL field. |
| (Optional) **Quarantine Site Library Name** Enter the Quarantine Site Library Name by accessing the documents in your SharePoint Site. See the example below. `Documents` |
5. Click **Test** **Connection** at the bottom of the page.

> [!NOTE]
> Note
> 
> Securiti connects to Microsoft 365 SharePoint Self-hosted automatically, without any human intervention during connector activation.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans configurations

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft 365 SharePoint Online (self-hosted):

- [Configuring Data Inventory Sync for SharePoint Online (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted).
- [Configuring discovery scans in Microsoft 365 SharePoint Online](/latest/docs/configure-discovery-scans-in-microsoft-365-sharepoint-online).
- [Configuring General and Access permissions for Microsoft 365 SharePoint (Self-hosted)](/latest/docs/configuring-general-and-access-permissions).
- [Fulfilling SharePoint Online Self-hosted DSR requests](/latest/docs/fulfilling-sharepoint-online-self-hosted-dsr-requests).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
