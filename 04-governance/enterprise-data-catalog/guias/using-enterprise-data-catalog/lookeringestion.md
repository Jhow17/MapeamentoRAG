---
title: "Looker Ingestion"
slug: "lookeringestion"
updated: 2026-09-21T11:41:59Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/lookeringestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Looker Ingestion

To ingest Looker metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Dataset Usage | ✅ | Enabled by default, configured using `extract_usage_history` |
| Descriptions | ✅ | Enabled by default |
| Extract Ownership | ✅ | Enabled by default, configured using `extract_owners` |
| Platform instance | ❌ | Not supported |

This plugin extracts the following:

- Looker dashboards, dashboard elements (charts) and explores
- Names, descriptions, URLs, chart types, input explores for the charts
- Schemas and input views for explores
- Owners of dashboards

> [!NOTE]
> Note
> 
> To get complete Looker metadata integration (including Looker views and lineage to the underlying warehouse tables), you must ALSO use the lookml module.

### Prerequisites

You need to provide the following permissions for ingestion to work correctly.

```plaintext
access_data
explore
manage_models
see_datagroups
see_lookml
see_lookml_dashboards
see_looks
see_pdts
see_queries
see_schedules
see_sql
see_system_activity
see_user_dashboards
see_users
```

### **Configuration options**

The following options control what the Looker source extracts, which dashboards and charts are included, and how names and browse paths are constructed. A dot in a field path indicates a nested field in the YAML recipe.

#### Extraction options

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `external_base_url` | string |  | Optional URL to use when constructing external URLs to Looker if the `base_url` is not the correct one to use. For example, https://looker-public.company.com. If not provided, the external base URL will default to `base_url`. |
| `extract_column_level_lineage` | boolean | True | When enabled, extracts column-level lineage from Views and Explores |
| `extract_embed_urls` | boolean | True | Produce URLs used to render Looker Explores as Previews inside of the EDC UI. Embeds must be enabled inside of Looker to use this feature. |
| `extract_independent_looks` | boolean | False | Extract looks which are not part of any Dashboard. To enable this flag the `stateful_ingestion` should also be enabled. |
| `extract_owners` | boolean | True | When enabled, extracts ownership from Looker directly. When disabled, ownership is left empty for dashboards and charts. |
| `extract_usage_history` | boolean | True | Whether to ingest usage statistics for dashboards. Setting this to True will query looker system activity explores to fetch historical dashboard usage. |
| `extract_usage_history_for_interval` | string | 30 days | Used only if `extract_usage_history` is set to True. Interval to extract looker dashboard usage history for. See https://docs.looker.com/reference/filter-expressions#date_and_time. |
| `include_deleted` | boolean | False | Whether to include deleted dashboards and looks. |
| `skip_personal_folders` | boolean | False | Whether to skip ingestion of dashboards in personal folders. Setting this to True will only ingest dashboards in the Shared folder space. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `chart_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Patterns for selecting chart ids that are to be included |
| `chart_pattern.allow` | array(string) |  |  |
| `chart_pattern.deny` | array(string) |  |  |
| `chart_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `dashboard_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Patterns for selecting dashboard ids that are to be included |
| `dashboard_pattern.allow` | array(string) |  |  |
| `dashboard_pattern.deny` | array(string) |  |  |
| `dashboard_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Naming and browse patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `explore_browse_pattern` | LookerNamingPattern | `{'pattern': '/{env}/{platform}/{project}/explores'…` | Pattern for providing browse paths to explores. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `explore_browse_pattern.pattern` | string |  |  |
| `explore_naming_pattern` | LookerNamingPattern | `{'pattern': '{model}.explore.{name}'}` | Pattern for providing dataset names to explores. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `explore_naming_pattern.pattern` | string |  |  |
| `view_browse_pattern` | LookerNamingPattern | `{'pattern': '/{env}/{platform}/{project}/views'}` | Pattern for providing browse paths to views. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `view_browse_pattern.pattern` | string |  |  |
| `view_naming_pattern` | LookerNamingPattern | `{'pattern': '{project}.view.{name}'}` | Pattern for providing dataset names to views. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `view_naming_pattern.pattern` | string |  |  |

#### Transport options

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `transport_options` | TransportOptionsConfig |  | Populates the TransportOptions struct for looker client |
| `transport_options.headers` | map(str,string) |  |  |
| `transport_options.timeout` | integer |  |  |
