---
title: "Snowflake Ingestion"
slug: "edc-dashboard-classic-1"
updated: 2026-09-21T11:32:58Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/edc-dashboard-classic-1"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Snowflake Ingestion

To ingest Snowflake metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Asset containers | ✅ | Enabled by default |
| Column-level lineage | ✅ | Enabled by default, can be disabled via configuration `include_column_lineage` |
| Data profiling | ✅ | Optionally enabled via configuration `profiling.enabled` |
| Dataset usage | ✅ | Enabled by default, can be disabled via configuration `include_usage_stats` |
| Descriptions | ✅ | Enabled by default |
| Detect deleted entities | ✅ | Optionally enabled via `stateful_ingestion.remove_stale_metadata` |
| Domains | ✅ | Supported via the `domain` config field |
| Extract tags | ✅ | Optionally enabled via `extract_tags` |
| Platform instance | ✅ | Enabled by default |
| Schema metadata | ✅ | Enabled by default |
| Table-level lineage | ✅ | Enabled by default, can be disabled via configuration `include_table_lineage` and `include_view_lineage` |

### **Prerequisites**

In order to execute this source, your Snowflake user need to have specific privileges granted to it for reading metadata from your warehouse.

Snowflake system admin can follow this guide to create a EDC-specific role, assign it the required privileges, and assign it to a new EDC user by executing the following Snowflake commands from a user with the `ACCOUNTADMIN` role or `MANAGE GRANTS` privilege.

```sql
create or replace role edc_role;

// Grant access to a warehouse to run queries to view metadata
grant operate, usage on warehouse "<your-warehouse>" to role edc_role;

// Grant access to view database and schema in which your tables/views exist
grant usage on DATABASE "<your-database>" to role edc_role;
grant usage on all schemas in database "<your-database>" to role edc_role;
grant usage on future schemas in database "<your-database>" to role edc_role;

// If you are NOT using Snowflake Profiling or Classification feature: Grant references privileges to your tables and views
grant references on all tables in database "<your-database>" to role edc_role;
grant references on future tables in database "<your-database>" to role edc_role;
grant references on all external tables in database "<your-database>" to role edc_role;
grant references on future external tables in database "<your-database>" to role edc_role;
grant references on all views in database "<your-database>" to role edc_role;
grant references on future views in database "<your-database>" to role edc_role;

// If you ARE using Snowflake Profiling or Classification feature: Grant select privileges to your tables
grant select on all tables in database "<your-database>" to role edc_role;
grant select on future tables in database "<your-database>" to role edc_role;
grant select on all external tables in database "<your-database>" to role edc_role;
grant select on future external tables in database "<your-database>" to role edc_role;

// Create a new EDC user and assign the EDC role to it
create user edc_user display_name = 'EDC' password='' default_role = edc_role default_warehouse = '<your-warehouse>';

// Grant the edc_role to the new EDC user.
grant role edc_role to user edc_user;

// Optional - required if extracting lineage, usage or tags (without lineage)
grant imported privileges on database snowflake to role edc_role;
```

A summarization of each privilege is as follows:

- `operate` is required only to start the warehouse. If the warehouse is already running during ingestion or has auto-resume enabled, this permission is not required.
- `usage` is required for us to run queries using the warehouse.
- `usage` on `database` and `schema` are required because without it tables and views inside them are not accessible. If an admin does the required grants on `table` but misses the grants on `schema` or the `database` in which the table/view exists then we will not be able to get metadata for the table/view.
- If metadata is required only on some schemas then you can grant the usage privileges only on a particular schema like

```plaintext
grant usage on schema "<your-database>"."<your-schema>" to role edc_role;
```

This represents the bare minimum privileges required to extract databases, schemas, views, tables from Snowflake.

To enable extraction of table lineage, via the `include_table_lineage` config flag, extraction of usage statistics, via the `include_usage_stats` config, or extraction of tags (without lineage), via the `extract_tags` config, you also need to grant access to the [Account Usage](https://docs.snowflake.com/en/sql-reference/account-usage.html) system tables, using which the EDC source extracts information. This can be done by granting access to the `snowflake` database.

```plaintext
grant imported privileges on database snowflake to role edc_role;
```

### **Configuration options**

The following options control what the Snowflake source ingests, which objects are included, and how profiling runs. A dot in a field path indicates a nested field in the YAML recipe.

#### General, lineage, and usage

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `convert_urns_to_lowercase` | boolean | True | Whether to convert dataset URNs to lowercase. |
| `enable_stateful_lineage_ingestion` | boolean | True | Enable stateful lineage ingestion. This stores lineage window timestamps after successful lineage ingestion, and does not run lineage ingestion for the same timestamps in a subsequent run. |
| `enable_stateful_profiling` | boolean | True | Enable stateful profiling. This stores profiling timestamps per dataset after successful profiling, and does not run profiling again in a subsequent run if the table has not been updated. |
| `enable_stateful_usage_ingestion` | boolean | True | Enable stateful usage ingestion. This stores usage window timestamps after successful usage ingestion, and does not run usage ingestion for the same timestamps in a subsequent run. |
| `extract_tags` | Enum |  | Controls tag extraction. One of `with_lineage`, `without_lineage`, or `skip`. |
| `format_sql_queries` | boolean | False | Whether to format SQL queries. |
| `include_column_lineage` | boolean | True | Populates table-to-table and view-to-table column lineage. Requires appropriate grants given to the role, and Snowflake Enterprise Edition or above. |
| `include_operational_stats` | boolean | True | Whether to display operational stats. |
| `include_table_lineage` | boolean | True | If enabled, populates the Snowflake table-to-table and S3-to-Snowflake table lineage. Requires appropriate grants given to the role, and Snowflake Enterprise Edition or above. |
| `include_tables` | boolean | True | Whether tables should be ingested. |
| `include_technical_schema` | boolean | True | If enabled, populates the Snowflake technical schema and descriptions. |
| `include_top_n_queries` | boolean | True | Whether to ingest the top N queries. |
| `include_usage_stats` | boolean | True | If enabled, populates the Snowflake usage statistics. Requires appropriate grants given to the role. |
| `include_view_column_lineage` | boolean | False | Populates view-to-view and table-to-view column lineage. |
| `include_view_lineage` | boolean | True | If enabled, populates the Snowflake view-to-table and table-to-view lineages. Requires appropriate grants given to the role, and `include_table_lineage` to be True. View-to-table lineage requires Snowflake Enterprise Edition or above. |
| `include_views` | boolean | True | Whether views should be ingested. |
| `incremental_lineage` | boolean | True | When enabled, emits lineage as incremental to lineage already in the EDC. When disabled, re-states lineage on each run. |
| `match_fully_qualified_names` | boolean | False | Whether `schema_pattern` is matched against the fully qualified schema name, `&lt;catalog&gt;.&lt;schema&gt;`. |
| `role` | string |  | Snowflake role. |
| `top_n_queries` | integer | 10 | Number of top queries to save to each table. |

#### Stateful ingestion

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `stateful_ingestion` | StatefulStaleMetadataRemovalConfig or null | None | Configuration for stateful ingestion and stale metadata removal. |
| `stateful_ingestion.enabled` | boolean | False | Whether to enable stateful ingestion. |
| `stateful_ingestion.remove_stale_metadata` | boolean | True | Soft-deletes the entities present in the last successful run but missing in the current run, when `stateful_ingestion` is enabled. |
| `stateful_ingestion.fail_safe_threshold` | number | 75.0 | Percentage threshold above which stale-entity removal is skipped, as a safeguard against accidental mass deletion. |

#### Filter patterns

Allow and deny patterns are matched against the start of the string, not the entire string. For example, the pattern `prod` matches `prod`, `prod_east`, and `production`. To require an exact match, anchor the pattern explicitly, for example `^prod$`. Deny patterns take precedence over allow patterns.

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `database_pattern` | AllowDenyPattern |  | Regex patterns for databases to filter in ingestion. Snowflake system databases are denied by default. |
| `database_pattern.allow` | array(string) |  |  |
| `database_pattern.deny` | array(string) |  |  |
| `database_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `domain` | map(str, AllowDenyPattern) |  | Allow and deny regexes for assigning assets to domains. |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `profile_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns to filter tables, or specific columns, for profiling during ingestion. Only tables allowed by `table_pattern` are considered. |
| `profile_pattern.allow` | array(string) |  |  |
| `profile_pattern.deny` | array(string) |  |  |
| `profile_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `schema_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for schemas to filter in ingestion. Specify a regex to match the schema name only. For example, to match all tables in the schema `analytics`, use the regex `analytics`. |
| `schema_pattern.allow` | array(string) |  |  |
| `schema_pattern.deny` | array(string) |  |  |
| `schema_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `table_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for tables to filter in ingestion. Specify a regex to match the entire table name in `database.schema.table` format. For example, to match all tables starting with `customer` in the Customer database and public schema, use the regex `Customer.public.customer.*`. |
| `table_pattern.allow` | array(string) |  |  |
| `table_pattern.deny` | array(string) |  |  |
| `table_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `view_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for views to filter in ingestion. Defaults to `table_pattern` if not specified. Specify a regex to match the entire view name in `database.schema.view` format. For example, to match all views starting with `customer` in the Customer database and public schema, use the regex `Customer.public.customer.*`. |
| `view_pattern.allow` | array(string) |  |  |
| `view_pattern.deny` | array(string) |  |  |
| `view_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Profiling

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `profiling` | GEProfilingConfig |  | Profiling configuration. Set the nested fields below. |
| `profiling.enabled` | boolean | False | Whether profiling should be done. |
| `profiling.include_field_distinct_count` | boolean | True | Whether to profile for the number of distinct values for each column. |
| `profiling.include_field_max_value` | boolean | True | Whether to profile for the max value of numeric columns. |
| `profiling.include_field_mean_value` | boolean | True | Whether to profile for the mean value of numeric columns. |
| `profiling.include_field_median_value` | boolean | True | Whether to profile for the median value of numeric columns. |
| `profiling.include_field_min_value` | boolean | True | Whether to profile for the min value of numeric columns. |
| `profiling.include_field_null_count` | boolean | True | Whether to profile for the number of nulls for each column. |
| `profiling.include_field_sample_values` | boolean | True | Whether to profile for the sample values for all columns. |
| `profiling.include_field_stddev_value` | boolean | True | Whether to profile for the standard deviation of numeric columns. |
| `profiling.partition_profiling_enabled` | boolean | True | Whether to profile partitioned tables. Only BigQuery and Amazon Athena support this. If enabled, the latest partition data is used for profiling. |
| `profiling.profile_table_level_only` | boolean | False | Whether to perform profiling at table level only, or include column-level profiling as well. |
| `profiling.query_combiner_enabled` | boolean | True | This feature is still experimental and can be disabled if it causes issues. Reduces the total number of queries issued and speeds up profiling by dynamically combining SQL queries where possible. |
| `profiling.turn_off_expensive_profiling_metrics` | boolean | False | Whether to turn off expensive profiling. This turns off profiling for quantiles, distinct value frequencies, histogram, and sample values. It also limits the maximum number of fields being profiled to 10. |

### **Caveats**

- Some of the features are only available in the Snowflake Enterprise Edition. This doc has notes mentioning where this applies.
- The underlying Snowflake views that we use to get metadata have a latency of 45 minutes to 3 hours. So we would not be able to get very recent metadata in some cases like queries you ran within that time period etc. This is applicable particularly for lineage, usage and tags (without lineage) extraction.
- If there is any incident going on for Snowflake we will not be able to get the metadata until that incident is resolved.

## Related

- [Glossary terms](/glossary-terms.md)
- [Datasets](/datasets.md)
- [Domains](/domains.md)
