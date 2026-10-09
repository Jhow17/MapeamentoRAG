---
title: "Connecting Amazon RDS for PostgreSQL with Securiti"
slug: "connecting-amazon-rds-for-postgresql-with-securiti"
updated: 2026-08-10T14:38:06Z
published: 2026-08-10T14:38:06Z
canonical: "helpcenter.securiti.ai/connecting-amazon-rds-for-postgresql-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon RDS for PostgreSQL with Securiti

This topic covers activation of the Amazon RDS for PostgreSQL (self-hosted) connector.

## Creating an Amazon RDS for PostgreSQL data system connector instance

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

## Authenticating the Amazon RDS for PostgreSQL connector

After creating an Amazon RDS for PostgreSQL connector instance, in the **Authentication** tab, authenticate your connector:

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
| Host | Enter the IP Address for your Amazon RDS for PostgreSQL database. See an example below: *<xxx.xxx.xxx.xxx>* |
| Port | Enter the specified port number for your Amazon RDS for PostgreSQL database. See an example below: *5432* |
| Authentication Type | Select **Basic** or **IAM Roles** from the menu. - For the basic authentication method, use your admin user and password to configure the connector. For IAM roles: 1. Enter your "IAM User/Role" in the field. > [!NOTE] > **Note** > > If you have previously added the IAM Role from the appliance, leave the field blank. 2. Specify the "Region" in the field. 3. Enter your "Accound Id" in the field. |
| (Optional) Use Keyring | You can enable the Use Keyring toggle if you want to use a keyring to manage credentials for the instance as described in [Managing keyrings](/v1/docs/managingcredentials-using-keyrings). Then choose the keyring type, such as HashiCorp and keyring (applies to the Self-hosted app version). |
| For **Basic Authentication** Type - For the basic authentication method, use your admin user and password to configure the connector. |
| User | Enter your Amazon RDS for PostgreSQL login username or email. |
| Password | Enter your Amazon RDS for PostgreSQL login password. |
| For **IAM Role Authentication** Type |
| IAM User/Role | Enter your "IAM User/Role" in the field. > [!NOTE] > **Note** > > If you have previously added the IAM Role from the appliance, leave the field blank. |
| Region | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab, as described above. The pre-populated value is according to the below region to location mapping: - `us-east-1: northernvirginia` - `us-east-2: ohio` - `us-west-1: northerncalifornia` - `us-west-2: oregon` - `us-gov-east-1: usgov-east` - `us-gov-west-1: usgov-west` - `af-south-1: capetown` - `ap-east-1: hongkong` - `ap-south-1: mumbai` - `ap-south-2: hyderabad` - `ap-northeast-3: osaka` - `ap-northeast-2: seoul` - `ap-southeast-1: singapore` - `ap-southeast-2: sydney` - `ap-southeast-3: jakarta` - `ap-southeast-4: melbourne` - `ap-southeast-5: malaysia` - `ap-northeast-1: tokyo` - `ca-central-1: centralcanada` - `ca-west-1: calgary` - `cn-north-1: beijing` - `cn-northwest-1: ningxia` - `eu-central-1: frankfurt` - `eu-central-2: zurich` - `eu-west-1: ireland` - `eu-west-2: london` - `eu-west-3: paris` - `eu-south-1: milan` - `eu-south-2: spain` - `eu-north-1: stockholm` - `il-central-1: telaviv` - `me-south-1: bahrain` - `me-central-1: uae` - `mx-central-1: mexico` - `sa-east-1: saopaulo` |
| Account Id | Specify your AWS account ID. The AWS account ID uses a 12 digit numeric value. See an example below. *123456789012* |
| (Optional) Default Database | Enter the name of a default database that the server can use to connect when no database list is provided. Then, this database is used to fetch the list of all available databases. > [!NOTE] > **Note** > > If both the **Default Database** and **Database** fields are empty, Securiti connects to the database that matches the username. |
| (Optional) Database | Enter the name(s) of the databases you wish to scan. You can enter a comma-separated list of names or upload a .csv file containing database names. > [!NOTE] > **Important** > > The database name is case-sensitive. Enter it exactly as it appears in the data system. Also, to prevent the connection from failing, do not leave the Database field blank when authenticating the connector via the IAM Roles method because Amazon RDS for PostgreSQL would consider the IAM User as the database name instead. |
| (Optional) Additional Connection String Options | (Optional) Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';' See the [driver guide](/v1/docs/securiti-pods-and-elastic-pods) for more information. |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon RDS for PostgreSQL:

- [Configure discovery scans in Amazon RDS for PostgreSQL](/latest/docs/configure-discovery-scans-in-amazon-rds-for-postgresql).
- [Fulfilling DSR requests in Amazon RDS for PostgreSQL](/latest/docs/fulfilling-dsr-requests-in-amazon-rds-for-postgresql).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
