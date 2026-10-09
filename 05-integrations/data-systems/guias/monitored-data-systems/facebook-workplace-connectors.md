---
title: "Facebook Workplace"
slug: "facebook-workplace-connectors"
status: "new"
updated: 2026-07-25T22:41:03Z
published: 2026-07-30T05:44:24Z
canonical: "helpcenter.securiti.ai/facebook-workplace-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Facebook Workplace

Facebook Workplace is an enterprise collaboration platform that brings the familiar Facebook experience into a business context. It is designed as an all-in-one internal communications hub, it combines chat, video calling, live streaming, news feeds, and group collaboration tools. It enables organizations to connect employees across teams, locations, and time zones without relying on traditional email.

The Facebook Workplace connector lets you integrate your Workplace environment with Securiti to discover and govern unstructured communication and collaboration data generated across your organization's groups, posts, and messaging activity.

Facebook Workplace falls under the category of monitored, unstructured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Facebook Workplace (Securiti Cloud) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation using APIs - Breach Analysis |

### Supported authentication methods

- For Securiti Cloud connector:
  - Workplace application-based authentication
    - OAuth based authentication using API Key

### Supported items for classification scans

Securiti scans the standard data items for Facebook Workplace connectors.

- Facebook Workplace Databases
- Files
- Apps

### Prerequisites for configuring Facebook Workplace connector

#### 1. Admin access

You must have admin access in Facebook Workplace to create a custom integration and obtain access token to authenticate your connector.

For more information, see [Create a custom integration in Facebook Workplace](/latest/docs/create-a-custom-integration-in-facebook-workplace).

#### 2. Use cases and permissions for Facebook Workplace

This table covers use cases and permissions required for Facebook Workplace (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | N/A | - Access to create **custom integration** in Facebook Workplace. - Access to create **access token.** | These permissions let Securiti to read files and schema metadata in Facebook Workplace for data scan purposes. |

### Steps to connect Facebook Workplace (Securiti Cloud) connector with Securiti

To configure the Facebook Workplace connector, perform the procedures in the following topics:

1. [Create a custom integration in Facebook Workplace](/latest/docs/create-a-custom-integration-in-facebook-workplace).
2. [Connect Facebook Workplace connector with Securiti](/latest/docs/connect-facebook-workplace-connector-with-securiti).
3. [Configure general scan settings for Facebook Workplace](/latest/docs/configuring-general-scan-settings-for-facebook-workplace).

Scanning the data to find primary data elements such as email, SSN, passport number, etc using the APIs. With this feature DSR Robotic Automation,Securiti does not store or build an index of primary data elements on the appliance. Refer to DSR Automation in data system connectors for more information.

Breach Impact Analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this functionality by enabling this feature while setting up the necessary discovery scan jobs for monitored data systems, ensuring comprehensive and proactive breach analysis. See Using Data Breach Management, for more information.

An API key is a unique identifier used to connect to, or perform, an API call.
