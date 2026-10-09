---
title: "MongoDB Ingestion"
slug: "mongodb-ingestion"
updated: 2026-09-21T11:44:46Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/mongodb-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# MongoDB Ingestion

To ingest MongoDB metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Schema metadata | ✅ | Enabled by default |

This plugin extracts the following:

- Databases and associated metadata
- Collections in each database and schemas for each collection (via schema inference)

By default, schema inference samples 1,000 documents from each collection. Setting `schemaSamplingSize: null` scans the entire collection. Moreover, setting `useRandomSampling: False` samples the first documents found without random selection, which may be faster for large collections.

Note that `schemaSamplingSize` has no effect if `enableSchemaInference: False` is set.

Really large schemas can be further truncated to a maximum of 300 schema fields. This is configurable using the `maxSchemaSize` parameter.

### **Configuration options**

The following options control schema inference and which databases and collections are included in ingestion. A dot in a field path indicates a nested field in the YAML recipe.

#### Schema inference

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `enableSchemaInference` | boolean | True | Whether to infer schemas. |
| `useRandomSampling` | boolean | True | If documents for schema inference should be randomly selected. If False, documents will be selected from start. |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `collection_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for collections to filter in ingestion. |
| `collection_pattern.allow` | array(string) |  |  |
| `collection_pattern.deny` | array(string) |  |  |
| `collection_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `database_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | regex patterns for databases to filter in ingestion. |
| `database_pattern.allow` | array(string) |  |  |
| `database_pattern.deny` | array(string) |  |  |
| `database_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
