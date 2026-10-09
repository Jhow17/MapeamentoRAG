---
title: "Salesforce Ingestion"
slug: "clone-redshift-ingestion"
updated: 2026-09-21T11:40:03Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/clone-redshift-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Salesforce Ingestion

To ingest Salesforce metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Data profiling | ✅ | Only table level profiling is supported via `profiling.enabled` config field |
| Detect deleted entities | ❌ | Not supported yet |
| Domains | ✅ | Supported via the `domain` config field |
| Platform instance | ✅ | Can be equivalent to Salesforce organization |

### **Prerequisites**

In order to ingest metadata from Salesforce, you will need one of:

- Salesforce username, password, security token.
- Salesforce username, consumer key and private key for JSON web token access.
- Salesforce instance url and access token/session id (suitable for one-shot ingestion only, as access token typically expires after 2 hours of inactivity).

The account used to access Salesforce requires the following permissions for this integration to work:

- View setup and configuration.
- View all data.

### **Configuration options**

The following options control which Salesforce objects are included in ingestion. A dot in a field path indicates a nested field in the YAML recipe.

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `domain` | map(str,AllowDenyPattern) |  | A class to store allow deny regexes |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `object_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for Salesforce objects to filter in ingestion. |
| `object_pattern.allow` | array(string) |  |  |
| `object_pattern.deny` | array(string) |  |  |
| `object_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `profile_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | Regex patterns for profiles to filter in ingestion, allowed by the `object_pattern`. |
| `profile_pattern.allow` | array(string) |  |  |
| `profile_pattern.deny` | array(string) |  |  |
| `profile_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
