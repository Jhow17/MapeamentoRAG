---
title: "Microsoft Access"
slug: "microsoft-access-connectors"
status: "update"
updated: 2026-07-20T17:26:12Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/microsoft-access-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Access

Microsoft Access, part of the Microsoft Office productivity suite, is a relational database management system (RDBMS) which utilizes tables as a means of storing data. Although Microsoft Access is similar to Microsoft SQL Server, another database hosting solution by Microsoft; it differs by the nature of its intended use case (for usage in personal databases and small-scale archives) compared to Microsoft SQL (which is used primarily by medium-large scale organizations). As part of its feature set, it offers the functions of generating complex reports and validating stored data on the basis of relative content integrity.

The Microsoft Access connector lets you integrate your Access databases with Securiti to discover and govern structured data stored in desktop and shared database files across your environment.

Microsoft Access falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Access (Self-hosted) | - Sensitive Data Intelligence (Standard data scan) - DSR Automation using SQL queries |

### Supported pod types

Standard Securiti Pod.

### Supported authentication methods

Microsoft Access (self-hosted) requires the file share path to authenticate with Securiti.

### Supported items for classification scans

Securiti supports scanning data items for Microsoft Access (self-hosted) connector.

### Prerequisites for configuring Microsoft Access Self-hosted connector

#### 1. Path access

You must have access to obtain the required file share path, so you can proceed with the Authentication.

- The file server host must be reachable.
- The file system must be mountable.
- Files must be accessible.

#### 2. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Access (Self-hosted) connector.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

### Connect Microsoft Access with Securiti

To configure the Microsoft Access (Self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. To use the Microsoft Access data system for DSR requests, you must link your structured on-premises database to Securiti.
3. [Connecting Microsoft Access with Securiti](/latest/docs/connect-microsoft-access-with-securiti).
4. [Configure data scans for Microsoft Access](/latest/docs/configure-microsoft-access-data-scanning).

#### Additional resources

- [Fulfilling Microsoft Access DSR requests](/latest/docs/fulfilling-dsr-requests-for-microsoft-access)
- [Table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
