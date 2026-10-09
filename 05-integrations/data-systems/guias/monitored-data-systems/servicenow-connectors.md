---
title: "ServiceNow"
slug: "servicenow-connectors"
status: "new"
updated: 2026-07-14T05:13:05Z
published: 2026-07-14T05:13:05Z
canonical: "helpcenter.securiti.ai/servicenow-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# ServiceNow

> [!NOTE]
> Note
> 
> Securiti recommends using the **ServiceNow** (latest) connector for this data system.

ServiceNow is a SaaS platform that provides help desk and IT support for large-scale enterprises. The system itself is focused on the isolation of operational IT incidents and resolution of such incidents either through changing the basis of the problem or root cause analysis to prevent such incidents from occurring in the future.

ServiceNow falls under the category of [Monitored, Structured data systems](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| ServiceNow (Securiti-Cloud) > [!NOTE] > Note > > Securiti recommends you to use this connector | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation - Automation Policy |
| ServiceNow (Legacy) (Securiti-Cloud) | - Sensitive Data Intelligence (Standard Data Scan) - Security Posture Management |

### Supported authentication method

- For ServiceNow, OAuth 2.0 authentication is supported.
- For ServiceNow (Legacy), Basic authentication is supported.

### Prerequisites for configuring ServiceNow connectors

You must have an admin role in running ServiceNow instance to create application registries and obtain credentials.

- If you are using Xanadu or older releases in ServiceNow, see [Create a ServiceNow instance and obtain credentials](/latest/docs/create-a-servicenow-instance-and-obtain-credentials).
- If you are using Yokohama release in ServiceNow, see, [Create a ServiceNow instance and obtain credentials (Yokohama release)](/latest/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release).

#### 2. Use cases and permissions for ServiceNow

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation | - DSR Automation is not supported in ServiceNow (Legacy) connectors - Scanning in Securiti connectors is supported through Standard Data Scan. | **Admin role** in ServiceNow instance | These role lets Securiti read the tables and views in ServiceNow for classification purposes. This role also fetch personal data through APIs for DSR Automation. |
| Security Posture Management | Security posture scan is only supported forServiceNow (Legacy) connectors. | **Admin role** in ServiceNow instance | This role lets Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

### Connect ServiceNow with Securiti

This section covers the methods to integrate your ServiceNow or ServiceNow (Legacy) connectors with Securiti.

#### Steps to connect the ServiceNow connector with Securiti

To configure the ServiceNow connector, perform the procedures in the following topics:

1. If you are using Xanadu or older release, [Create a ServiceNow instance and obtain credentials](/latest/docs/create-a-servicenow-instance-and-obtain-credentials).

Or if you are using Yokohma release, [Create a ServiceNow instance and obtain credentials (Yokohama release)](/latest/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release).
2. [Connecting ServiceNow with Securiti](/latest/docs/connecting-servicenow-with-securiti).
3. [Configuring General permissions for ServiceNow](/latest/docs/configuring-general-permissions-for-servicenow).

#### Steps to connect the ServiceNow (Legacy) connector with Securiti

To configure the ServiceNow (Legacy) connector, perform the procedures in the following topics:

1. If you are using Xanadu or older release, [Create a ServiceNow instance and obtain credentials](/latest/docs/create-a-servicenow-instance-and-obtain-credentials).

Or if you are using Yokohma release, [Create a ServiceNow instance and obtain credentials (Yokohama release)](/latest/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release).
2. [Connecting ServiceNow (Legacy) with Securiti](/latest/docs/connecting-servicenow-legacy-with-securiti).
3. [Configuring General permissions for ServiceNow (Legacy)](/latest/docs/configuring-general-permissions-for-servicenow-legacy).

**Additional resources**

- [Fulfilling DSR requests for ServiceNow](/latest/docs/fulfilling-dsr-requests-for-servicenow) (for ServiceNow connector only).
- [Troubleshooting for ServiceNow connector](/latest/docs/troubleshooting-for-servicenow-connector).
