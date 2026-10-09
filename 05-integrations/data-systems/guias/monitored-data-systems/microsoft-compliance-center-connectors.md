---
title: "Microsoft Compliance Center"
slug: "microsoft-compliance-center-connectors"
status: "new"
updated: 2026-07-20T16:18:02Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/microsoft-compliance-center-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Compliance Center

Microsoft Compliance Center is the unified platform for managing data governance, regulatory compliance, and risk mitigation across Microsoft 365 tenants. It provides pre-built assessments for common industry and regional standards, workflow capabilities for completing risk assessments, and a compliance score that helps organizations prioritize the actions most critical to their regulatory posture.

The Microsoft Compliance Center connects with Securiti to extend visibility into the compliance and classification signals already present in your Microsoft 365 tenant. It lets you to align your data governance posture across platforms from a single control plane.

Microsoft Compliance Center falls under the category of scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector type and module

| Connector type | Modules supported |
| --- | --- |
| Microsoft Compliance Center (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication method

Microsoft Compliance Center (Securiti Cloud) requires the following:

- Microsoft Azure application based authentication
- OAuth based authentication

### Prerequisites for configuring Microsoft Compliance Center connector

#### 1. Admin access in Microsoft Entra ID

You must be an administrator to grant permissions to the applications created in the Microsoft Entra ID.

For more information, see [Acquire authentication credentials in Microsoft Compliance Center connector](/latest/docs/acquire-authentication-credentials-in-microsoft-compliance-center-connector).

#### 2. Use cases and permissions for Microsoft Compliance Center

This section covers use cases and permissions required for Microsoft Compliance Center connectors.

> [!NOTE]
> **Note**
> 
> When you authenticate using OAuth based authentication, an Microsoft 365 administrator must provide consent to the permissions you have configured for the Azure application.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | Access to **Directory ID** or **Organization ID** in Microsoft | These permissions let Securiti read the files and retrieve metadata in MCC for reporting and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

#### Steps to connect Microsoft Compliance Center Securiti-Cloud connector with Securiti

To configure the Microsoft Compliance Center Securiti-Cloud connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Microsoft Compliance Center connector](/latest/docs/acquire-authentication-credentials-in-microsoft-compliance-center-connector).
2. [Connecting Microsoft Compliance Center connector in](/latest/docs/connecting-microsoft-compliance-center-with-securiti) Securiti.
3. [Steps for generating a report in Microsoft Compliance Center](/latest/docs/steps-for-generating-a-report-in-microsoft-compliance-center).

#### Additional resources

- [Fulfilling DSR requests for Microsoft Compliance Center](/v1/docs/fulfilling-dsr-requests-for-microsoft-compliance-center).

Scanning the data to find primary data elements such as email, SSN, passport number, etc using the APIs. With this feature DSR Robotic Automation,Securiti does not store or build an index of primary data elements on the appliance. Refer to DSR Automation in data system connectors for more information.
