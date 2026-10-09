---
title: "Discovery scans for structured connectors"
slug: "creating-a-discovery-scan-for-structured-connectors"
updated: 2026-09-29T11:17:13Z
published: 2026-09-29T11:17:13Z
canonical: "helpcenter.securiti.ai/creating-a-discovery-scan-for-structured-connectors"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Discovery scans for structured connectors

Structured data systems store information in tabular form, in rows and columns, for efficient and quick access. For example, employee records and their salary information are stored in tabular rows and columns. Configure the discovery scans for structured connectors to let Securiti identify the sensitive data elements and content profiles that exist in the tables, databases, schemas, and views that reside on your data system.

## Supported data systems for CLOB and sample scan

Use the following table to understand which structured and hybrid data systems support CLOB scan and sample CLOB scan:

| Data systems | CLOB scan support | Sample CLOB support |
| --- | --- | --- |
| [Amazon Athena](/v1/docs/configure-discovery-scans-in-amazon-athena) | Yes | Yes |
| [Amazon DocumentDB](/v1/docs/configure-discovery-scans-in-amazon-documentdb) | Yes | No |
| [Amazon RDS MariaDB](/v1/docs/configure-discovery-scans-in-amazon-rds-mariadb) | Yes | No |
| [Amazon RDS MySQL](/v1/docs/configure-discovery-scans-in-amazon-rds-for-mysql) | Yes | No |
| [Amazon Redshift](/v1/docs/configure-discovery-scans-in-amazon-redshift) | Yes | Yes |
| [Apache Hbase](/v1/docs/configure-discovery-scans-in-apache-hbase) | Yes | No |
| [Apache Hive](/v1/docs/configure-discovery-scans-in-apache-hive) | Yes | No |
| [Apache Trino](/v1/docs/configure-discovery-scans-in-apache-trino) | Yes | No |
| [Asana Enterprise](/v1/docs/configure-discovery-scans-in-asana-enterprise) | Yes | No |
| [Azure Cosmos DB](/v1/docs/configure-discovery-scans-in-azure-cosmos-db) | Yes | No |
| [Azure Cosmos DB for MongoDB](/v1/docs/configuring-discovery-scans-in-azure-cosmos-db-for-mongodb) | Yes | No |
| [Azure Synapse](/v1/docs/configure-discovery-scans-in-azure-synapse) | Yes | No |
| [Braze](/v1/docs/configure-discovery-scans-in-braze) | Yes | No |
| [Cassandra](/v1/docs/configure-discovery-scans-in-cassandra) | Yes | No |
| [Cloudera Impala](/v1/docs/configure-discovery-scans-in-cloudera-impala) | Yes | No |
| [Databricks](/v1/docs/configuring-discovery-scans-in-databricks) | Yes | Yes |
| [Domo](/v1/docs/configure-discovery-scans-in-domo) | Yes | No |
| [Elasticsearch](/v1/docs/configure-discovery-scans-in-elasticsearch) | Yes | No |
| [GCP MySQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-mysql) | Yes | Yes |
| [GCP PostgreSQL](/v1/docs/configure-discovery-scans-in-google-cloud-sql-for-postgresql) | Yes | Yes |
| [GCP SQL Server](/v1/docs/configure-discovery-scans-in-google-cloud-sql-for-sql-server) | Yes | Yes |
| [Google BigQuery](/v1/docs/configure-discovery-scans-in-google-bigquery) | Yes | Yes |
| [Greenplum](/v1/docs/configure-discovery-scans-in-greenplum) | Yes | No |
| HP Nonstop SQL | Yes | No |
| [IBM Db2](/v1/docs/configure-discovery-scans-in-ibm-db2-zos) | Yes | Yes |
| [IBM Db2 zOS](/v1/docs/configure-discovery-scans-in-ibm-db2-zos) | Yes | Yes |
| [IBM Netezza](/v1/docs/configure-discovery-scans-in-ibm-netezza) | Yes | No |
| [InterSystem Cache](/latest/docs/configuring-discovery-scans-in-intersystems-cache) | Yes | No |
| LDAP Active Directory | Yes | No |
| [MariaDB](/v1/docs/configure-discovery-scans-in-mariadb) | Yes | No |
| [Microsoft Azure SQL Database](/v1/docs/configure-discovery-scans-in-microsoft-azure-sql-database) | Yes | No |
| [Microsoft Dynamics 365 CRM](/v1/docs/configure-discovery-scans-in-microsoft-dynamics-365-crm-suite) | Yes | No |
| [MongoDB](/v1/docs/configure-discovery-scans-in-mongodb) | Yes | No |
| [MySQL](/v1/docs/configure-discovery-scans-in-mysql) | Yes | Yes |
| [Oracle](/v1/docs/configure-discovery-scans-in-oracle) | Yes | Yes |
| Oracle Autonomous Data Warehouse | Yes | No |
| Oracle Autonomous Transactional | Yes | No |
| [PostgreSQL](/latest/docs/configure-discovery-scans-in-postgresql-en) | Yes | No |
| [Power BI Service](/v1/docs/configure-discovery-scans-in-power-bi-service) | Yes | No |
| [SAP HANA](/v1/docs/configure-discovery-scans-in-sap-hana) | Yes | No |
| [SAP SuccessFactors](/v1/docs/sap-successfactors-self-hosted-connectors) | Yes | No |
| [SQL Server](/v1/docs/configure-discovery-scans-in-microsoft-sql-server) | Yes | No |
| [Salesforce CRM](/v1/docs/configure-discovery-scans-in-salesforce-crm) | Yes | No |
| [Salesforce](/v1/docs/configure-discovery-scans-in-salesforce-legacy) | Yes | No |
| [Salesforce Customer Data Platform](/v1/docs/configure-discovery-scans-in-salesforce-customer-data-platform) | Yes | No |
| [ServiceNow Tables](/v1/docs/configuring-discovery-scans-in-servicenow-tables) | Yes | Yes |
| [Snowflake](/v1/docs/configure-discovery-scans-in-snowflake) | Yes | Yes |
| [Starburst](/v1/docs/configuring-discovery-scans-in-starburst) | Yes | No |
| [Tableau Server](/v1/docs/configure-discovery-scans-in-tableau-server) | Yes | No |
| [Teradata](/latest/docs/configure-discovery-scans-in-teradata) | Yes | No |
| [Treasure Data CDP](/v1/docs/configure-discovery-scans-in-treasure-data-cdp) | Yes | No |
| [Workday](/v1/docs/configure-discovery-scans-in-workday-self-hosted) | Yes | No |
| [Zendesk Support](/v1/docs/configure-discovery-scans-in-zendesk-support) | Yes | No |
| [Zoho Recruit](/v1/docs/configure-discovery-scans-in-zoho-recruit) | Yes | No |

To create a discovery scan for a structured data system such as MySQL, Snowflake, or MongoDB, follow the steps below.

## Specifying the scan details and scope

To specify the scan details and scope:

1. From the left navigation bar, hover over **Sensitive Data Intelligence** and choose **Discovery Scans > Scan Definitions.**
2. Near the upper-right corner of the **Scan Definitions** page, click **+ Create Discovery Scan**, as shown below.

![Overview of scan definitions with active and completed job statuses displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creatediscoveryscanoption_scandefinitions(1).png)

> [!WARNING]
> Important
> 
> A structured data system can belong to only one scan definition.
3. In the **Scan Details** section, enter a name and description for the scan.

![Details of EDM Indexing Scale Testing with MySQL target selection and job description.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scandetails_structureddatasystem.png)
4. In the **Scope** section, choose the data system type and the specific data system you want to scan. When you choose a data system, a popup displays the data system instances, accounts, and regions.

![Interface for selecting data systems with options for account and region settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingdatasystems_structureddiscoveryscans.png)

> [!NOTE]
> Note
> 
> You can include both tables and views in the scan. However, Securiti displays data element counts for tables only. Views do not show detection counts in the **Structured Data Explorer**.
5. In the **Data System Scope** section, use the data system tools to choose which databases, schemas, tables, and views to include in or exclude from the scan.

The available tools vary by data system type.

![Data system configuration interface showing database and schema selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemscope_discoveryscan.png)

> [!NOTE]
> Note
> 
> Securiti limits the number of records displayed for scopes. We recommend that you use the case-insensitive search to find and choose the scope for your data system accurately. This applies to all data systems whose scopes are listed in the **Data System Scope** section.

## Configuring advanced settings for a scan

After specifying the scan scope, expand the **Advanced Settings** section to configure the following settings for your structured data system.

### Specifying field classification settings

Configure the field classification settings for a discovery scan, as shown below.

![Settings for field classification including options for sampling rows and data storage.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fieldclassificationoptions_discoveryscan.png)

Use the following table to understand the settings in the **For field classification** section:

| Setting | Description |
| --- | --- |
| Sample first 'x' rows | Collects a sample of the table with a simple `LIMIT` query and classifies the first 'x' rows discovered. |
| Sample random 'x' rows | Enables random sampling, which collects the data column by column in a random order. > [!NOTE] > Note > > - Random sampling is a resource-intensive operation. The duration depends on the table size and the access latency of the data source. > - Securiti does not support random sampling on views. Random sampling applies to tables only. > - If the actual number of table rows is fewer than the specified random sampling limit, Securiti performs regular sampling using a `LIMIT` query. The default limit is 1,000 rows, unless you set a different value in Sampling Limit. |
| Sampling Limit | Defines the size of the table sample, that is, the number of rows collected for classification, either by choosing the first rows or by fetching them randomly. For **first 'x' rows**, you can set a minimum of 1 row and a maximum of 10,000 rows. For **random 'x' rows**, you can set a minimum of 1 row and a maximum of 500 rows. |
| Store Sample Data | Stores your sample files in the location you configured during connector activation. This setting is enabled by default. When you disable it, Securiti does not store sample files on the pod or in the cloud, so you cannot preview them on the Table Training page. > [!NOTE] > Note > > - Sample files stored in the cloud support encryption. Contact your Customer Success Manager or Account Representative to enable encryption for your tenant. > - Files stored on the pod are not encrypted. |
| Include empty database tables | Mark the checkbox to include tables that have zero or empty rows. > [!NOTE] > Note > > When you disable Include empty database tables, the discovery scan excludes empty tables from classification if the table headers are being classified. For more information, see [Customizing system data element types](/latest/docs/data-elements-customizing-system-data-element-types). |
| Skip empty fields and the fields below | Mark the checkbox to skip rows that have empty values in all the CLOB columns fetched during sampling. This setting also lets Securiti skip fields that contain values such as "Unknown", "NA", "Null", or "Not Applicable", which saves scanning time and cost. |
| Include newly discovered tables and schemas into the scan scope | Automatically includes all newly discovered tables and schemas in the scan scope, while retaining the configuration you set in the **Scope** section. |
| Breach Impact Analysis | Mark the checkbox to automatically calculate identities and residencies for the Breach Impact Analysis module. Securiti scans the required data elements, and you can choose additional elements in the **Sensitive Data** section. > [!WARNING] > Important > > - Breach Impact Analysis is a premium feature available by subscription. Contact your Customer Success Manager or Account Representative to enable it for your Securiti tenant. > - Breach Impact Analysis also requires Breach Analysis to be enabled so that linking jobs can run. Contact your Customer Success Manager or Account Representative to enable it for your Securiti tenant. If you enable both **Full Scan** under **Scan of string data type (CLOB) columns** and **Breach Impact Analysis** in the same scan job, Securiti runs a full scan of string type fields and a full scan of columns that contain unique identifiers. Securiti uses all scan results to calculate the unique identity count. |

### Configuring CLOB scanning

In the **For CLOB scanning** section, configure the following settings:

![Settings for CLOB scanning, including scan types and data limits for discovery jobs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clobscanningoptions_discoveryscans.png)

1. Mark the **Scan of string data type (CLOB) columns** checkbox to scan every field of a string data type column for every data element type. String data types include the following and vary for each data system.
  - `VARCHAR`
  - `JSON`
  - `TINYTEXT`
2. Select one of the following scan options:
  - **Full Scan**: Mark the checkbox to scan text columns on all rows whose data type matches the selected string types.

> [!NOTE]
> Note
> 
> A full scan is a resource-intensive operation and might result in slower performance.
  - **Sample Scan**: Mark the checkbox to perform sample CLOB scanning, then configure the sample scan settings.

Use the following table to understand the **Sample Scan** settings:

| Setting | Description |
| --- | --- |
| Sample first 'x' rows | Collects a sample of the table with a simple `LIMIT` query and classifies the first 'x' rows discovered. |
| Sample random 'x' rows | Enables random sampling, which collects the data column by column in a random order. > [!WARNING] > Important > > - Random sampling is a resource-intensive operation. The duration depends on the table size and the access latency of the data source. > - Securiti does not support random sampling on views. Random sampling applies to tables only. > - If the actual number of table rows is fewer than the specified random sampling limit, Securiti performs regular sampling using a `LIMIT` query. The default limit is 1,000 rows, unless you set a different value in **Sampling Limit**. |
| Sampling Limit | Defines the size of the table sample, that is, the number of rows collected for classification, either by choosing the first rows or by fetching them randomly. For **first 'x' rows**, you can set a minimum of 1 row and a maximum of 100,000 rows. For **random 'x' rows**, you can set a minimum of 1 row and a maximum of 500 rows. |
| Skip empty fields and the fields below | Mark the checkbox to skip rows that have empty values in all the CLOB columns fetched during sampling. This setting also lets Securiti skip fields that contain values such as "Unknown", "NA", "Null", or "Not Applicable", which saves scanning time and cost. |
3. Mark the **Include evidence file for CLOB scanning in discovery scan job** checkbox to include the evidence file for the scan. Marking this checkbox enables the **Max Detections to Store** field, where you specify the limit per discovery scan, per column, and per data element type.

> [!WARNING]
> Important
> 
> The **Include evidence file for CLOB scanning in discovery scan job** checkbox requires [Private Cloud Storage](/latest/docs/system-settings-configuring-private-cloud-storage) to be enabled.

The **Max Detections to Store** limits determine how many data elements Securiti collects in the evidence files for a discovery scan job. Use the following table to understand the maximum limit for each control:

| Control | Maximum limit |
| --- | --- |
| Per discovery scan job | 2,500,000 detections |
| Per column | 500,000 detections |
| Per data element type | 100,000 detections |

### Setting classification preferences for successive scans

Use the following table to understand the settings in the **Classification preferences for successive scans** section:

![Settings for CLOB scanning and classification preferences in data management software.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/classificationpreferencesforsuccessivescans_discoveryscans.png)

| Setting | Description |
| --- | --- |
| Perform classification on columns and tables previously learned | Performs field classification on columns Securiti learned previously and uses any new evidence found in those columns. If a column has no data, Securiti classifies it as "Unknown". If a column has new data, Securiti classifies that data in the new scan. |
| Retain manually classified data elements and content profiles | Mark the checkbox to retain manually classified data elements and content profiles, and to append new classifications when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When you disable this setting, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |

### Specifying exact data matching

In the **Exact data matching** section, mark the **Allow Exact Data Profiles** checkbox to use exact data profiles as a validator in structured discovery scans, as shown below. Exact Data Matching (EDM) profiles let you identify whether records from a known dataset match any of the records in an EDM index for your data system.

![Settings for exact data matching and evidence collection in a data scanning interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exactdatamatchingoption_discoveryscans.png)

In **Scan Depth of Exact Data Scanning**, specify the number of top rows to use as the scan depth. Leave the field empty or enter 0 to scan the complete table.

For more information, see [Supported data systems for exact data indexes](/latest/docs/supported-data-systems-for-exact-data-indexes).

### Configuring BLOB scanning

Mark the **Perform Blob Scan** checkbox to scan BLOB data types in your data system instance.

> [!WARNING]
> Important
> 
> - **Perform Blob Scan** is available for the MongoDB and IBM Db2 connectors only.
> - Securiti treats each BLOB column as unstructured data and displays the results in the Unstructured Data Explorer.

After you mark the checkbox, the following settings appear.

![Settings for Blob Scanning, including options for data extraction and automation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/blobscanningoption_structureddatadiscovery.png)

Use the following table to understand these settings:

| Setting | Description |
| --- | --- |
| Extract text from images using OCR | Mark the checkbox to extract text from images using optical character recognition (OCR). > [!NOTE] > Note > > OCR is available on pod-based deployments only. |
| Extract text from compressed and archived files | Mark the checkbox to extract text from compressed and archived files. |
| Enable Data Subject Requests (DSR) Automation on this data | Mark the checkbox to index data elements for use in DSR searches on unstructured data. Marking this checkbox selects all core data elements, and you cannot clear them while the checkbox remains marked. |
| Full Scan of Blob data type columns | Performs a full scan of columns that have BLOB data types. > [!NOTE] > Note > > This checkbox is marked by default. |
| Include document metadata in classification scope | Mark the checkbox to include file name and header information in the classification scope. |
| Enable Similar Document Cluster Analysis | Mark the checkbox to detect similar files and clusters within this discovery scan and every other discovery scan that has this setting enabled. > [!NOTE] > Note > > Securiti runs cluster analysis automatically within 24 hours. You can also start it manually from the **Cluster Analysis Settings** page. |

## Specifying sensitive data specifications

To specify the sensitive data specifications for a scan:

1. In the **Sensitive Data** section, choose the locality enabled for your tenant.
2. Choose the specific types of data to scan. Click a category to open it, then choose the required data elements, content profiles, and exact data profiles, as shown below.

![Selection of sensitive data categories for structured content profile management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedataspecification_discoveryscans.png)

## Configuring the scan schedule

After all the scan configurations are complete, you can schedule the scan. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below.

![Settings for scheduling scans, including manual and periodic options with time exclusions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscanschedule_scandefinitions(1).png)

Use the following table to understand the scan schedule options:

| Scan option | Specifications |
| --- | --- |
| Run manually, Admin needs to start a job for this policy | Activate and deactivate the scan manually, and start or cancel it whenever you choose. |
| Run on periodic schedule | The scheduled time starts and ends according to your local time or the time set in your device settings. Set the specific time for your scan, choose **Daily**, **Weekly**, or **Monthly** from **Periodic Schedule Frequency**, and specify a time of the day, week, or month. You can also set a scan exclusion start and end time to pause your scan jobs for that interval. The minimum pause interval you can specify is one hour. > [!NOTE] > Note > > If a scan job runs for more than a day, for example a larger scan, and you set a pause interval of one hour, Securiti applies the same one-hour pause interval every day. |

### Using a custom cron expression

For custom cron jobs, use the [expression builder](https://crontab.guru/), which provides minute, hour, day of the week, and day of the month settings. Enter the resulting expression in the **Enter Cron** field. You can also exclude the times when you do not want the scan to run, and specify multiple times weekly or monthly. Choose the hour blocks in the 24x7 matrix where scanning runs, as shown below.

![cron matrix to exclude time to not run the scans for](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46.png)

> [!NOTE]
> Note
> 
> - Securiti pauses the scan at the beginning of each block and resumes it at the end of the block.
> - Securiti does not allow a scan to start immediately after it times out or errors, because Securiti performs back-end checks and remediation actions first. The scan job can take up to an hour to start automatically, with no action required from you. The **Scan Now** option remains disabled for an hour until the system recovers.

## Specifying responses for a scan

Configure the **Responses** section to choose what Securiti does when the scan completes.

1. (Optional) In the **Responses** area, specify one or more email addresses with a relevant email template.
2. (Optional) In the **Responses** area, trigger a discovery scan workflow. To do this, configure a [discovery scan trigger node](/latest/docs/discovery-scan-trigger-node).

![Email notification settings and workflow trigger options for data catalog management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/responsessection_structureddiscovyerscans.png)
3. (Optional) In the **Responses** area, scroll to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** to add a new table or topic, or to update all table and topic selections. Mark **Add sections if not present** to add a new topic.
4. From the **Default Governance Status** menu, choose the appropriate status for the metadata being ingested.
5. Mark the **Extract Lineage from SQL** checkbox to extract the lineage of field data assets from the SQL objects included in the schemas or databases in scope.
6. Mark the **Add Dataset in lower case** checkbox to add structured or streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> Note
> 
> To convert a data system that has a unique set of table, view, function, topic, or column names to lowercase URNs in the data catalog, mark **Add Dataset in lower case** for that data system on the structured or streaming data dashboard.
7. Mark the **Always Execute Response** checkbox to ingest the datasets into the Enterprise Data Catalog whether or not they were registered previously. This setting keeps your catalog accurate as your data changes, as shown below.

![Data catalog registration options including governance status and environment settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datacatalog_structureddatadiscovery.png)

Use the following table to understand the governance statuses you can choose for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |

### Setting the environment

From the **Set Environment** menu, choose the suitable environment, as shown below. This selection lets you choose the environment for the objects registered in the Enterprise Data Catalog, so that you can distinguish and manage metadata across environments such as Production and QA.

![Data catalog registration options with governance status and environment selection highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/setenvironmentdropdown_discoveryscan.png)

Use the following table to understand the available environment values:

| Value | Description |
| --- | --- |
| PROD | Designates production fabrics. |
| PROD-Hidden | Designates hidden production fabrics. Maintains original production behavior, displaying PROD metadata in the URN but hiding the environment in breadcrumbs. |
| DEV | Designates development fabrics. |
| TEST | Designates testing fabrics. |
| QA | Designates quality assurance fabrics. |
| UAT | Designates user acceptance testing fabrics. |
| EI | Designates early integration fabrics. |
| PRE | Designates pre-production fabrics. |
| STG | Designates staging fabrics. |
| NON_PROD | Designates non-production fabrics. |
| CORP | Designates corporation fabrics. |

## Saving and activating the scan

After completing all the scan configurations, near the upper-right corner of the page, click one of the following options.

![Interface for creating a Discovery Scan with various options and buttons highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveoptions_discoveryscans.png)

Use the following table to understand the save options:

| Option | Description |
| --- | --- |
| Finish and Activate | Saves and activates the discovery scan immediately. |
| Save | Saves the scan configuration without activating it. |
| Save as Draft | Saves the scan as a draft for completion at a later time. |

For more information, see [Viewing discovery scan results for structured data systems](/latest/docs/viewing-discovery-scan-results).

Structured data systems refer to the systems that are used to store structured data in the form of databases, tables, and schemas. The most common examples of unstructured data include MySQL, Oracle, Snowflake, and so on.
