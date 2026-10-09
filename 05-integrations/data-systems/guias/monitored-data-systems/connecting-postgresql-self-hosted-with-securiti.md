---
title: "Connecting PostgreSQL (self-hosted) with Securiti"
slug: "connecting-postgresql-self-hosted-with-securiti"
updated: 2026-05-29T05:36:29Z
published: 2026-05-29T05:36:29Z
canonical: "helpcenter.securiti.ai/connecting-postgresql-self-hosted-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting PostgreSQL (self-hosted) with Securiti

This topic covers activation of the PostgreSQL self-hosted connector.

## Creating a PostgreSQL data system instance

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

## Authenticating the PostgreSQL connector

After creating the PostgreSQL instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, from the **Driver** menu, choose the latest driver.
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

| Parameter | Description |
| --- | --- |
| Host | Enter the IP Address for your PostgresSQL Database in *xxx.xxx.xxx.xxx* format. See the example below. `192.158.1.38` |
| Port | Enter the specified port number *(5432)* |
| (Optional) Use Keyring | Enable the toggle and from the **Keyring Type** menu, choose your preferred vault. You can manage keyrings as mentioned in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). Enter the Keyring in the **Keyring** field you configured earlier. PostgreSQL supports the following keyrings: - **Basic keyring.** - **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **CyberArk**: For more information, see [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault). - **AWS Secrets Manager**: For more information, see [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault). - **CredStash**: For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). - **Azure Key Vault**: For more information, see [Configuring Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault). |
| (Optional when using HashiCorp Keyring only) Enable the **Generate Dynamic Credentials** toggle to use dynamic credentials from HashiCorp vault using the database secrets engine. For more information, see [Using Database secrets engine for dynamic credentials](/latest/docs/using-database-secrets-engine-for-dynamic-credentials). |
| User | If not using keyring, then enter the username for the account you recorded earlier in [Obtain database credentials for your PostgreSQL configuration](/latest/docs/obtain-database-credentials-for-your-postgresql-configuration). *john_securiti* |
| Password | If not using keyring, then enter the password for the account you recorded earlier in [Obtain database credentials for your PostgreSQL configuration](/latest/docs/obtain-database-credentials-for-your-postgresql-configuration). |
| Default Database | Enter the name of a default Database that the server can use to connect when no Database list is provided. Then, this Database is used to fetch the list of all available databases. > [!NOTE] > **Note** > > If both the **Default Database** and **Database** fields are empty, Securiti connects to the Database that matches the username. |
| Database | Enter the name(s) of the databases you wish to scan. You can enter a comma-separated list of names. Alternatively, you can upload a CSV file containing the databases you want to include. > [!NOTE] > **Important** > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. > > Optionally, you may find some connectors accepting the blank or empty Database field and would still activate the usual way. See example below. *automation, access db* |
| (Optional) Additional Connection String Options | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ;. |
| (Optional) Utilize prepared statements | Enable the toggle if you want Securiti to execute prepared statements for the PostgreSQL Connector. > [!NOTE] > **Note** > > After the 1.89 release, you have to reconfigure the existing Connector instances before running a Discovery scan to update the Configuration. You do not lose any data in the process. |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test Connection** at the bottom of the page.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Connector Diagnostics Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for PostgreSQL:

- [Configure discovery scans in PostgreSQL](/latest/docs/configure-discovery-scans-in-postgresql-en).
- [Fulfilling DSR requests for PostgreSQL](/latest/docs/fulfilling-dsr-requests-for-postgresql)
