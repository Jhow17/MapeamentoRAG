---
title: "S3 Compatible Storage"
slug: "s3-compatible-storage-connectors"
status: "update"
updated: 2026-06-22T14:42:43Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/s3-compatible-storage-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# S3 Compatible Storage

The S3 Compatible Storage connector enables integration with open-source and S3-compatible storage platforms, providing flexibility beyond native AWS S3. Currently, the connector supports those S3 Compatible Storages that have S3-compatible APIs, such as MinIO, StorageGRID, IBM Cloud Object Storage, etc. S3 Compatible Storage falls under the [Monitored, structured data systems.](https://portal.us.document360.io/v1/docs/configuring-connectors-for-monitored-data-systems)

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| S3 Compatible Storage (Self-hosted) | Sensitive Data Intelligence |

### Supported pod types for self-hosted connector

S3 Compatible Storage supports standard Securiti pod for self-hosted connector.

### Supported authentication methods

Securiti supports IAM Keys authentication method for S3 Compatible Storage connector.

#### Keyring support for S3 Compatible Storage

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **AWS Secret Manager**: For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CyberArk**: For more information, see [CyberArk credential vault](/latest/docs/cyberark-credential-vault).

### Supported items for classification scans

- S3 Objects in Buckets.

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring S3 Compatible Storage in Securiti

#### 1. Pod deployment for self-hosted connector

You must deploy a Securiti pod in your environment to connect your S3 Compatible Storage with a Self-hosted connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and S3 Compatible Storage API endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Required privileges in S3 Compatible Storage

> [!NOTE]
> Note
> 
> Securiti supports open-source S3 Object Storages that have S3-compatible APIs. For example, we provide you with the steps to obtain credentials in MinIO.

You must have access to a MinIO account with the privileges to create a user and assign permissions

For more information, see [Obtain authentication credentials from MinIO](/latest/docs/obtain-authentication-credentials-from-minio-s3-compatible-storage-en).

#### 3. Permissions and use cases for S3 Compatible Storage connector

This section covers use cases and permissions for S3 Compatible Storage connector.

> [!WARNING]
> Important
> 
> Ensure proper permissions are granted to avoid misleading scan results and skipping objects during the scanning process.
> 
> - If permission is not provided, the pod displays an error while listing objects. Despite the error, upon completion, the scan job on the UI turns green, potentially misleading the end customer into believing the scan was successful.
> - Additionally, when initiating a new scan and the connector has permission to list objects, it skips all objects with the message "Ignoring item, as it isn't falling under the scan time boundary."

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | N/A | - `s3:ListBucket` - `s3:GetObject` - `s3:GetObjectTagging` | These permissions let Securiti read the files and file metadata in S3 Compatible Storage for classification purposes. |

### Connect S3 Compatible Storage connector with Securiti

To configure the S3 Compatible Storage connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in the [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain authentication credentials from MinIO.](/latest/docs/obtain-authentication-credentials-from-minio-s3-compatible-storage-en)
3. [Connecting S3 Compatible Storage with Securiti](/latest/docs/connecting-s3-compatible-storage-with-securiti).
4. [Configure discovery scans for S3 Compatible Storage](/latest/docs/configure-discovery-scans-in-s3-compatible-storage-en).
