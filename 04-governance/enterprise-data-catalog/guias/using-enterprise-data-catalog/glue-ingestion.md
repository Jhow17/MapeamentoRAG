---
title: "Glue Ingestion"
slug: "glue-ingestion"
updated: 2026-09-21T09:00:49Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/glue-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Glue Ingestion

To ingest Glue metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Detect deleted entities | ✅ | Enabled by default when stateful ingestion is turned on. |
| Domains | ✅ | Supported via the `domain` config field |
| Platform instance | ✅ | Enabled by default |

This plugin extracts the following:

- Tables in the Glue catalog.
- Column types associated with each table.
- Table metadata, such as owner, description and parameters.
- Jobs and their component transformations, data sources, and data sinks.

### **Configuration options**

The following options control what the Glue source ingests, which objects are included, and how profiles are read from Glue tables. A dot in a field path indicates a nested field in the YAML recipe.

#### General, lineage and tags

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `emit_s3_lineage` | boolean | False | Whether to emit S3-to-Glue lineage. |
| `extract_transforms` | boolean | True | Whether to extract Glue transform jobs. |
| `ignore_resource_links` | boolean | False | If set to True, ignore database resource links. |
| `ignore_unsupported_connectors` | boolean | True | Whether to ignore unsupported connectors. If disabled, an error will be raised. |
| `use_s3_bucket_tags` | boolean | False | If an S3 Buckets Tags should be created for the Tables ingested by Glue. Please Note that this will not apply tags to any folders ingested, only the files. |
| `use_s3_object_tags` | boolean | False | If an S3 Objects Tags should be created for the Tables ingested by Glue. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `database_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for databases to filter in ingestion. |
| `database_pattern.allow` | array(string) |  |  |
| `database_pattern.deny` | array(string) |  |  |
| `database_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `domain` | map(str,AllowDenyPattern) |  | A class to store allow deny regexes |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `table_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for tables to filter in ingestion. |
| `table_pattern.allow` | array(string) |  |  |
| `table_pattern.deny` | array(string) |  |  |
| `table_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Profiling

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `profiling` | GlueProfilingConfig |  | Configs to ingest data profiles from glue table |
| `profiling.column_count` | string |  | The parameter name for column count in glue table. |
| `profiling.max` | string |  | The parameter name for the max value of a column. |
| `profiling.mean` | string |  | The parameter name for the mean value of a column. |
| `profiling.median` | string |  | The parameter name for the median value of a column. |
| `profiling.min` | string |  | The parameter name for the min value of a column. |
| `profiling.null_count` | string |  | The parameter name for the count of null values in a column. |
| `profiling.null_proportion` | string |  | The parameter name for the proportion of null values in a column. |
| `profiling.row_count` | string |  | The parameter name for row count in glue table. |
| `profiling.stdev` | string |  | The parameter name for the standard deviation of a column. |
| `profiling.unique_count` | string |  | The parameter name for the count of unique value in a column. |
| `profiling.unique_proportion` | string |  | The parameter name for the proportion of unique values in a column. |
