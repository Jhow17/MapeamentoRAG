---
title: "PowerBI Ingestion"
slug: "powerbi-ingestion"
updated: 2026-09-21T11:34:20Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/powerbi-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# PowerBI Ingestion

To ingest PowerBI metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Descriptions | ✅ | Enabled by default |
| Extract Ownership | ✅ | Disabled by default, configured using `extract_ownership` |
| Platform instance | ✅ | Enabled by default |

This plugin extracts the following:

- Power BI dashboards, tiles and datasets
- Names, descriptions and URLs of dashboard and tile
- Owners of dashboards

### **Configuration options**

The following options control what the PowerBI source extracts and which workspaces and datasets are included. A dot in a field path indicates a nested field in the YAML recipe.

#### Extraction and lineage

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `admin_apis_only` | boolean | False | Retrieve metadata using PowerBI Admin API only. If this is enabled, then Report Pages will not be extracted. Admin API access is required if this setting is enabled |
| `convert_lineage_urns_to_lowercase` | boolean | True | Whether to convert the urns of ingested lineage dataset to lowercase |
| `convert_urns_to_lowercase` | boolean | False | Whether to convert the PowerBI assets urns to lowercase |
| `enable_advance_lineage_sql_construct` | boolean | False | Whether to enable advance native sql construct for parsing like join, sub-queries. along this flag , the `native_query_parsing` should be enabled. By default `convert_lineage_urns_to_lowercase` is enabled, in-case if you have disabled it in previous ingestion execution then it may break lineage as this option generates the upstream datasets URN in lowercase. |
| `extract_dashboards` | boolean | True | Whether to ingest PBI Dashboard and Tiles as EDC Dashboard and Chart |
| `extract_dataset_schema` | boolean | False | Whether to ingest PBI Dataset Table columns and measures |
| `extract_datasets_to_containers` | boolean | False | PBI tables will be grouped under an EDC Container, the container reflect a PBI Dataset |
| `extract_endorsements_to_tags` | boolean | False | Whether to extract endorsements to tags, note that this may overwrite existing tags. Admin API access is required is this setting is enabled |
| `extract_independent_datasets` | boolean | False | Whether to extract datasets not used in any PowerBI visualization |
| `extract_lineage` | boolean | True | Whether lineage should be ingested between X and Y. Admin API access is required if this setting is enabled |
| `extract_ownership` | boolean | False | Whether ownership should be ingested. Admin API access is required if this setting is enabled. Note that enabling this may overwrite owners that you've added inside the EDC's web application. |
| `extract_reports` | boolean | True | Whether reports should be ingested |
| `extract_workspaces_to_containers` | boolean | True | Extract workspaces to EDC containers |
| `native_query_parsing` | boolean | True | Whether PowerBI native query should be parsed to extract lineage |
| `workspace_id_as_urn_part` | boolean | False | Highly recommend changing this to True, as you can have the same workspace name. To maintain backward compatability, this is set to False which uses workspace name |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `filter_dataset_endorsements` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Filter and ingest datasets which are 'Certified' or 'Promoted' endorsement. If both are added, dataset which are 'Certified' or 'Promoted' will be ingested . Default setting allows all dataset to be ingested |
| `filter_dataset_endorsements.allow` | array(string) |  |  |
| `filter_dataset_endorsements.deny` | array(string) |  |  |
| `filter_dataset_endorsements.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `workspace_id_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns to filter PowerBI workspaces in ingestion |
| `workspace_id_pattern.allow` | array(string) |  |  |
| `workspace_id_pattern.deny` | array(string) |  |  |
| `workspace_id_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
