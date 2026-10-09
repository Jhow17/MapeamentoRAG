---
title: "Azure Blob Storage (Hyperdrive)"
slug: "azure-blob-storage-hyperdrive"
status: "update"
updated: 2026-05-19T12:24:07Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/azure-blob-storage-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Azure Blob Storage (Hyperdrive)

Microsoft Azure Blob Storage (Binary Large Objects) is a cloud storage format that stores and categorizes unstructured data (such as images and audio clips) on Azure servers. Data items contained within Blobs are encrypted automatically with AES 256-bit level protection. Additionally, the spread (and concurrency) of Azure servers worldwide mitigates potential issues associated with storing data at fixed physical locations.

You can integrate your Azure Blob Storage with Securiti and scan data for your data system. Azure Blob Storage is a [monitored, unstructured data system](/v1/docs/managing-data-system-connectors).

## Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Blob Storage (Self-hosted) | It supports: - Sensitive Data Intelligence - Discovery Scan - Data Inventory Sync |

## Supported pod type

- Securiti Outpost deployment

## Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Storage Account | Account Key |
| - Service Principal - Service Principal with Certificate | - Client Id - Tenant Id - Secret Key (For Service Principal only) - Service Principal Certificate (For Service Principal with Certificate only) - Service Principal Private Key (For Service Principal with Certificate only) |

### Keyring support

Keyring support is not available for data systems using Hyperdrive.

## Supported items for Inventory and Classification Scans

Data Inventory Sync builds an inventory of data resources and entitlements in your system without performing full content classification scans. Classification scans identify and classify sensitive data based on configured scan profiles and settings. For more information, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors) and [Understanding Discovery Scans](/v1/docs/discovery-scans).

Securiti supports the following items for Inventory and Classifican scans:

- Azure Containers
- Blobs in containers

### Scanning methods for Azure Blob Storage

Securiti offers two primary methods for performing scans:

- Listing
- Native Inventory

Each method uses a different approach to discover your data assets. The table below explains the difference between the two available scan methods.

| Method | Explanation |
| --- | --- |
| Listing | This is the standard method that directly queries the cloud storage service to build an inventory of Blob storage containers in real-time. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | This method leverages the inventory reports generated directly by Azure Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) and configure the inventory reporting feature within your cloud provider's console. You must do the following to use the *Native Inventory* method: - Enable [blob inventory in your Azure account](/v1/docs/enable-blob-inventory-in-your-azure-account) - Enable **Use Native Inventory** toggle while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) For discovery scans, *Native Inventory* method is enabled if you configure your discovery scan without the prefix scan condition, along with fulfilling the above mentioned prerequisites. > [!NOTE] > **Note** > > Securiti doesn’t list the Blob containers if the inventory report generated in your Microsoft Azure account is older than 30 days. By default, the latest inventory report is used for listing blobs in containers. |

## Prerequisites

### Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).

#### Azure Storage account

You must have an Azure Storage account in order to facilitate the connector activation process between your Azure Blob Containers and the Securiti app.

For more information, see [Using Storage Account authentication](/v1/docs/using-storage-account-authentication).

#### Configure the inventory rule for Data inventory sync

If you want to run data inventory sync using the *Native Inventory* method, you must configure your first inventory rule in your Microsoft Azure account. Securiti uses these blob inventory reports to pull inventory information.

For more information, see [Enable blob inventory in your Azure account](/v1/docs/enable-blob-inventory-in-your-azure-account).

#### Use cases and permissions for Azure Blob Storage

To provide the Azure Blob Storage access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Inventory Sync (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) | N/A | **For Service Principal authentication** - Azure Blob Data Reader role. - Monitoring Reader role | - These permissions let Securiti discover and scan blobs and containers for inventory and classification purposes and to build the Personal Data Index for DSR Automation. - `Monitoring Reader` role is required only for resource size calculation of the Azure Blob storage account. |

### Connect the Azure Blob Storage connector with Securiti

See the sections below to connect your data system connector with Securiti.

1. Configure the Outpost as described in [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment).
2. [Enable blob inventory in your Azure account (Hyperdrive)](/latest/docs/enable-blob-inventory-in-your-azure-account-1) if you want to use the *Native Inventory* method.
3. [Using Storage Account authentication (Hyperdrive)](/latest/docs/using-storage-account-authentication-1) or [Using Service Principal authentication](/latest/docs/using-service-principal-authentication-1).
4. [(New UI) Connecting Azure Blob Storage (Self Hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-azure-blob-storage-self-hosted-with-securiti-1)
5. [Configuring discovery scans in Azure Blob Storage (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-azure-blob-storage-1) or [Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted) (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted-1)
