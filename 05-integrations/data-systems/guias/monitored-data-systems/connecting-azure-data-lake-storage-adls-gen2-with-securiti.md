---
title: "Connecting Azure Data Lake Storage (ADLS) Gen2 with Securiti"
slug: "connecting-azure-data-lake-storage-adls-gen2-with-securiti"
updated: 2026-05-21T05:19:35Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/connecting-azure-data-lake-storage-adls-gen2-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Azure Data Lake Storage (ADLS) Gen2 with Securiti

This topic covers activation of the Azure Data Lake Storage (ADLS) Gen2 self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating an Azure Data Lake Storage (ADLS) Gen2 (Self Hosted) data system instance

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
| Hosting Location | Your **Hosting Location** will be set to **SaaS**. | SaaS |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. | - |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Azure Data Lake Storage (ADLS) Gen2 (Self Hosted) connector

After creating an Azure Data Lake Storage (ADLS) Gen2 connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Authentication type | N/A | Select one of the following authentication types: - **Account Key** - **Azure Service Principal** |
| Account Name | Account Key | Enter the Account Name you recorded in earlier. The Account Name uses a string value. See the example below. `azurestoragefiles` |
| Account Key | Account Key | In case you are not using a keyring, enter the Account Key you recorded earlier. The account key uses a string value. See the example below. `8a7b3c9d-12e4-567f-=!=!89ab-0123456789cd` |
| Client ID | Azure Service Principal | Enter the application ID you recorded earlier. The Client ID uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | Azure Service Principal | Enter the Client Secret you recorded earlier. The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
| Retrieve Last Access Time | - Account Key - Azure Service Principal | Enable the **Retrieve Last Access Time** to fetch the last access time for files. |
| Allow Quarantine actions on this Data System | - Account Key - Azure Service Principal | Enable if you want to use the quarantine feature for your Azure Data Lake Storage (ADLS) Gen 2. |
| (Optional) Use Keyring | - Account Key - Azure Service Principal | Enable the **Use Keyring** toggle to manage credentials for your instance. For more information on keyrings, see [using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| From **Keyring**, select the available keyrings: - [Configuring Azure key vault](/latest/docs/configuring-credential-vaults-azure-key-vault) - [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) For more information on HashiCorp OAuth token, see [(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2). |
4. In the **Cloud Configuration** section, configure the following settings:

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Account Name | - Account Key - Azure Service Principal | Enter the Account Name you recorded in earlier. The Account Name uses a string value. See the example below. `azurestoragefiles` |
| Tenant ID | Azure Service Principal | Enter the Tenant ID that follows the string format. See the example below. `0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01` |
5. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Azure Data Lake Storage (ADLS) Gen2:

- [Configure discovery scans in Azure Data Lake Storage (ADLS) Gen2](/latest/docs/configure-discovery-scans-in-azure-data-lake-storage-adls-gen2).
- [Configuring Data Inventory Sync for ADLS connector](/latest/docs/configuring-data-inventory-sync-for-adls-connector-en).
