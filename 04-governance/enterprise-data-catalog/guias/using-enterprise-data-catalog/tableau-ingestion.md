---
title: "Tableau Ingestion"
slug: "tableau-ingestion"
updated: 2026-09-21T11:12:46Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/tableau-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Tableau Ingestion

To ingest Tableau metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Dataset usage | ✅ | Dashboard/Chart view counts, enabled using extract_usage_stats config |
| Descriptions | ✅ | Enabled by default |
| Detect deleted entities | ✅ | Enabled by default when stateful ingestion is turned on. |
| Domains | ❌ | Requires transformer |
| Extract ownership | ✅ | Requires recipe configuration |
| Platform instance | ✅ | Enabled by default |
| Table-level lineage Column-level lineage | ✅ | Enabled by default |

### **Prerequisites**

In order to ingest metadata from Tableau, you will need:

- Tableau Server Version 2021.1.10 and above. It may also work for older versions.
- [Enable the Tableau Metadata API](https://help.tableau.com/current/api/metadata_api/en-us/docs/meta_api_start.html#enable-the-tableau-metadata-api-for-tableau-server) for Tableau Server, if its not already enabled.
- Tableau Credentials (Username/Password or [Personal Access Token](https://help.tableau.com/current/pro/desktop/en-us/useracct.htm#create-and-revoke-personal-access-tokens))
- The user or token must have **Site Administrator Explorer** permissions.

### **Configuration options**

The following options control what the Tableau source extracts and which projects are included. A dot in a field path indicates a nested field in the YAML recipe.

#### General and extraction

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `extract_column_level_lineage` | boolean | True | When enabled, extracts column-level lineage from Tableau Datasources. |
| `extract_project_hierarchy` | boolean | True | Whether to extract the entire project hierarchy for nested projects. |
| `ingest_external_links_for_charts` | boolean | True | Ingest a URL to link out to from charts. |
| `ingest_external_links_for_dashboards` | boolean | True | Ingest a URL to link out to from dashboards. |
| `ingest_tables_external` | boolean | False | Ingest details for tables external to (not embedded in) Tableau as entities. |
| `project_path_separator` | string | `/` | The separator used in the `project_pattern` field between project names. A slash is used by default. Change this if your Tableau projects contain slashes in their names and you want to filter by project. |
| `projects` | array(string) |  |  |
| `site` | string |  | Tableau site. Always required for Tableau Online. Use an empty string to connect to the Default site on Tableau Server. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `project_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Filter for specific Tableau projects. For example, use `My Project` to ingest a root-level project named My Project, or `My Project/Nested Project` to ingest a nested project named Nested Project. By default, all projects nested inside a matching project are included in ingestion. You can allow and deny projects by name or by regex pattern. Deny patterns always take precedence over allow patterns. By default, all projects are ingested. |
| `project_pattern.allow` | array(string) |  |  |
| `project_pattern.deny` | array(string) |  |  |
| `project_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
