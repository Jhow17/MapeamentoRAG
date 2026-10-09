---
title: "Starburst"
slug: "starburst-connectors"
status: "update"
updated: 2026-09-11T11:47:45Z
published: 2026-09-11T11:50:27Z
canonical: "helpcenter.securiti.ai/starburst-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Starburst

Starburst is a data access platform that enables unified querying across distributed data sources. By connecting Starburst with Securiti, organizations can discover and classify sensitive data through Discovery Scan and efficiently locate personal data for Data Subject Requests, improving data visibility, governance, and privacy compliance.

Starburst falls under the category of [Monitored, Structured data systems.](/latest/docs/managing-data-system-connectors)

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Starburst (Self-hosted) | - DSR automation using SQL queries - Sensitive Data Intelligence - Access Intelligence scan |

### Supported pod types

Starburst supports standard Securiti pod.

### Supported authentication methods

Securiti supports basic authentication method for Starburst

### Supported items for Inventory and Classification scans

Securiti supports discovery scans for the items mentioned below. For more information, see [Configuring discovery scans in Starburst](/latest/docs/configuring-discovery-scans-in-starburst).

- Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring Starburst in Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Starburst with a Self-hosted connector. For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Starburst instance access

Make sure you have access to a running Starburst Instance, or you have access to the Instance's admin to acquire the required information before activating the connector.

#### 3. Catalogue and Cluster creation in Starburst app

In the Starburst app, create a catalogue and Cluster to connect with access your database. For more information [Registering an app in Starburst Enterprise](/latest/docs/registering-an-app-in-starburst-enterprise).

#### 4. Use cases and permissions

You must complete these prerequisites before connecting your Starburst connector with Securiti

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | N/A | Grant All Privilege access to the user. | These permissions let Securiti to discover and scan network shares for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect Starburst with Securiti

To connect your Starburst connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Registering an app in Starburst Enterprise](/latest/docs/registering-an-app-in-starburst-enterprise).
3. [Grant permissions and obtain credentials in Starburst](/latest/docs/grant-permissions-and-obtain-credentials-in-starburst).
4. [Connecting Starburst with Securiti](/latest/docs/connecting-starburst-with-securiti).
5. [Configuring discovery scans in Starburst](/latest/docs/configuring-discovery-scans-in-starburst).

**Additional resources**

- [Fulfilling Starburst DSR requests](/latest/docs/fulfilling-starburst-dsr-requests).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
