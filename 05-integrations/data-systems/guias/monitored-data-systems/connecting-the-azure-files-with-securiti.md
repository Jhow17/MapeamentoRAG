---
title: "Connecting the Azure Files with securiti"
slug: "connecting-the-azure-files-with-securiti"
updated: 2026-06-22T11:04:18Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/connecting-the-azure-files-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Azure Files with securiti

This topic covers activation of the Azure Files self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

> [!NOTE]
> **Note**
> 
> (Optional) Although enabled by default, in **Settings > Configuration**, select the Allow storage account key access radio button (if not already selected), as shown below, before activating the connector.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(627).png)

## Creating an Azure Files (Self Hosted) data system instance

Perform the following steps to create a Data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | This field is automatically set to your data system's service provider. | Azure |
| Subscription ID | Enter the Azure **Subscription ID** for your data system account. The subscription ID uses an alphanumeric string value. | `acde070d-8c4c-4f0d-9d8a-162843c10333` |
| Resource Group | Enter the **Resource Group** name that contains the relevant Azure resources. The Resource Group uses an alphanumeric string value. > [!WARNING] > Important > > For connectors activated on pod versions 1.140.0 and above, this field is non-editable after activation. This ensures consistent ARN generation and preserves the container identity required for Data Inventory Syncs. To update this field, you must create a new connector. | `rg-finance-files` |
| Server / Storage Account Name | Enter the Azure **Server/ Storage Account Name**. The storage account name uses an alphanumeric string value. > [!WARNING] > Important > > For connectors activated on pod versions 1.140.0 and above, this field is non-editable after activation. This ensures consistent ARN generation and preserves the container identity required for Data Inventory Syncs. To update this field, you must create a new connector. | `financestorage01` |
| Activate at Storage Account Level | Mark the **Activate at Storage Account Level** checkbox to choose whether to activate the connector at the storage account level or at the container/file share level. |  |
| Resource Name | Enter the File share name in the resource group you specified earlier. The resource name uses an alphanumeric string value. > [!WARNING] > Important > > For connectors activated on pod versions 1.140.0 and above, this field is non-editable after activation. This ensures consistent ARN generation and preserves the container identity required for Data Inventory Syncs. To update this field, you must create a new connector. | `invoiceshare` |
| Region | Select your region from the menu. | `Australiacentral` |
| Managed | Enable the toggle to differentiate between native and non-native (dark) assets. |  |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Azure Files (Self Hosted) connector

After creating an Azure Files connector instance, in the **Authentication** tab, authenticate your connector:

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
| Authentication Type | Select your required authentication type from the menu. The following authentication types are supported for Azure Files. - Storage Account - Service Principal |
| File Share Name | Enter the Azure file share name in your resource group, which you acquired in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). See an example below. `marketing-logs` |
| Resource Group | Enter the resource group name containing your relevant file share, which you acquired in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). See the example below. `securitiTest` |
| Subscription ID | Specify the subscription ID for your Azure storage account, acquired in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). See an example below. `12345678-abcd-ef12-3456-7890abcdef` |
| (Optional) Private Endpoint | Enter the endpoint URL if you have hosted the Azure Files service on a private server. |
| (Optional) Allow Quarantine Actions on this Data System | Enable the toggle if you want to enable the quarantine policy for your Azure Files instance. > [!WARNING] > Important > > - You must configure your Azure Files connector with pod version 1.147.0 and above to enable quarantine actions on the data system. > - The connector must have read and write privileges on both the scanned target location and the designated quarantine folder. Without these permissions, quarantine actions cannot execute successfully. |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information. - **Azure Key Vault:** For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). - **CredStash**: For more information, see [Configuring CredStash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault). - **AWS Secret Manager** |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| (Storage Account authentication) Account Key | If you have selected **Storage Account** as an authentication type: Enter the Account Key you recorded earlier in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account) Enter either *key1* or *key2* generated for your Azure storage drive. The Account Key uses string value. See the example below. `8a7b3c9d-12e4-567f-=!=!89ab-0123456789cd` |
| (Service Principal authentication) Application (Client) Id | If you have selected Service Principal as an authentication type: Specify the **Client ID** you acquired for your Entra ID application in [Using Service Principal authentication](/v1/docs/using-service-principal-authentication) The client ID uses a string value. See an example below. `8a7b3c9d12e4567` |
| (Service Principal authentication) Application (Client) Secret Key | If you have selected Service Principal as an authentication type: Enter the value for your **Secret Key** that you created in [Using Service Principal authentication](/v1/docs/using-service-principal-authentication) |
| (Optional) Evaluate data system size | Mark the checkbox to evaluate the data system size at the time of authentication. It lists all shares and computes total storage usage for Azure Files. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |
4. In the **Cloud Configuration** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Storage Account Name | Enter the account name you recorded earlier in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). The Account Name uses a string value. See the example below. `azurestoragefiles` |
| Tenant Id | If you have selected Service Principal as an authentication type: Specify the tenant ID you acquired for your Entra ID application in [Using Service Principal authentication](/v1/docs/using-service-principal-authentication) The tenant ID uses a string value. See an example below. `12343c9d12e4567` |
5. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Box:

- [Configure discovery scans in Azure Files](/latest/docs/configure-discovery-scans-in-azure-files)
- [Fulfilling DSR requests for Azure Files](/latest/docs/fulfilling-dsr-requests-for-azure-files)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
