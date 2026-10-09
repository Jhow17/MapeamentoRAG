---
title: "OCR settings for discovery scans"
slug: "scan-conditions-to-use-ocr-settings"
updated: 2026-09-28T06:37:56Z
published: 2026-09-28T06:38:03Z
canonical: "helpcenter.securiti.ai/scan-conditions-to-use-ocr-settings"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# OCR settings for discovery scans

Securiti uses Optical Character Recognition (OCR) to extract and classify text from image files and PDF documents during discovery scans. You can enable OCR from the **Advanced Settings** of a discovery scan.

> [!WARNING]
> Important
> 
> OCR is only available on pod-based deployments.

Once enabled, Securiti extracts text from image file types such as `PNG`, `BMP`, `JPG`, and `JPEG`, as well as PDF documents, and uses it for sensitive data classification. OCR scanning is available for the following unstructured and semi-structured data systems:

- Alibaba Cloud Object Storage Service (OSS)
- Alfresco
- Amazon S3
- Azure Blob Storage
- Azure Data Lake Gen2
- Azure Files
- Box
- Citrix ShareFile
- Confluence Data Center
- Dropbox
- G Suite Gmail
- G Suite Google Drive
- GitHub
- Go File Room
- Google Cloud Storage
- Hadoop Distributed File System (HDFS)
- Jira Software
- Microsoft 365 Lists
- Microsoft 365 OneDrive
- Microsoft 365 Outlook
- Microsoft 365 SharePoint Online
- NFS
- Oracle Object Storage
- OpenText Content Server
- Salesforce CRM
- ServiceNow Files
- SFTP
- Slack Enterprise Grid
- Slack Pro
- SMB
- Tableau Server
- Workday
- Zendesk Support
- Zoho Recruit

![Settings for advanced data extraction and sampling options in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ocroptions_discoveryscansadvancedsettings.png)

For more information, see [Scan conditions in OCR settings](/latest/docs/scan-conditions-to-use-ocr-settings-1) and [OCR-supported document types](/latest/docs/ocs-supported-document-types).
