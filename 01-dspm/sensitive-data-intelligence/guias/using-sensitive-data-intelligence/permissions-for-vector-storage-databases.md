---
title: "Vector storage permissions"
slug: "permissions-for-vector-storage-databases"
updated: 2026-09-23T05:26:14Z
published: 2026-09-23T05:26:14Z
canonical: "helpcenter.securiti.ai/permissions-for-vector-storage-databases"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Vector storage permissions

You must provide the following permissions to your OpenSearch or Elasticsearch Vector storage.

## Cluster-level permissions

Use the table below for the required cluster-level permissions for AI tuning operations:

| OpenSearch permission | Elasticsearch equivalent permission | Reason |
| --- | --- | --- |
| `cluster_monitor` | `monitor` | Enables Securiti to monitor cluster health, node availability, and routing. The permission is required before creating or updating indices used for embeddings. |
| `cluster_composite_ops` | `manage_ilm` | Required to manage lifecycle operations for vector indices (rollover, retention). |
| `indices:admin/template/*` | `manage_index_templates` | Required for creating or updating index templates that define vector field mappings. |
| `indices:admin/index_template/*` | `manage_index_templates` | Required for creating or updating index templates that define vector field mappings. |
| `cluster:admin/opensearch/ml/*` | `manage_ml`, `monitor_ml` | Required for embedding model registration, KNN or vector search setup, and ML model monitoring. |
| `cluster:admin/script/put` | `cluster:admin/script/put` | Enables Securiti to store custom scripts used for pipeline transforms. |
| `cluster:admin/script/get` | `cluster:admin/script/get` | Required so AI Tuning can fetch stored scripts for template or index operations. |
| `cluster:admin/script/delete` | `cluster:admin/script/delete` | Required for removal of unused scripts to avoid conflicts during deployments. |
| `cluster:admin/knn_get_model_action` | Covered by `manage_ml` | Required for retrieving vector or KNN models for similarity search. |
| `cluster:admin/knn_search_model_action` | Covered by `manage_ml` | Required for executing KNN search model operations needed for embedding queries. |
| `cluster:admin/knn_training_model_action` | Covered by `manage_ml` | Required for training or optimizing vector models (OpenSearch-specific). |
| `cluster:admin/knn_training_job_route_decision_info_action` | Covered by `manage_ml` | Required for managing routing decisions for ML training jobs. |
| `cluster:admin/knn_update_model_graveyard_action` | Covered by `manage_ml` | Required for cleanup of old or deleted ML models to avoid conflicts. |
| `cluster:admin/knn_delete_model_action` | Covered by `manage_ml` | Required for removing obsolete vector search models. |
| (ES completeness) | `manage_pipeline` | Required because embedding ingestion often uses ingest pipelines (for text preprocessing). |
| (ES completeness) | `manage_ingest_pipelines` | Required for creation or update of ingest pipelines used in vector indexing flows. |
| (ES completeness) | `read_pipeline` | Required for fetching pipeline definitions when sending documents for embedding. |

## Index-level permissions (on `*`)

| OpenSearch permission | Elasticsearch equivalent permission | Reason |
| --- | --- | --- |
| `read` | `read` | Required for reading documents during similarity search and embedding retrieval. |
| `write` | `write` | Required for writing embedding vectors into indices. |
| `create_index` | `create_index` | Required for creating new vector indices dynamically. |
| `delete_index` | `delete_index` | Required for cleanup or re-creation of vector indices during configuration updates. |
| `manage` | `manage` | Required for index-level control needed for settings updates and reindex operations. |
| `search` | Included in `read` | Required for semantic search queries across embeddings. |
| `get` | Included in `read` | Required for retrieving documents during debug, tuning, or validation steps. |
| `index` | `index` | Required for inserting new vector documents into the index. |
| `delete` | `delete` | Required for removing outdated embeddings. |
| `crud` | `create + read + write + delete` | Simplifies granting all core data actions needed for indexing embeddings. |
| `indices:data/write/bulk` | Included in `write` + `index` | Required for fast bulk ingestion of embeddings during AI tuning. |
| `indices:data/write/index` | Included in `index` | Required for single-document indexing operations. |
| `indices:data/write/update` | Included in `write` | Required for updating existing embedding vectors when documents evolve. |
| `indices:data/read/search` | Included in `read` | Required for vector search queries. |
| `indices:data/read/get` | Included in `read` | Required for retrieving source documents. |
| `indices:data/read/scroll` | Included in `read` | Required for batch retrieval during training or re-indexing. |
| `indices:data/read/scroll/clear` | Included in `read` | Required to clean up scroll contexts to avoid resource leaks. |
| (Added for ES completeness) | `view_index_metadata` | AI Tuning must inspect index mappings and settings during validation. |
| (Added for ES completeness) | `monitor` | Enables monitoring of index health and shard status, which is important before running vector queries. |
