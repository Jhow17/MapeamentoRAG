---
title: "Databricks Ingestion"
slug: "clone-postgres-ingestion"
updated: 2026-10-05T09:18:02Z
published: 2026-10-05T09:18:02Z
canonical: "helpcenter.securiti.ai/clone-postgres-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Databricks Ingestion

To ingest Databricks metadata into the EDC, read the following required configurations.

### **Important capabilities**

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Asset containers | ✅ | Enabled by default |
| Column-level lineage | ✅ | Enabled by default |
| Dataset usage | ✅ | Enabled by default |
| Descriptions | ✅ | Enabled by default |
| Detect deleted entities | ✅ | Optionally enabled via `stateful_ingestion.remove_stale_metadata` |
| Domains | ✅ | Supported via the `domain` config field |
| Extract ownership | ✅ | Supported via the `include_ownership` config |
| Platform instance | ✅ | Enabled by default |
| Schema metadata | ✅ | Enabled by default |
| Table-level lineage | ✅ | Enabled by default |

This plugin extracts the following metadata from Databricks Unity Catalog:

- Metastores
- Schemas
- Tables and column lineage

### **Prerequisites**

- Get your databricks instance's [workspace url](https://docs.databricks.com/workspace/workspace-details.html#workspace-instance-names-urls-and-ids).
- Create a [databricks service principal](https://docs.databricks.com/administration-guide/users-groups/service-principals.html#what-is-a-service-principal).
  - You can skip this step and use your own account to get things running quickly, but it is strongly recommended that creating a dedicated service principal for production use.
- Generate a databricks personal access token following the following guides:
  - [Service principals](https://docs.databricks.com/administration-guide/users-groups/service-principals.html#personal-access-tokens).
  - [Personal access tokens](https://docs.databricks.com/dev-tools/auth.html#databricks-personal-access-tokens).
- Provision your service account:
  - To ingest your workspace's metadata and lineage, your service principal must have all of the following:
    - One of: metastore admin role, ownership of, or `USE CATALOG` privilege on any catalogs you want to ingest.
    - One of: metastore admin role, ownership of, or `USE SCHEMA` privilege on any schemas you want to ingest.
    - Ownership of or `SELECT` privilege on any tables and views you want to ingest.
    - [Ownership documentation](https://docs.databricks.com/data-governance/unity-catalog/manage-privileges/ownership.html)
    - [Privileges documentation](https://docs.databricks.com/data-governance/unity-catalog/manage-privileges/privileges.html)
  - To `include_usage_statistics` (enabled by default), your service principal must have `CAN_MANAGE` permissions on any SQL Warehouses you want to ingest: See this [guide](https://docs.databricks.com/security/auth-authz/access-control/sql-endpoint-acl.html).
  - To ingest `profiling` information with `call_analyze` (enabled by default), your service principal must have ownership or `MODIFY` privilege on any tables you want to profile.
    - Alternatively, you can run [analyze table](https://docs.databricks.com/sql/language-manual/sql-ref-syntax-aux-analyze-table.html) yourself on any tables you want to profile, then set `call_analyze` to `false`. You will still need `SELECT` privilege on those tables to fetch the results.
- Check the starter recipe below and replace `workspace_url` and `token` with your information from the previous steps.

### **Configuration options**

The following options control what the Databricks source ingests, which objects are included, and how profiling runs. A dot in a field path indicates a nested field in the YAML recipe.

#### General, lineage, and usage

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `enable_stateful_profiling` | boolean | True | Enable stateful profiling. This will store profiling timestamps per dataset after successful profiling. and will not run profiling again in subsequent run if table has not been updated. |
| `format_sql_queries` | boolean | False | Whether to format sql queries |
| `include_column_lineage` | boolean | True | Option to enable/disable lineage generation. Currently we have to call a rest call per column to get column level lineage due to the Databrick api which can slow down ingestion. |
| `include_table_lineage` | boolean | True | Option to enable/disable lineage generation. |
| `include_top_n_queries` | boolean | True | Whether to ingest the `top_n_queries`. |
| `include_usage_statistics` | boolean | True | Generate usage statistics. |
| `platform_instance` | string |  | The instance of the platform that all assets produced by this recipe belong to |
| `top_n_queries` | integer | 10 | Number of top queries to save to each table. |
| `workspace_name` | string |  | Name of the workspace. Default to deployment name present in `workspace_url` |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `catalog_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for catalogs to filter in ingestion. Specify regex to match the full `metastore.catalog` name. |
| `catalog_pattern.allow` | array(string) |  |  |
| `catalog_pattern.deny` | array(string) |  |  |
| `catalog_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `domain` | map(str,AllowDenyPattern) |  | A class to store allow deny regexes |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `schema_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for schemas to filter in ingestion. Specify regex to the full `metastore.catalog.schema` name. e.g. to match all tables in schema analytics, use the regex `^mymetastore\.mycatalog\.analytics$`. |
| `schema_pattern.allow` | array(string) |  |  |
| `schema_pattern.deny` | array(string) |  |  |
| `schema_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `table_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for tables to filter in ingestion. Specify regex to match the entire table name in `catalog.schema.table` format. e.g. to match all tables starting with customer in Customer catalog and public schema, use the regex `Customer\.public\.customer.*`. |
| `table_pattern.allow` | array(string) |  |  |
| `table_pattern.deny` | array(string) |  |  |
| `table_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Profiling

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `profiling` | UnityCatalogProfilerConfig | `{'enabled': False, 'operation_config': {'lower_fre…` | Data profiling configuration |
| `profiling.enabled` | boolean | False | Whether profiling should be done. |
| `profiling.profile_table_level_only` | boolean | False | Whether to perform profiling at table-level only or include column-level profiling as well. |
| `profiling.warehouse_id` | string |  | SQL Warehouse id, for running profiling queries. |
| `profiling.pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns to filter tables for profiling during ingestion. Specify regex to match the `catalog.schema.table` format. Note that only tables allowed by the `table_pattern` will be considered. |
| `profiling.pattern.allow` | array(string) |  |  |
| `profiling.pattern.deny` | array(string) |  |  |
| `profiling.pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

### Troubleshooting

#### No data lineage captured or missing lineage

- Check that you meet the [Unity Catalog lineage requirements](https://docs.databricks.com/data-governance/unity-catalog/data-lineage.html#requirements).
- Also check the [Unity Catalog limitations](https://docs.databricks.com/data-governance/unity-catalog/data-lineage.html#limitations) to make sure that lineage would be expected to exist in this case.

#### Lineage extraction is too slow

Currently, there is no way to get table or column lineage in bulk from the Databricks Unity Catalog REST api. Table lineage calls require one API call per table, and column lineage calls require one API call per column. If you find metadata extraction taking too long, you can turn off column level lineage extraction via the `include_column_lineage` config flag.
