---
title: "Druid Ingestion"
slug: "druid-ingestion"
updated: 2026-09-21T11:22:56Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/druid-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Druid Ingestion

To ingest Druid metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Platform instance | ✅ | Enabled by default |

This plugin extracts the following:

- Metadata for databases, schemas, and tables
- Column types associated with each table
- Table, row, and column statistics via optional SQL profiling.

> [!NOTE]
> Note
> 
> It is important to explicitly define the deny schema pattern for internal Druid databases (lookup and sys) if adding a schema pattern. Otherwise, the crawler may crash before processing relevant databases. This deny pattern is defined by default but is overridden by user-submitted configurations.

### **Configuration options**

The following options control what the Druid source ingests, which objects are included, and how profiling runs. A dot in a field path indicates a nested field in the YAML recipe.

#### General, tables and views

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `include_tables` | boolean | True | Whether tables should be ingested. |
| `include_views` | boolean | True | Whether views should be ingested. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `domain` | map(str,AllowDenyPattern) |  | A class to store allow deny regexes |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `profile_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns to filter tables (or specific columns) for profiling during ingestion. Note that only tables allowed by the `table_pattern` will be considered. |
| `profile_pattern.allow` | array(string) |  |  |
| `profile_pattern.deny` | array(string) |  |  |
| `profile_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `schema_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': ['^(lookup\|sysgit\|view)….` | regex patterns for schemas to filter in ingestion. |
| `schema_pattern.allow` | array(string) |  |  |
| `schema_pattern.deny` | array(string) |  |  |
| `schema_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `table_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for tables to filter in ingestion. Specify regex to match the entire table name in `database.schema.table` format. e.g. to match all tables starting with customer in Customer database and public schema, use the regex `'Customer.public.customer.*'` |
| `table_pattern.allow` | array(string) |  |  |
| `table_pattern.deny` | array(string) |  |  |
| `table_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `view_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for views to filter in ingestion. Note: Defaults to `table_pattern` if not specified. Specify regex to match the entire view name in `database.schema.view` format. e.g. to match all views starting with customer in Customer database and public schema, use the regex `'Customer.public.customer.*'` |
| `view_pattern.allow` | array(string) |  |  |
| `view_pattern.deny` | array(string) |  |  |
| `view_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Profiling

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `profiling` | GEProfilingConfig | `{'enabled': False, 'operation_config': {'lower_fre…` |  |
| `profiling.enabled` | boolean | False | Whether profiling should be done. |
| `profiling.include_field_distinct_count` | boolean | True | Whether to profile for the number of distinct values for each column. |
| `profiling.include_field_max_value` | boolean | True | Whether to profile for the max value of numeric columns. |
| `profiling.include_field_mean_value` | boolean | True | Whether to profile for the mean value of numeric columns. |
| `profiling.include_field_median_value` | boolean | True | Whether to profile for the median value of numeric columns. |
| `profiling.include_field_min_value` | boolean | True | Whether to profile for the min value of numeric columns. |
| `profiling.include_field_null_count` | boolean | True | Whether to profile for the number of nulls for each column. |
| `profiling.include_field_sample_values` | boolean | True | Whether to profile for the sample values for all columns. |
| `profiling.include_field_stddev_value` | boolean | True | Whether to profile for the standard deviation of numeric columns. |
| `profiling.profile_table_level_only` | boolean | False | Whether to perform profiling at table-level only, or include column-level profiling as well. |
