---
title: "Microsoft Information Protection (MIP) label extraction for data systems"
slug: "microsoft-information-protection-mip-label-extraction-for-data-systems"
updated: 2026-08-03T05:59:02Z
published: 2026-08-03T05:59:02Z
canonical: "helpcenter.securiti.ai/microsoft-information-protection-mip-label-extraction-for-data-systems"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Information Protection (MIP) label extraction for data systems

In Securiti, Microsoft Information Protection (MIP) labels enable you to classify and protect data in data systems. The classification labels are collected during the Data Inventory Sync or Discovery scan, after your Connector Activation. With label extraction, these sensitivity labels are retrieved for your files and displayed in the platform, providing enhanced visibility and enforcement of data protection policies. The topic explains the Configuration for MIP labels extraction for the supported Self-hosted connectors.

### Prerequisites

Following prerequisites must be fulfilled before configuring the MIP label extraction for your Data system Connector.

- For Microsoft 365 data systems, ensure your organization has the necessary licensing to use the premium Microsoft Graph API for sensitivity labels. Typically, a Microsoft 365 E5 or Microsoft 365 E5 Compliance license is required.
- Configure any required Permissions for MIP label extraction for your Data system.

### Supported data systems for MIP label extraction

Securiti supports the following Data system (Self-hosted) connectors for MIP label extraction. See the Table below for the scans used to extract MIP labels for each Data system.

> [!NOTE]
> **Note**
> 
> Refer to your data system connector's documentation for any permissions and limitations related to MIP label extraction.

| Data system | MIP label extraction method |
| --- | --- |
| [Microsoft 365 Onedrive](/v1/docs/microsoft-365-onedrive-connectors) | [Data Inventory Sync](/v1/docs/data-inventory-sync-for-self-hosted-connectors) |
| [Microsoft 365 SharePoint Online](/v1/docs/managing-data-system-connectors) | [Data Inventory Sync](/v1/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted) |
| [NFS](/v1/docs/nfs-connectors) | [Discovery Scan](/v1/docs/configure-discovery-scans-in-nfs) |
| [SMB](/v1/docs/smb-connectors) | [Discovery Scan](/v1/docs/configuring-discovery-scans-in-smb) |
| [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) | [Discovery Scan](/latest/docs/configuring-discovery-scans-in-azure-blob-storage) |

- For Microsoft 365 Onedrive and Microsoft 365 SharePoint Online, MIP labels are collected during the Data Inventory Sync

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EIB8EDPK.png)
- For SMB, NFS, and Azure Blob Storage, MIP labels are collected during the Discovery scan. On the **Create Discovery scan** page for your Connector, in the **Advanced Settings** section, enable the **Get MIP Labels Information** toggle.
- ![MIP_Discoveryscan_Setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6097d084-677e-aff0-da2e-3a60edc179fc.png)

### Viewing MIP labels in Graph Explorer

The Data Inventory Sync or Discovery scan triggers label extraction, collecting MIP labels from the data systems and integrating them into Securiti’s Database and graph. For more information, see [Viewing scan results for data system connectors](/v1/docs/viewing-scan-results-for-data-system-connectors).

To view the extracted labels in the [Graph Explorer](/v1/docs/using-graph-explorer).

1. From the New Navigation left sidebar, select **Graph Explorer**, as shown below.

![graphexplorer_nav.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3dd4e992-a8d5-bb09-6bb6-361cf2cc84b7.png)
2. Create a query by searching and adding the **Files** or **Discovery scan Files** entity.
3. Click options (three dots) and select **Add properties** to specify your **Data system Type**.
4. Click **Add relationship** to fetch labels for your files only.
5. Select **Scanned Classification Label** entity to view all the scanned classification labels for your files.

![MIP_query.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7519952d-6abd-d5c1-fa64-c8249760d0ad.png)
6. Click on any Instance to view the relationships in the Instance explorer.

![MIP_instexplorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-438c6287-036f-5e18-335e-5bfa2577b44e.png)

## Related

- [Data Inventory Sync and Entitlement Scan for data systems](/data-inventory-sync-for-self-hosted-connectors.md)
- [Viewing scan results in Data Command Graph](/viewing-scan-results-for-data-system-connectors.md)
