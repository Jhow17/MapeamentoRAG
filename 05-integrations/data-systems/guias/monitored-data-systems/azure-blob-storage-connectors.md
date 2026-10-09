---
title: "Azure Blob Storage"
slug: "azure-blob-storage-connectors"
status: "update"
updated: 2026-07-30T08:01:31Z
published: 2026-07-30T08:01:31Z
canonical: "helpcenter.securiti.ai/azure-blob-storage-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Blob Storage

Microsoft Azure Blob Storage (Binary Large Objects) is a cloud storage format that stores and categorizes unstructured data (such as images and audio clips) on Azure servers. Data items contained within Blobs are encrypted automatically with AES 256-bit level protection. Additionally, the spread (and concurrency) of Azure servers worldwide mitigates potential issues associated with storing data at fixed physical locations.

You can integrate your Azure Blob Storage with Securiti and scan data for your data system. Azure Blob Storage is a [monitored, unstructured data system](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Blob Storage (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation - Data Breach Management |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Storage Account | Account Key |
| - Service Principal - Service Principal with Certificate | - Client Id - Tenant Id - Secret Key (For Service Principal only) - Service Principal Certificate (For Service Principal with Certificate only) - Service Principal Private Key (For Service Principal with Certificate only) |

#### Keyring support for Azure blob Storage (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/creating-keyrings).

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **AWS Secrets Manager**: For more information, see [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**: For more information, ee [Configuring Credstash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault).

### Supported items for Inventory and Classification Scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- Azure Containers
- Blobs in containers

#### Scanning methods for Azure Blob Storage

Securiti offers two primary methods for performing scans:

- Listing
- Native Inventory

Each method uses a different approach to discover your data assets. The table below explains the difference between the two available scan methods.

| Method | Explanation |
| --- | --- |
| Listing | This is the standard method that directly queries the cloud storage service to build an inventory of Blob storage containers in real-time. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | This method leverages the inventory reports generated directly by Azure Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) and configure the inventory reporting feature within your cloud provider's console. You must do the following to use the *Native Inventory* method: - Enable [blob inventory in your Azure account](/v1/docs/enable-blob-inventory-in-your-azure-account) - Enable **Use Native Inventory** toggle while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) For discovery scans, *Native Inventory* method is enabled if you configure your discovery scan without the prefix scan condition, along with fulfilling the above mentioned prerequisites. > [!NOTE] > **Note** > > Securiti doesn’t list the Blob containers if the inventory report generated in your Microsoft Azure account is older than 30 days. By default, the latest inventory report is used for listing blobs in containers. |

### Prerequisites for configuring the Azure Blob Storage connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Azure Blob Storage with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Azure Storage account

You must have an Azure Storage account in order to facilitate the connector activation process between your Azure Blob Containers and the Securiti app.

For more information, see [Using Storage Account authentication](/v1/docs/using-storage-account-authentication) .

#### 3. Configure the inventory rule for Data inventory sync

If you want to run data inventory sync using the *Native Inventory* method, you must configure your first inventory rule in your Microsoft Azure account. Securiti uses these blob inventory reports to pull inventory information.

For more information, see [Enable blob inventory in your Azure account](/v1/docs/enable-blob-inventory-in-your-azure-account).

#### 4. Use cases and permissions for Azure Blob Storage

To provide the Azure Blob Storage access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Data Inventory Sync (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | **For Service Principal authentication** - Azure Blob Data Reader role. - Monitoring Reader role | - These permissions let Securiti discover and scan blobs and containers for inventory and classification purposes and to build the Personal Data Index for DSR Automation. - `Monitoring Reader` role is required only for resource size calculation of the Azure Blob storage account. |
| Data Labeling Policy | Assign the following roles: **For Service Principal with and without certificate authentication** - Storage Blob Data Contributor - Storage Blob Data Reader | These permissions let Securiti view, manage, and apply labels to Azure Blob Storage containers. With these permissions, you can apply the Data Labelling Policy to your files. |
| Quarantine policy | Assign the following roles: **For Service Principal with and without certificate authentication** - Storage Blob Data Contributor - Storage Blob Data Reader | These permissions let Securiti enable Quarantine Policies to move data between locations in your Azure Blob containers. |

### Connect the Azure Blob Storage connector with Securiti

See the sections below to connect your data system connector with Securiti.

#### Steps to connect the Azure Blob Storage (Self-hosted) connector with Securiti

To configure the Azure Blob Storage connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).
3. [Enable blob inventory in your Azure account](/latest/docs/enable-blob-inventory-in-your-azure-account) if you want to run data inventory sync using the *Native Inventory* method.
4. [Using Storage Account authentication](/v1/docs/using-storage-account-authentication) or [Using Service Principal authentication](/v1/docs/using-service-principal-authentication).
5. [Connecting Azure Blob Storage (Self-hosted) with Securiti](/latest/docs/connecting-azure-blob-storage-self-hosted-with-securiti).
6. [Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted).
7. [Configuring discovery scans in Azure Blob Storage](/latest/docs/configuring-discovery-scans-in-azure-blob-storage) .

**Additional resources**

- [Fulfilling DSR requests for Azure Blob Storage](/latest/docs/fulfilling-dsr-requests-for-azure-blob-storage)

## Related

- [Using Storage Account authentication](/using-storage-account-authentication.md)
- [Enable blob inventory in your Azure account](/enable-blob-inventory-in-your-azure-account.md)
- [Using Service Principal to authenticate Azure Blob Storage](/using-service-principal-authentication.md)
- [Configuring discovery scans in Azure Blob Storage](/configuring-discovery-scans-in-azure-blob-storage.md)
- [Fulfilling DSR requests for Azure Blob Storage](/fulfilling-dsr-requests-for-azure-blob-storage.md)
