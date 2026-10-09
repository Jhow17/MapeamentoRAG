---
title: "Azure AD Ingestion"
slug: "azure-ad-ingestion"
updated: 2026-09-21T11:14:18Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/azure-ad-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Azure AD Ingestion

To ingest Azure AD metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Detect deleted entities | ✅ | Optionally enabled via `stateful_ingestion` |

This plugin extracts the following:

- Users
- Groups
- Group membership

### **Configuration options**

The following options control how Azure AD responses are mapped into the EDC and which users and groups are included in ingestion. A dot in a field path indicates a nested field in the YAML recipe.

#### Response mapping and options

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `azure_ad_response_to_groupname_attr` | string | displayName | Which Azure AD Group Response attribute to use as input to EDC group name mapping. |
| `azure_ad_response_to_groupname_regex` | string | `(.*)` | A regex used to parse the EDC group name from the attribute specified in `azure_ad_response_to_groupname_attr`. |
| `azure_ad_response_to_username_attr` | string | userPrincipalName | Which Azure AD User Response attribute to use as input to EDC username mapping. |
| `azure_ad_response_to_username_regex` | string | `(.*)` | A regex used to parse the EDC username from the attribute specified in `azure_ad_response_to_username_attr`. |
| `filtered_tracking` | boolean | True | If enabled, report will contain names of filtered users and groups. |
| `mask_group_id` | boolean | True | Whether workunit ID's for groups should be masked to avoid leaking sensitive information. |
| `mask_user_id` | boolean | True | Whether workunit ID's for users should be masked to avoid leaking sensitive information. |
| `redirect` | string | https://login.microsoftonline.com/common/oauth2/na… | Redirect URI. Found in your app registration on Azure AD Portal. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `groups_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for groups to include in ingestion. |
| `groups_pattern.allow` | array(string) |  |  |
| `groups_pattern.deny` | array(string) |  |  |
| `groups_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `users_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for users to filter in ingestion. |
| `users_pattern.allow` | array(string) |  |  |
| `users_pattern.deny` | array(string) |  |  |
| `users_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
