---
title: "Azure Synapse"
slug: "azure-synapse-connectors"
status: "new"
updated: 2026-07-16T05:41:02Z
published: 2026-07-16T05:41:02Z
canonical: "helpcenter.securiti.ai/azure-synapse-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Synapse

Azure Synapse Analytics is a Microsoft analytics service that brings together data integration, enterprise data warehousing, and big data analytics. In Securiti, the Azure Synapse connector lets you discover and classify sensitive data stored in Azure Synapse databases. Azure Synapse is a [monitored, structured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Synapse (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types

- Standard Securiti pod
- Elastic pod (EDSS)

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Basic authentication | - Host - Port - Database - User - Password |

### Supported items for classification scans

Securiti scans the following items for Azure Synapse databases. For more information, see [Configuring discovery scans for Azure Synapse](/latest/docs/configure-discovery-scans-in-azure-synapse).

- Tables
- Views
- Schemas

### Prerequisites for configuring the Azure Synapse connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect Azure Synapse with a self-hosted connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors) and [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

> [!NOTE]
> **Note**
> 
> To perform table training on the Azure Synapse data system instance, you must establish connectivity by enabling firewalls and NSG (Network Security Groups) to allow access on ports **1433** and **11000–11999**.

#### 2. Database permissions

You must grant the connector user the required `SELECT`database permission before authenticating. For more information, see [Granting DB permissions for Azure Synapse](/v1/docs/granting-db-permissions-for-azure-synapse).

### Use cases and permissions for Azure Synapse

To provide Azure Synapse access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence - DSR Automation | Only available for self-hosted connector. | Grant `SELECT` on tables and schemas for your user account. | These permissions let Securiti discover and scan tables for inventory and classification purposes and to build the Personal Data Index for DSR Automation. `SELECT` permission can be applied to individual columns within a table. |

### Connect Azure Synapse with Securiti

To connect Azure Synapse with Securiti, perform the following procedures in sequence:

1. If you have not yet done so, deploy and configure a Securiti pod. For more information, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
2. Grant the required database permissions. For more information, see [Granting DB permissions for Azure Synapse](/v1/docs/granting-db-permissions-for-azure-synapse).
3. Acquire authentication credentials. For more information, see [Acquire authentication credentials in Azure Synapse](/latest/docs/acquire-authentication-credentials-in-azure-synapse).
4. Connect the Azure Synapse connector with Securiti. For more information, see [Connecting Azure Synapse with Securiti](/latest/docs/connecting-azure-synapse-with-securiti).
5. Initiate learning and configure scan settings. For more information, see [Initiate Azure Synapse learning](/latest/docs/initiate-azure-synapse-learning).

### Additional resources

- For information on table training for the Azure Synapse data system, see [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- For information on fulfilling DSR requests for Azure Synapse, see [Fulfilling DSR requests for Azure Synapse](/latest/docs/fulfilling-dsr-requests-for-azure-synapse).

## Related

- [Acquire authentication credentials in Azure Synapse](/acquire-authentication-credentials-in-azure-synapse.md)
- [Granting DB permissions for Azure Synapse](/granting-db-permissions-for-azure-synapse.md)
- [Connecting Azure Synapse with Securiti](/activate-the-azure-synapse-connector-in-securiti.md)
- [Configure discovery scans in Azure Synapse](/configure-discovery-scans-in-azure-synapse.md)
- [Fulfilling DSR requests for Azure Synapse](/fulfilling-dsr-requests-for-azure-synapse.md)
