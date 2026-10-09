---
title: "Reviewing Outlook scan results in Securiti"
slug: "clone-reviewing-sharepoint-scan-results-in-securiti"
updated: 2026-05-25T21:19:52Z
published: 2026-05-25T21:19:52Z
canonical: "helpcenter.securiti.ai/clone-reviewing-sharepoint-scan-results-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Reviewing Outlook scan results in Securiti

After you complete Data Inventory Syncs or Discovery scans on M365 Outlook, you can review the metadata from the discovered Sites, Files, and any classification results in the [Unstructured Data Scans](/latest/docs/using-the-unstructured-data-discovery) in SDI or [Data Command Graph](/latest/docs/viewing-scan-results-for-data-system-connectors).

## Data Command Graph entities for Outlook data

The discovered metadata for Outlook can be viewed and analyzed in Securiti's Graph Explorer to see which sites and files are discovered during the Data Inventory Sync and understand their properties and relationships.

The **Files** graph entity represents the scanned Microsoft 365 Outlook metadata and files.

The screenshot below shows a Graph Explorer query that displays files in Outlook folders and child folders along with their properties discovered during a Discovery scan and Data Inventory Sync.

For more information, see [Viewing scan results in Data Command Graph](/latest/docs/viewing-scan-results-for-data-system-connectors).

![Overview of files in Office 365 Outlook with modification dates and sizes listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlookfiles_dcgpage.png)

### Properties for Outlook files

In **Unstructured Data Explorer** and **Data Command Graph**, you can view the following properties for your Microsoft 365 Outlook files after discovery scans and Data Inventory Sync completion. The table below lists some key properties for Outlook files.

| Property | Description |
| --- | --- |
| Data Source | Displays the unique ID of the specific connector instance that scanned the file. |
| File Owner | Displays the email address or display name for the file’s owner in Outlook. |
| File Modified Time | Displays the date and time of the file's last change in the data system. |
| File Size | Displays the size of the file such as, in Bytes, KB, or MB. |
| File Name | Displays the name of the document or file. |
| File Format | Displays the detected format of the file, such as Plain Text, PDF, or DOCX. |
| Resource Path | Displays the downloadable URL to the file in Outlook. |
| Data System Type | Displays the Data system where the file resides, such as Microsoft 365 Outlook. |
| Resource URL | Displays a direct link to access the file in Outlook. The Resource URL field displays no value if there is no valid URL to populate. |
| Discovery Scan IDs | Displays the discovery scan job IDs associated with a data system instance where the file resides. |
| Errored | Indicates whether a file was errored during scan processing. |
| Data Element Count | Shows the number of distinct categories or types of Sensitive data elements for example, Credit Card Number, Email Address etc identified within the document. |
| Skipped Reason | Displays a skip reason for the files skipped during discovery scan. |
| Skipped | Indicates whether the file was skipped during a discovery scan job or not. |
| File Record Creation Time | Displays the original creation date and time of the file. |
| File Record Updated Time | Displays the date and time of the file's last change in the Data system. |

![Overview of Microsoft 365 Outlook file details including resource paths and scan information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlookfiles_udspage.png)
