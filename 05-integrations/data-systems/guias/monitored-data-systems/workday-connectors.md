---
title: "Workday"
slug: "workday-connectors"
status: "update"
updated: 2026-08-10T20:19:24Z
published: 2026-08-10T20:20:02Z
canonical: "helpcenter.securiti.ai/workday-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Workday

Workday is a cloud-based software program for human resources (HR) designed to simplify workforce management. You may use its products to handle payroll, scheduling, employee onboarding, time tracking, learning, talent management, and performance evaluations.

Workday falls under the category of [monitored](/latest/docs/managing-data-system-connectors) and is a combination of structured and unstructured data systems.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Workday (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Data Security Posture Management |
| Workday (Securiti Cloud) | Securiti Cloud connector supports: - Sensitive Data Intelligence - DSR Automation - Security Posture Management - Data Breach Management |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

- For Self-hosted connector:
  - Basic authentication.
  - OAuth based authentication
- For Securiti Cloud connector:
  - Basic authentication.
  - OAuth based authentication

#### Keyring support for Workday (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings) for more information.

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault). HashiCorp is OAuth supported with Workday.

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Workday objects in modules and services.

### Prerequisites for configuring Workday connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Workday with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and Workday API endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in Workday instance

You must have an admin access to **create user** and **create group** in the Workday instance.

- For more information on connecting Workday to Securiti, see [Integration details required for Workday authentication](/latest/docs/integration-details-required-for-workday-authentication) and [Acquire authentication credentials in Workday](/latest/docs/acquire-authentication-credentials-in-workday).

#### 3. Use cases and permissions for Workday

This section covers use cases and permissions required for Workday Self-hosted and Cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | - SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. - Securiti only retrieves structured data for Workday connector’s DSR requests. | **Access** rights to organization for Workday groups Necessary permissions to OAuth app authentication. | These permissions let Securiti read the files and file metadata in Workday classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Security Posture Management Rule Evaluation | Only supported for Basic authentication method. | **Get** operations access to Security Group Security Group has necessary permissions for Human Resource Module. | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

#### 4. Steps to connect Workday with Securiti

To configure the Workday connector, perform the procedures in the following topics:

To configure Workday Self-hosted connector:

1. [Integration details required for Workday authentication](/latest/docs/integration-details-required-for-workday-authentication).
2. [Acquire authentication credentials in Workday](/latest/docs/acquire-authentication-credentials-in-workday).
3. [Connecting the Workday (Self-hosted) connector in Securiti](/latest/docs/connecting-the-workday-self-hosted-connector-in-securiti).
4. [Configure discovery scans in Workday (Self-hosted)](/latest/docs/configure-discovery-scans-in-workday-self-hosted)
5. Do [table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for the Workday data system instance.

To configure Workday Securiti Cloud connector:

1. [Integration details required for Workday authentication](/latest/docs/integration-details-required-for-workday-authentication).
2. [Acquire authentication credentials in Workday](/latest/docs/acquire-authentication-credentials-in-workday).
3. [Connecting Workday (Securiti Cloud) with Securiti](/latest/docs/connecting-workday-securiti-cloud-with-securiti).
4. [Initiate Workday data scanning](/latest/docs/initiate-workday-data-scanning)
5. Do [table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for the Workday data system instance.

#### Additional resources

- [Troubleshooting guide for Workday connector](/latest/docs/troubleshooting-guide-for-workday-connector).
- [Fulfilling DSR requests for Workday](/latest/docs/fulfilling-dsr-requests-for-workday).
