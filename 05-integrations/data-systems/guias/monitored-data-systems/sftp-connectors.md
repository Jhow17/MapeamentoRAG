---
title: "SFTP"
slug: "sftp-connectors"
status: "new"
updated: 2026-07-16T07:39:35Z
published: 2026-07-16T07:39:39Z
canonical: "helpcenter.securiti.ai/sftp-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# SFTP

SFTP (SSH File Transfer Protocol) is a secure file transfer protocol used to transfer and manage files over encrypted SSH connections. By connecting SFTP with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence (SDI), efficiently locate personal data for Data Subject Requests (DSR), and assess the impact of security incidents with Breach Impact Analysis, helping strengthen data governance and privacy compliance.

SFTP falls under the category of [Monitored, Unstructured data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| SFTP (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation using Full Scan - Breach Analysis |

### Supported pod types

SFTP supports Securiti standard Pod.

### Supported authentication method

Securiti supports following authentication methods for SFTP:

- Key Based
- Password Based

### Supported items for Classification scans

Securiti supports following items for classification purposes.

- All instances in a data system

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring SFTP connector

#### 1. SFTP instance

You must install SFTP (SSH File Transfer Protocol) to activate the connector and obtain authentication credentials. For more information, see [Acquire authentication credentials in SFTP](/latest/docs/acquire-authentication-credentials-in-sftp).

### Connect SFTP with Securiti

To configure the SFTP connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
3. [Acquire authentication credentials in SFTP](/latest/docs/acquire-authentication-credentials-in-sftp).
4. [Connecting SFTP with Securiti](/latest/docs/connecting-sftp-with-securiti).
5. [Configuring discovery scans in SFTP](/latest/docs/configuring-discovery-scans-in-sftp).

**Additional resources**

- [Fulfilling DSR requests for SFTP](/latest/docs/fulfilling-dsr-requests-for-sftp).
