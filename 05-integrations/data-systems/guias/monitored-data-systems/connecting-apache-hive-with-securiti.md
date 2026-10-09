---
title: "Connecting Apache Hive with Securiti"
slug: "connecting-apache-hive-with-securiti"
updated: 2026-07-01T19:59:41Z
published: 2026-07-01T19:59:41Z
canonical: "helpcenter.securiti.ai/connecting-apache-hive-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Apache Hive with Securiti

This topic covers activation of the Apache Hive (Self-hosted) connector.

## Creating a Apache Hive data system connector instance

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

## Authenticating Apache Hive connector

After creating a Apache Hive (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, select the JDBC driver file. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).
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

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Driver type | N/A | Select the type of driver from the menu: - Select the **Standalone** option to use the official Apache Hive JDBC driver. Ideal for basic Hive interactions with standard features. - Select the **Cloudera** option for the Cloudera JDBC driver that offers enhanced features, optimizations, and enterprise support tailored for Cloudera's ecosystem |
| Hive Host | N/A | Enter the hostname for your data system See an example below: `&lt;example&gt;.securiti.xyz` |
| Hive Port | N/A | Enter the access port address for your data system, See an example below: `5121` |
| (Optional) Enable SSL | N/A | Enable the toggle to enable SSL. |
| Authentication | N/A | Select the type of authentication from the menu: - ***Use password*** - ***Use keytab*** |
| (Optional) Use Keyring | Use Password | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Managing keyrings](/latest/docs/managing-credentials-using-keyrings). |
| (Optional) User | Use Password | Enter the username credential to access your data system. |
| (Optional) Password | Use Password | Enter the password credential to access your data system. |
| (Optional) Keytab Prinicpal (or Primary) | Use Keytab | Enter the Keytab Principal or primary name. If you enter a fully qualified name, for example, “<user>/<instance>@<realm>”, Securiti uses it as is. When you enter the information without the “@<realm>,” Securiti uses the realm from the provided field. |
| (Optional) Hive/Service Principal (or Primary) | Use Keytab | Enter the hive service principal. The treatment is identical to the keytab parameter above as it uses the “@” and “/” in the name. |
| Keytab | Use Keytab | Upload the keytab file. |
| (Optional) Kerberos Config | Use Keytab | Upload a sample “krb5.conf” file. You may need to remove any “#include” directives from the file. See the example below: ```plaintext [libdefaults] default_realm = EXAMPLE.COM dns_lookup_kdc = false dns_lookup_realm = false ticket_lifetime = 86400 renew_lifetime = 604800 forwardable = true default_tgs_enctypes = aes256-cts default_tkt_enctypes = aes256-cts permitted_enctypes = aes256-cts udp_preference_limit = 1 [realms] EXAMPLE.COM = { kdc = <kerberos kdc ip or host> admin_server = <kerberos admin server ip or host> } [domain_realm] .example.com = EXAMPLE.COM example.com = EXAMPLE.COM ``` > [!NOTE] > Note > > *<kerberos-server>:88* should be accessible from the appliance (securiti VM). 88 is the default port for Kerberos service |
| Instance/FQDN | Use Keytab | Enter the instance from the kerberos principal. See the examplee.g. instance component in <user>/<instance>@<realm> |
| Kerberos Realm | Use Keytab | Enter the Kerberos Realm name, which is usually a domain name. See the example below: `ABC.COM` |
| Transport Mode HTTP | N/A | In the **Transport Mode HTTP**, from the dropdown select Enable or Disable. |
| (Optional) HTTP Path | N/A | If you enable Transport Mode HTTP, then enter the Path of the endpoint to be used for HTTP/HTTPS requests. The default for an Apache Knox gateway is "gateway/default/hive" and that of Kerberos is "cliservice" `&lt;https://example.example/example.html&gt;` |
| Database | N/A | Enter the default database you use for this connector. See an example below: `exampleDatabase123` > [!NOTE] > **Note** > > The database name is case-sensitive. Enter it exactly as it appears in the data system. |
| (Optional) Additional Connection String Options | N/A | Enter additional parameters string options or keys if your driver supports them. |
| (Optional) Store Sample file on PCS | N/A | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page

> [!NOTE]
> Note
> 
> This step assumes you have downloaded the required drivers (Step 11) before activation. Otherwise, an error message reminding you to upload drivers is displayed.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Apache Hive (Self-hosted):

- [Configure discovery scans in Apache Hive](/latest/docs/configure-discovery-scans-in-apache-hive).

**Additional Resources**

- [Fulfilling DSR requests for Apache Hive](/latest/docs/fulfilling-dsr-requests-for-apache-hive).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
