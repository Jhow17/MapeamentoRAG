---
title: "Connecting Databricks with Securiti"
slug: "new-ui-connecting-databricks-with-securiti"
updated: 2026-07-21T05:32:21Z
published: 2026-07-21T05:32:21Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-databricks-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Databricks with Securiti

This topic covers activation of the Databricks (self-hosted) connector.

## Creating a Databricks data system connector instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations** > **Monitored Data Systems**
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add** **Integration** page, click the **Self-Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, complete the following parameters to create an instance:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
8. In the **Hosting** **Location**, select the following available hosting locations:
  - **SaaS**
  - **Private Cloud**
  - **IaaS**

> [!NOTE]
> Note
> 
> For SaaS and private Cloud hosting location, below mentioned IaaS configurations must be skipped.

For the IaaS hosting location, complete the following parameters for each service provider:

**IaaS-AWS**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **AWS.** | AWS |
| Account ID | To obtain the **Account ID**, log in to your AWS Management Console, and your account ID can be found in the upper right corner of the dashboard. | `012345678901` |
| Region | Specify the AWS region where you want to host your Securiti instance. | `us-east-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-GCP**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **GCP**. | GCP |
| Project ID | To obtain the **Project ID**, log in to your Google Cloud Console, select your project, and the Project ID can be found on the project dashboard. | `project-123456` |
| Region | Specify the GCP region where you want to host your Securiti instance. | `us-east-1` |
| Resource Name / Instance Id | In the **Resource Name / Instance Id**, enter the instance id for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) instance, bucket name for cloud storage or dataset name for BigQuery. | `my-bigtable-instance` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-OCI**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **OCI**. | OCI |
| Tenancy Id | To obtain the **Tenancy Id**, log in to your OCI Console, navigate to your tenancy details, and the Tenancy Id can be found in the tenancy information. | `ocid1.tenancy.oc1..aaaaaaaa` |
| Account Id | Similar to the Tenancy ID, the **Account ID** can be found in the tenancy information. | `ocid1.oc1..aaaaaaaa` |
| Region | Specify the OCI region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-Azure**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your Service provider as **Azure**. | Azure |
| Subscription ID | Enter the subscription id for your Azure resource. | - |
| Resource Group | Enter the resource group for your Azure resource. | - |
| Server / Storage Account Name | In the **Server / Storage Account Name**, enter the server name for SQL Server or Cosmos DB, or the storage account name for Blob Storage/File Share. | - |
| Region | Specify the AZURE region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

1. After configuring the hosting location and service provider information, continue by completing the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Country | Select the country from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the state or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the city where the data source or resource is located. | Calgary |
| Owners | Choose the primary owner for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (Optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (Optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
2. At the bottom of the page, click **Create and Continue**.
3. It redirects you to the **Authentication** page.

## Authenticating the Databricks connector

After creating a Databricks connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, from the **Driver** menu, choose the latest driver. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).
3. > [!WARNING]
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
4. In the **Credentials** section, configure the following settings:

| Setting | Authentication Method | Description |
| --- | --- | --- |
| Host | N/A | Enter the hostname for Databricks you recorded earlier. See an example below: `&lt;example&gt;.cloud.databricks.com` |
| Port | N/A | Enter the access port address for Databricks you recorded earlier. See an example below: `443` |
| Authentication | N/A | Select one of the following authentication methods from the menu: - **Personal Access Token** - **OAuth 2.0** |
| (Optional) Use Keyring | - Personal Access Token - OAuth 2.0 | Enable the toggle if you have used a credential vault to store the keyring. From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **CyberArk:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault-1). - **Azure Key Vault:** For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). Select the keyring or vault instance in the **Keyring** field. |
| Access Token | - Personal Access Token | If not using keyring, enter the access Token you recorded in [Grant permissions and obtain credentials in Databricks](/latest/docs/grant-permissions-and-obtain-credentials-in-databricks). |
| Client ID | - OAuth 2.0 | If not using keyring, enter the Client ID you recorded in [Create Service Principal and obtain credential](/latest/docs/create-service-principal-and-obtain-credential). See the example below. `aba1010-a10b-1a10-110a-ba1b10ab10ab` |
| Client Secret | - OAuth 2.0 | If you are using OAuth 2.0 authentication, enter the Client Secret you recorded in [Create Service Principal and obtain credential](/latest/docs/create-service-principal-and-obtain-credential). See the example below. `aba11011b110abab101a0001b0ab101a110` |
| HTTP Path | - Personal Access Token - OAuth 2.0 | Enter the HTTP path you recorded in [Grant permissions and obtain credentials in Databricks](/latest/docs/grant-permissions-and-obtain-credentials-in-databricks). |
| Account Id | - Personal Access Token - OAuth 2.0 | Enter the Databricks Account Id that follows the string format. See the example below. `ea1ad0101-a10a-1010-ab0a-aaba01e0101a` |
| (Optional) Use SSL | - Personal Access Token - OAuth 2.0 | Enable this option if you want to use SSL configuration. See an example below: *false* |
| (Optional) Additional Connection String Options | - Personal Access Token - OAuth 2.0 | (Optional) Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. For more information, see the [driver guide](https://www.databricks.com/spark/jdbc-drivers-download), mentioned in [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors). |
| (Optional) Bypass Proxy Configuration | - Personal Access Token - OAuth 2.0 | Enable this option if you want to bypass proxy configuration. See an example below: `false` |
| (Optional) Store Sample file on PCS | - Personal Access Token - OAuth 2.0 | **Store Sample files on PCS** toggle is disabled by default. Note In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in your tenant. Without PCS, support for storing sample files is unavailable for structured or hybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). Note This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which store sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Databricks:

- [Configuring discovery scans in Databricks](/latest/docs/configuring-discovery-scans-in-databricks).
- [Configuring General and Access permissions in Databricks](/latest/docs/new-ui-configuring-general-and-access-permissions-1).

**Additional resources**

- [Fulfilling DSR requests for Databricks](/latest/docs/fulfilling-dsr-requests-for-databricks).
- [Table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Troubleshooting for Databricks](/latest/docs/troubleshooting-for-databricks)
