---
title: "Presto Ingestion"
slug: "presto-ingestion"
updated: 2026-09-21T11:41:29Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/presto-ingestion"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Presto Ingestion

To ingest Presto metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Data profiling | ✅ | Optionally enabled via configuration |
| Domains | ✅ | Supported via the `domain` config field |

This plugin extracts the following:

- Metadata for databases, schemas, and tables
- Column types and schema associated with each table
- Table, row, and column statistics via optional SQL profiling
