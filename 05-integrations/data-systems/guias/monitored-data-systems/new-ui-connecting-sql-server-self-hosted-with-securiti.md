---
title: "Connecting Microsoft SQL Server with Securiti"
slug: "new-ui-connecting-sql-server-self-hosted-with-securiti"
status: "update"
updated: 2026-09-16T10:14:10Z
published: 2026-09-16T10:14:10Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-sql-server-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft SQL Server with Securiti

This topic covers activation of the SQL Server (self-hosted) connector.

## Creating SQL Server data system connector instance

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
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating SQL Server (self-hosted) connector

After creating an SQL Server connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, from the **Select Driver File** menu, On the **Driver files** menu, select the driver file you previously uploaded. If you haven’t uploaded Driver files, click **Go to driver library** to its right.

See the following topics for more information.

> [!NOTE]
> **Note**
> 
> Securiti supports all versions of MS SQL Server when an appropriate JDBC driver is used. Consult the [MS SQL Server documentation](https://learn.microsoft.com/en-us/sql/connect/jdbc/microsoft-jdbc-driver-for-sql-server?view=sql-server-ver16) or reach out to your Database administrator to determine the correct JDBC driver version.
  - [Uploading JDBC driver files in Securiti](/v1/docs/uploading-jdbc-driver-files-in-securiti)
  - [Downloading JDBC drivers for SQL connectors](/v1/docs/downloading-jdbc-drivers-for-sql-connectors)
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

| **Setting** | **Authentication Type** | **Description** |
| --- | --- | --- |
| Driver files | N/A | On the **Driver files** menu, select the driver file you previously uploaded. Or if you have uploaded Driver files, click "Go to driver library" to its right. See the following topics for more information. - [Uploading JDBC driver files in Securiti](/v1/docs/uploading-jdbc-driver-files-in-securiti) - [Downloading JDBC drivers for SQL connectors](/v1/docs/downloading-jdbc-drivers-for-sql-connectors) > [!NOTE] > **Note** > > Securiti supports all versions of MS SQL Server when an appropriate JDBC driver is used. Consult the [MS SQL Server documentation](https://learn.microsoft.com/en-us/sql/connect/jdbc/microsoft-jdbc-driver-for-sql-server?view=sql-server-ver16) or reach out to your Database administrator to determine the correct JDBC driver version. |
| Authentication Type | N/A | From the menu, select the type as shown below. - SQL Server Authentication - Windows Authentication > [!WARNING] > **Important** > > For windows Authentication, you must provide public and private IP address. - Azure AD Authentication (applies only to SQL Server deployed as a service in Azure). See [Downloading JDBC drivers for SQL connectors](/v1/docs/downloading-jdbc-drivers-for-sql-connectors) for information on the additional driver(s) required when using Azure AD connect via password. > [!NOTE] > **Note** > > For Windows Authentication and Active Directory Password Authentication, we assume you have access to a running SQL Server Instance or have access to its admin to obtain the necessary Credentials for Connector Activation. - Kerberos Authentication. Select one of the following strategies in the **Authentication Strategy** field. - **Use Password** - **Use Keytab** |
| Host | N/A | Enter the hostname or IP address for your Microsoft SQL Server database, recorded in Prerequisites for Microsoft SQL Server connector. Valid hostnames take the form 'hostname', 'hostname.domain', or 'hostname.domain.com'. IP addresses use the format 'x.x.x.x', where x is a number between 0 and 255. See the example below. *10.10.1.0* |
| Port | N/A | Enter the port number you recorded in [Prerequisites for Microsoft SQL Server connector](/latest/docs/prerequisites-for-microsoft-sql-server-connector). Valid port numbers are between 1 and 65535 (inclusive). Use the default instance's port, or enter the specific port for a named instance. See the example below. *50432* |
| Database | N/A | Enter the name(s) of the databases you wish to scan. You can enter a comma-separated list of names or leave the field empty to scan all databases. In the **Upload File**, you can import a CSV file containing database names in a single column (without a header row). > [!WARNING] > **Important** > > - The Database name(s) are case-sensitive. Enter them exactly as they appear in the Data system. > - Service account needs to have access to all databases and tables in the Data system. If not, you need to configure individual Database names in the Connector for Authentication.. |
| (Optional) Exclude JTDS Driver | Windows Authentication | Enable this toggle to avoid the use of the JTDS driver using Windows Authentication. > [!NOTE] > **Note** > > This option works with the JTDS driver version *mssql-jdbc-12.8.1.jre11.jar*. It does not work with the older versions. If you enable this toggle, you need to add an additional string value in the Additional Connection String Options field. For more information, see the Additional Connection String Options Row below. |
| Domain | Windows Authentication | Enter your SQL Server domain name here. |
| (Optional) Kerberos Config | Kerberos Authentication | Upload the Kerberos Configuration file (krb5.conf) containing the following information: - Location of KDCs and admin servers of the Kerberos realms of interest. - Defaults for the current realm - Mappings of hostnames onto Kerberos realms |
| (Optional) Keytab Principal **(For Keytab strategy only)** | Kerberos Authentication | Specify the Keytab principal if using AD user principal. If the keytab principal is the same the SPN, leave the field empty. See an example below if using AD user principal. *user@REALM* |
| Keytab **(For Keytab strategy only)** | Kerberos Authentication | Upload the keytab file you acquired in [(Optional) Using Kerberos authentication](/v1/docs/prerequisites-for-microsoft-sql-server-connector). The keytab file uses **.keytab** file extension. |
| KDC | Kerberos Authentication | Enter the hostname or IP address for your KDC server, acquired in [(Optional) Using Kerberos authentication](/latest/docs/prerequisites-for-microsoft-sql-server-connector). This must match the KDC defined in the realm section of your Kerberos configuration file (krb5.conf). See an example below. `13.60.225.50` |
| Kerberos Realm | Kerberos Authentication | Specify the realm name corresponding to the Active Directory domain that you acquired in [(Optional) Using Kerberos authentication](/v1/docs/prerequisites-for-microsoft-sql-server-connector). See an example below. `SQL.COM` |
| Service Principle Name | Kerberos Authentication | Specify the Service Principle Name (SPN) registered against your active directory user that you acquired in [(Optional) Using Kerberos authentication](/v1/docs/prerequisites-for-microsoft-sql-server-connector). See an example below. *MSSQLSvc/EC2AMAZ-S8AQ7PH.example.com:1433* |
| (Optional) Use SSL | N/A | Toggle on if the Data system supports it. When not toggled, Securiti shows the status as *false*. |
| Additional Connection String Options | N/A | - Contact your Database administrator for specific JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. See the example below. *'param1=value1;param2=value2'* - In the case of Exclude JTDS Driver option using Windows Authentication, set the *integratedSecurity=true;* in the **Additional Connection String Options**. - For Kerberos Authentication set the *trustServerCertificate=true;ApplicationIntent=ReadOnly* for read only access. > [!NOTE] > **Note** > > Use troubleshooting tools like Dbeaver to test connectivity manually if Authentication fails. |
| (Optional) Use Keyring | N/A | Enable the toggle and from the **Keyring Type** menu, choose your preferred vault. You can manage keyrings as mentioned in [Using keyrings](/v1/docs/using-keyrings). See [Configuring credential vaults](/v1/docs/configuring-credential-vaults) for more information. Enter the Keyring in the **Keyring** field you configured earlier. SQL Server supports the following keyrings: - HashiCorp. See [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault), for more information. - CyberArk. See [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault), for more information. - CredStash. See [Configuring CredStash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault), for more information. - AWS Secrets Manager. See [Configuring AWS Secrets Manager](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault), for more information. - Azure Key Vault. See [Configuring Azure key vault](/v1/docs/configuring-credential-vaults-azure-key-vault), for more information. - Delinea Secret Server. See [Configuring Delinea Secret Manager](/v1/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault), for more information. |
| Keyring | N/A | From the **Keyring** dropdown, select the keyring. For more information, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| **When using HashiCorp Keyring only** (Optional) Generate Dynamic Credentials | N/A | Enable the toggle to use dynamic Credentials from HashiCorp vault using the Database secrets engine. See [Using Database secrets engine for dynamic credentials](/v1/docs/using-database-secrets-engine-for-dynamic-credentials), for more information. |
| (Optional) Utilize prepared statements | N/A | Enable the toggle if you want Securiti to execute prepared statements for the Microsoft SQL Server Connector. > [!NOTE] > **Note** > > After the 1.89 Securiti release, you must reconfigure the existing Connector instances before running a Discovery scan to update the Configuration. You do not lose any data in the process. |
| (Optional) Store Sample file on PCS | N/A | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test Connection**.

Securiti activates the Connector.

> [!NOTE]
> **Note**
> 
> - It's assumed you have the required drivers before Activation. Otherwise, Securiti shows an error message reminding you to upload drivers.
> - When using Kerberos Authentication with the SQL Server Connector, a file-based cache mechanism is used to securely store Authentication tickets. This approach eliminates the need to re-enter Credentials, especially where frequent logins are required.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft SQL Server.

- [Configuring General permissions for Microsoft SQL Server](/latest/docs/new-ui-configuring-general-permissions-for-microsoft-sql-server)
- [Configure discovery scans in Microsoft SQL Server](/latest/docs/configure-discovery-scans-in-microsoft-sql-server).

**Additional resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

> [!NOTE]
> **Note**
> 
> Row counting for SQL Server data system is not supported either due to the data system's inability to provide this data or the performance impact Securiti would cause on the data system by counting rows.
- [Fulfilling Microsoft SQL Server DSR requests](/latest/docs/fulfilling-microsoft-sql-server-dsr-requests).
- [Microsoft SQL Server FAQs](/latest/docs/microsoft-sql-server-faqs).
- [Troubleshooting for Microsoft SQL Server connector](/latest/docs/troubleshooting-for-microsoft-sql-server-connector).
