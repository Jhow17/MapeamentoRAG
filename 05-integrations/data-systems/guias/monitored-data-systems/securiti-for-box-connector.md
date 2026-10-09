---
title: "Securiti for Box"
slug: "securiti-for-box-connector"
status: "update"
updated: 2026-06-23T10:07:06Z
published: 2026-06-23T10:07:06Z
canonical: "helpcenter.securiti.ai/securiti-for-box-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Securiti for Box

Securiti for Box is a partnership between Securiti and Box, and is recommended to use for efficient API usage.

Box data system connector is an online server-based file storage and management platform that lets a single drive to be shared among multiple users in team-based settings for viewing, editing, and folder modification. However, the [Box data system](/v1/docs/managing-data-system-connectors)(s) limits your API usage based on account type, with different criteria as documented in [Box's official documentation](https://www.box.com/pricing/business). Box bills you for every additional API call if you exceed the provided quota.

Due to the above mentioned limitations, we recommend Securiti for Box instead. This specialized connector was developed through a partnership between Securiti and Box. It enhances Box's functionality by providing a more efficient and cost-effective solution for managing your Box environment.

- The limit of X API calls for business accounts does not apply to partner applications available in the app center.
- Rate limits are applied to each user rather than to the entire partner application.

> [!NOTE]
> **Note**
> 
> Box can still set temporary limits if it notices heavy use of resources and network to prevent overuse and ensure fair access for everyone.

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the Securiti for Box connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> 
> 
> For more information, see [API quota tracking for SaaS connectors](/v1/docs/api-quota-tracking-for-saas-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Only self-hosted connector | It supports: - DSR automation - Sensitive Data Intelligence - Data Access Governance (Privilege Analysis) |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

Box supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| OAuth | Enterprise ID |

### Prerequisites for connecting Securiti for Box connector with Securiti

You must complete these prerequisites before connecting your Securiti for Box connector connector with Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Securiti for Box connector with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Accepting Custom Terms of Service (ToS) for Box

You must have a Box administrator account and accept Custom Terms of Service (ToS) to let Securiti perform scans and DSR fulfillment successfully.

Securiti skips scanning the user's directly-owned data if the ToS is not accepted and continues to process other users. This prevents the scan from failing and ensures that data from compliant users is still processed.

> [!NOTE]
> **Note**
> 
> Files owned by a skipped user may still be included in the scan if they are accessed via a collaborator who is within the scan's scope and has accepted the ToS.

A user's ToS status directly impacts DSR fulfillment. If a data subject has not accepted a pending ToS agreement in their Box account, any DSR actions (such as access or erasure requests) for that user are failed. This occurs because DSR fulfillment requires Securiti to access data as the document's owner, and the Box API blocks this access if the owner has not accepted the latest terms.

### Steps to connect Securiti for Box with Securiti

To configure the Securiti for Box (self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain authentication credentials for Securiti for Box](/latest/docs/grant-permissions-and-obtain-authentication-credentials-for-securiti-for-box).
3. [Connecting Securiti for Box (self-hosted) with Securiti](/latest/docs/new-ui-connecting-securiti-for-box-self-hosted-with-securiti).
4. [Configuring Data Inventory Sync for Securiti for Box](/latest/docs/configuring-data-inventory-sync-for-securiti-for-box).
5. [Configure discovery scans in Securiti for Box](/latest/docs/configure-discovery-scans-in-securiti-for-box).

**Additional resources**

- [Fulfilling DSR requests in Securiti for Box](/latest/docs/fulfilling-dsr-requests-in-securiti-for-box).
