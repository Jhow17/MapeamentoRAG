---
title: "Kafka Ingestion"
slug: "clone-salesforce-ingestion"
updated: 2026-09-21T11:39:37Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/clone-salesforce-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Kafka Ingestion

To ingest Kafka metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Descriptions | ✅ | Set dataset description to top level doc field for Avro schema |
| Platform instance | ✅ | For multiple Kafka clusters, use the `platform_instance` configuration |
| Schema metadata | ✅ | Schemas associated with each topic are extracted from the schema registry. Avro and Protobuf (certified), JSON (incubating). Schema references are supported. |

This plugin extracts the following:

- Topics from the Kafka broker.
- Schemas associated with each topic from the schema registry (Avro, Protobuf and JSON schemas are supported).

### **Configuration options**

The following options control which Kafka topics are included in ingestion. A dot in a field path indicates a nested field in the YAML recipe.

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `domain` | map(str,AllowDenyPattern) |  | A class to store allow deny regexes |
| `domain.key.allow` | array(string) |  |  |
| `domain.key.deny` | array(string) |  |  |
| `domain.key.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `topic_patterns` | AllowDenyPattern | `{'allow': ['.*'], 'deny': ['^_.*'], 'ignoreCase': True}` |  |
| `topic_patterns.allow` | array(string) |  |  |
| `topic_patterns.deny` | array(string) |  |  |
| `topic_patterns.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
