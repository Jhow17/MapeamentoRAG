---
title: "Connecting Microsoft Azure SQL Database with Securiti"
slug: "connecting-microsoft-azure-sql-database-with-securiti"
updated: 2026-06-22T14:46:47Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/connecting-microsoft-azure-sql-database-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft Azure SQL Database with Securiti

This topic covers activation of the Microsoft Azure SQL Database (Self-hosted) connector.

## Creating Microsoft Azure SQL Database data system connector instance

Perform the following steps to create a Data system instance for Self-hosted connectors:

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

## Authenticating Microsoft Azure SQL Database connector

After creating a Microsoft Azure SQL Database connector instance, in the **Authentication** tab, authenticate your connector:

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
| Authentication Type | N/A | Selector as the Authentication type. - **Service Principal** - **Service Principal with Certificate** - **Basic Authentication** - **Azure AD Authentication** |
| Host | N/A | Specify the fully qualified domain name (FQDN) of your Azure SQL Server. See an example below. *myazuresqlserver.Database.windows.net* Provide the IP address if the SQL Server is accessible via a static IP. See an example below. `52.168.25.42` |
| Port | N/A | Enter the port number for SQL Server connections, the default port is *(1433)*. |
| Database | N/A | Enter the name of the database you wish to scan. > [!NOTE] > **Important** > > For pod versions 1.137.0 and above, you can only enter a single database name. The Database name is case-sensitive. Enter it exactly as it appears in the data system. > > > > For previously configured connectors with blank or multiple database names, Securiti continues to activate them without changes. See the example below. `automation, access db` |
| (Optional) Use Keyring | N/A | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **Azure Key Vault**: For more information, see [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Managing keyrings](/latest/docs/managing-credentials-using-keyrings). |
| User | - Service Principal - Service Principal with Certificate - Basic Authentication - Azure AD Authentication | If you are not using Keyring, add the user depending on the Authentication type you choose. - For **Service Principal** based Authentication: Specify the client ID of the service principal you acquired in [Acquire credentials for Service Principal authentication](/latest/docs/obtain-credentials-for-service-principal-authentication). The client ID uses a string value. See an example below. `12345678-90ab-cdef-1234-567890abcdef` - For **Basic** Authentication: Enter the SQL admin username you set while creating an Azure SQL Server in [Acquire credentials for Basic authentication](/latest/docs/prerequisites-for-microsoft-azure-sql-database). See the example below. `testusera1010` |
| Password | - Service Principal - Service Principal with Certificate - Basic Authentication - Azure AD Authentication | If you are not using Keyring, add the password depending on the Authentication type you choose. - For **Service Principal** based Authentication: Specify the client secret or the .pfx Certificate password of the service principal you acquired in [Acquire credentials for Service Principal authentication](/latest/docs/obtain-credentials-for-service-principal-authentication). The client secret uses a string value. See an example below. `wJ7F8cK4hT7w9P8sQ4Lr3M2xX1dZ0Y` - For **Basic** Authentication: Enter the password you set while creating an Azure SQL Server in [Acquire credentials for Basic authentication](/latest/docs/prerequisites-for-microsoft-azure-sql-database). See the example below. `yourpassword@1a013` |
| Certificate | Service Principal with Certificate | Upload the Certificate file you recorded in [Acquire credentials for Basic authentication](/latest/docs/prerequisites-for-microsoft-azure-sql-database). |
| (Optional) Additional Connection String Options | - Service Principal - Service Principal with Certificate - Basic Authentication - Azure AD Authentication | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. |
| (Optional) Use SSL | - Service Principal - Service Principal with Certificate - Basic Authentication - Azure AD Authentication | Enable the option if you wish to use Secure Sockets Layer (SSL) encryption between Securiti and Azure SQL server. |
| (Optional) Store Sample file on PCS | - Service Principal - Service Principal with Certificate - Basic Authentication - Azure AD Authentication | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
4. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft Azure SQL Database (Self-hosted)

- [Configure discovery scans in Microsoft Azure SQL Database](/latest/docs/configure-discovery-scans-in-microsoft-azure-sql-database).

**Additional resources**

- [Fulfilling DSR requests for Microsoft Azure SQL Database](/latest/docs/fulfilling-dsr-requests-for-microsoft-azure-sql-database).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
