---
title: "IBM Db2 and zOS"
slug: "ibm-db2-and-zos-connectors"
status: "new"
updated: 2026-06-23T09:46:48Z
published: 2026-06-23T09:50:17Z
canonical: "helpcenter.securiti.ai/ibm-db2-and-zos-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# IBM Db2 and zOS

IBM Db2 is a relational database management system designed for transaction processing, data warehousing, and analytics. IBM Db2 zOS is a version of Db2 optimized for mainframe environments. It is used for high-performance transaction processing and is a key component in mainframe systems. Securiti scans the structured data such as tables, columns, indexes, and rows within the Db2 systems by integrating with these connectors. IBM Db2 and IBM Db2 zOS fall under the category of [monitored, structured data systems](/v1/docs/managing-data-system-connectors).

> [!NOTE]
> **Note**
> 
> DB2 on zOS uses a slightly different SQL syntax, which required the creation of a separate connector. Other than that, the activation parameters remain identical to those of the standard DB2 connector.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| IBM Db2 (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |
| IBM Db2 zOS (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types for self-hosted connector

Standard Securiti pod.

### Supported authentication methods

- Basic authentication (username and password)

#### Keyring support for IBM Db2 and IBM Db2 zOS

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **Azure Key Vault**: For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).

> [!NOTE]
> **Important**
> 
> Azure Key Vault is not supported for IBM Db2 zOS connector.
- **CredStash**: For more information, see [Configuring Credstash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault).
- **CyberArk**: For more information, see [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault).
- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Prerequisites for configuring IBM Db2 connectors

#### Pod deployment

You must deploy a Securiti pod in your environment to connect your IBM Db2 with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### Administrative user privileges

A user with administrative privileges must be created to connect to the database. Avoid changing the username after creating a user.

#### `SELECT` access to system catalog schemas

You must grant `SELECT` access to specific system catalog schemas in your IBM Db2 environments. This access is required for authentication, metadata scanning, row count estimation, and optional SQL lineage and DDL extraction features.

- For **IBM Db2**, grant `SELECT` access to the `SYSCAT` views
- For **IBM Db2 zOS**, grant `SELECT` access to the `SYSIBM` schema.

For more information, see [Prerequisites for IBM Db2](/latest/docs/prerequisites-for-ibm-db2) and [Prerequisites for IBM Db2 zOS](/latest/docs/prerequisites-for-ibm-db2-zos).

#### Use cases and permissions for IBM Db2 and IBM Db2 zOS

To provide the IBM Db2 and IBM Db2 zOS connectors access for data discovery and classification, use the following use cases and permissions.

For more information, see the following topics:

- Prerequisites for IBM Db2
- Prerequisites for IBM Db2 zOS

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | - SDI Discovery Scans and DSR Automation Indexing is only available on the self-hosted connector. - If you have implemented `ASUTIME` for your IBM Db2 zOS instance, we recommend you configure the parameter value between 9000 and 12000 to continue processing DSRs. Anything below 9000 would result in a DSR runtime error. For more information, see [ASUTIME parameter best practices](https://www.ibm.com/support/pages/db2-zos-stored-procedure-asutime-parameter-best-practices). | **IBM Db2 zOS:** - `SELECT` privileges on the `SYSIBM` schema (granted to `ro_securiti` role). **IBM Db2:** - `SELECT` privileges on key `SYSCAT` views. | These permissions let Securiti scan database metadata, estimate row counts, and extract SQL lineage information without directly modifying any system data. |

### Connect IBM Db2 and IBM Db2 zOS connectors with Securiti

This section covers the methods to integrate your IBM Db2 and IBM Db2 zOS with Securiti using self-hosted connectors.

#### Steps to connect IBM Db2 (Self-hosted) connector with Securiti

To configure the IBM Db2 (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Prerequisites for IBM Db2](/latest/docs/prerequisites-for-ibm-db2)
3. [Connecting IBM Db2 with Securiti](/latest/docs/connecting-ibm-db2-with-securiti).
4. [Configure discovery scans in IBM Db2](/latest/docs/configure-discovery-scans-in-ibm-db2)
5. [Fulfilling DSR requests for IBM Db2 and IBM Db2 zOS](/latest/docs/fulfilling-dsr-requests-for-ibm-db2-and-ibm-db2-zos).

#### Steps to connect IBM Db2 zOS (Self-hosted) connector with Securiti

To configure the IBM Db2 zOS (Self-hosted) connector, perform the following steps:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Prerequisites for IBM Db2 zOS](/latest/docs/prerequisites-for-ibm-db2-zos).
3. [Connecting IBM Db2 zOS with Securiti](/latest/docs/connecting-ibm-db2-zos-with-securiti).
4. [Configure discovery scans in IBM Db2 zOS](/latest/docs/configure-discovery-scans-in-ibm-db2-zos).
5. [Fulfilling DSR requests for IBM Db2 and IBM Db2 zOS](/latest/docs/fulfilling-dsr-requests-for-ibm-db2-and-ibm-db2-zos).
