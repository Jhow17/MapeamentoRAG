---
title: "NFS"
slug: "nfs-connectors"
status: "update"
updated: 2026-07-22T15:56:20Z
published: 2026-07-22T19:27:04Z
canonical: "helpcenter.securiti.ai/nfs-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# NFS

The Sun NFS (Network File System) is a remote access filesystem focused on providing universal portability of storage configurations across operating systems and processor architectures. It focuses on facilitating transmissions across networked devices.

NFS uses a specialized Kerberos 5.0 protocol to ensure security and privacy across network file systems. NFS is a data export-centric system which might be vulnerable to unauthorized access by malicious parties if the filesystem is exported without the proper control mechanisms in place. The issue of imposterizing file handles for access to the databases is also an issue if a legitimate file handle is being used for the unauthorized viewing and subsequent distribution of proprietary information.

NFS falls under the category of [Monitored, Unstructured data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| NFS (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using Full Scan - Breach Analysis |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

NFS uses the file share path to authenticate with Securiti

### Supported items for inventory and classification scans

Securiti supports data inventory sync and discovery scans. It performs discovery scans for the following items:

- Files in NFS shares
- MIP labels. For more information, see [Microsoft Information Protection (MIP) label extraction for data systems](/latest/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).

> [!NOTE]
> **Note**
> 
> Securiti doesn't collect NFS owner's information as a part of Discovery scan or Data Inventory Sync.

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring NFS

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your NFS with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and NFS endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

**Pods container privilege requirement for NFS File Share scanning**

NFS file share scanning requires the pods to dynamically mount remote file systems. To perform these mount operations and access files and directories within the mounted share, the scanning containers must be granted the following Linux privileges:

- `SYS_ADMIN`
- `DAC_READ_SEARCH`

For more information, see [Container privileges requirement for NFS and SMB File Share scans](/latest/docs/container-privileges-requirement-for-nfs-and-smb-file-share-scans).

#### 2. Access requirement for NFS resources

- The file server host must be reachable.
- The file system must be mountable.
- Files must be accessible.

### Steps to connect NFS connector with Securiti

To configure the NFS connectors, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Connecting the NFS with Securiti](/latest/docs/connecting-the-nfs-with-securiti).
3. [Configure discovery scans in NFS](/latest/docs/configure-discovery-scans-in-nfs)
4. [Configuring Data Inventory Sync for NFS](/latest/docs/configuring-data-inventory-sync-for-nfs)

#### Additional resources

- [Fulfilling DSR requests for NFS](/latest/docs/fulfilling-dsr-requests-for-nfs)
- [NFS FAQs](/latest/docs/nfs-faqs)

Breach Impact Analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this functionality by enabling this feature while setting up the necessary discovery scan jobs for monitored data systems, ensuring comprehensive and proactive breach analysis. See Using Data Breach Management, for more information.
