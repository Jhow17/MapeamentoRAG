---
title: "Superset Ingestion"
slug: "superset-ingestion"
updated: 2026-06-12T13:46:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/superset-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Superset Ingestion

To ingest Superset metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Detect deleted entities | ✅ | Optionally enabled via stateful_ingestion |

This plugin extracts the following:

- Charts, dashboards, and associated metadata.

See documentation for superset's /security/login at [here](https://superset.apache.org/docs/rest-api) for more details on superset's login api.
