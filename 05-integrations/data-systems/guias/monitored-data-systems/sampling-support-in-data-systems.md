---
title: "Sampling support in structured data systems scans"
slug: "sampling-support-in-data-systems"
updated: 2026-08-10T15:16:11Z
published: 2026-08-10T15:16:11Z
canonical: "helpcenter.securiti.ai/sampling-support-in-data-systems"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Sampling support in structured data systems scans

Sampling controls how data is read during Discovery scans for structured and Hybrid connectors. Field Classification always uses sampling to inspect a subset of rows and identify Sensitive data types in each column. CLOB scanning can either scan all rows in selected CLOB columns using Full Scan or inspect a subset of rows using Sample Scan. On connectors where sampling is configurable, you can choose the sampling method and row limit. Some Self-hosted connectors and Securiti Cloud connectors that support Legacy Data Scans do not allow sampling to be configured. In these cases, Securiti uses the default sampling behavior.

> [!NOTE]
> Note
> 
> This article covers only self-hosted structured and hybrid connectors that support Discovery Scans. It does not include Securiti Cloud connectors or self-hosted connectors that support only legacy (standard) scans. For information about those connectors, see the [section](/latest/docs/sampling-support-in-data-systems#sampling-support-matrix) below.

## Managing scan sampling across connector types

Sampling behavior varies by connector type. The table below explains how sampling is managed and whether sampling configuration is available for each connector category:

| Connector type | Description |
| --- | --- |
| Securiti Cloud | Sampling configuration is not available for Securiti Cloud connectors because they use the Legacy Standard Data Scan method. Instead, Securiti uses the default First x Rows sampling limit during scans. |
| Self-hosted connectors | Self-hosted connectors that support Discovery Scans provide structured data sampling for Field Classification and, where supported, CLOB scanning. Depending on the connector, sampling settings can be configured or Discovery Scans use the connector's default sampling behavior. > [!NOTE] > Note > > Sampling configuration is not available for Self-hosted connectors that use Legacy Standard Data scanning method. However, Securiti uses default limit to choose First x rows for scanning. |

## Understanding sampling in Discovery Scans

The table below summarizes how sampling is used in Discovery Scans for Field Classification and CLOB scanning, including feature availability, supported scan options, and configuration behavior.

### Field Classification

Field Classification identifies sensitive data types in columns by scanning a subset of rows from each table or view. This feature is available for all structured and hybrid data systems that support Discovery Scans.

- On connectors that support configurable sampling, you can choose the sampling method and row limit.
- Some connectors do not support configurable sampling. In these cases, Field Classification uses the connector's default sampling behavior.

### CLOB Scanning

CLOB scanning detects sensitive data in supported string-based columns, such as VARCHAR, JSON, and TINYTEXT. Supported string-based column types vary by connector. This feature is available only for structured and hybrid connectors that support CLOB scanning.

- Where configurable sampling is supported, you can choose between the following scan options:
  - **Full Scan:** It scans all rows in the selected CLOB columns.
  - **Sample Scan:** It scans a subset of rows using the configured sampling method and row limit.
- Some connectors do not support configurable sampling. In these cases, CLOB scanning uses the connector's default sampling behavior.

## Sampling methods

The table below summarizes how sampling is used in Discovery Scans for Field Classification and CLOB scanning, including feature availability, supported scan options, and configuration behavior.

| Sampling method | Description |
| --- | --- |
| Sample first x rows | Reads the first x rows from the table or view. |
| Sample random x rows | Reads x rows selected at random from the table. > [!NOTE] > Note > > Random sampling is not supported on views. |

## Standard sampling and default limits

The following limits and defaults apply across all connectors where sampling is configurable. Individual connectors might support a narrower range. For more information, see the per-connector matrix [below](/latest/docs/sampling-support-in-data-systems#sampling-support-matrix).

| Discovery scan option | Method | Range | Default limit |
| --- | --- | --- | --- |
| Field Classification | Sample first x rows | 1 to 10,000 | 1,000 |
| Sample random x rows | 1 to 500 | 200 |
| Clob Scan | Sample first x rows | 1 to 100,000 | 1,000 |
| Sample random x rows | 1 to 10,000 | 200 |

## Sampling on tables

For tables, Discovery Scans use the sampling method and row limit configured in the scan settings. Depending on the connector, you can configure Sample First X and/or Sample Random X for Field Classification and CLOB scanning. On connectors where sampling configuration is not available, the scan uses connector-defined default behavior. Field Classification always uses sampling, while CLOB scanning can use either Full Scan or Sample Scan, depending on the connector's capabilities.

## Sampling on views

- Random sampling does not apply to views. The system uses the first X rows for both Field Classification and CLOB scanning on views, regardless of the sampling method selected. The configured row limit still applies.
- For MariaDB, Amazon RDS MariaDB, Amazon Aurora for PostgreSQL, Azure Synapse, and Amazon Athena, views scanning can be enabled or disabled at connector activation using the **Include Views** option, which is disabled by default. When “Include Views” is disabled, views are not scanned regardless of scan-level scope configuration.
- For SAP SuccessFactors, views are not scanned. This behavior is fixed and there is no option to enable view scanning.

## Sampling support matrix

The table below provides the sampling support available for sampling tables and views for structured and hybrid self-hosted data system using discovery scan:

| Connector | FC First X | FC Random X | CLOB Supported | CLOB First X | CLOB Random X | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| [Amazon Athena](/latest/docs/configure-discovery-scans-in-amazon-athena#advanved-settings2) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | Include Views toggle at connector activation (off by default) |
| [Amazon Aurora for PostgreSQL](/latest/docs/configure-discovery-scans-in-amazon-aurora-for-postgresql#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | Include Views toggle at connector activation (off by default) |
| [Amazon DocumentDB](/latest/docs/configure-discovery-scans-in-amazon-documentdb#advanced-settings2) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Amazon DynamoDB](/latest/docs/configure-discovery-scans-in-amazon-dynamodb#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Amazon RDS for MySQL](/latest/docs/configure-discovery-scans-in-amazon-rds-for-mysql#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Amazon RDS for PostgreSQL](/latest/docs/configure-discovery-scans-in-amazon-rds-for-postgresql#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Amazon RDS for SQL Server](/latest/docs/configure-discovery-scan-in-amazon-rds-for-mysql#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Amazon RDS MariaDB](/latest/docs/configure-discovery-scans-in-amazon-rds-mariadb#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | Include Views toggle at connector activation (off by default) |
| [Amazon Redshift](/latest/docs/configure-discovery-scans-in-amazon-redshift#advanced-settings1) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Apache HBase](/latest/docs/configure-discovery-scans-in-apache-hbase#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Apache Hive](/latest/docs/configure-discovery-scans-in-apache-hive#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Apache Phoenix](/latest/docs/initiate-apache-phoenix-data-scanning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Apache Presto](/latest/docs/configure-discovery-scans-in-apache-presto#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Apache Trino](/latest/docs/configure-discovery-scans-in-apache-trino#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Auth0](/latest/docs/configure-discovery-scans-in-auth0-self-hosted#advanced-settings1) | Not available | Not available | No | — | — | — |
| [Azure Cosmos DB](/latest/docs/configure-discovery-scans-in-azure-cosmos-db#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Azure Cosmos DB for MongoDB](/latest/docs/configuring-discovery-scans-in-azure-cosmos-db-for-mongodb#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Azure Synapse](/latest/docs/configure-discovery-scans-in-azure-synapse#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Braze](/latest/docs/configure-discovery-scans-in-braze#advanced-settings2) | Not available | Not available | Yes | Not available | Not available | — |
| [Btrieve / Pervasive SQL](/latest/docs/initiate-btrieve-learning) | Discovery scan is not supported |
| [Cassandra](/latest/docs/configure-discovery-scans-in-cassandra#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Cloudera Impala](/latest/docs/configure-discovery-scans-in-cloudera-impala#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [CockroachDB](/latest/docs/configure-discovery-scans-in-cockroachdb-en#advanced-settings1) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Couchbase NoSQL](/latest/docs/initiate-couchbase-learning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Coupa](/latest/docs/initiate-coupa-learning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Databricks](/latest/docs/configuring-discovery-scans-in-databricks#advanced-settings1) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Domo](/latest/docs/configure-discovery-scans-in-domo#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | — |
| [Elasticsearch](/latest/docs/configure-discovery-scans-in-elasticsearch#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Firebird](/latest/docs/configure-discovery-scans-in-firebird#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Front](/latest/docs/initiate-data-scanning-for-front#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Gladly](/latest/docs/configure-discovery-scans-in-gladly#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Google BigQuery](/latest/docs/configure-discovery-scans-in-google-bigquery#advanced-settings) | Not available | 1–500 | Yes | 1–100,000 | 1–10,000 | Sample First X not supported for Field Classification |
| [Google Bigtable](/latest/docs/configure-discovery-scans-in-google-bigtable#advanced-settings2) | 1–10,000 | Not available | No | — | — | — |
| [Google Cloud SQL for MySQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-mysql#advanced-settings2) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Google Cloud SQL for PostgreSQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-postgresql#advanced-settings2) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Google Cloud SQL for SQL Server](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-sql-server#advanced-settings2) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Greenplum](/latest/docs/configure-discovery-scans-in-greenplum#advanced-settings2) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| HP NonStop SQL | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| IBM Db2 | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [IBM Db2 zOS](/latest/docs/configure-discovery-scans-in-ibm-db2-zos#advanced-settings2) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [IBM Netezza](/latest/docs/configure-discovery-scans-in-ibm-netezza) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [IBM Informix](/latest/docs/configure-ibm-informix-data-scanning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [InterSystems Caché](/latest/docs/configuring-discovery-scans-in-intersystems-cache#advanced-settings2) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [InterSystems Iris](/latest/docs/initiate-intersystems-iris-data-scanning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Jira Cloud](/latest/docs/configure-discovery-scans-in-jira-cloud-self-hosted-1#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Jira Data Center](/latest/docs/configure-discovery-scans-in-jira-data-center#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [LDAP Active Directory](/latest/docs/configure-discovery-scans-in-ldap-active-directory#advanced-settings2) | 1–10,000 | Not available | No | — | — | — |
| [MariaDB](/latest/docs/configure-discovery-scans-in-mariadb#advanced-settings) | 1–10,000 | Not available | Yes | Not available | Not available | Include Views toggle at connector activation (off by default) |
| [Microsoft Access](/latest/docs/configure-microsoft-access-data-scanning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Microsoft Azure SQL Database](/latest/docs/configure-discovery-scans-in-microsoft-azure-sql-database#advanced-settings) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Microsoft Dataverse](/latest/docs/configure-discovery-scans-for-microsoft-dataverse#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Microsoft Dynamics 365 CRM (Suite)](/latest/docs/configure-discovery-scans-in-microsoft-dynamics-365-crm-suite#advanced-settings) | Not available | Not available | No | — | — | — |
| [Microsoft Dynamics 365 Finance & Operations](/latest/docs/configure-discovery-scans-for-microsoft-dynamics-finance-operations#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [MongoDB](/latest/docs/configure-discovery-scans-in-mongodb#advanced-settings1) | 1–10,000 | Not available | Yes | 1–100,000 | Not available | — |
| [MySQL](/latest/docs/configure-discovery-scans-in-mysql#advanced-settings) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [NetSuite](/latest/docs/configuring-general-permissions-for-netsuite-self-hosted#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Oracle](/latest/docs/configure-discovery-scans-in-oracle#advanced-settings) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Oracle Autonomous Data Warehouse](/latest/docs/configure-discovery-scans-in-oracle-autonomous-data-warehouse#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| Oracle Autonomous Transactional | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [Oracle Eloqua Marketing Automation](/latest/docs/configure-discovery-scans-in-jira-data-center-1#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | — |
| [Oracle HCM](/latest/docs/configure-discovery-scans-in-oracle-hcm#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | — |
| [Oracle Service Cloud](/latest/docs/initiate-oracle-service-cloud-learning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [PostgreSQL](/latest/docs/configure-discovery-scans-in-postgresql-en#advanced-settings1) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Power BI Service](/latest/docs/configure-discovery-scans-in-power-bi-service#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Progress OpenEdge DB](/latest/docs/initiate-progress-openedge-db-learning#data-scan-policies) | Discovery scan is not supported |
| [SAP ECC](/latest/docs/configure-discovery-scans-in-sap-ecc#advanced-settings) | 1–10,000 | Not available | No | — | — | — |
| [SAP HANA](/latest/docs/configure-discovery-scans-in-sap-hana#advanced-settings1) | 1–10,000 | Not available | Yes | Not available | Not available | — |
| [SAP SuccessFactors](/latest/docs/configure-discovery-scans-in-sap-successfactors#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | Views are not scanned. This behavior is fixed and cannot be changed. |
| [Salesforce (Legacy)](/latest/docs/configure-discovery-scans-in-salesforce-legacy#advanced-settings1) | Not available | Not available | No | — | — | — |
| [Salesforce CRM](/latest/docs/configure-discovery-scans-in-salesforce-crm#advanced-settings1) | Not available | Not available | No | — | — | — |
| [Salesforce Customer Data Platform](/latest/docs/configure-discovery-scans-in-salesforce-customer-data-platform#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | — |
| [ServiceNow Tables](/latest/docs/configuring-discovery-scans-in-servicenow-tables#advanced-settings1) | Not available | Not available | Yes | Not available | Not available | — |
| [Shopify](/latest/docs/configure-discovery-scans-in-shopify#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Snowflake](/latest/docs/configure-discovery-scans-in-snowflake#advanced-settings1) | Not available | 1–500 | Yes | 1–100,000 | 1–10,000 | Sample First X not supported for Field Classification |
| [SQL Server](/latest/docs/configure-discovery-scans-in-microsoft-sql-server#advanced-settings1) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Starburst](/latest/docs/configuring-discovery-scans-in-starburst#advanced-settings) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Sybase ASE](/latest/docs/initiate-sybase-ase-learning#data-scan-policies-and-filters1) | Discovery scan is not supported |
| [Tableau Server](/latest/docs/configure-discovery-scans-in-tableau-server#advanced-settings1) | Not available | Not available | No | — | — | — |
| [Teradata](/latest/docs/configure-discovery-scans-in-teradata#advanced-settings) | 1–10,000 | 1–500 | Yes | 1–100,000 | 1–10,000 | — |
| [Treasure Data CDP](/latest/docs/configure-discovery-scans-in-treasure-data-cdp#advanced-settings1) | 1–10,000 | 1–500 | Yes | Not available | Not available | — |
| [Workday](/latest/docs/configure-discovery-scans-in-workday-self-hosted#advanced-settings1) | Not available | Not available | No | — | — | — |
| [Zendesk](/latest/docs/configure-discovery-scans-in-zendesk-self-hosted#advanced-settings) | Not available | Not available | No | — | — | — |
| [Zendesk Support](/latest/docs/configure-discovery-scans-in-zendesk-support#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |
| [Zoho Recruit](/latest/docs/configure-discovery-scans-in-zoho-recruit#advanced-settings) | Not available | Not available | Yes | Not available | Not available | — |

## FAQ

****What does “Not available” mean in the sampling support matrix table?****

Not available means that the corresponding sampling method or option is not available for the specific connector.

****What does “Discovery scan is not supported” mean?****

It means that the connector does not support Discovery Scans but supports Legacy Data scan, so the sampling controls described in this topic do not apply. For more information on available scanning capabilities, see connector documentation.

****Is Field Classification unavailable when both FC First X and FC Random X show “Not available”?****

No. For a connector that supports Discovery Scans, Field Classification still runs using the connector’s default sampling behavior. However, you cannot configure the sampling method or row limit.

****What happens when CLOB Supported is “Yes,” but its sampling methods show “Not available”?****

CLOB scanning is supported, but its sampling method and row limit cannot be configured. The connector uses its default CLOB scanning behavior.

****Can I use random sampling when scanning views?****

No. Random sampling does not apply to views. Securiti uses the first X rows for Field Classification and CLOB scanning on views, regardless of the sampling method selected. The configured row limit still applies.

****Why does the sampled data in Table Training differ from the data stored in the database?****

For supported data systems, values displayed in the Data Sample Preview are independently and randomly shuffled within each column. Therefore, the preview does not preserve the original relationships between values in a row and cannot be used to reconstruct database records.

For more information, see Previewing Data Samples in [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

You use discovery scan jobs to look for specific data elements distributed across different locations, and different data systems, on specific schedules and owners, etc. These discovery scans can be based on structured, streaming, or unstructured data systems.

Under a hybrid compliance type, data subjects can manage both opt-in and opt-out consent within the same jurisdiction, depending on the type of cookie and applicable laws. You can configure default consent states for different cookie categories, such as setting sensitive data cookies to **Declined** and others to **Granted**. This ensures compliance with varying consent requirements under different privacy laws.

Field classification in discovery scan refers to the process of collecting samples of tables or views and classifying the data within the first 'x' rows or a random sample of 'x' rows.

Sensitive data can constitute any unit or set of data that an organization deems valuable and should have specific security controls or governance applied to it. Examples may include, but are not limited to the personal data of customers, patients, employees, or business partners.

CLOB scanning is the process of scanning all rows or sample rows of string data type (CLOB) columns for every data element type. The string data types include VARCHAR, JSON, TINYTEXT, etc., which vary for each data system.
