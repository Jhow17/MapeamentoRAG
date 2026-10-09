---
title: "Connecting Azure Blob Storage (Self Hosted) with Securiti (Hyperdrive)"
slug: "connecting-azure-blob-storage-self-hosted-with-securiti-hyperdrive"
updated: 2026-05-25T20:26:49Z
published: 2026-05-25T20:26:49Z
canonical: "helpcenter.securiti.ai/connecting-azure-blob-storage-self-hosted-with-securiti-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting Azure Blob Storage (Self Hosted) with Securiti (Hyperdrive)

This topic covers activation of the Azure Blob Storage self-hosted connector.

> [!NOTE]
> **Note**
> 
> (Optional) Although enabled by default, in **Settings > Configuration**, select the Allow storage account key access radio button (if not already selected), as shown below, before activating the connector.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(627).png)

## Creating an Azure Blob Storage (Self Hosted) data system instance

Perform the following steps to create a Data system instance for **Self Hosted** connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | This field is automatically set to your data system's service provider. | Azure |
| Subscription ID | Enter the Azure **Subscription ID** for your data system account. The subscription ID uses an alphanumeric string value. | `acde070d-8c4c-4f0d-9d8a-162843c10333` |
| Resource Group | Enter the **Resource Group** name that contains the relevant Azure resources. The Resource Group uses an alphanumeric string value. | `rg-production-apps` |
| Server / Storage Account Name | Enter the Azure **Server/ Storage Account Name**. The storage account name uses an alphanumeric string value. | `mystorageacctprod01` |
| Activate at Storage Account Level | Mark the **Activate at Storage Account Level** checkbox to choose whether to activate the connector at the storage account level or at the container/file share level. |  |
| Resource Name | If you don’t mark the **Activate at Storage Account Level** checkbox, enter the File share name in the resource group you specified earlier. The resource name uses an alphanumeric string value. | `marketing-logs` |
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

After creating an Azure Blob Storage connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Outpost** you configured earlier in [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment)..
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
| Authentication Type | N/A | Select your required authentication type from the menu. The following authentication types are supported for Azure Files. - **Storage Account** - **Service Principal** - **Service Principal with Certificate** |
| Blob Container Name | N/A | Enter the Blob rule name in your resource group, which you acquired in [Enable blob inventory in your Azure account](/latest/docs/enable-blob-inventory-in-your-azure-account). See an example below. `marketing-logs` |
| Resource Group | N/A | Enter the resource group name that contains the relevant Azure resources. The Resource Group uses an alphanumeric string value, see an example below. `rg-production-apps` |
| Subscription ID | N/A | Specify the subscription ID for your Azure storage account, acquired in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). See an example below. `12345678-abcd-ef12-3456-7890abcdef` |
| (Optional) Private Endpoint | N/A | Enter the endpoint URL if you have hosted the Azure Files service on a private server. See an example below. `https://&lt;storage-account-name&gt;.privatelink.blob.core.windows.net` |
| (Optional) Use Keyring | N/A | **Use Keyring** support is not available for data systems that use Hyperdrive mode for authenticating the connector. |
| Account Key | Storage Account | If you are not using Keyring, then enter the **Account Key** you recorded earlier in [Using Service Principal to authenticate Azure Blob Storage](/latest/docs/using-service-principal-authentication). Enter either *key1* or *key2* generated for your Azure storage drive. The Account Key uses string value. See an example below. `8a7b3c9d-12e4-567f-=!=!89ab-0123456789cd` |
| Client ID | - Service Principal - Service Principal with Certificate | Specify the **Client ID** you acquired for your Entra ID application in [Using Service Principal to authenticate Azure Blob Storage](/latest/docs/using-service-principal-authentication) The client ID uses a string value. See an example below. `8a7b3c9d12e4567` |
| Secret Key | Service Principal | Specify the client secret you recorded for your Entra ID application in [Using Service Principal to authenticate Azure Blob Storage](/latest/docs/using-service-principal-authentication) |
| Service Principal Certificate | Service Principal with Certificate | Upload the certificate file you used for your Entra ID application in [Using Service Principal to authenticate Azure Blob Storage](/latest/docs/using-service-principal-authentication) The certificate file is in .pem format. |
| Service Principal Private Key | Service Principal with Certificate | Upload the private key file you generated for your Entra ID application in [Using Service Principal to authenticate Azure Blob Storage](/latest/docs/using-service-principal-authentication) |
| (Optional) Use Native Inventory | N/A | > [!NOTE] > **Note** > > By default, the Listing method is used for scanning. > > > > We recommend you understand the differences between the two available scanning methods. For more information, see [scanning methods for Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) . Enable the toggle **Use** **Native Inventory** for scanning. For Discovery scans, enabling this toggle uses the Native Inventory method only when the discovery scan job is configured without a prefix scan condition. If the prefix scan condition is used, the discovery scan uses the default Listing method even if this toggle is enabled. You must provide values for the following parameters in case you enable the toggle. - **Inventory Container**: Add the Inventory Container name you used to store the inventory reports in [Enable blob inventory in your Azure account](/latest/docs/enable-blob-inventory-in-your-azure-account). See an example below. *inventory-destination-container* - **Inventory Rule Name**: Add the Inventory Rule name you recorded in [Enable blob inventory in your Azure account](/latest/docs/enable-blob-inventory-in-your-azure-account). See an example below. *ruleName.* |
| (Optional) Allow Quarantine actions on this data system | N/A | > [!WARNING] > Important > > Files Quarantine support is not available for Azure Blob Storage using Hyperdrive mode. |
| (Optional) Evaluate data system size | - Service Principal - Service Principal with Certificate | Enable the toggle to evaluate the resource size during authentication. The option calculates the cumulative size of all containers for a storage account. Securiti calculates resource size on a weekly basis to keep the data size value up to date. > [!NOTE] > **Important** > > - To use this option, ensure you have provided the required `Monitoring Reader` role for your service principal account, as described in [Enabling resource size evaluation for Azure Storage Account](/v1/docs/using-service-principal-authentication). > - Resource size evaluation is only supported for **Service Principal** and **Service Principal with Certificate** authentication types. > - Resource size metrics for Azure Blob Storage update every 24 hours. When objects are added to storage buckets, their sizes are reflected in Securiti only during the next weekly evaluation cycle, provided the cloud provider has updated its metrics since your previous evaluation. > - You must use pod version 1.130 and above to enable resource size evaluation. You must provide values for the following parameters when you enable the toggle. - **Resource ID**: Specify the Resource ID of your Azure storage account that you acquired in [Enabling resource size evaluation for Azure Storage Account](/latest/docs/using-service-principal-authentication). See an example below. `/subscriptions/1234-acme-wxyz-5678-abcd/resourceGroups/test/Microsoft` |
4. In the **Cloud Configuration** section, configure the following settings:

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Storage Account Name | N/A | Enter the account name you recorded earlier in [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account). The Account Name uses a string value. See the example below. `azurestorageblob` |
| Tenant Id | - Service Principal - Service Principal with Certificate | Specify the **Tenant Id** you acquired for your Entra ID application in [Using Service Principal authentication](/v1/docs/using-service-principal-authentication) The tenant ID uses a string value. See an example below. `12343c9d12e4567` |
5. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Box:

- [Configuring discovery scans in Azure Blob Storage (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-azure-blob-storage-1)
- [Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted) (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted-1)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
