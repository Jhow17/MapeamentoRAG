---
title: "Viewing Confluence Cloud metadata in Securiti"
slug: "viewing-confluence-cloud-metadata-in-securiti"
updated: 2025-10-31T13:57:24Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/viewing-confluence-cloud-metadata-in-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Viewing Confluence Cloud metadata in Securiti

After Securiti completes an inventory or discovery scan on an unstructured data system like Confluence Cloud, you can select any attachment, page, comment, etc in the [Unstructured Data Explorer](/v1/docs/using-the-unstructured-data-explorer) or [Data Command Graph](/v1/docs/using-data-command-graph) to view its detailed properties. These properties provide key metadata about a site's origin, content, ownership, and scan history, giving you a complete picture of your data.

### Properties for Confluence Cloud documents

In **Unstructured Data Explorer** and **Data Command Graph**, you can view the following properties for your Confluence Cloud sites and documents after discovery scans and Data Inventory Sync completion. The Table below lists some key properties for Confluence Cloud documents.

| Property | Description |
| --- | --- |
| Data System Type | Displays the data system where the document resides, such as Confluence Cloud. |
| Data System | Displays the specific connector instance that scanned the file. |
| File Format | Displays the detected format of the file, such as Plain Text, PDF, or DOCX. |
| Document Owner | Displays the email address or display name for the site's owner in Confluence Cloud. |
| Document Size | Displays the size of the file (e.g., in Bytes, KB, or MB). |
| Resource Path | Displays the path where the file is located within the data system. > [!NOTE] > **Note** > > For pod versions 1.132.0 and above, the Resource Path field is populated only for Pages and Blogposts and is empty for Confluence Cloud attachments and comments. You can get the direct file link to the document from the **Resource URL** property. |
| Resource URL | Displays a direct link to access the document in Confluence Cloud application. The Resource URL exists for all discovered attachments, comments, pages, and blogposts. |
| Date Created | Displays the original creation date and time of the file. |
| Last Modified | Displays the date and time of the file's last change in the data system. |
| First Scanned | Displays the date and time when Securiti first scans the file. |
| Last Scanned | Displays the most recent date and time when Securiti scans this file. |
| Scan Name | Displays the name of the scan job that discovers the file's information. |
| Scan Job ID | Displays the unique identifier for the specific scan job. |

![confluence_properties_ude.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c9d1eca-9428-70a5-b1e3-5b29ff468ac8.png)![confluence_properties_dcg.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92611cc3-af3c-d976-c0ee-96f59e805ff7.png)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
