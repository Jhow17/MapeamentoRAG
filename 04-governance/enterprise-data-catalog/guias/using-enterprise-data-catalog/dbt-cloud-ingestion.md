---
title: "DBT Cloud Ingestion"
slug: "dbt-cloud-ingestion"
updated: 2026-09-21T11:43:23Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/dbt-cloud-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# DBT Cloud Ingestion

To ingest DBT Cloud metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Dataset usage | ❌ | N/A |
| Detect deleted entities | ✅ | Enabled via stateful ingestion |
| Table-level lineage | ✅ | Enabled by default |

The artifacts used by this source are:

- [dbt manifest file](https://docs.getdbt.com/reference/artifacts/manifest-json)
  - This file contains model, source, tests and lineage data.
- [dbt catalog file](https://docs.getdbt.com/reference/artifacts/catalog-json)
  - This file contains schema data.
  - DBT does not record schema data for Ephemeral models, as such EDC shows Ephemeral models in the lineage, however there is no associated schema for Ephemeral models.
- [dbt sources file](https://docs.getdbt.com/reference/artifacts/sources-json)
  - This file contains metadata for sources with freshness checks.
  - We transfer dbt's freshness checks to the EDC's last-modified fields.
  - Note that this file is optional – if not specified, use time of ingestion instead as a proxy for time last-modified.
- [dbt run_results file](https://docs.getdbt.com/reference/artifacts/run-results-json)
  - This file contains metadata from the result of a dbt run, e.g. dbt test.
  - When provided, we transfer dbt test run results into assertion run events to see a timeline of test runs on the dataset.

### **Configuration options**

The following options control how dbt metadata is mapped into the EDC, which dbt entities are emitted, and which nodes are included. A dot in a field path indicates a nested field in the YAML recipe.

#### Behavior and mapping

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `convert_column_urns_to_lowercase` | boolean | False | When enabled, converts column URNs to lowercase to ensure cross-platform compatibility. If `target_platform` is Snowflake, the default is True. |
| `incremental_lineage` | boolean | True | When enabled, emits lineage as incremental to existing lineage already in the EDC. When disabled, re-states lineage on each run. |
| `metadata_endpoint` | string | https://metadata.cloud.getdbt.com/graphql | The dbt Cloud metadata API endpoint. |
| `owner_extraction_pattern` | string |  | Regex string to extract owner from the dbt node using the (?P<name>...) syntax of the match object, where the group name must be owner. Examples: (1)r"(?P<owner>(.*)): (\w+) (\w+)" will extract jdoe as the owner from "jdoe: John Doe" (2) r"@(?P<owner>(.*))" will extract alice as the owner from "@alice". |
| `query_tag_mapping` | object | `{}` | mapping rules that will be executed against dbt query_tag meta properties. Refer to the section below on dbt meta automated mappings. |
| `target_platform_instance` | string |  | The platform instance for the platform that dbt is operating on. Use this if you have multiple instances of the same platform (e.g. redshift) and need to distinguish between them. |
| `use_identifiers` | boolean | False | Use model identifier instead of model name if defined (if not, default to model name). |

#### Entities enabled

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `entities_enabled` | DBTEntitiesEnabled | `{'models': 'YES', 'sources': 'YES', 'seeds': 'YES'…` | Controls for enabling / disabling metadata emission for different dbt entities (models, test definitions, test results, etc.) |
| `entities_enabled.models` | Enum | YES | Emit metadata for dbt models when set to Yes or Only |
| `entities_enabled.seeds` | Enum | YES | Emit metadata for dbt seeds when set to Yes or Only |
| `entities_enabled.snapshots` | Enum | YES | Emit metadata for dbt snapshots when set to Yes or Only |
| `entities_enabled.sources` | Enum | YES | Emit metadata for dbt sources when set to Yes or Only |
| `entities_enabled.test_definitions` | Enum | YES | Emit metadata for test definitions when enabled when set to Yes or Only |
| `entities_enabled.test_results` | Enum | YES | Emit metadata for test results when set to Yes or Only |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `node_name_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for dbt model names to filter in ingestion. |
| `node_name_pattern.allow` | array(string) |  |  |
| `node_name_pattern.deny` | array(string) |  |  |
| `node_name_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
