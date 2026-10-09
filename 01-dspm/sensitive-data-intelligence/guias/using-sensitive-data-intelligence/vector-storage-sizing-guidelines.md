---
title: "Vector storage sizing guidelines"
slug: "vector-storage-sizing-guidelines"
updated: 2026-09-21T09:03:25Z
published: 2026-09-21T09:03:25Z
canonical: "helpcenter.securiti.ai/vector-storage-sizing-guidelines"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Vector storage sizing guidelines

Vector storage sizing for AI Tuning depends on the volume of data you scan. This article provides sizing guidance for OpenSearch or Elasticsearch clusters connected to use AI Tuning.

AI Tuning supports both:

- **Structured AI Tuning**, where each scanned column is stored as one vector document.
- **Document Type AI Tuning**, where each scanned file is stored as one vector document.

When sizing vector storage, add the number of scanned columns and scanned files together. Use this guidance to estimate memory, disk capacity, node count, and shard configuration before creating your vector storage.

> [!NOTE]
> Note
> 
> The same disk, shard, and replica configuration applies to both, whether you deploy on AWS or on Elastic Cloud, including when Elastic Cloud is hosted on Microsoft Azure.

AI Tuning writes one document for every scanned item. Use the table below to understand what one document represents for your data.

| AI Tuning mode | One document represents | Index |
| --- | --- | --- |
| Structured | One scanned column | `column_vector_embeddings-*` |
| Document Type | One scanned file | `document_type_vector_embeddings-*` |

> [!NOTE]
> Tip
> 
> Each document contains two 384-dimension embeddings:
> 
> - For a column, the embeddings represent the column name and its content.
> - For a file, the embeddings represent the file name and its content.
> 
> For structured AI Tuning, a document contains two additional embeddings only after tuning feedback is submitted for that column.
> 
> For sizing purposes, add your scanned columns and scanned files together. For example, if AI Tuning processes 8 million columns and 2 million files, size the deployment for 10 million scanned items.

## Sizing recommendations

Use the following baseline sizing guidelines.

- **Memory:** 7 GB per 1 million scanned items
- **Disk:** 20 GB per 1 million scanned items

> [!NOTE]
> Note
> 
> This 20 GB figure is 7 GB of raw data, doubled for the replica, plus extra room for merges and snapshots.
- **Shards:** Size each shard using the same ratio of 7 GB per 1 million scanned items

> [!CAUTION]
> Caution
> 
> Memory is typically the limiting factor. A cluster with sufficient disk but insufficient memory can evict search graphs, slow down, or stop responding to vector queries. Because memory also has the greatest impact on infrastructure cost, size it carefully and treat disk as the less expensive resource.

## Choosing nodes

Estimate the required node configuration as follows.

1. Add the total number of scanned columns and files.
2. Multiply the number of scanned items (in millions) by 7 to determine the required memory.
3. Multiply the number of scanned items (in millions) by 20 to determine the required disk capacity.
4. Divide the required memory by the memory available per node to determine the required number of data nodes.
5. Use at least two data nodes, regardless of the calculation.

One data node cannot host a replica. A single-node deployment therefore provides no redundant copy of the data and becomes unavailable while the node restarts.

### Recommendations for node configuration

When selecting node sizes:

- Choose the node size before determining the node count.
- Use 32 GB to 64 GB of memory per node for production deployments.
- Use nodes smaller than 16 GB only for trial environments.
- Nodes larger than 64 GB provide limited additional benefit because the search engine limits heap size to approximately 32 GB, using the remaining memory for caching.
- Plan for approximately 1 vCPU per 4 GB of memory, which general-purpose instance families typically provide.
- Add three dedicated master nodes when your deployment uses more than three data nodes or spans multiple availability zones.

### Example configuration

| Scanned items (columns + files) | Memory | Disk (including one replica) | Data nodes | Recommended node configuration |
| --- | --- | --- | --- | --- |
| 10 million | 70 GB | 200 GB | 2 | 64 GB memory, 16 vCPU, 100 GB disk |

For a size that is not listed, calculate the requirements proportionally.

For example, if AI Tuning processes 12 million columns and 3 million files, the deployment contains 15 million scanned items. This requires approximately 105 GB of memory and 300 GB of disk. Two 64 GB nodes provide sufficient memory, with approximately 150 GB of disk per node.

## Instance equivalents

The following instance types provide approximately equivalent compute capacity across supported cloud providers.

| Memory and vCPU | AWS OpenSearch | Google Cloud | Microsoft Azure |
| --- | --- | --- | --- |
| 8 GB, 2 vCPU | `m5.large.search` | `n2-standard-2` | `Standard_D2s_v5` |
| 32 GB, 8 vCPU | `m5.2xlarge.search` | `n2-standard-8` | `Standard_D8s_v5` |
| 64 GB, 16 vCPU | `m5.4xlarge.search` | `n2-standard-16` | `Standard_D16s_v5` |

> [!NOTE]
> Note
> 
> Securiti recommends the node configurations listed above. We have tested and validated these configurations for AI Tuning. Equivalent instance families with similar CPU and memory resources might also work but are not validated by Securiti.

## Configuring shards and replicas

You must configure shard and replica counts before AI Tuning creates the indexes.

### Replicas

Securiti recommends configuring **one replica**. One replica stores a second copy of the data on another node, helping AI Tuning remain available during node restarts and allowing searches to run from either copy.

> [!NOTE]
> Note
> 
> - Use **zero replicas** only for single-node trial environments, where a replica cannot be assigned and would leave the index permanently yellow.
> - Using more than one replica multiplies storage and memory for very little additional benefit, so one replica is the recommendation at every size.

### Primary shards

Size primary shards based on the amount of data the index is expected to hold. Aim for 20 GB to 50 GB of data per shard. As a general guideline, use one primary shard per 6 million scanned items, with a minimum of one shard.

Use the following table to understand the shard counts.

> [!NOTE]
> Note
> 
> - Apply the same shard count to both the Structured and Document Type AI Tuning indexes.
> 
> If one mode contains significantly more data than the other, size the shard count for the larger index. The smaller index can use shards below the preferred size, with a small additional memory cost.
> - Changing the number of primary shards after creating your instance requires re-indexing your data. Contact your Customer Success Manager or Account Representative for assistance.

| Scanned items (columns) | Data | Primary shards | Data per shard | Replicas |
| --- | --- | --- | --- | --- |
| 1 million | 7 GB | 1 | 7 GB | 1 |
| 5 million | 35 GB | 1 | 35 GB | 1 |
| 10 million | 70 GB | 2 | 35 GB | 1 |
| 25 million | 175 GB | 4 | 44 GB | 1 |
| 50 million | 350 GB | 8 | 44 GB | 1 |
| 100 million | 700 GB | 16 | 44 GB | 1 |

## Scaling your deployment

Your structured and unstructured AI Tuning data can grow over time. Consider the following when scaling the vector storage:

- **Primary shard count** cannot be increased without rebuilding the indexes. Size your deployment based on expected growth over the next year rather than only your current data volume.
- **Data nodes** are the preferred scaling mechanism. Adding or removing nodes of the same size is routine.
- **Node size** changes require migrating data to new nodes, which can take considerable time on large deployments.
- **Replica count** can be increased or decreased at any time.
- **Disk capacity** can usually be expanded in place but often cannot be reduced.

When scaling down, reduce capacity in this order:

1. Remove replicas.
2. Remove data nodes.
3. Reduce node size if necessary.

## Cost considerations

Memory is the primary driver of infrastructure cost. To reduce costs:

- Use a single-node deployment with no replica for non-production environments.
- On AWS, use a two-zone domain without standby. Standby holds a full spare zone in reserve and roughly doubles your node count for availability that AI Tuning does not need, since a scan can be re-run.
- Purchase reserved capacity only after your scanned item count has stabilized.
- Re-evaluate cluster sizing when the number of scanned items grows by more than half, rather than provisioning significantly ahead of demand.
