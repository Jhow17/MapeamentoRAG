---
title: "LDAP Active Directory"
slug: "ldap-active-directory-connectors-1"
status: "update"
updated: 2026-07-13T06:31:53Z
published: 2026-07-13T06:31:53Z
canonical: "helpcenter.securiti.ai/ldap-active-directory-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# LDAP Active Directory

Lightweight Directory Access Protocol (LDAP) is an industry-grade application protocol for the maintenance and restoration of data directories at specified IP addresses. These directories are used by other applications and service providers to share information in a universal format, accessible over a variety of platforms. LDAP also functions as a hierarchical framework for data storage by assigning unique values to each entry within a certain directory and then establishing categorical attributes for each of these "individuals".

LDAP falls under the category of [Monitored, Structured data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| LDAP Active Directory (Self-hosted) | - Sensitive Data Intelligence - DSR automation using SQL queries |

### Supported pod types

LDAP Active Directory supports standard Securiti pod.

### Supported authentication methods

Securiti supports basic authentication method for LDAP Active Directory.

#### Keyring support for LDAP Active Directory connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/creating-keyrings).

- **CredStash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault).
- **Basic.**

### Supported items for classification scans

Securiti scans the following items for LDAP Active Directory connector.

- Databases
- Tables
- Schemas
- Views

For more information, see [Configure discovery scans in LDAP Active Directory](/latest/docs/configure-discovery-scans-in-ldap-active-directory). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your LDAP Active Directory with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin rights in LDAP Active Directory

You must have an account with admin rights in LDAP Active Directory to get the authentication credentials for connector activation.

### Connect LDAP Active Directory with Securiti

#### Steps to connect LDAP Active Directory connector

To configure the LDAP Active Directory connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pod-quick-install-guides-cluster-version-v128-en).
3. [Obtain LDAP configuration information](/latest/docs/obtain-ldap-configuration-information).
4. [Connecting LDAP Active Directory with Securiti](/latest/docs/connecting-ldap-active-directory-with-securiti)
5. [Configure discovery scans in LDAP Active Directory](/latest/docs/configure-discovery-scans-in-ldap-active-directory)

#### Additional resources

- [Table Training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

> [!NOTE]
> **Note**
> 
> The LDAP connector does not have any DSR response capabilities. It allows only read access for DSR requests submitted by data subjects.
