---
title: "Connecting Amazon DocumentDB with Securiti"
slug: "connecting-amazon-documentdb-with-securiti"
updated: 2026-07-01T15:36:56Z
published: 2026-07-01T15:36:56Z
canonical: "helpcenter.securiti.ai/connecting-amazon-documentdb-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon DocumentDB with Securiti

This topic covers activation of the Amazon DocumentDB (self-hosted) connector.

## Creating an Amazon DocumentDB data system connector instance

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

## Authenticating the Amazon DocumentDB connector

After creating an Amazon DocumentDB connector instance, in the **Authentication** tab, authenticate your connector:

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
| Host | Enter the IP address or domain name of the server. The Amazon DocumentDB host URL ends in **docdb.amazonaws.com**. See the example below. *connectors-docdb.xyz-west.docdb.amazonaws.com* |
| Port | Enter the port number on which the Amazon DocumentDB server is running. The default port number for Amazon DocumentDB is 27017. See the example below. *27017* |
| (Optional) Use Keyring | Enable the toggle to use the keyring to manage credentials for your instance. See below topics for more information on supported credential vaults for Amazon DocumentDB. - [Using keyrings](/v1/docs/using-keyrings) - [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) - [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [Configuring CredStash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault) - [Configuring Azure key vault](/latest/docs/configuring-credential-vaults-azure-key-vault) |
| (Optional) Keyring Type | Select your keyring from the menu. |
| (Optional) Keyring | Select your vault instance for the selected keyring. |
| User | Enter your username with the required permissions. See the example below. *John_Securiti* |
| Password | Enter your account password. |
| Database | Enter the name of the database, you want to connect with. The database name uses a string value. See the example below. *automation db* > [!NOTE] > **Note** > > The database name is case-sensitive. Enter it exactly as it appears in the data system. |
| Auth Database Name | Enter the database name used for authentication. See the example below. *admin* |
| Row scan depth | Enter the row scan depth value for your data scan. The row scan depth value is a number. See the example below. *100* |
| Use SSL (optional) | Enable the toggle if you want to use a certificate for authentication. |
| Use SSH (Only for outside VPC connection) | Enable the toggle if you want to connect the Amazon DocumentDB outside VPC. |
| SSH Host (Only for outside VPC connection) | Enter the SSH Host of the EC2 machine, that you created within the same VPC. Host is the public DNS name or the public IP address of the EC2 instance The SSH Host URL ends in **docdb.amazonaws.com**. See the example below. *ec2-203-0-113-25.compute-1.amazonaws.com* |
| SSH Port (Only for outside VPC connection) | Enter the default SSH Port. See the example below *27017* |
| SSH User (Only for outside VPC connection) | Enter the default user of the EC2 instance's operating system. See the example below. *Ec2-user* |
| Upload Certificate File (Only for outside VPC connection) | Upload the SSH certificate downloaded using [Amazon Documentation](https://truststore.pki.rds.amazonaws.com/global/global-bundle.pem) SSH certificate file uses the **.pem** format. See the example below. *global_bundle.pem* |
| Additional Connection String Options (optional) | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ;. |
| Timeout | Enter a custom timeout if you want the activation session greater than Securiti default. |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
4. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector. /sn

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon DocumentDB:

- [Configure discovery scans in Amazon DocumentDB](/latest/docs/configure-discovery-scans-in-amazon-documentdb).
- [Fulfilling DSR requests in Amazon DocumentDB](/latest/docs/fulfilling-dsr-requests-for-amazon-documentdb).
- [Troubleshooting for Amazon DocumentDB connector](/latest/docs/troubleshooting-for-amazon-documentdb-connector)
