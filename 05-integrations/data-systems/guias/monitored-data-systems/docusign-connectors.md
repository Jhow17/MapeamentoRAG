---
title: "DocuSign"
slug: "docusign-connectors"
status: "new"
updated: 2026-07-16T05:53:40Z
published: 2026-07-16T05:53:40Z
canonical: "helpcenter.securiti.ai/docusign-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# DocuSign

DocuSign is a software-based documentation solution that lets individuals digitally collaborate over drafting, authorizing, and signing official documentation. DocuSign's services can be used either on a subscription-based model or free of charge (as an app for mobile-based operating systems). The authentication of DocuSign-based signatures and documents relies on encryption (in the form of unique hash identifiers assigned by DocuSign), and any unauthorized modifications or alterations made to such documents will be verified on behalf of DocuSign as being following their records or invalidated and tagged as "tampered" documents.

DocuSign falls under the category of [monitored, unstructured data system](/v1/docs/managing-data-system-connectors).

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the DocuSign self-hosted connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions. For more information, see [API quota tracking for SaaS connectors](/v1/docs/api-quota-tracking-for-saas-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| DocuSign (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Data Breach Management |
| DocuSign (Securiti Cloud) | Securiti Cloud connector supports: - Sensitive Data Intelligence - Security Posture Management - Data Breach Management |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.

### Supported authentication methods

- For Self-hosted connector:
  - OAuth based authentication
- For Securiti Cloud connector:
  - OAuth based authentication

#### Keyring support for Self-hosted connector (Not supported)

Keyring support is not available for DocuSign self-hosted connectors.

### Supported items for Classification Scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

Securiti supports the following folders for classification scans:

- Inbox
- Sent items
- Draft
- Deleted items

Securiti supports the following items within the selected folders:

- Documents
- Comment
- Attachment

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your DocuSign with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and DocuSign API endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/v1/docs/elastic-pods-1).

For more information on configuring pods, see [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Account requirement

You must need one of the following DocuSing accounts:

- Demo account
- Permanent account

For more information, see [Set up DocuSign API access credentials](/v1/docs/set-up-docusign-api-access-credentials).

#### 3. Use cases and permissions

This section covers use cases and permissions required for DocuSign self-hosted and cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and Indexing is only available on the self- hosted connector. | Share envelopes with the user | These permissions let Securiti read the files and file metadata in DocuSign for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Security Posture Management Rule Evaluation | Security Posture Management is supported only for Securiti cloud connector. | Share envelopes with the user | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

### Connect your DocuSign with Securiti

To configure the DocuSign connector, perform the procedures in the following topics:

1. [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials)
2. For [Connecting DocuSign (Self-hosted) with Securiti](/latest/docs/activate-the-docusign-connector-in-securiti) and for Securiti-cloud connector, see [Connecting DocuSign (Securiti Cloud) with Securiti](/latest/docs/connecting-docusign-securiti-cloud-with-securiti).
3. For self-hosted connector, see the below post-authentication articles:
  - [Configure discovery scans in DocuSign](/latest/docs/configure-discovery-scans-in-docusign)
  - [Configuring general scan settings for DocuSign (Self-hosted)](/latest/docs/configuring-general-scan-settings-for-docusign-self-hosted)
  - [Fulfilling DSR requests for DocuSign (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-docusign-self-hosted)
4. For Securiti Cloud connector, see [Configuring general scan settings for DocuSign (Securiti Cloud)](/latest/docs/configuring-docusign-scanning)

### 

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.
