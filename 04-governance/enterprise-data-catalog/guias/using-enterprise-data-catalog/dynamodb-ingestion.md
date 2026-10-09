---
title: "DynamoDB Ingestion"
slug: "dynamodb-ingestion"
updated: 2026-09-21T11:45:45Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/dynamodb-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# DynamoDB Ingestion

To ingest DynamoDB metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Detect deleted entities | ✅ | Optionally enabled via `stateful_ingestion.remove_stale_metadata` |
| Platform instance | ✅ | By default, platform_instance will use the AWS account id |

This plugin extracts the following:

- AWS DynamoDB table names with their region, and infer schema of attribute names and types by scanning the table.
