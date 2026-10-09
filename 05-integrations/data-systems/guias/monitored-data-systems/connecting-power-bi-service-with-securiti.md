---
title: "Connecting Power BI Service with Securiti"
slug: "connecting-power-bi-service-with-securiti"
updated: 2026-07-31T09:50:43Z
published: 2026-07-31T09:50:43Z
canonical: "helpcenter.securiti.ai/connecting-power-bi-service-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Power BI Service with Securiti

This topic covers activation of the Power BI Service self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Power BI Service data system instance

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

## Authenticating the Power BI Service connector

After creating the Power BI Service instance, in the **Authentication** tab, authenticate your connector:

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

> [!NOTE]
> Note
> 
> To scan all worspaces, you must add the user to the worspaces as described in [Add a user to the Power BI workspaces](/latest/docs/add-a-user-to-powerbi-workspace).

| Parameter | Description |
| --- | --- |
| Tenant ID | Enter the Tenant ID that you acquired in [Grant permissions and obtain credentials in Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-in-power-bi-service). - Tenant ID follows the string format. See the example below. `0a1b01a1-aob1b-1a1a-b0b0-101010ab1a01` > [!NOTE] > Note > > For pod versions 1.145.0 and above, you can configure multiple connectors using same Tenant ID to enable parallel PowerBI scans and improve performance, unless restricted by technical limitations. |
|  | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| (Optional) Use Keyring | From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information. - To authenticate Power BI Service connector without Service Principal-based authentication, you must configure OAuth as described in [(Optional) Configure the Hashicorp OAuth token for Power BI Service](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-power-bi-service). - To authenticate Power BI Service connector through Service Principal-based authentication, you must configure the OAuth as described in [Configuring OAuth token for Microsoft 365 applications](https://helpcenter.securiti.ai/docs/storing-data-system-credentials-in-hashicorp-vault#configuring-oauth-token-for-microsoft-365-applications). - **Azure Key Vault:** see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) for more information. - **CyberArk:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault). |
|  | (Optional) Use the **OAuth 2.0 Secrets Engine Plugin** toggle to control whether this connector requires the OAuth plugin for HashiCorp Vault keyrings. - **Disabled:** Keeping the toggle disabled means the connector does not require the OAuth plugin integration. In this case, Securiti retrieves vault credentials and generates an access token, removing the dependency on the OAuth 2.0 plugin. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) and [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp). - **Enabled****:** Enabling the toggle means the connector requires the OAuth plugin integration. In this case, the plugin retrieves credentials and generates an access token to authenticate with Securiti For more information, see [Installing and setting up the OAuth 2.0 secrets engine plugin with HashiCorp](/latest/docs/installing-and-setting-up-oauth2-secrets-engine). > [!WARNING] > **Important** > > - Starting with Securiti release 1.143 replaces manual admin authentication for the Power BI Service with Service Principal–based authentication. > - For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Client ID | Enter the client ID that you recorded in [Grant permissions and obtain credentials in Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-in-power-bi-service). The client ID uses a string value. See an example below. `1234abcd-wxyz-1234-5678abcde` > [!NOTE] > Note > > Starting with Securiti release 1.143 replaces manual admin authentication for the Power BI Service with Service Principal–based authentication. For more information, see [Grant Permissions and obtain credentials using Service Principal for Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-using-service-principal). |
| Client Secret | Enter the client secret that you recorded in [Grant permissions and obtain credentials in Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-in-power-bi-service). > [!NOTE] > Note > > Starting with Securiti release 1.143 replaces manual admin authentication for the Power BI Service with Service Principal–based authentication. For more information, see [Grant Permissions and obtain credentials using Service Principal for Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-using-service-principal). The Client Secret uses a string value. See an example below. `1234abcdwxyz12345678abcde` |
4. Click **Test Connection** at the bottom of the page.

> [!NOTE]
> Note
> 
> - If you have authenticated using service principal credentials, then Securiti connects to Power BI Service without any human intervention during connector activation.
> - If you have authenticated without service principal credentials, then Securiti redirects to Microsoft Azure portal for admin consent to successfully activate the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Power BI Service:

- [Configure discovery scans in Power BI Service](/latest/docs/configure-discovery-scans-in-power-bi-service).
- [Fulfilling DSR requests for Power BI Service](/latest/docs/fulfilling-dsr-requests-for-power-bi-service).
