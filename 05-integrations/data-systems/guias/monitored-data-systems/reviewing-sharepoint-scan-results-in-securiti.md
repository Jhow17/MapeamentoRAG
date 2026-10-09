---
title: "Reviewing SharePoint scan results in Securiti"
slug: "reviewing-sharepoint-scan-results-in-securiti"
updated: 2026-02-07T13:46:30Z
published: 2026-02-09T20:00:06Z
canonical: "helpcenter.securiti.ai/reviewing-sharepoint-scan-results-in-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Reviewing SharePoint scan results in Securiti

After you complete Data Inventory Syncs or Discovery scans on SharePoint, you can review the metadata from the discovered Sites, Files, and any classification results in the [Unstructured Data Discovery](/v1/docs/using-the-unstructured-data-explorer) in SDI or [Data Command Graph](/v1/docs/using-data-command-graph).

## Data Command Graph entities for SharePoint data

The discovered metadata and the MIP labels for SharePoint can be viewed and analyzed in Securiti's Graph Explorer to see which sites and files are discovered during the Data Inventory Sync and understand their properties and relationships.

The following graph nodes can be used to view Microsoft 365 SharePoint Online metadata.

- **Sites**: For SharePoint sites and scoping inventory results
- **Files**: For SharePoint files and data inventory results
- **Scanned Classification Label**: For MIP labels discovered during the Data Inventory Sync

The screenshot below shows a Graph Explorer query that displays files in SharePoint sites and their properties discovered during a Discovery scan and Data Inventory Sync.

For more information, see [Using Graph Explorer](/v1/docs/using-graph-explorer).

![Graph Explorer interface displaying file details and data sources for various files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sitehasfiles_graph.png)

In case the Microsoft 365 SharePoint Online connector is activated via a Credential vault or with restrictive site access, the following data for the SharePoint sites is not available in the Data Command Graph.

- **Site Type** (shows SITE) property
- Relationship between sites and hubsites
- **Sharing Enabled** property
- **Sharing Capabilities** property. For more information about site sharing capabilities, see [Microsoft's documentation](https://learn.microsoft.com/en-us/graph/api/resources/sharepointsettings?view=graph-rest-1.0#sharingcapabilities-values).

### Properties for SharePoint files

In **Unstructured Data Explorer** and **Data Command Graph**, you can view the following properties for your Microsoft 365 SharePoint Online files after discovery scans and Data Inventory Sync completion. The Table below lists some key properties for SharePoint files.

| Property | Description |
| --- | --- |
| Document Name/Classification Label | Displays the name of the document or file. This Column may also show any applied classification labels for example, "Confidential," "Internal", etc. |
| Document Owner | Displays the email address or display name for the document's owner in SharePoint. |
| Content Profiles | Displays any Content Profiles that the document's content has matched, indicating predefined categories or types of content recognized. |
| Data Elements All/Unique | Displays the total number of all individual sensitive Data element occurrences found within the document. It may also indicate a count of distinct Data element types if presented in this Column. |
| Data element Types | Shows the number of distinct categories or types of Sensitive data elements for example, Credit Card Number, Email Address etc identified within the document. |
| Quarantine | Indicates the quarantine status of the document, showing if it has been moved, restricted, or flagged based on applied policies. |
| Document Category | Displays any category assigned to the document. This can be based on its content, source, applied policies, or sensitivity level. For example, “Financial”, “Academic”. |
| Data system Location | Displays the geographical region configured for the Data system where the document resides. For example, “United States of America” |
| Org Name | Shows the name of the organization associated with the Data system. |
| Data system Type | Displays the Data system where the file resides, such as Microsoft 365 SharePoint Online. |
| Data system | Displays the specific Connector Instance that scanned the file. |
| File Format | Displays the detected format of the file, such as Plain Text, PDF, or DOCX. |
| Document Size | Displays the size of the file such as, in Bytes, KB, or MB. |
| Resource Path | Displays the downloadable URL to the file in SharePoint. > [!NOTE] > **Note** > > For SharePoint files, the Resource Path field currently displays the same URL as the Resource URL field. > > We use webDavUrl field from graph API response for our "Resource Path:" > > - **Description**: It provides a direct, file-system-like path for accessing files via WebDAV, bypassing SharePoint’s web interface. > - **Reason**: It omits _layouts because it is intended for programmatic or mapped drive access, not browser-based navigation.. |
| Resource URL | Displays a direct link to access the file in SharePoint application. > [!NOTE] > **Note** > > Resource URL is a clickable link to open the file in your browser. > > We use webURL field from graph API response for our “Resource URL:" > > - **Description**: It is a user-friendly, browser-accessible link that routes through SharePoint's _layouts pages to enable rich in-browser viewing or editing, especially for files like .xlsx. > - **Reason**: It shows _layouts in the URL because SharePoint uses it to launch integrated apps like Excel Online with parameters that control how the document is opened. |
| Top Level Directory | Displays the library that stores the file, such as "Documents". |
| O365 ID | Displays a unique identifier for the document's list item (`listItemId`) in the Microsoft 365 SharePoint library. For more information on SharePoint document's list item identifiers, see [SharePoint’s documentation](https://learn.microsoft.com/en-us/graph/api/resources/sharepointids?view=graph-rest-1.0). |
| Date Created | Displays the original creation date and time of the file. |
| Last Modified | Displays the date and time of the file's last change in the Data system. |
| First Scanned | Displays the date and time when Securiti first scans the file. |
| Last Scanned | Displays the most recent date and time when Securiti scans this file. |
| Scan Name | Displays the name of the scan job that discovers the file's information. |
| Scan Job ID | Displays the unique identifier for the specific scan job. |

![sharepoint_ude_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4966999-c386-4d15-447c-453179bd7448.png)

![Graph Explorer interface displaying file details and search options for Office 365 SharePoint.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharepointfiles_graph.png)

### Properties for SharePoint sites

In the **Data Command Graph**, you can view the following properties for your Microsoft 365 SharePoint Online sites after discovery scans and Data Inventory Sync completion. The Table below lists some key properties for SharePoint sites.

| Property | Description |
| --- | --- |
| Account ID | Displays the unique ID of the Microsoft 365 account or tenant that hosts the SharePoint site. For example, `securitiadmin`. |
| Asset ID | Displays the unique identifier of the Data system Instance containing the site. For example, `acme1234-abcd-wxyz-abcd-1234abcd` |
| Description | Displays the description of the SharePoint site, as provided in its settings within SharePoint. |
| Site Name | Displays the SharePoint site name. For example, `Communication site` |
| Sensitivity Labels | Displays the sensitivity label assigned to each SharePoint site, for example, `Financial`. The label represents the site sensitivity setting configured in the SharePoint admin center. > [!NOTE] > Note > > - To ingest SharePoint site sensitivity labels, you must configure and activate the SharePoint connector and complete the Scoping Inventory Sync. Sensitivity labels must already be applied to SharePoint sites in Microsoft 365 for this information to be ingested and displayed in Securiti. > - Site sensitivity labels are independent of file-level sensitivity labels. Securiti does not infer file sensitivity based on the site’s sensitivity label. |
| Graph Data system Type | Displays Data system type of the SharePoint site within the Securiti Data Graph. |
| Organization | Shows the name(s) of the organization or tenant to which the SharePoint site belongs. For example, "Default organization", "sites org", etc. |
| Sharing Capabilities | Displays the configured external and internal sharing Permissions for the site for example, `ExternalUserAndGuestSharing`, `Disabled`. For more information site sharing capabilities, see [Microsoft’s documentation](https://learn.microsoft.com/en-us/sharepoint/change-external-sharing-site). |
| Sharing Enabled | Shows whether sharing, particularly external sharing, is currently enabled or disabled for the SharePoint site. |
| Site Owner | Displays the email address of the SharePoint site owner. For example, `john.doe@securitiadmin.net`. |
| Site Type | Displays whether the site is a standard SharePoint site (**SITE**) or if it is designated as a SharePoint Hub Site (**HUBSITE**). |
| Web ID | Displays the Web ID of the site. For example, `securitiadmin.sharepoint.com`, `662acme-12345678-wxyz` |
| Web URL | Displays the direct web address (URL) to access the SharePoint site. For example, `https://securitiadmin.sharepoint.com/sites/commsite12345` |

![Graph Explorer interface displaying site data and sharing capabilities for various organizations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharepointsites_graph.png)
