---
title: "HDFS"
slug: "hdfs-connectors-1"
status: "new"
updated: 2026-07-16T06:20:30Z
published: 2026-07-16T06:20:34Z
canonical: "helpcenter.securiti.ai/hdfs-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# HDFS

HDFS (Hadoop Distributed File System) is a distributed storage system designed to store and manage large volumes of data across clustered environments. By connecting HDFS with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence (SDI), maintain an up-to-date Data Inventory, and efficiently locate personal data for Data Subject Requests (DSR), helping improve data governance and privacy compliance.

HDFS data system falls under the [Monitored, Unstructured data systems](/latest/docs/getting-started-with-data-system-connectors) category.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| HDFS (Self-hosted) | - DSR Automation - Sensitive Data Intelligence (Discovery Scan) - Data Inventory Sync - Data Access Control (Permissions Management Policies) - Breach Analysis |

### Supported Pod types

Securiti supports standard pod for HDFS. For more information, see [Configuring Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

### Supported authentication method

Securiti supports following authentication methods for HDFS:

- Keytab
- Password

#### Keyring support for self-hosted connector

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **AWS Secrets Manager**: For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash:** For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault).

### Prerequisites for configuring HDFS connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your HDFS with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access in HDFS

You must have admin access in HDFS to activate the connector.

#### 3. Running Kerberos instance in case of Kerberos authentication

If you are using Kerberos authentication method, then you must have active Kerberos instance running to obtain authentication credentials.

### Connect HDFS connectors with Securiti

This section covers the methods to integrate your HDFS with Securiti.

#### Steps to connect the HDFS connector with Securiti

To configure the HDFS (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain permissions and authentication credentials in HDFS](/latest/docs/obtain-permissions-and-authentication-credentials-in-hdfs).
3. [Connecting HDFS (Self-hosted) with Securiti](/latest/docs/connecting-hdfs-self-hosted-with-securiti).
4. [Configuring Data Inventory Sync for HDFS](/latest/docs/configuring-data-inventory-sync-for-hdfs).
5. [Configure discovery scans in HDFS](/latest/docs/configure-discovery-scans-in-hdfs)

**Additional resources**

- [Fulfilling DSR requests in HDFS](/latest/docs/fulfilling-dsr-requests-in-hdfs).
