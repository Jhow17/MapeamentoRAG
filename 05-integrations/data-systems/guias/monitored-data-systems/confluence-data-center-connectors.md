---
title: "Confluence Data Center"
slug: "confluence-data-center-connectors"
status: "new"
updated: 2026-06-23T07:16:14Z
published: 2026-06-23T07:16:25Z
canonical: "helpcenter.securiti.ai/confluence-data-center-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Confluence Data Center

Confluence Data Center is Atlassian’s self-managed collaboration and knowledge management platform for creating, organizing, and sharing content across teams. By connecting Confluence Data Center with Securiti, organizations can discover and classify sensitive data within pages, spaces, and attachments through Discovery Scan (SDI), and efficiently locate personal data for Data Subject Requests (DSR), helping improve data governance and privacy compliance.

Confluence Data Center falls under the category of [Monitored, Structured data systems.](/latest/docs/managing-data-system-connectors)

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Confluence Data Center (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using full scan - Breach Analysis - Workflow |

### Supported Pod types

Following types of Pods are supported for Confluence Data Center self-hosted connector. For more information, see [Configuring Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

- Securiti standard pod.
- Securiti epod.

### Supported authentication methods

Confluence Data Center supports Personal Access Token method for integration with Securiti.

#### Keyring support for Confluence Data Center connector

You can use a keyring during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for classification scans

Securiti supports the below mentioned items for the Confluence Data Center connector. For more information, see [Configure discovery scans for Confluence Data Center](/latest/docs/configure-discovery-scans-in-confluence-data-center).

- Repositories
- Space(s)

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the Confluence Data Center connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Confluence Data Center with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-deployment).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin or custom user access in Confluence

You should either be an administrator to get Personal Access Token for any space in Confluence. In case you don’t have admin permissions, then you must have user with relevant permissions assigned to get Personal Access Token in Confluence.

#### 3. Use cases and permissions for Confluence Data Center

This section covers use cases and permissions required for Confluence Data Center self-hosted connectors.

If you are using a custom user with non-admin account, you must assign the relevant permissions to the custom user as mentioned below.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights | N/A | Assign desired permissions to the user for a space in Confluence to view, edit, or delete content. | These permissions let Securiti read the files and metadata in Confluence Data Center for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Confluence Data Center to Securiti

To configure the Confluence Data Center connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Confluence Data Center](/latest/docs/acquire-authentication-credentials-in-confluence-data-center).
3. [Connecting Confluence Data Center with Securiti](/latest/docs/connecting-confluence-data-center-with-securiti)
4. [Configure discovery scans for Confluence Data Center](/latest/docs/configure-discovery-scans-in-confluence-data-center).

**Additional resources**

- [Fulfilling DSR requests for Confluence Data Center](/latest/docs/fulfilling-dsr-requests-for-confluence-data-center).
