---
title: "Connect Sybase ASE connector with Securiti"
slug: "connect-sybase-ase-connector-with-securiti"
updated: 2026-08-11T11:03:50Z
published: 2026-08-11T11:03:50Z
canonical: "helpcenter.securiti.ai/connect-sybase-ase-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Sybase ASE connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers setup of the Sybase ASE connector.

## Creating a Sybase ASE data system connector instance

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
9. In the **Hosting** **Location**, select from the following available hosting locations and service providers:

**SaaS/Privatecloud**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred hosting location as **SaaS** or **Private Cloud**. | SaaS, Private Cloud |

**IaaS-AWS**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **AWS**. | AWS |
| Account ID | Enter the **Account ID** for your AWS account. | `012345678901` |
| Region | From the **Region**, select your preferred region for the AWS account. | `us-east-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-GCP**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **GCP**. | GCP |
| Project ID | Enter the **Project ID** for your GCP account. | `project-123456` |
| Region | From the **Region**, select your preferred region for the GCP account. | `us-east-1` |
| Resource Name / Instance Id | In the **Resource Name / Instance Id**, enter the instance id for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) instance, bucket name for cloud storage or dataset name for BigQuery | `my-bigtable-instance` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-OCI**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **OCI**. | OCI |
| Tenancy Id | Enter the tenancy id for your OCI account to identify the root container. | `ocid1.tenancy.oc1..aaaaaaaa` |
| Account Id | Enter the account id or OCID for your OCI account to identify a specific resource. | `ocid1.oc1..aaaaaaaa` |
| Region | From the **Region**, select your preferred region for the OCI account. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-Azure**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **Azure**. | Azure |
| Subscription ID | Enter the subscription id for your Azure resource. | - |
| Resource Group | Enter the resource group for your Azure resource. | - |
| Server / Storage Account Name | In the **Server / Storage Account Name**, enter the server name for SQL Server or Cosmos DB, or the storage account name for Blob Storage/File Share | - |
| Region | From the **Region**, select your preferred region for the OCI account. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

1. After configuring the hosting location, continue by completing the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Country | Select the country from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the state or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the city where the data source or resource is located. | Calgary |
| Owners | Choose the primary owner for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
2. At the Bottom of the page, click **Create and Continue**.
3. It redirects you to the **Authentication** page.

## Authenticating Sybase ASE (Self-hosted) connector

After creating a Sybase ASE instance, in the **Authentication** tab, authenticate your connector:

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

1. Under the **Drivers** section, select the JDBC driver. You can select one the following driver from the menu:
  - Sybase JDBC driver
  - JTDS driver

> [!NOTE]
> **Note**
> 
> If you have not already uploaded the driver, download the required JDBC driver JAR files for your SQL database from the database vendor's website and upload them using the driver upload feature in Securiti before activating the data system.

For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti) and [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors).

1. In the **Credentials** section, configure the following settings that you recorded in [Configure your local Sybase ASE database for synchronization](/latest/docs/configure-your-local-sybase-ase-database-for-synchronization):

| **Setting** | **Description** |
| --- | --- |
| Host | Enter the IP address for your Sybase Database. The IP address follows *xxx.xx.xx.xx* format. See example below. `10.10.1.0` |
| Port | Enter the applicable port address for your Database The port address uses a number value. See example below `50432` |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** For more information, [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| User | Enter the username for the account with Administrative access. The username uses a string value. See the example below. `John` |
| Password | Enter the password for the account with Administrative access. |
| Database | Enter the name of your created Database. > [!NOTE] > **Important** > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. |
| (Optional) Use Jtds driver | Enable the **Use jtds driver** toggle if you are using jtds driver that uses Roman8 encoding for data storage. > [!NOTE] > **Note** > > Enabling this option requires you to upload jtds driver above in **Driver files** menu instead of JDBC driver. |
| (Optional) Additional Connection String Options | In case of JDBC driver, specify any JDBC additional string connections. You can specify multiple options separated by and '&'. In case of JTDS driver, specify any additional string connections. You can specify multiple options separated by a semicolon ';'. |
| (Optional) Include Views | Enable the toggle to include views as a part of the scan. > [!NOTE] > **Note** > > Including views may take a long time to finish Learning and increase the load on the Database server. |
| (Optional) store sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
2. Click **Test** **Connection** at the bottom of the page.
3. Proceed to [Configuring General scan settings for Sybase ASE](/latest/docs/initiate-sybase-ase-learning).

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scan settings for the Sybase ASE (self-hosted):

- [Configuring General scan settings for Sybase ASE](/latest/docs/initiate-sybase-ase-learning).

**Additional resources**

- [Fulfilling DSR requests for Sybase ASE](/latest/docs/fulfilling-dsr-requests-for-sybase-ase).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
