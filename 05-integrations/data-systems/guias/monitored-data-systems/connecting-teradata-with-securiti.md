---
title: "Connecting Teradata with Securiti"
slug: "connecting-teradata-with-securiti"
updated: 2026-06-28T11:03:12Z
published: 2026-06-28T11:03:12Z
canonical: "helpcenter.securiti.ai/connecting-teradata-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Teradata with Securiti

This topic covers activation of the Teradata (Self-hosted) connector.

## Creating a Teradata data system connector instance

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

## Authenticating the Teradata connector

After creating a Teradata connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. On the **Driver files** menu, select the driver file you previously uploaded.

> [!NOTE]
> **Note**
> 
> Use the latest driver because Snowflake deprecated the drivers older than the 3.13 version as of October 31, 2022.
  - If you don't see a driver file in the menu, click **Go to driver library** to upload the Teradata Driver files. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti)
  - For more information on the required drivers, see [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors).
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

| **Setting** | **Description** |
| --- | --- |
| Host | Enter the Host name or IP address of your Teradata Database. |
| Port | Enter the default port for the Teradata Database. The default port is 1050. > [!NOTE] > **Note** > > You must ensure that the Port is open between the Pod and the Teradata server. Otherwise, Securiti fails to establish the Connection. |
| (Optional) Use Keyring | You can enable the **Use Keyring** toggle if you want to use a Keyring to manage Credentials for the Instance as described in [Using keyrings](/v1/docs/using-keyrings). Then choose the **Keyring Type**, such as HashiCorp, and select your **Keyring**. Teradata supports the following credential vaults as keyrings. - [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [CyberArk](/latest/docs/cyberark-credential-vault-1) - [HashiCor](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)p > [!WARNING] > **Important** > > AWS Secret Manager, CredStash, and CyberArk support is not available for LDAP login mechanism. |
| Logmech | From the menu, choose your preferred login mechanism option: - TD2 (Traditional Teradata Database login mechanism) - LDAP (Lightweight Directory Access Protocol) |
| User | In case you are not using Keyring, enter the username based on the login mechanism: - In case of TD2 login mechanism, enter the username for your Teradata user you created in [Create a user and assign permissions in Teradata](/v1/docs/create-a-user-and-assign-permissions-in-teradata). - In case of the LDAP login mechanism, enter the username of the user configured in the LDAP server integrated with the Teradata database. See an example below. `john-Doe` |
| Password | In case you are not using Keyring, enter the username based on the login mechanism: - In case of TD2 login mechanism, enter the password for your Teradata user you created in [Create a user and assign permissions in Teradata](/v1/docs/create-a-user-and-assign-permissions-in-teradata). - In case of the LDAP login mechanism, enter the password of the user configured in the LDAP server integrated with the Teradata database. |
| (Optional) Query Band | Provide query band values to tag queries generated by this connector. The query band values must be specified in the `name=value` pairs to support workload management of query tracking in Teradata’s DBQL logs. Each pair must follow the `Name=Value` format and end with a semicolon, including the last pair. The `Value` can be empty as well. See some examples below. - `adminapp=securiti;jobID=daily_run;` - `AppName=Securiti;` > [!NOTE] > Note > > - Enter key-value pairs in the format: `Key=Value;` > - End each pair with a semicolon. > - Ensure keys and values meet the character limits defined in the UI. For keys, the character limit is 1-128 characters and for values, the limit is 0-256. > - Name and values cannot contain `=` `,` `;` or null characters. |
| Database/ [Schema] | Enter the name(s) of the databases you wish to scan. You have two options to add the Databases: - Enter a comma-separated list of database names. - Upload the CSV containing the list of database names. You must download the CSV template by clicking on the **Download CSV Template** link to use the correct format. > [!NOTE] > **Note** > > Some Teradata environments might require the Database name to be entered with exact case sensitivity to avoid metadata sync or Connection failures. Since behavior might vary, it is recommended to use the Database name exactly as it appears in the source system. |
| (Optional) Additional Connection string options | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. Add **JDBC_TREAT_DECIMAL_AS_INT=false** as an additional Connection parameter if the Database tables contain very large numbers to avoid running into errors. |
| (Optional) Include Views *(for Cloud Connector)* | Enable the toggle to include views as a part of the scan. > [!NOTE] > **Note** > > Including views may take a long time to finish Learning and increase the load on the Database server. |
| (Optional) store sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Teradata:

- [Configure discovery scans in Teradata](/latest/docs/configure-discovery-scans-in-teradata)
