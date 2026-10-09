---
title: "Shopify"
slug: "shopify-connectors"
status: "update"
updated: 2026-06-20T10:25:44Z
published: 2026-06-20T10:25:53Z
canonical: "helpcenter.securiti.ai/shopify-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Shopify

Shopify is an online e-commerce platform for online stores and retail Point-of-Sale (PoS) systems.

Shopify retains personal information until the user (Partners and Merchants) discontinues using its services, after which it immediately deletes all such data. However, it does not control how long a merchant may retain their customers’ information. Per GDPR, Shopify deals with Data Subject Requests (DSR) on the part of customers and establishes consumer-side opt-in/out permissions for consensual disclosure of personal data.

Shopify (Self-hosted) falls under [Monitored, Hybrid](/latest/docs/managing-data-system-connectors) data system.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Self-hosted | - Sensitive Data Intelligence |
| Securiti Cloud connector | - DSR automation using APIs |

### Supported pod type for self-hosted connector

- Standard Securiti pods
- Elastic pods

### Supported authentication methods

- For self-hosted connector:
  - Admin API access token
- For Securiti Cloud connector:
  - OAuth based authentication.

#### Keyring support for Shopify (Self-hosted)

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **CyberArk**. For more information, see [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault).

> [!NOTE]
> **Note**
> 
> When creating an account and safe in CyberArk for Shopify, the **username** and **password** are unique parameters. All other parameters remain the same across configurations.
> 
> | Setting | Value |
> | --- | --- |
> | Username | Provide any username such as Shopify |
> | Password | For more information, see Create an application and obtain authentication credentials for Shopify (self-hosted) |

### Prerequisites for configuring Shopify connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Shopify with a self-hosted connector. Make sure the Pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti.ai endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Shopify account access

You must have an access to Shopify account to activate the connector.

#### 3. Private Cloud Storage configuration

You must configure Private Cloud Storage (PCS) for your tenant to successfully authenticate Shopify (Self-hosted) connector. For more information on configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage).

#### 4. Permissions and use cases

If you want to provide the Shopify connectors access to all of your Shopify store entities for data discovery and classification, use the following use cases and permissions.

| Use case | Constraints | Permissions | Explanation for use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | It is available for Self-hosted connector. | **Admin API scopes**: - read_orders - read_files - read_products - read_content - read_locations - read_customers - read_draft_orders | These permissions let Securiti read the files and file metadata for classification purposes. |

### Connect Shopify with Securiti

This section covers the integration topic of the following Shopify connectors:

#### Steps to connect Shopify (self-hosted) with Securiti

Perform the following steps to connect Shopify (self-hosted) connector:

1. [Create an application and obtain authentication credentials for Shopify (self-hosted)](/latest/docs/create-an-application-and-obtain-authentication-credentials-for-shopify-self-hosted)
2. [Connecting Shopify with Securiti (Self-hosted)](/latest/docs/connecting-shopify-with-securiti)
3. [Configure discovery scans in Shopify](/latest/docs/configure-discovery-scans-in-shopify)

#### Steps to connect Shopify (Securiti Cloud) with Securiti

Perform the following steps to connect Shopify (Securiti Cloud):

1. [Register an application in Shopify (Securiti hosted)](/latest/docs/register-an-application-in-shopify-securiti-hosted)
2. [Connecting Shopify with Securiti (Securiti hosted)](/latest/docs/connecting-shopify-with-securiti-securiti-hosted)
3. [Fulfilling DSR requests for Shopify](/latest/docs/fulfilling-dsr-requests-for-shopify).

#### Additional resources

- [(New UI) Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
- [Classification of scanning items for Shopify](/latest/docs/classification-and-gencore-scanning-items-for-shopify)
