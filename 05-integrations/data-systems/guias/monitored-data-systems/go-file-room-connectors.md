---
title: "Go File Room"
slug: "go-file-room-connectors"
status: "new"
updated: 2026-07-07T07:00:53Z
published: 2026-07-07T07:01:21Z
canonical: "helpcenter.securiti.ai/go-file-room-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Go File Room

Go File Room is a cloud-based document management and workflow platform for accounting and tax professionals. By connecting Go File Room with Securiti, organizations can discover and classify sensitive data through Discovery Scan (SDI) and efficiently locate personal data for Data Subject Requests (DSR), helping improve data visibility and support privacy compliance.

Go File Room falls under the category of [monitored, unstructured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Go File Room(Self-hosted) | - Sensitive Data Intelligence - DSR Automation using full scan - Breach Analysis |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

Securiti supports OAuth authentication method for Go File Room connector.

### Supported items for Classification scans

Securiti scans the following entities for Go File Room during discovery scans.

- All the containers.
- All the drawers in the containers.

For more information on configuring discovery scans, see [Configure discovery scans in Go File Room](/latest/docs/configure-discovery-scans-in-go-file-room)

### Prerequisites for configuring Go File Room connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Go File Room with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-deployment).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access in Go File Room service account

You must have admin access to grant required permissions to the service account in the Go File Room.

#### 3. Use cases and permissions for Go File Room

This section covers use cases and permissions required for Go File Room self-hosted connector.

#### Permissions for custom admin role

Use the table below for permissions and use cases if you are using a custom role.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | Assign **Read** permissions to the service account in Go File Room. | These permissions let Securiti read the files and metadata in Go File Room for classification purposes. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |

### Connect Go File Room connectors with Securiti

This section covers the methods to integrate your Go File Room with Securiti using Self-hosted connector.

#### Steps to connect the Go File Room (Self-hosted) connector with Securiti

To configure the Go File Room (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Acquire authentication credentials in Go File Room](/latest/docs/acquire-authentication-credentials-in-go-file-room)
3. [Connecting Go File Room with Securiti](/latest/docs/connecting-go-file-room-with-securiti).
4. [Configure discovery scans in Go File Room](/latest/docs/configure-discovery-scans-in-go-file-room).

**Additional resources**

- [Fulfilling DSR requests in Go File Room](/latest/docs/fulfilling-dsr-requests-in-go-file-room).
