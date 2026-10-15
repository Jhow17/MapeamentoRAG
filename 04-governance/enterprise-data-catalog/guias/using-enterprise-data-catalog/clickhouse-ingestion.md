---
title: "ClickHouse Ingestion"
slug: "clickhouse-ingestion"
updated: 2026-09-21T11:23:32Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/clickhouse-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# ClickHouse Ingestion

To ingest ClickHouse metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Data profiling | ✅ | Optionally enabled via configuration |
| Detect deleted entities | ✅ | Enabled via stateful ingestion |

This plugin extracts the following:

- Metadata for tables, views, materialized views and dictionaries
- Column types associated with each table(except *AggregateFunction and DateTime with timezone)
- Table, row, and column statistics via optional SQL profiling.
- Table, view, materialized view and dictionary(with CLICKHOUSE source_type) lineage

> [!NOTE]
> Tip
> 
> You can also get fine-grained usage statistics for ClickHouse using the `clickhouse-usage` source described below.
