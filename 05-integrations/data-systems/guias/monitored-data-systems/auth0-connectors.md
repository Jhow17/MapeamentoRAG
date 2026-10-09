---
title: "Auth0"
slug: "auth0-connectors"
status: "new"
updated: 2026-07-30T07:52:58Z
published: 2026-07-30T07:52:58Z
canonical: "helpcenter.securiti.ai/auth0-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Auth0

Auth0 is a popular identity and access management (IAM) platform that simplifies the implementation of authentication and authorization for applications. Auth0 supports OAuth 2.0, OpenID Connect, and other protocols, making it easier for developers to secure applications without needing to build authentication systems from scratch. With Auth0 connectors, you can integrate with Securiti and scan data for your data system.

Auth0 (Self-hosted) is a monitored, structured connector and Auth0 (Securiti Cloud) is a [monitored, scanless connector](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Auth0 (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence |
| Auth0 (Securiti-Cloud) | Securiti Cloud connector is a scanless connector that supports: - DSR Automation using APIs (smart search) |

### Supported pods type for self-hosted connector

- Standard Securiti pods.

### Supported authentication methods

- For Self-hosted connector:
  - OAuth based authentication
- For Securiti Cloud connector:
  - OAuth based authentication

### Supported items for discovery scans

Securiti supports scanning for the following entities for Auth0 (Self-hosted) connector. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

> [!NOTE]
> **Important**
> 
> Auth0 (Securiti Cloud) connector is a scanless connector and does not support data scanning.

- Organizations
  - Users within a scoped organization

### Prerequisites for configuring Auth0 connector

#### 1. Pod deployment for self-hosted connector

You must deploy a Securiti pod in your environment to connect your Auth0 with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/v1/docs/elastic-pods-1).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Allowlisting APIs for Discovery scan with Auth0 (Self-hosted)

Securiti requires the following URLs to be allowlisted on your firewall for the Auth0 (Self-hosted) connector for Sensitive Data Intelligence (SDI) to work as expected:

| Sr. No | URL | Purpose |
| --- | --- | --- |
| 1 | `https://&lt;domain&gt;.us.auth0.com/api/v2/organizations` | Fetch all organizations |
| 2 | `https:/&lt;domain&gt;.us.auth0.com/api/v2/organizations/org_eE1TYA3lbIe2V2pP/members` | Fetch organization members |
| 3 | `https://&lt;domain&gt;.us.auth0.com/api/v2/users` | Fetch users |

#### 3. Use cases and permissions for Auth0

This section covers use cases and permissions required for Auth0 self-hosted and cloud connectors.

To provide the Auth0 connectors access for data discovery and classification, use the following use cases and permissions.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | SDI Discovery scans are supported for self-hosted connector only | - read:users - read:organizations_summary - read:organizations - read:organization_members | These permissions let Securiti read all the users within the organization or any independent user. |

### Connect Auth0 connectors with Securiti

#### Steps to connect Auth0 (Self-hosted) with Securiti

To configure the Auth0 (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Granting permissions and acquiring credentials in Auth0 (self-hosted)](/latest/docs/granting-permissions-and-acquiring-credentials-in-auth0)
3. [Connecting Auth0 (Self-hosted) with Securiti](/latest/docs/connecting-auth0-with-securiti)
4. [Configure discovery scans in Auth0 (Self-hosted)](/latest/docs/configure-discovery-scans-in-auth0-self-hosted)

#### Steps to connect Auth0 Securiti-Cloud with Securiti

To configure the Auth0 Securiti-Cloud connector, perform the procedures in the following topics:

1. [Granting permissions and acquiring credentials in Auth0 (Securiti-Cloud)](/latest/docs/granting-permissions-and-acquiring-credentials-in-auth0-securiti-hosted)
2. [Connecting Auth0 (Securiti-Cloud) with Securiti](/latest/docs/connecting-auth0-securiti-cloud-with-securiti)

**Additional resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Related

- [Granting permissions and acquiring credentials in Auth0 (Self-hosted)](/granting-permissions-and-acquiring-credentials-in-auth0.md)
- [Configure discovery scans in Auth0 (Self-hosted)](/configure-discovery-scans-in-auth0-self-hosted.md)
