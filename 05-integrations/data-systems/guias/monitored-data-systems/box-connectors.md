---
title: "Box"
slug: "box-connectors"
status: "update"
updated: 2026-07-30T08:37:21Z
published: 2026-07-30T08:37:51Z
canonical: "helpcenter.securiti.ai/box-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Box

Box data system connector is an online server-based file storage and management platform that allows for a single drive to be shared among multiple users in team-based settings for viewing, editing, and folder modification.

This documentation covers the configuration and activation process for self-hosted and cloud versions of the Box connector.

> [!NOTE]
> **Important**
> 
> The Box data system(s) limit your API usage based on your account type, with varying criteria for different types as documented in [Box's official documentation](https://www.box.com/pricing/business). Box bills you for every additional API call if you exceed the provided quota. To avoid extra charges, Securiti stops making API calls for DSRs and also halts the scanning of DSRs if the relevant option is disabled during connector activation.

Box meets the data security standards of GDPR by providing a standardized Data Processing Agreement (DPA) form that lets customers grant access to their data to external parties. Box has also separated its physical hosting sites into “BoxZones” to comply with regional privacy laws.

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the Box connectors. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.

Box connector falls under the category of Monitored, Unstructured data systems. For more information, see [data system classifications](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Box (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation - Security Posture Management |
| Box (Securiti Cloud) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation using smart search - Security Posture Management - Data Breach Management |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

Box supports the following authentication types for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| OAuth | - Client ID - Client Secret |

#### Keyring support for Box (Self-hosted)

Securiti does not support keyrings for Box (self-hosted) connector currently. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

### Supported items for classification scans

- Box Group(s)

For more information, see [Configuring discovery scans in Box](/v1/docs/configuring-discovery-scans-in-box) and [Configure Box scanning](/v1/docs/configure-box-scanning)

### Prerequisites for connecting Box with Securiti

You must complete these prerequisites before connecting your Box connector with Securiti

#### Pod deployment for self-hosted connector

You must deploy a Securiti pod in your environment to connect your Box with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### Permissions and use cases for Box

> [!NOTE]
> **Note**
> 
> The below mentioned scopes are required for both self-hosted and Securiti Cloud connectors.

| Modules use case | Constraint | Scopes | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) - DSR Automation using Smart Search - Security Posture Management - Breach Analysis | - SDI Discovery scans are available on the self- hosted connector - Security Posture scans are available on the Securiti Cloud connector only. - Breach Analysis is supported for the Securiti Cloud connector only. - DSR Automation using Smart Search is supported for the Securiti Cloud connector only | **Content Actions:** - Read all files and folders stored in Box - Write all files and folders stored in Box. **Administrative Actions:** - Manage users - Manage groups - Manage enterprise properties > [!NOTE] > **Note** > > You must provide the "Suppress notification" scope for this permission. | These permissions let Securiti discover and scan Box groups for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Security Posture Management Rule Evaluation | Security Posture Management requires you to use a Box Enterprise account. | **Content Actions:** - Read all files and folders stored in the box **Administrative Actions:** - Manage Users - Manage Groups - Manage retention policies - Manage Enterprise Properties | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| DSR Automation using Smart Search | DSR Automation using Smart Search is supported for the Securiti Cloud connector only. | **Content Actions:** - Read all files and folders stored in the Box. - Write all files and folders stored in the Box **Administrative Actions:** - Manage users - Enterprise_content. > [!NOTE] > Note > > This permission requires an admin to submit a request to the Box Support team. For more information, see [Box documentation](https://developer.box.com/guides/search/enterprise/). | This permission lets Securiti read all of the data within your Box groups for DSR searches. |

### Connect the Box connector with Securiti

See the sections below to connect your Box self-hosted or Box (Securiti Cloud) connectors with Securiti.

#### Steps to connect Box (Self-hosted) connector with Securiti

To configure the Box self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods)
3. [Grant permissions and obtain credentials in Box](/v1/docs/grant-permissions-and-obtain-credentials-in-box).

(optional) [Enable the enterprise_content scope in Box](/latest/docs/enable-the-enterprise-content-scope-in-box)
4. [Connecting Box (Self-hosted) with Securiti](/latest/docs/connecting-box-self-hosted-connector-with-securiti)
5. [Configuring General permissions for Box (Self-hosted)](/latest/docs/configuring-general-permissions-for-box)
6. [Configuring discovery scans in Box](/v1/docs/configuring-discovery-scans-in-box)

#### Steps to connect Box (Securiti-Cloud) connector with Securiti

To configure the Box (Securiti-Cloud) connector, perform the following steps:

1. [Grant permissions and obtain credentials in Box](/v1/docs/grant-permissions-and-obtain-credentials-in-box).

(optional) [Enable the enterprise_content scope in Box](/latest/docs/enable-the-enterprise-content-scope-in-box)
2. [Connecting Box (Securiti-Cloud) with Securiti](/latest/docs/connecting-box-securiti-cloud-with-securiti)
3. [Configuring General permissions for Box (Securiti-Cloud)](/latest/docs/configuring-general-permissions-for-box-cloud)

#### Additional resources

- [Fulfilling DSR requests for Box](/latest/docs/fulfilling-dsr-requests-for-box).

## Related

- [Grant permissions and obtain credentials in Box](/grant-permissions-and-obtain-credentials-in-box.md)
- [Configuring discovery scans in Box](/configuring-discovery-scans-in-box.md)
