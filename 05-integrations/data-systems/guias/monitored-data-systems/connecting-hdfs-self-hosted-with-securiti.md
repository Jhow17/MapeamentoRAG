---
title: "Connecting HDFS (Self-hosted) with Securiti"
slug: "connecting-hdfs-self-hosted-with-securiti"
updated: 2026-07-08T08:02:38Z
published: 2026-07-08T08:02:38Z
canonical: "helpcenter.securiti.ai/connecting-hdfs-self-hosted-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting HDFS (Self-hosted) with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers activation of the HDFS (Self-hosted) connector.

## Creating a HDFS data system connector instance

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

## Authenticating HDFS connector

After creating a HDFS (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Authentication Method | Description |
| --- | --- | --- |
| Authentication Type | N/A | Select one the following the Authentication types. - **No authentication** - **Keytab** - **Password** Once you've selected the Authentication, configure the options for that type and enter parameters as outlined in [Obtain permissions and authentication credentials in HDFS](/latest/docs/obtain-permissions-and-authentication-credentials-in-hdfs). |
| Host | - No authentication - Keytab - Password | Enter the HDFS host address you acquired in [Obtain permissions and authentication credentials in HDFS](/latest/docs/obtain-permissions-and-authentication-credentials-in-hdfs). The HDFS host can be an IP address or domain name for the HDFS NameNode. See an example below. `192.0.2.1` or `namenode.example.com` |
| Port | - No authentication - Keytab - Password | Enter the HDFS port you acquired in [Obtain permissions and authentication credentials in HDFS](/latest/docs/obtain-permissions-and-authentication-credentials-in-hdfs). See an example below. `8020` |
| Path | - No authentication - Keytab - Password | Enter the HDFS path you want to scan. Enter the path you recorded in [Obtain permissions and authentication credentials in HDFS](/latest/docs/obtain-permissions-and-authentication-credentials-in-hdfs). See an example below. `/user/hadoop/data` |
| Use Keyring | - No authentication - Keytab - Password | Select Credentials from the Keyring by enabling the toggle. Following Keyring types are supported for HDFS. - [AWS Secrets Manager](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CredStash](/v1/docs/configuring-credential-vaults-credstash-credential-vault) - [HashiCorp](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) See [Using keyrings](/v1/docs/using-keyrings) for more information. |
| (Optional) Use Keyring | - No authentication - Keytab - Password | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **AWS Secrets Manager**: For more information, see [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault). - **Credstash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault). For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Managing keyrings](/latest/docs/creating-keyrings). |
| User | No authentication | If you are not using Keyring, specify which HDFS user the client will act as. See an example below. |
| Use Kerberos Configuration | - Keytab - Password | Enable the **Use Kerberos Configuration**, to provide a way to control various aspects of Kerberos authentication by uploading the config file that uses following format: `krb5.conf` |
| Kerberos Configuration File | - Keytab - Password | If Kerberos Configuration is enabled, then upload the configuration file for Kerberos. |
| Kerberos Host | - Keytab - Password | Enter the hostname used to communicate with the Kerberos server. |
| Kerberos Port | - Keytab - Password | Enter the port number used to communicate with the Kerberos server. |
| Kerberos Realm | - Keytab - Password | Enter the Kerberos realm, which is usually a domain name. See the example below. `domainname.com` |
| Kerberos Principal for Namenode | - Keytab - Password | Enter the Service Principal Name for the Namenode. See the example below. `namenode/_HOST` |
| (Optional for keytab) Kerberos Principal for User | - Keytab - Password | Enter the Service Principal Name for the user from the keytab. See the example below. `user/admin.domain.com` > [!NOTE] > Note > > If the principal belongs to a different realm than the default realm (in the Kerberos config), the principal should be in the following format. > > `&lt;USERNAME&gt;/&lt;FQDN&gt;@REALM.COM` |
| (Optional) Data transfer protection | - Keytab - Password | Select the following supported SASL protection values. - **Authentication** - **Integrity** - **Privacy** These values are used for secured connections to the DataNode when reading or writing block data. |
| Kerberos Keytab | Keytab | Upload the keytab file for Kerberos. It uses the following format. `filename.keytab` |
| Kerberos User Password | Password | Enter the password for your Kerberos user. |
| (Optional) Use datanode hostnames | - No authentication - Keytab - Password | This checkbox is not marked by default. - If you choose to keep **Use datanode hostnames** checkbox unmarked, you must allowlist all of the DataNode addresses to be accessible from our Appliance: - DataNode address using the default port **50010**. For more information, see [Hadoop documentation.](https://hadoop.apache.org/docs/r1.2.1/hdfs-default.html) - Custom DataNode address port, such as 1019. - If the DataNodes are accessible only through hostnames, mark the checkbox for **Use datanode hostnames** to connect using hostnames instead of IP addresses. |
| (Optional) Evaluate Data system size | - No authentication - Keytab - Password | Mark the checkbox to calculate the total size of the specified paths. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |
| Data secured with encryption | No authentication | Enable the toggle if data is encrypted in data nodes. Enabling this option will decrypt the data in encrypted file so content classification (CC) can be performed on that data. > [!NOTE] > **Note** > > This option is displayed only when **No Authentication** is selected as the Authentication type. |
| WebHDFS API Port | No authentication | Specify the port number used for communication with the WebHDFS (Hadoop Distributed File System over HTTP) service in a Hadoop cluster. > [!NOTE] > **Note** > > - This field is available only when the **Data secured with encryption** toggle is enabled. > - By default, the WebHDFS API listens on port 50070 for HTTP. However, the port number can be customized during the Configuration of the Hadoop cluster. |
4. Click **Test** **Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the HDFS (Self-hosted):

- [Configuring Data Inventory Sync for HDFS](/latest/docs/configuring-data-inventory-sync-for-hdfs).
- [Configure discovery scans in HDFS](/latest/docs/configure-discovery-scans-in-hdfs).

**Additional resources**

- [Fulfilling DSR requests in HDFS](/latest/docs/fulfilling-dsr-requests-in-hdfs).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
