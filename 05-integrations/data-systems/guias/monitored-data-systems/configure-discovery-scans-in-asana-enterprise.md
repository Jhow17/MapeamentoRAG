---
title: "Configure discovery scans in Asana Enterprise"
slug: "configure-discovery-scans-in-asana-enterprise"
updated: 2026-05-29T10:21:44Z
published: 2026-05-29T10:21:44Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-asana-enterprise"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Asana Enterprise

This section describes creating a discovery scan for Asana Enterprise (Self-hosted). See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

1. On the Create Discovery Scan page Scan details area, enter a convenient name and description for the scan job.
2. In the Scope area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Asana Enterprise**. |
| Select Data Systems | Choose the specific data system instances to scan. |
| Data System Scope | (Optional) Expand the Data System Scope area. From the **Specify Workspace(s)** menu, add the workspace(s) you wish to be scanned and from the **Specify Project(s)**menu, select projects. By default, all projects of all selected workspaces are scanned. |
3. Selecting the data system and its instance(es) enables the **Select Primary Scan** field. Specify any of your older scans as primary or the current one.

> [!NOTE]
> **Note**
> 
> When you select an unstructured data system, multiple scans might exist for that data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured data system.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(618).png)

Click the **View Scans** link to view the specified scan on the Discovery Scans List page.
4. In the **Scan Conditions** area, select your desired file object category to include or exclude from the scan for your selected unstructured data system. This list of excluded file objects skips the processing of less important files and improves overall scan performance. You may add or remove additional exclusions based on your requirements.

![ds_scan_conditions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04cd7e51-25ff-97e9-1277-642a8e6d6af7(2).png)

Securiti includes or excludes the files according to the following conditions:

If a file does not fall into the above 3 categories, it is downloaded and passed on for classification where it is again classified based on its content. Hence Some of the VOB files or .aax files were classified as they were below 10GB in size and not part of video file extensions as shown below:

![video_formats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d(3).png)

You can include or exclude the File Owner field from the scan conditions to scan files for specific users only.
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file extension is in common video formats(see image) then such files are not downloaded and are not shown as part of the dashboard.
5. In the **Advanced Settings**, use the following settings for your structured data systems. The settings available vary by data system type.

| Parameter | Description |
| --- | --- |
| Incremental scan | The scan processes only the new files, objects, columns, tables, schemas, and databases in the next scan and skips them in the next scan. |
| Sampling | Samples % of data files to scan. **For Unstructured data** Specify the number of files and maximum size of files that you intend to include in this scan. **For Semi-structured data** Specify the number of files and maximum size of records that you intend to include in this scan. |
| Document metadata scan | Scans properties of the files such as file names, types, created by, created on, and so on. |
| Enable Data Subject Requests (DSR) Automation on this Data | Indexes the scanned data elements for use when processing the DSR request. |
| Text extraction | Extracts text from images, zipped and archived files. For more details, see [Step 7](/v1/docs/configure-discovery-scans-in-asana-enterprise). |
| Breach Impact Analysis | Integrates it with the data breach module. This option displays only if an existing breach is detected for that connector. |
6. (Optional) In the Advanced Settings, for unstructured data systems, select **Enable Data Subject Requests (DSR) Automation on this data**. A popup appears about the data elements that are automatically enabled for DSR processing.

> [!NOTE]
> **Note**
> 
> The settings available vary by data system type.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(619).png)
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

> **Tip**
> 
> For a better understanding, visit the following:
> 
> - [Common aspect ratio for images and videos](/v1/docs/securiti-pods-and-elastic-pods)
> - [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes)

**Example**:
    - For an image with the dimension of 1000x748 where 1000 is the width and 748 is the height.
    - If you divide the width by height it gives you the aspect ratio, which in this case is 1.33 that you can specify as the aspect ratio. The greater the height, the smaller the aspect ratio.
  - Set the number of PDF pages containing the images to extract the text from. The number of pages can be specified between 1 and 100.

![text_extraction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31aeedb9-39c1-6733-01f2-b8bd4a52da4f.png)
8. Enable the **Breach Impact Analysis** toggle to initiate analyzing the security breaches.

> [!NOTE]
> **Note**
> 
> This toggle is available for all unstructured data systems. If a connector does not support the discovery scan, then you can see the Breach Analysis toggle on the data system's **Permissions** tab.
9. (Optional) Mark the **Enable Duplicate and Cluster Detection** checkbox to enable the identification of duplicate documents in clusters.

![ds_enable_duplicate_detection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fba37b1-b58b-bed8-9d46-73b068f9c6c6.png)

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
10. In the **Sensitive Data** area, choose the locality enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
11. In the **Sensitive Data** area, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(3).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(3).png)

> [!NOTE]
> **Note**
> 
> - If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data Element that helps with DSR automation’ when you hover over those data elements.
12. (Optional) If you have enabled private cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per data element type in each document (up to 20,000) |
  1. If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
  2. If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the discovery scan job.
13. In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(15).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour is followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(15).png)
14. (Optional) In the Responses area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
15. (Optional) In the Responses area, trigger a specified workflow. To do this, configure a [Discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
16. (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new table/topic or update all table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - Mark the **Add Dataset in lower case** checkbox to add the structured or streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> **Note**
> 
> If you want to convert your data system (that has a unique set of names (tables, views, functions, topics, or columns) to lowercase Uniform Resource Names (URNs) in the data catalog, you can mark the **Register Dataset in the lower case** option for your current data system from the structured or streaming data dashboard.
  - Mark the **Always Execute Response** checkbox to ingest the datasets to the Enterprise Data Catalog regardless of whether it has already been registered before. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.
17. Near the top right side of the page, click **Finish and Activate**. To view discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

#### Key considerations for scan results

- **Project briefs**: Project Brief objects lack "modified_at" or similar fields, and modifying them does not impact the project's "modified_at" field. They undergo scanning in every incremental scan.
- **Attachments**: Attachments incorporated from external hosts are not included in the initial scan. Support for these files may be introduced at a later stage.
- **Edited subtasks**: Incremental scanning may not include edited subtasks in cases where the parent task remains unmodified. This is due to the delta API not returning tasks if only the subtasks have undergone modifications.

## Related

- [Discovery scans](/discovery-scans.md)
- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
- [Viewing scan results in Data Command Graph](/viewing-scan-results-for-data-system-connectors.md)
