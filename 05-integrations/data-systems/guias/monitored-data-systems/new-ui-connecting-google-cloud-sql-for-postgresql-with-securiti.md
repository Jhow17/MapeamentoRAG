---
title: "Connecting Google Cloud SQL for PostgreSQL with Securiti"
slug: "new-ui-connecting-google-cloud-sql-for-postgresql-with-securiti"
updated: 2026-04-28T04:21:59Z
published: 2026-04-28T04:21:59Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-google-cloud-sql-for-postgresql-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Google Cloud SQL for PostgreSQL with Securiti

This topic covers activation of the Google Cloud SQL for PostgreSQL connector.

## Creating a Google Cloud SQL for PostgreSQL data system connector instance

Perform the following steps to create a data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations** > **Monitored Data Systems.**
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add Integration** page, click the **Self-Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | The **Service Provider** is automatically set to **GCP**. | GCP |
| Project ID | **Project ID** is the project identifier of the associated dataset physically present in the project. | `CloudSQL-project-1122334` |
| Region | Select the **Region** for your GCP account | `us-west` |
| Resource Name / Instance Id | Enter the Instance ID for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) Instance, Bucket name for Cloud Storage or Dataset name for BigQuery | `GBQ-admin` |
| Managed | Enable the **Managed** toggle to help differentiate between Native and Non-Native assets (Dark assets) | - |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
8. At the bottom of the page, click **Create and Continue.**

It redirects you to the **Authentication** page.

## Authenticating the Google Cloud SQL for PostgreSQL connector

After creating a Google Cloud SQL for PostgreSQL connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. In the **Drivers**, select the driver file you previously uploaded. Or if you have not, click **Go to driver file library** to its right.

See the following topics for more information:
  - [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).
  - [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors).
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
| Authentication Type | N/A | In **Authentication Type**, select one of the following supported authentication types for your connector. - Basic - SQL Cloud Proxy |
| Authentication Strategy | SQL Cloud Proxy | For SQL Cloud Proxy Authentication type, select one of the following Authentication strategies. - **IAM Authentication** - **User Credentials** |
| Host | Basic | Enter the IP Address for your MySQL Database that you recorded in [Prerequisites for Google Cloud for MySQL](/latest/docs/prerequisites-for-google-cloud-for-mysql) The host name uses *xxx.xxx.xxx.xxx* format. See an example below. `192.168.1.10` |
| Port | Basic | The port number is usually a default value specific to the database type. |
| Use SSL | N/A | This option is enabled by default. Disable the **Use SSL** toggle if your SSL Certificate has expired or is disabled. You can disable this toggle option during activation. |
| (Optional) Use Keyring | N/A | Enable the toggle, and from the **Keyring Type** menu, choose **Basic** or **GCP Secret Manager**. > [!NOTE] > **Note** > > Basic Keyring is not supported for **IAM Authentication** strategy. Enter the Keyring in the **Keyring** field you configured earlier. - See [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults) for more information. - For **Basic** Keyring, see [Managing keyrings](/latest/docs/managing-credentials-using-keyrings), for more information. - See [Configuring GCP Secret Manager credential vaults](/latest/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault), for more information. |
| User | - Basic - SQL Cloud Proxy (with User Credentials) | Enter the username for the account with administrative access. See the example below: `john_securiti` |
| Password | - Basic - SQL Cloud Proxy (with User Credentials) | Enter the password for the account with administrative access. |
| IAM User | SQL Cloud Proxy (with IAM Authentication) | Specify the IAM user that you recorded in [Prerequisites for Google Cloud for MySQL](/v1/docs/prerequisites-for-google-cloud-for-mysql), with access Permissions to the SQL Instance. See an example below. *gcp-iam-user@myproject.iam.gserviceaccount.com* |
| Credentials File | SQL Cloud Proxy (with User Credentials and IAM Authentication) | Upload the JSON file that contains the Credentials for the service account or IAM user. Use the file you recorded in [Prerequisites for Google Cloud for MySQL](/latest/docs/prerequisites-for-google-cloud-for-mysql). See an example below. *iam-user-creds.json* |
| Connection Identifier | SQL Cloud Proxy (with User Credentials and IAM Authentication) | Specify the Instance Connection name that you recorded in [Prerequisites for Google Cloud for MySQL](/latest/docs/prerequisites-for-google-cloud-for-mysql). The onnection identifier uses a string value in the below format. `myproject:us-central1:myinstance` |
| Default Database | N/A | Enter the name of a default Database for the server to connect. > [!NOTE] > **Note** > > The default Database is used for connection if list of Database names is empty. |
| (Optional) Database | - Basic - SQL Cloud Proxy (with User Credentials and IAM Authentication) | Enter the name(s) of the databases you wish to scan. You can enter a comma-separated list of names. In the **Upload File**, you can upload a CSV file with relevant database names. Click **Download CSV template** to see the template. > [!NOTE] > **Important** > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. Optionally, you may find some connectors accepting the blank or empty Database field and would still activate the usual way. See the example below. `automation, access db` |
| (Optional) Additional Connection String Options | N/A | Specify any additional JDBC string connections. You can specify multiple options separated by a semicolon ';'. |
| (Optional) Store Sample file on PCS | N/A | Sample files related to the field classification will be stored in the Private Cloud Storage location that you have configured. > [!WARNING] > Important > > This functionality can be enabled only if you have configured a Private Cloud Storage location. |
5. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Google Cloud SQL for PostgreSQL:

- [Configure discovery scans in Google Cloud SQL for PostgreSQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-postgresql).
- [Fulfilling DSR requests for Google Cloud SQL for PostgreSQL](/latest/docs/fulfilling-dsr-requests-for-google-cloud-sql-for-postgresql).

**Additional Resources**

- [Troubleshooting for Google Cloud SQL for PostgreSQL connectors](/latest/docs/troubleshooting-for-google-cloud-sql-for-postgresql-connectors).
