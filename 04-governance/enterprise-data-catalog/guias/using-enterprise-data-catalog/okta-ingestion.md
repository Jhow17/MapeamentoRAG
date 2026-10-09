---
title: "Okta Ingestion"
slug: "okta-ingestion"
updated: 2026-09-21T11:21:49Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/okta-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Okta Ingestion

To ingest Okta metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Descriptions | ✅ | Optionally enabled via configuration |
| Detect deleted entities | ✅ | Optionally enabled via `stateful_ingestion` |

This plugin extracts the following:

- Users
- Groups
- Group Membership

from your Okta instance.

> [!NOTE]
> Note
> 
> Any users ingested from this connector are not be able to log into EDC unless you have Okta OIDC SSO enabled. You can, however, have these users ingested into EDC before they log in for the first time if you would like to take actions like adding them to a group or assigning them a role.

### **Configuration options**

The following options control masking, which users and groups are fetched from Okta, and how Okta profiles are mapped into the EDC. A dot in a field path indicates a nested field in the YAML recipe.

#### Options and masking

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `mask_group_id` | boolean | True |  |
| `mask_user_id` | boolean | True |  |

#### Filtering and search

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `okta_groups_filter` | string |  | Okta filter expression (not regex) for ingesting groups. Only one of `okta_groups_filter` and `okta_groups_search` can be set. See (https://developer.okta.com/docs/reference/api/groups/#filters) for more info. |
| `okta_groups_search` | string |  | Okta search expression (not regex) for ingesting groups. Only one of `okta_groups_filter` and `okta_groups_search` can be set. See (https://developer.okta.com/docs/reference/api/groups/#list-groups-with-search) for more info. |
| `okta_users_filter` | string |  | Okta filter expression (not regex) for ingesting users. Only one of `okta_users_filter` and `okta_users_search` can be set. See (https://developer.okta.com/docs/reference/api/users/#list-users-with-a-filter) for more info. |
| `okta_users_search` | string |  | Okta search expression (not regex) for ingesting users. Only one of `okta_users_filter` and `okta_users_search` can be set. See (https://developer.okta.com/docs/reference/api/users/#list-users-with-search) for more info. |

#### Profile mapping

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `okta_profile_to_group_name_attr` | string | name | Which Okta Group Profile attribute to use as input to EDC group name mapping. |
| `okta_profile_to_group_name_regex` | string | `(.*)` | A regex used to parse the EDC group name from the attribute specified in `okta_profile_to_group_name_attr`. |
| `okta_profile_to_username_attr` | string | email | Which Okta User Profile attribute to use as input to EDC username mapping. Common values used are - login, email. |
| `okta_profile_to_username_regex` | string | `(.*)` | A regex used to parse the EDC username from the attribute specified in `okta_profile_to_username_attr`. |
