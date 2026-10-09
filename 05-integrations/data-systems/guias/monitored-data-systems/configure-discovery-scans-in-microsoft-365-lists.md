---
title: "Configure discovery scans in Microsoft 365 Lists"
slug: "configure-discovery-scans-in-microsoft-365-lists"
updated: 2026-07-31T06:18:39Z
published: 2026-07-31T06:18:39Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-microsoft-365-lists"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Microsoft 365 Lists

This section describes creating a Discovery scan for Microsoft 365 Lists. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

1. On the Create Discovery scan page Scan details area, enter a convenient name and description for the scan job.
2. In the Scope area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Microsoft 365 Lists.** |
| Select Data Systems | Choose the specific Data system instances to scan. |
3. Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. Specify any of your older scans as primary or the current one.

> [!NOTE]
> **Note**
> 
> When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured Data system.

![M365lists_primaryscan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2306082-2b24-0b38-b71a-6ed1cee70f99.png)

Click the **View Scans** link to view the specified scan on the Discovery Scans List page.
4. In the Data system Scope area:

> [!NOTE]
> **Important**
> 
> When creating a Discovery scan in Microsoft 365 Lists, all Sites and Subsites appear as a single list in a flat structure within the **Data system Scope**. Each Subsite must be manually selected from the list. Essentially, every Site whether a Subsite or not, is listed as an independent entry in the **Data system Scope.**
  1. Enter the site's name in the **Site(s)** field and select it from the menu to include in the scan. You can select all or multiple site collections and exclude them from the scan as well.
  2. Choose a List for that site.

![M365lists_datasystem_Scope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1fec1945-09e9-5546-af2a-26d6b68db01a.png)
5. Under the **Scan Conditions**, choose an attribute to configure it to be included or excluded from the scan. These include file extension category, file name, and so on. ![M365lists_scanconditions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c645034-82ba-5084-1e2b-ddae0eaf7b03.png)
6. In the Advanced Settings, use the following settings for your Structured data systems. The settings available vary by Data system type.

| Parameter | Description |
| --- | --- |
| Incremental scan | The scan processes only the new files, objects, columns, tables, schemas, and databases in the next scan and skips them in the next scan. |
| Sampling | Samples % of data files to scan. **For Unstructured data** Specify the number of files and maximum size of files that you intend to include in this scan. **For Semi-structured data** Specify the number of files and maximum size of records that you intend to include in this scan. |
| Document metadata scan | This option scans properties of the files such as file names, types, created by, created on, and so on. |
| Scan Attachments | Enabling this option triggers the scanning for attachments in your Microsoft 365 Lists Data system. |
| Exclude System Lists | Enabling this option excludes all system lists from scanning. |
| Text extraction | This option extracts text from images zipped and archived files. |
| Breach Impact Analysis | This option integrates it with the data breach module. This option displays only if an existing breach is detected for that Connector. |
| Enable Duplicate and Cluster Detection | Creates clusters for duplicate and near-duplicate documents. For more information see [Using the cluster analysis dashboard](/latest/docs/detecting-and-reducing-duplicate-and-near-duplicate-data). |
7. Enable the **Text Extraction** toggle to extract the text from images using the Optical Character Recognition (OCR) technology. Using this feature, Securiti extracts text from different image types such as PNG, BMP, JPG, JPEG, and PDF documents.

Enabling the **Text Extraction** toggle enables the **Extract text from compressed and archived files** field.

(Optional) Mark the **Extract text from compressed and archived files** checkbox to enable extracting text from the files that you have compressed or archived. You can specify the image dimensions for pixel ratio and aspect ratio.

> [!NOTE]
> **Note**
> 
> Extraction of text from images using the OCR option is only available where the pods have been deployed.

Securiti then uses this text for data classification, so the image dimensions that you should follow are:
  - Specify the minimum pixel ratio between 10,000 to 80,00,000 pixels.
  - Specify the maximum pixel ratio between 90,000 and 1,00,00,000 pixels.
  - Specify the minimum aspect ratio between 0 to 10.
  - Specify the maximum aspect ratio between 1 to 10.

> [!NOTE]
> **Tip**
> 
> For a better understanding, visit the following:
> 
> - [Common aspect ratio for images and videos](https://www.istockphoto.com/blog/best-practices/design/a-guide-to-video-aspect?utm_source=wp_blog&amp;utm_medium=referral&amp;utm_campaign=migration&amp;utm_term=redirect)
> - [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes)

**Example**:
    - For an image with the dimension of 1000x748 where 1000 is the width and 748 is the height.
    - If you divide the width by height it gives you the aspect ratio, which in this case is 1.33 that you can specify as the aspect ratio. The greater the height, the smaller the aspect ratio.
  - Set the number of PDF pages containing the images to extract the text from. The number of pages can be specified between 1 and 100.

![text_extraction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31aeedb9-39c1-6733-01f2-b8bd4a52da4f(2).png)
8. Enable the **Breach Impact Analysis** toggle to initiate analyzing the security breaches.

> [!NOTE]
> **Note**
> 
> This toggle is available for all unstructured Data system connectors. If a Connector does not support the Discovery scan, then you can see this toggle on the Data system's **Permissions** tab.
9. (Optional) Mark the **Enable Duplicate and Cluster Detection** checkbox to enable the identification of duplicate documents in clusters.

![ds_enable_duplicate_detection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fba37b1-b58b-bed8-9d46-73b068f9c6c6(2).png)

> [!NOTE]
> **Note**
> 
> The Discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
10. In the **Sensitive data** area, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
11. In the Sensitive data area, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![M365lists_sensitivedata.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bdcca6a-ed8d-40c8-461c-469845c9f97c.png)

![M365lists_sensitivedata1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41ce3592-eab9-4e5f-07b8-f6b1b5654f5f.png)
12. (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per Data element type in each document (up to 20,000) |
  1. If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
  2. If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the Discovery scan job.
13. In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(63).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(57).png)
14. (Optional) In the Responses area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
15. (Optional) In the Responses area, trigger a specified Workflow. To do this, configure a [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
16. Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/discovery-scans-updated).

- Securiti lets you toggle scanning of **Attachments** within a List.
- Securiti lets you exclude **System Lists** from scanning within a Site.
- Scan condition based on **File Size** is not supported for Microsoft Lists
- Scan conditions based on **Created/Modified Date** are not applicable on List attachments.
- Scan condition based on **File Name** is not applicable on List Rows and List Rows Comments
- As a limitation from Microsoft Lists APIs, the **Created/Modified Date** and **Owner** for a List Attachment is associated with the **Created/Modified Date** and **Owner** of the List Item.
- Scan conditions based on **File Extension** and **File Extension Category** are not applicable on List Rows and List Rows Comments because data is always prepared for these items in CSV file extension.
- In the Incremental scan, List item's Attachments and Comments are scanned only if the corresponding List Item has been modified (changes to columns or attachments) or a new List Item has been discovered. This limitation is enforced by Microsoft Lists APIs.
- For Lists generated by the System, the author's email is unavailable. Instead, the author title appears as "Document Owner" for such List items. For example, "System Account" might be displayed for these items.
