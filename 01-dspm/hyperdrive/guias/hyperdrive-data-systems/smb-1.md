---
title: "SMB"
slug: "smb-1"
status: "update"
updated: 2026-07-20T08:29:56Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/smb-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# SMB

The Server Message Block protocol (SMB protocol) is a client-server communication protocol used for sharing access to files, printers, serial ports, and other resources on a network. It enables shared access to files, printers, and other resources, and it has a significant impact on how data is stored, accessed, and managed.

## Supported modules

| Connector type | Modules supported |
| --- | --- |
| Only self-hosted connector | Self-hosted connector supports: - Sensitive Data Intelligence - Discovery scan - Data Inventory Sync - Policies - Files Quarantine - Data Labeling |

## Supported authentication methods

SMB supports the following authentication types for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| NTLM (User/Password) | - User - Password |
| Kerberos Keytab | - Kerberos Configuration File - Kerberos Keytab - Kerberos User Principal |
| Kerberos Password | - Kerberos Configuration File - Kerberos Password - Kerberos User Principal |

### Keyring support

Keyring support is not available for SMB using Hyperdrive mode.

## Supported pod types

- Securiti Outpost Deployment

## Prerequisites

Complete the following prerequisites to authenticate the SMB.

1. ### Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).
2. ### Samba Installation and Network Port Requirement
  - We assume that you have Samba installed before activating the connector.
  - Also, ensure you are running TCP port 445 to enable SMB mount.
3. ### Permissions

The following permissions are required for SMB Data system instances:

| Permission | Purpose |
| --- | --- |
| List shares | The permission is required to discover network shares. It is necessary in case you are activating the Connector with “/” as a shared path. |
| Read | The permission is required to scan an SMB share. This permission also lets Securiti read file content and metadata on the SMB share to evaluate and run Quarantine and Data Labeling policies in SDI. |
| Write | This permission lets Securiti create or modify files on the SMB share when executing Quarantine and Data Labeling policy actions in SDI. |
| Write Attributes | This permission lets Securiti update file attributes when applying Quarantine and Data Labeling policy actions in SDI. |
| Execute | This permission lets Securiti traverse directories on the SMB share to access and evaluate files for Quarantine and Data Labeling policies in SDI. |
| Read and Write | The read and write Permissions are required on both the source share and the quarantine share if the quarantine and Data Labeling policy is being used. |
| Delete | This permission lets Securiti delete files from the SMB share when executing deletion-based Quarantine actions in SDI. |

## Connect your SMB

To configure the SMB connector, perform the procedures in the following topics:

1. [Deploy AWS-based Outpost](/latest/docs/securiti-outpost-deployment)
2. [Acquire authentication credentials in SMB (Hyperdrive)](/latest/docs/acquire-authentication-credentials-in-smb-hyperdrive).
3. [Connecting the SMB with Securiti (Hyperdrive)](/latest/docs/activate-the-smb-connector-in-securiti-hyperdrive).

## Configure scans and policies

1. [Configure Data Inventory Sync for SMB (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-smb-hyperdrive)
2. [Configuring discovery scans in SMB (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-smb-hyperdrive)
3. [Create a file quarantine policy using Hyperdrive mode](/latest/docs/using-quarantine-policy-with-hyperdrive-mode)
4. [Create a data labeling policy using Hyperdrive mode](/latest/docs/using-data-labeling-policies-with-hyperdrive-mode-1)

## Additional resources

- [Troubleshooting for SMB connector (Hyperdrive)](/latest/docs/troubleshooting-for-smb-connector-hyperdrive)
- [Using authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive)
- [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive)
