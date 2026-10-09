---
title: "NFS"
slug: "nfs"
status: "update"
updated: 2026-03-10T20:03:55Z
published: 2026-03-10T20:03:55Z
canonical: "helpcenter.securiti.ai/nfs"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# NFS

The Sun NFS (Network File System) is a remote access filesystem focused on providing universal portability of storage configurations across operating systems and processor architectures. It focuses on facilitating transmissions across networked devices.

NFS uses a specialized Kerberos 5.0 protocol to ensure security and privacy across network file systems. NFS is a data export-centric system which might be vulnerable to unauthorized access by malicious parties if the filesystem is exported without the proper control mechanisms in place. The issue of imposterizing file handles for access to the databases is also an issue if a legitimate file handle is being used for the unauthorized viewing and subsequent distribution of proprietary information.

NFS falls under the category of Monitored, Unstructured data systems.

## Supported modules

| Connector type | Modules supported |
| --- | --- |
| Only self-hosted connector | - Sensitive Data Intelligence - Discovery scan - Data Inventory Sync - Policies - Files quarantine - Data Labeling |

## Supported pod type

- Securiti Outpost deployment

## Supported authentication types

NFS uses the file share path to authenticate with Securiti

### Supported items for Inventory and Classification scans

- Files in NFS shares

> [!NOTE]
> **Note**
> 
> Securiti doesn't collect NFS owner's information as a part of Discovery scan or Data Inventory Sync.
- MIP labels. For more information, see [Microsoft Information Protection (MIP) label extraction for data systems](/v1/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

## Prerequisites

#### 1. Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).

#### 2. Access to NFS shares

- The file server host must be reachable.
- The file system must be mountable.
- Files must be accessible.

## Connecting NFS with Securiti using Hyperdrive

To authenticate the NFS connectors, perform the following procedures in sequence:

1. [Deploy AWS-based Outpost](/latest/docs/securiti-outpost-deployment)
2. [Connecting the NFS connector in Securiti (Hyperdrive)](/latest/docs/connecting-the-nfs-connector-in-securiti-hyperdrive).

## Configuring scans and policies

1. [Configuring Data Inventory Sync for NFS (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-nfs-hyperdrive)
2. [Configure discovery scans in NFS (Hyperdrive)](/latest/docs/configure-discovery-scans-in-nfs-hyperdrive)
3. [Create a file quarantine policy using Hyperdrive mode](/latest/docs/using-quarantine-policy-with-hyperdrive-mode)
4. [Create a data labeling policy using Hyperdrive mode](/latest/docs/using-data-labeling-policies-with-hyperdrive-mode-1)

## Additional resources

- [Using the authentication dashboard](/latest/docs/using-authentication-statuses)
- [Using the Inventory Sync Statistics](/latest/docs/using-inventory-sync-statistics)
