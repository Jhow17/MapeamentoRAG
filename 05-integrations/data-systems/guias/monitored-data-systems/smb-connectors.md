---
title: "SMB"
slug: "smb-connectors"
status: "update"
updated: 2026-08-31T08:36:03Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/smb-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# SMB

The Server Message Block protocol (SMB protocol) is a client-server communication protocol used for sharing access to files, printers, serial ports, and other resources on a network. It enables shared access to files, printers, and other resources, and it has a significant impact on how data is stored, accessed, and managed.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Only self-hosted connector | Self-hosted connector supports: - DSR automation - Sensitive Data Intelligence - Data Access Governance - Only supports Data Access Intelligence (Privilege Analysis) - Breach Analysis |

### Supported pod types

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

SMB supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| NTLM (User/Password) | - User (if keyring is not used) - Password (if keyring is not used) |
| Kerberos Keytab | - Kerberos Configuration File (if keyring is not used) - Kerberos Keytab (if keyring is not used) - Kerberos User Principal |
| Kerberos Password | - Kerberos Configuration File (if keyring is not used) - Kerberos Password (if keyring is not used) - Kerberos User Principal |

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **HashiCorp****:** For more information, see [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **Basic:** For more information, see [Managing Keyrings](/v1/docs/using-keyrings).
- **CyberArk:** For more information, see [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault).
- **AWS Secrets Manager****:** For more information, see [Configuring AWS Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash****:** For more information, see [Configuring Credstash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault).
- **AzureKey Vault****:** For more information, see [Configuring Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault).
- **Delinea Secret Server****:** For more information, see [Configuring Delinea Secret Manager](/v1/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault).

### Supported items for inventory and classification scans

Securiti supports discovery scans for both the primary and replica servers for the following items:

- SMB shares
- Files in SMB shares
- SMB Share names
- MIP labels

> [!NOTE]
> Note
> 
> Securiti supports MIP label extraction for `ONENOTE` and `ONENOTE_TOC2` files with size lesser than 50MB.

For more information, see the topics below:

- [Configuring discovery scans in SMB](/v1/docs/configuring-discovery-scans-in-smb)
- [Configure Data Inventory Sync for SMB](/v1/docs/configure-data-inventory-sync-for-smb)
- [Microsoft Information Protection (MIP) label extraction for data systems](/v1/docs/microsoft-information-protection-mip-label-extraction-for-data-systems)

### Prerequisites for configuring SMB in Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your SMB with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate endpoints.

For more information on configuring pods, see [Pods (cluster version v1.28 and later)](/latest/docs/pods-cluster-version-v128-and-later).

**Pods container privilege requirement for SMB File Share scanning**

SMB file share scanning requires the pods to dynamically mount remote file systems. To perform these mount operations and access files and directories within the mounted share, the scanning containers must be granted the following Linux privileges:

- `SYS_ADMIN`
- `DAC_READ_SEARCH`

For more information, see [Container privileges requirement for NFS and SMB File Share scans](/latest/docs/container-privileges-requirement-for-nfs-and-smb-file-share-scans).

#### 2. Use cases and permissions

You must complete these prerequisites before connecting your SMB connector with Securiti

> [!NOTE]
> **Note**
> 
> We assume that you have Samba installed before activating the connector.
> 
> Also, ensure you are running TCP port 445 to enable mounting for SMB connector.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Inventory Sync (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans, Data Inventory Sync and DSR Automation Indexing is only available on the self- hosted connector | - List Shares - Read - Read and Write | These permissions let Securiti to discover and scan network shares for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Data Access Intelligence | It is available for self-hosted connector only. | - Share Permission - Read - Basic NTFS Permission - Read - Advanced NTFS Permission - Read permissions | These permissions let Securiti leverages these permissions s as part of determining which users and user groups have access to data in SMB and what level of permissions they have on that data. |
| Data Labeling Policy | N/A | - Share Permission - Change - NTFS/File-level - Write | These permissions let Securiti view, manage, and apply labels to SMB shares. With these permissions, you can apply the Data Labelling Policy to your files. |

### Steps to connect SMB with Securiti

To connect your SMB connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
3. [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb).
4. [Connecting SMB with Securiti](/latest/docs/connecting-smb-with-securiti).
5. [Configure Data Inventory Sync for SMB](/latest/docs/configure-data-inventory-sync-for-smb).
6. [Configuring discovery scans in SMB](/latest/docs/configuring-discovery-scans-in-smb).

**Additional resources**

- [Fulfilling DSR requests for SMB](/latest/docs/fulfilling-dsr-requests-for-smb).
- [Troubleshooting for SMB connector](/latest/docs/troubleshooting-for-smb-connector).
- [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3).
