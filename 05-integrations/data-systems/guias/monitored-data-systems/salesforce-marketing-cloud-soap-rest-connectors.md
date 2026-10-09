---
title: "Salesforce Marketing Cloud (SOAP + REST)"
slug: "salesforce-marketing-cloud-soap-rest-connectors"
status: "new"
updated: 2026-07-31T11:18:20Z
published: 2026-07-31T11:18:20Z
canonical: "helpcenter.securiti.ai/salesforce-marketing-cloud-soap-rest-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Salesforce Marketing Cloud (SOAP + REST)

The Salesforce Marketing Cloud (SOAP + REST) connector in Securiti enables integration with Marketing Cloud to access and manage customer data across its services using both APIs. It allows organizations to discover and govern personal data, while supporting automated Data Subject Requests (DSR) such as access and deletion to help ensure compliance with privacy regulations.

Salesforce Marketing Cloud falls under the [Monitored, structured data systems](/latest/docs/managing-data-system-connectors) category.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Salesforce Marketing Cloud (SOAP) (Securiti cloud) | DSR Automation using SQL queries |
| Salesforce Marketing Cloud (REST) (Securiti cloud) | DSR Automation using SQL queries |

### Supported authentication methods

- For Salesforce Marketing Cloud (SOAP) connector:
  - Basic authentication
- For Salesforce Marketing Cloud (REST) connector:
  - OAuth-based authentication

### Prerequisites for configuring Salesforce Marketing Cloud (SOAP+REST) connector

#### 1. Admin access in Salesforce Marketing Cloud

You must be an administrator to grant permissions to the packages created in the Salesforce Marketing Cloud.

For more information, see [Acquire authentication credentials in Salesforce Marketing Cloud (SOAP + REST)](/latest/docs/acquire-authentication-credentials-in-salesforce-marketing-cloud-soap-rest).

#### 2. Use cases and permissions for Salesforce Marketing Cloud

This section covers use cases and permissions required for the Salesforce Marketing Cloud (SOAP+REST) Securiti cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| DSR Automation (Data Subject Rights) | N/A | - Give the **Read** permission to all of the available scopes. - The following scopes require relevant permissions: - Data Extensions - `Read` and `Write` - File Locations - `Read` and `Write` - Tracking Events - `Read` and `Write` - Managing Keys - `Viewstatus/logs` | These permissions let Securiti to discover and scan Salesforce Marketing Cloud objects to build the Personal Data Index for DSR Automation. |

### Connect Salesforce Marketing Cloud (SOAP+REST) with Securiti

To configure the Salesforce Marketing Cloud (SOAP+REST) connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Salesforce Marketing Cloud (SOAP + REST)](/latest/docs/acquire-authentication-credentials-in-salesforce-marketing-cloud-soap-rest).
2. [Connecting Salesforce Marketing Cloud (SOAP) with Securiti](/latest/docs/connecting-salesforce-marketing-cloud-soap-with-securiti).
3. [Connecting Salesforce Marketing Cloud (REST) with Securiti](/latest/docs/connecting-salesforce-marketing-cloud-rest-with-securiti).
4. [Configuring General permissions for Salesforce Marketing Cloud (SOAP+REST)](/latest/docs/configuring-general-permissions-for-salesforce-marketing-cloud-soap-rest).

**Additional resources**

- [Fulfilling DSR requests for Salesforce Marketing Cloud (SOAP + REST)](/latest/docs/fulfilling-dsr-requests-for-salesforce-marketing-cloud-soap-rest)
