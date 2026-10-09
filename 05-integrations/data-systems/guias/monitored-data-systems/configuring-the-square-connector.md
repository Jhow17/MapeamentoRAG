---
title: "Square"
slug: "configuring-the-square-connector"
status: "new"
updated: 2026-07-20T08:32:21Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-the-square-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Square

Square is a financial services platform specializing in mobile payments, point-of-sale solutions, and merchant aggregation. Beyond payment processing, it has expanded to offer a broader suite of commerce tools including inventory management, invoicing, and custom interface development. This makes it a widely adopted platform for small to mid-sized businesses managing in-person and online transactions.

The Square connector lets you integrate your Square environment with Securiti to discover and govern financial and commerce data stored across your Square account, including payment records, merchant profiles, and transaction histories.

Square (Securiti Cloud) falls under the category of monitored, Scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Square (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- For Securiti Cloud connector:
  - Square application-based authentication
    - OAuth-based authentication for APIs

### Prerequisites for configuring Square connector

#### 1. Admin access

You must have admin access in Square to obtain Client ID and Client Secret to authenticate your connector.

For more information, see [Register an application in Square](/latest/docs/register-an-application-in-square).

#### 2. Use cases and permissions for Square

This table covers use cases and permissions required for Square (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to **create** a new application in **Square Developer Portal**. - Access to **obtain** the following: - **Application ID** - **Application Secret** | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Square (Securiti Cloud) connector with Securiti

To configure the Square connector, perform the procedures in the following topics:

1. [Register an application in Square](/latest/docs/register-an-application-in-square).
2. [Connect Square connector with Securiti](/latest/docs/connect-square-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Square](/v1/docs/fulfilling-dsr-requests-for-square).

Data systems which do not undergo scanning of data as Securiti can query them in real-time as DSR requests come in and respond to queries on specific elements of personal data.
