---
title: "Container privileges requirement for NFS and SMB File Share scans"
slug: "container-privileges-requirement-for-nfs-and-smb-file-share-scans"
updated: 2026-06-15T11:34:12Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/container-privileges-requirement-for-nfs-and-smb-file-share-scans"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Container privileges requirement for NFS and SMB File Share scans

To provide comprehensive visibility, discovery, and active governance across NFS and SMB file shares, Securiti scanning pods require specific Linux capabilities. These capabilities enable the scanner containers to dynamically mount remote file systems, traverse directory structures, and perform advanced data security and governance operations. The required privileges are granted only to the scanning pods and are essential for supporting enterprise-scale file share scanning, data classification, remediation, and policy enforcement.

Use the following table to understand the privileges required for NFS and SMB Files Share scanning:

| Privilege | Description |
| --- | --- |
| `SYS_ADMIN` | - `SYS_ADMIN` is required for performing mount operations, which involve modifying the file system. - Mounting network file systems like NFS and SMB requires these elevated privileges, specifically to use the mount system call. |
| `DAC_READ_SEARCH` | - `DAC_READ_SEARCH` is required to bypass Discretionary Access Control (DAC) checks for reading files and searching directories. - Also required to access the necessary files and directories within the container's file system to set up the mount successfully. |

## Dynamic management of mounts

While some approaches rely on Kubernetes-managed Persistent Volumes (PVs/PVCs), we have architected our solution to manage these connections dynamically for two critical reasons:

| Reason | Description |
| --- | --- |
| Operational Scalability | Our platform requires your infrastructure team to manually provision, manage, and tear down PVs/PVCs for every target share introduces significant operational friction. Our dynamic approach allows for the automated discovery and management of thousands of shares without administrative bottlenecks. |
| Advanced Policy Operations | Our platform is not a passive scanner; it supports active enforcement, such as dynamically labeling files or enforcing quarantine workflows. These features require the application to have direct control over the connection state and protocol interactions. Relying on abstracted, kubelet-managed mounts would break these core governance capabilities. |

## Security and governance guardrails

Securiti understands that granting elevated capabilities requires trust and alignment with your security standards. We have built-in several guardrails to ensure these permissions are used safely and transparently:

| Guardnail | Description |
| --- | --- |
| Scope limitation | Scope of the capabilities is restricted to the containers specifically responsible for scanning. They are not granted globally across the platform. |
| Configurability | Flexibility in configuration is available to opt out of this functionality. If your organization chooses not to utilize SMB/NFS scanning features, these capabilities can be disabled entirely via your configuration settings: ```plaintext global: enable_sys_admin: false ``` > [!NOTE] > Note > > Disabling this setting effectively turns off all SMB and NFS scanning functionality within the Securiti platform. |
| Designed for Enterprise | Architecture design is built to support complex enterprise environments, including those utilizing Active Directory for identity resolution and ACL enforcement. By integrating directly with these protocols (using established tools like rpcclient and smbcacls), we ensure that our scanning adheres to your existing organizational identity and permission models. |
