---
title: "Configuring AI Tuning"
slug: "configuring-ai-tuning"
status: "update"
updated: 2026-09-23T09:17:00Z
published: 2026-09-23T09:17:00Z
canonical: "helpcenter.securiti.ai/configuring-ai-tuning"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring AI Tuning

AI Tuning is configured at the tenant level through a one-time setup. It lets you connect your Vector Storage, sync existing classification data, and enable AI Tuning for your tenant. Once configured, Securiti generates vector embeddings from sample data collected during discovery scans and uses them to identify similar columns and files during feedback sessions.

> [!WARNING]
> Important
> 
> - Securiti does not store customer data for AI Tuning. It reads sample values from data to generate vector embeddings and stores only the generated embeddings in the configured vector storage. This is a one-way process, and the embeddings cannot be converted back to the original customer data.
> - When using the AI Tuning feature, Securiti syncs existing data classification information collected from completed discovery scans, stored in private cloud and pod local storage, and generates vector embeddings from this information. Once the embeddings are complete, the rest of the AI Tuning logic operates entirely on them.

Follow the sections below to configure AI Tuning.

## Configure Private Cloud Storage (PCS)

To use AI Tuning, you must have PCS configured in your tenant. From the **Configuration** tab, click **Configure Private Cloud Storage** to set up your storage configuration. If it is already configured, click **Continue**, as shown below. For more information, see [Configuring private cloud storage](/latest/docs/system-settings-configuring-private-cloud-storage).

> [!WARNING]
> Important
> 
> If AI Tuning is enabled and you delete the Private Cloud Storage, AI Tuning is automatically disabled.

![Configuration settings for AI Tuning and Private Cloud Storage management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-19 at 9.33.51 AM.png)

## Setting up vector storage

AI Tuning stores generated vector embeddings in a vector storage instance. You can use a Securiti-hosted instance or host the instance yourself. Securiti supports **OpenSearch** and **Elasticsearch** vector databases for vector storage. AI Tuning writes vector embeddings to the vector storage instance from the pod. The Securiti SaaS cloud requires read access only to display AI Tuning charts.

AI Tuning stores vectors generated for columns or files by using sample data collected during discovery scans. Securiti fetches data from vector storage to compare column or file similarities and improve classification accuracy.

To ensure a successful connection with the vector storage, you must fulfill the following prerequisites:

- You must allowlist the Securiti SaaS IPs. For more information, see [Allow listing IPs or domains for PCS connection](/latest/docs/configuring-private-cloud-storage-allow-listing-domains-or-ips-for-private-cloud-storage)

> [!WARNING]
> Important
> 
> If allowlisting is not configured, AI Tuning cannot write embeddings to the database.
- You must provide your pod with the required network access to the VectorDB instance.

### Supported vector storages

Securiti supports the following vector storages for AI tuning:

> [!WARNING]
> Important
> 
> We recommend that you use the versions listed below. These versions have been tested and validated for AI Tuning.

| Vector storage | Supported version |
| --- | --- |
| OpenSearch | - `2.17.0` - `2.19.0` |
| Elasticsearch | - `8.17.0` - `8.17.1` - `9.3.0` |

### Vector storage instance creation

AI Tuning stores the embeddings it generates from your data in a vector storage instance. Securiti supports two vector storage engines:

- AWS OpenSearch Service
- Elasticsearch

You must create your vector storage instance to use in AI tuning. For more information, see [Creating a vector storage instance](/latest/docs/creating-a-vector-storage-instance).

### Vector storage sizing guidelines

Vector storage capacity depends on the total number of scanned items used by AI Tuning. For structured data, a scanned item is one scanned column. Whereas for document type, a scanned item is one scanned file.

To estimate storage requirements, add the total number of scanned columns and scanned files together. Use this total to size memory, disk, nodes, and shards. For more information, see Vector storage sizing guidelines.

> [!NOTE]
> Note
> 
> Securiti recommends provisioning additional disk capacity beyond the minimum values in this article to accommodate future growth, indexing overhead, merges, and snapshots.

### Permissions for vector storage

Your Elasticsearch or OpenSearch instance must have the following permissions:

- Read
- Write
- Delete data
- Index

> [!NOTE]
> Note
> 
> - Securiti requires the Index creation permission to automatically create the index during embedding storage.
> - Securiti automatically creates index names using the following prefix. We recommend to not change this standard:
>   - `column_vector_embeddings-*` for Structured AI Tuning
>   - `document_type_vector_embeddings-*` for Document Type AI Tuning
> - Securiti manages index retention.
> - Embedding data is deleted only when the corresponding data scans are deleted.

For more information on the complete list of permissions, see [Vector storage permissions](/latest/docs/permissions-for-vector-storage-databases).

## Configuring vector storage for AI Tuning

Once you have set up your vector storage instance with the required permissions, configure in Securiti as described below.

1. In **Settings > AI Tuning > Tuning Configuration**, click **Configure Vector Storage**.
2. For Securiti-hosted environments, the option appears as **Securiti-Hosted Storage**, indicating that vector storage is fully managed by Securiti. No additional configuration is required with Securiti Cloud Storage.
3. Click **Add new** to manage and store your vectors in your self-hosted vector storage.

![Configuration options for vector storage in AI tuning settings are displayed on the screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-19 at 9.35.02 AM.png)
4. Specify your **Self-Hosted Vector Storage**, and in the **Add Vector Storage Credentials**, provide the required credentials.

![Form for adding vector storage credentials with various input fields and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-19 at 9.36.12 AM.png)

| Self-Hosted Vector Storage | Authentication Type | Required Credentials | Example |
| --- | --- | --- | --- |
| ElasticSearch | API key | - Name - URL - API Key | - Name: `Elastic-AITuning` - URL: `https://elastic.example.com:9200` - API Key: `2f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0…` |
| Credentials | - Name - URL - Username - Password | - Name: `Elastic-AITuning` - URL: `https://elastic.example.com:9200` - Username: `elastic-admin` |
| OpenSearch | - | - Name - URL - Username - Password | - Name: `OpenSearch-Prod-AIStorage` - URL: `https://opensearch-vdb.internal.myorg.com:9200` - Username: `vector-admin` |

Configure the following additional fields:

| Fields | Description |
| --- | --- |
| Primary shards | Specifies how your data is split across the vector storage. For example, 4 million columns take approximately 20 GB of vector storage and require 1 primary shard. Up to 70 million columns can be accommodated within 20 shards. > [!NOTE] > Note > > Consider the following for primary shards: > > - Securiti supports a maximum of 100 shards. > - If you need to change the number of primary shards after a scan, you must re-index your data. Contact your Customer Success Manager or Account Representative for assistance. |
| Replica shards | Specifies how many copies of each shard are kept. One replica is sufficient for most use cases. > [!NOTE] > Note > > - Increase replicas if you need higher search performance or additional fault tolerance. > - Unlike primary shards, replicas can be changed at any time. |
| Skip SSL certificate verification | Mark the **Skip the SSL certificate verification** checkbox to skip the certificate validation or leave unmarked to verify the uploaded CA certificates. > [!NOTE] > Note > > When the **Skip the SSL certificate verification** checkbox is marked, the upload **Custom CA certificate** option is disabled. |
| Custom CA certificate | Upload certificates by clicking **Custom CA certificate**. > [!NOTE] > Note > > - In case you do not upload any custom certificate, default CA certificates are used for authentication. > - You can upload only supported certificate formats i.e, `.pem` or `.crt` files. |
5. Click **Save credentials** to continue.

Securiti authenticates the provided credentials at this step. If authentication succeeds, the configured vector storage appears on the screen. If it fails, review and correct the information provided.
6. To edit the details of an existing vector storage configuration or delete it to add a new one, click **Edit** or **Delete**, as applicable.

![Settings page for configuring vector storage and AI tuning options in a system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-19 at 12.51.05 PM.png)
7. Click **Save and Continue** to initiate the data sync. This process syncs existing data classification information from completed discovery scans. Securiti retrieves this information from private cloud and pod local storage.

> [!NOTE]
> Note
> 
> Consider the following for data sync:
> 
> - For Structured Data AI Tuning, vector setup takes approximately 5 minutes per 1,000 columns.
> - For Structured Data AI Tuning, AI Tuning can be applied to columns scanned before it was enabled, as long as sample data was collected. Run the data sync to generate vectors for those columns.
> - For Document Type AI Tuning, syncing previously collected sample data is not supported. You must enable AI Tuning before running a scan for its files to be eligible for AI Tuning.
> - For Securiti-hosted vector storage, Securiti automatically syncs data from PCS to the vector storage.
> - For self-hosted vector storage, data sync is initiated after the setup is complete.

## Enabling AI Tuning

To make the data from future discovery scans available for the AI Tuning feature, mark the enable AI Tuning checkbox.

> [!WARNING]
> Important
> 
> - AI Tuning must be enabled to perform a sync.
> - Document Type AI Tuning does not support syncing sample data collected before it was enabled. You must enable this toggle before running a discovery scan for that scan's files to be eligible for AI Tuning.

To do so, follow the steps below:

1. Select the tab for the AI Tuning type, either **Structured Data** or **Document Type**, as shown below**.**

![Configuration settings for AI tuning and data synchronization in a cloud environment.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tabselection_tuningconfiguration.png)
  1. For **Structured Data**, turn on the **Enable AI Tuning for Structured Data** toggle.
  2. For **Document Type**, turn on the **Enable AI Tuning for Document Type** toggle.

> [!NOTE]
> Note
> 
> Consider the following for this toggle:
> 
> - Securiti automatically enables the toggle once the Vector Storage configuration is complete.
> - The toggle is unavailable if:
> 
> For more information on sync states, see [Understanding sync states](/latest/docs/configuring-ai-tuning#understanding-sync-states1).
>   - Data sync is in Scheduled state.
>   - Data sync is In Progress state.
>   - Vector Storage setup has failed.
2. Click **Save Changes**.

> [!NOTE]
> Note
> 
> Turning this toggle on makes data from future discovery scans available for AI Tuning. It doesn't apply automatically to scans that already completed before you enabled it.

## Understanding sync states

Once the AI Tuning is initiated, you can review the sync state indicator to track data sync progress, as shown below.

> [!WARNING]
> Important
> 
> You can cancel only the data sync while it is in progress.

![Configuration settings for AI tuning and data classification in a system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/stateofsync_aituningconfiguration.png)Use the following table to understand the possible sync states:

| State | Description | Available sync actions |
| --- | --- | --- |
| Scheduled | Data sync is scheduled. | None |
| Vector storage setup in progress | Data sync starts after the Vector Storage setup is complete. > [!NOTE] > Note > > It applies to self-hosted Vector Storage only. | None |
| Vector storage setup failed | Data sync cannot be initiated because the Vector Storage setup failed. > [!NOTE] > Note > > It applies to self-hosted Vector Storage only. | None |
| Data sync in progress | Vector storage setup is complete and data sync is in progress. | None |
| Complete | Data sync has completed. | If a scan completed while AI Tuning was disabled, click **Sync Updates** to resync the missing data. |
| Data sync partially complete | Data sync completed for some items but not all. | Click **Retry Sync** to resync items for which data sync was unsuccessful. |
| Failed | Data sync failed for all items. | Click **Retry Sync** to reinitiate the data sync. |
| Canceled | Data sync was canceled by a user. | Click **Continue Sync** to resume the sync from where it was canceled. |

> [!NOTE]
> Note
> 
> Sync actions are available only when AI Tuning is enabled and sample data is available in PCS. Use them to generate vectors for items where vector generation failed or is missing.

## Viewing Vectorization statistics

In the **Configure AI Tuning** tab, click **Statistics** to open **Vectorization Statistics** popup, which displays aggregated vectors generated during the initial setup and subsequent discovery scans.

![Vectorization statistics for various data systems and their corresponding organizations and columns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vectorization Statistics_UDS.png)

> [!NOTE]
> Note
> 
> Once the Vector Storage configuration is complete and data syncing begins, you can view the sample data count stored on the pod and PCS on the [**Tuning Audit Logs**](/latest/docs/viewing-ai-tuning-audit-logs) page.

For more information, see Classifying structured data using AI Tuning and [Classifying document types using AI Tuning](/latest/docs/classifying-document-types-using-ai-tuning).
