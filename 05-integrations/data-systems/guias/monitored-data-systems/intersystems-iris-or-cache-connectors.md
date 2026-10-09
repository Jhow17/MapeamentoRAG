---
title: "InterSystems IRIS or Cache"
slug: "intersystems-iris-or-cache-connectors"
status: "update"
updated: 2026-09-11T08:57:03Z
published: 2026-09-11T08:57:43Z
canonical: "helpcenter.securiti.ai/intersystems-iris-or-cache-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# InterSystems IRIS or Cache

> [!WARNING]
> Important
> 
> Securiti recommends using the **InterSystems IRIS** (latest) connector for this data system to access new capabilities, ongoing improvements, and full platform support.
> 
> **Legacy connectors are in maintenance mode and do not receive new features or enhancements.** This includes, but is not limited to:
> 
> - API version upgrades
> - Additional Keyrings for this connector
> - New or enhanced scopes for Discovery Scan and Data Inventory Sync
> - Additional modules (for example, HyperDrive, Data Inventory Sync, and DSR)
> - Any future functionality introduced for this connector
> 
> Some of the enhancements listed above may not be available on this connector. Refer to the recommended connector’s documentation for currently supported modules and capabilities.

InterSystems IRIS and Cache are enterprise data management platforms used to build and manage high-performance data-driven applications. By connecting InterSystems IRIS and Cache with Securiti, organizations can discover and classify sensitive data through Data Scan (IRIS) or Discovery Scan (Cache), and efficiently locate personal data for Data Subject Requests (DSR), helping strengthen data governance and privacy compliance.

InterSystems IRIS and Cache fall under the category of [Monitored, Structured data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| InterSystems IRIS (Self-hosted) > [!NOTE] > Note > > Securiti recommends you to use this connector. | - DSR Automation using SQL queries - Sensitive Data Intelligence (Standard Data Scan) |
| InterSystems Cache (Legacy) (Self-hosted) | - DSR Automation using SQL queries - Discovery Scan |

### Supported pod types for self-hosted connector

InterSystems IRIS and InterSystems Cache support standard Securiti pod.

### Supported authentication methods

InterSystems IRIS and InterSystems Cache support basic authentication method.

### Supported Items for classification scans

InterSystems IRIS or Cache support following items for classification:

- Databases
- Schemas
- Tables
- Views

Additional resources

- For more information, see [Configuring discovery scans in InterSystems Cache](/latest/docs/configuring-discovery-scans-in-intersystems-cache), or [Configuring General scan settings for InterSystems IRIS](/latest/docs/initiate-intersystems-iris-data-scanning).
- For more information about classification in discovery scans, see [Discovery scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the InterSystems IRIS and Cache connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your InterSystems IRIS and Cache with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. InterSystems IRIS or Cache instance

Before proceeding with the connector authentication, you must have InterSystems IRIS or Cache instance.

## Connect InterSystems IRIS or Cache with Securiti

#### Steps to connect the InterSystems IRIS connector with Securiti

To configure the InterSystems IRIS connector served through pod:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in InterSystems IRIS](/latest/docs/acquire-authentication-credentials-in-intersystems-iris).
3. [Connecting InterSystems IRIS with Securiti](/latest/docs/connecting-intersystems-iris-with-securiti).
4. [Configuring general scan settings for InterSystems IRIS](/latest/docs/initiate-intersystems-iris-data-scanning).

#### Steps to connect the InterSystems Cache (Legacy) connector with Securiti

To activate the InterSystems Cache (Legacy) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in InterSystems Cache](/latest/docs/acquire-authentication-credentials-in-intersystems-cache).
3. [Connecting InterSystems Cache (Legacy) with Securiti](/latest/docs/connecting-intersystems-cache-legacy-with-securiti).
4. [Configuring discovery scans in InterSystems Cache](/latest/docs/configuring-discovery-scans-in-intersystems-cache).

**Additional resources**

- [Fulfilling DSR requests for InterSystems IRIS or Cache](/latest/docs/fulfilling-dsr-requests-for-intersystems-iris-or-cache).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
