---
title: "Loggly"
slug: "loggly-connectors"
status: "new"
updated: 2026-07-20T20:05:55Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/loggly-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Loggly

Loggly is a cloud-based log management and analytics platform designed to centralize log data from across an organization's entire infrastructure into a single, searchable location. Built as a pure SaaS solution with no proprietary agents or additional hardware required, it supports log collection from applications, servers, cloud environments, containers, and IoT devices. It enables technical and operations teams to troubleshoot issues, monitor deployments, and analyze application behavior at scale.

The Loggly connector lets you integrate with Securiti to discover and govern log and event data aggregated across your infrastructure and application stack.

Loggly falls under the category of Monitored, Scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Loggly (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- For Securiti Cloud connector:
  - Loggly application-based authentication
    - API Key for authentication

### Prerequisites for configuring Loggly connector

#### 1. Admin access

You must have admin access in Loggly to obtain access token and domain to authenticate your connector.

For more information, see [Acquire authentication credentials in Loggly](/latest/docs/acquire-authentication-credentials-in-loggly).

#### 2. Use cases and permissions for Loggly

This table covers use cases and permissions required for Loggly (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to create **API Keys** in Loggly API Tokens page. - Access to obtain **access token** and **domain URL.** | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Loggly (Securiti Cloud) connector with Securiti

To configure the Loggly connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Loggly](/latest/docs/acquire-authentication-credentials-in-loggly).
2. [Connect Loggly connector with Securiti](/latest/docs/connect-loggly-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR Requests for Loggly](/latest/docs/fulfilling-dsr-requests-for-loggly).

Data systems which do not undergo scanning of data as Securiti can query them in real-time as DSR requests come in and respond to queries on specific elements of personal data.

An API key is a unique identifier used to connect to, or perform, an API call.
