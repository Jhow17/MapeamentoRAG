---
title: "Files.com"
slug: "filescom-connectors"
status: "new"
updated: 2026-07-30T06:19:18Z
published: 2026-07-30T06:19:26Z
canonical: "helpcenter.securiti.ai/filescom-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Files.com

Files.com is a cloud-native file orchestration and managed file transfer (MFT) platform that enables organizations to securely transfer, store, automate, and integrate files across systems, users, and partners. It is designed as a modern replacement for legacy FTP servers and on-premise MFT solutions. It consolidates every file flow into a single platform with centralized access controls, audit logging, and compliance support, presenting connected cloud storage from AWS, Azure, Google Cloud, and others as one governed namespace.

The Files.com connector lets you integrate your Files.com environment with Securiti to discover and govern unstructured file and transfer data stored and orchestrated across your Files.com platform.

Files.com falls under the category of monitored, unstructured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Files.com (Securiti Cloud) | - Sensitive Data Intelligence (Standard Data Scan) - Security Posture Scan - Breach Analysis |

### Supported authentication methods

- For Securiti Cloud connector:
  - Files.com application-based authentication
    - API authentication using API Key

### Supported items for classification scans

Securiti scans the standard data items for Files.com connectors.

- Files.com Databases
- Files
- Apps

### Prerequisites for configuring Files.com connector

#### 1. Admin access

You must have admin access in Files.com to create and obtain API Key to authenticate your connector.

For more information, see [Acquire the API key in Files.com](/latest/docs/acquire-the-api-key-in-filescom).

#### 2. Use cases and permissions for Files.com

This table covers use cases and permissions required for Files.com (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | N/A | - Access to create **API Key** in Files.com. - Access to read **available API Keys**. | These permissions let Securiti to read files and schema metadata in Files.com for data scan purposes. |
| Security Posture Management Rule Evaluation | This capability lets Securiti to evaluate posture findings in Files.com. | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

### Steps to connect Files.com (Securiti Cloud) connector with Securiti

To configure the Files.com connector, perform the procedures in the following topics:

1. [Acquire the API key in Files.com](/latest/docs/acquire-the-api-key-in-filescom).
2. [Connect Files.com connector with Securiti](/latest/docs/connect-filescom-connector-with-securiti).
3. [Configuring general scan settings for Files.com](/latest/docs/configuring-general-scan-settings-for-files-com).

Breach Impact Analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this functionality by enabling this feature while setting up the necessary discovery scan jobs for monitored data systems, ensuring comprehensive and proactive breach analysis. See Using Data Breach Management, for more information.

An API key is a unique identifier used to connect to, or perform, an API call.
