---
title: "Coupa"
slug: "coupa-connectors-1"
status: "new"
updated: 2026-07-07T06:33:12Z
published: 2026-07-07T06:33:28Z
canonical: "helpcenter.securiti.ai/coupa-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Coupa

Coupa is a cloud-based business spend management platform that helps organizations manage procurement, expenses, invoicing, and supplier relationships. By connecting Coupa with Securiti, organizations can discover and classify sensitive data through Data Scan and efficiently locate personal data for Data Subject Requests (DSR), helping strengthen data governance and support privacy compliance.

Coupa falls under the category of [hybrid data systems](/latest/docs/getting-started-with-data-system-connectors) connectors.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Coupa (Self-hosted) | DSR Automation |
| Coupa (Securiti-Cloud) | Standard Data Scan |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

| Authentication type | Supported credentials |
| --- | --- |
| API key (for Securiti-Cloud connector) | API Key |
| OAuth 2.0 (for Self-hosted connector | - Client ID - Client Secret |

#### Keyring support for self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/using-keyrings) for more information.

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

HashiCorp is OAuth supported with Coupa Online. For more information on configuring OAuth tokens, see [(Optional) Configure HashiCorp OAuth token for Coupa](/latest/docs/optional-configure-hashicorp-oauth-token-for-coupa).
- **Basic.**

### Prerequisites

#### 1. Pod deployment for self-hosted connector

You must deploy a Securiti pod in your environment to connect your Coupa with a Self-hosted connector. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-1).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access in Coupa instance

You must have an administrator or create a user role access in Coupa to obtain credentials.

For more information on obtaining credentials for Coupa, see [Obtain permissions and authentication credentials in Coupa](/latest/docs/obtain-permissions-and-authentication-credentials-in-coupa).

#### 5. Permissions and use cases

You must assign these permissions to the Coupa user to meet different use cases. See the table below.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) Automation Indexing | N/A | Enable **Read** scopes in Coupa account. | These permissions let Securiti read the data to build the Personal Data Index for DSR Automation. |

### Connect Coupa connectors with Securiti

This section covers the methods to integrate your Coupa with Securiti using Self-hosted or Securiti-Cloud connectors, depending on your setup.

#### Steps to connect the Coupa (Self-hosted) connector with Securiti

To configure the Coupa (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Obtain permissions and authentication credentials in Coupa](/latest/docs/obtain-permissions-and-authentication-credentials-in-coupa).

If you want to configure HashiCorp OAuth token, see [(Optional) Configure HashiCorp OAuth token for Coupa](/latest/docs/optional-configure-hashicorp-oauth-token-for-coupa).
3. [Connecting Coupa (Self-hosted) with Securiti](/latest/docs/connecting-coupa-self-hosted-with-securiti).
4. [Configuring General scan settings for Coupa](/latest/docs/initiate-coupa-learning).

#### Steps to connect the Coupa (Securiti-Cloud) connector with Securiti

To configure the Coupa (Securiti-Cloud) connector, perform the following steps:

1. [Connecting Coupa (Securiti-Cloud) with Securiti](/latest/docs/connecting-coupa-securiti-cloud-with-securiti).

**Additional resources**

- [Object scanning in Coupa](/latest/docs/object-scanning-in-coupa).

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

An advanced process of enabling data intelligence on a data system before fulfilling a DSR request.
