---
title: "Configure discovery scans in Slack Enterprise Grid"
slug: "configure-discovery-scans-in-slack-enterprise-grid"
updated: 2026-02-11T10:42:19Z
published: 2026-02-11T10:42:19Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-slack-enterprise-grid"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Slack Enterprise Grid

This section describes creating a Discovery scan for Slack Enterprise Grid. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

1. On the Create Discovery scan page **Scan Details** area, enter a convenient name and description for the scan job.
2. In the Scope area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Slack Enterprise Grid.** |
| Select Data Systems | Choose the specific Data system instances to scan. |
3. Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. Specify any of your older scans as primary or the current one.

> [!NOTE]
> **Note**
> 
> When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured Data system.

![slack_ent_primary_scan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56aa52b8-3ea4-b634-d2da-f8a0f88d3fdb.png)

Click the **View Scans** link to view the specified scan on the Discovery Scans List page.
4. In the **Data system Scope** area, select All or any specific Slack Workspace(es) and Channels you want to include or exclude from the scan. By default, the list has all the workspaces marked.
5. In the **Scan Conditions** area, select your desired file object category to include or exclude from the scan for your selected unstructured Data system. This list of excluded file objects skips the processing of less important files and improves overall scan performance. You may add or remove additional exclusions based on your requirements.

![ds_scan_conditions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04cd7e51-25ff-97e9-1277-642a8e6d6af7(16).png)

Securiti includes or excludes the files according to the following conditions:

If a file does not fall into the above 3 categories, it is downloaded and passed on for classification where it is again classified based on its content. Hence Some of the VOB files or .aax files were classified as they were below 10GB in size and not part of video file extensions as shown below:

![video_formats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d(24).png)

You can include or exclude the File Owner field from the scan conditions to scan files for specific users only.
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file extension is in common video formats(see image) then such files are not downloaded and are not shown as part of the dashboard.
6. In the **Advanced Settings**, use the following settings for your Structured data systems. The settings available vary by Data system type.

| Parameter | Description |
| --- | --- |
| Incremental scan | The scan processes only the new files, objects, columns, tables, schemas, and databases in the next scan and skips them in the next scan. |
| Sampling | Samples % of data files to scan. **For Unstructured data** Specify the number of files and maximum size of files that you intend to include in this scan. **For Semi-structured data** Specify the number of files and maximum size of records that you intend to include in this scan. |
| Document metadata scan | This option scans properties of the files such as file names, types, created by, created on, and so on. |
| Enable Data Subject Requests (DSR) Automation on this Data | This option indexes the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data element types, which includes: - Username - Email - Passport Number - Driver License Number - US SSN - TSA Precheck Number - US Tax Payer ID - US DoD ID Number - US VISA Number - US Alien Registration Number - IN Aadhaar Card Number - IN PAN Number - BR CPF - AU Medicare Number - AU Tax File Number - NZ NHI - MRN |
| Text extraction | This option extracts text from images, zipped and archived files. For details, see [Step 8](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data). |
| Breach Impact Analysis | This option integrates it with the data breach module. This option displays only if an existing breach is detected for that Connector. |
| Enable Duplicate and Cluster Detection | Creates clusters for duplicate and near-duplicate documents. For more information see [Using the cluster analysis dashboard](/modules/data-intelligence/en/data-intelligence-target/dashboards/using-the-cluster-analysis-dashboard.html). |
7. (Optional) In the Advanced Settings, for Unstructured data systems, select **Enable Data Subject Requests (DSR) Automation on this data**. A popup appears about the data elements that are automatically enabled for DSR processing.

> [!NOTE]
> **Note**
> 
> The settings available vary by Data system type.

![DSP_enable_in_discovery_scan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f790e9e9-0e0c-7ff7-c845-9259a7f3ce68(6).png)
8. Enable the **Text Extraction** toggle to extract the text from images using the Optical Character Recognition (OCR) technology. Using this feature, Securiti extracts text from different image types such as PNG, BMP, JPG, JPEG, and PDF documents.

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
> - [Common aspect ratio for images and videos](/v1/docs/securiti-pods-and-elastic-pods)
> - [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes)

**Example**:
    - For an image with the dimension of 1000x748 where 1000 is the width and 748 is the height.
    - If you divide the width by height it gives you the aspect ratio, which in this case is 1.33 that you can specify as the aspect ratio. The greater the height, the smaller the aspect ratio.
  - Set the number of PDF pages containing the images to extract the text from. The number of pages can be specified between 1 and 100.

![text_extraction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31aeedb9-39c1-6733-01f2-b8bd4a52da4f(9).png)
9. Enable the **Breach Impact Analysis** toggle to initiate analyzing the security breaches.

> [!NOTE]
> **Note**
> 
> This toggle is available for all Unstructured data systems. If a Connector does not support the Discovery scan, then you can see the Breach Analysis toggle on the Data system's **Permissions** tab.
10. (Optional) Mark the **Enable Duplicate and Cluster Detection** checkbox to enable the identification of duplicate documents in clusters. ![ds_enable_duplicate_detection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fba37b1-b58b-bed8-9d46-73b068f9c6c6(8).png)

> [!NOTE]
> **Note**
> 
> The Discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
11. In the **Sensitive data** area, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
12. In the **Sensitive data** area, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below. ![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(38).png) ![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(38).png)

> [!NOTE]
> **Note**
> 
> If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data element that helps with DSR Automation’ when you hover over those data elements.
13. (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

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
14. In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(92).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(85).png)
  - **Custom Cron**

For custom cron jobs, use the [expression builder](/v1/docs/securiti-pods-and-elastic-pods). It has the minute, hour, day of the week, and day of the month settings. When you are done, use that expression in the Enter Cron field. ![cronjob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc9b8076-799b-9c0f-c533-8c0a42fe28c8(11).png)

You can also exclude the times when you don't want the scan to run and specify multiple times weekly, or monthly. Select the hour block(s) in the 24x7 matrix where scanning should be executed. The scan is automatically paused at the beginning of each execution block and resumed at the end. ![exclude_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46(11).png)
15. (Optional) In the **Responses** area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
16. (Optional) In the **Responses** area, enable the **Trigger Workflow** toggle, and click **Add Workflow**. ![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(29).png)

On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**. ![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(29).png)

For more information, see [Discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
17. Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

#### Key considerations for scope configuration

- Slack's org-shared channels are not associated with specific workspaces but are connected to the entire enterprise, and thus cannot be listed under regular workspace scope. To address this, Securiti creates a new custom workspace named "Org Shared Channels" to list all enterprise-tied channels.

> [!NOTE]
> **Note**
> 
> - When you modify a channel's setting to enable sharing across "All org workspaces", Slack ties the channel to the Enterprise instead of to a specific workspace. If the setting is later reverted back to "Selected workspaces", the channel remains associated with the Enterprise and is listed under your custom workspace "Org Shared Channels" regardless of whether it is org-shared or not.
> - If a channel is shared between more than one workspace (but not all), it still appears as an org-shared channel.
- The draft attachments (uploaded to Slack Enterprise Grid but not sent) are automatically scanned when the Discovery scan is configured for ALL scope.

> [!NOTE]
> **Note**
> 
> Securiti does not scan draft attachments when the Discovery scan is scoped.
- Securiti automatically scans canvases when the Discovery scan is configured for the "ALL" scope, therefore no separate scan condition is required for canvases. This includes scanning all attachments directly uploaded to the canvas, as well as those added in the comments.

> [!NOTE]
> **Note**
> 
> - Securiti treats each canvas as a separate file in Slack and is scanned accordingly.
> - Securiti does not scan canvases when the Discovery scan is scoped.
- In the case of a scoped scan, Securiti processes DMs & MPDMs only of those users who are members of the scoped channels.
- In the case of selecting "ALL" as scope in Discovery scan for attachments, in some cases the Slack APIs do not provide any Team or Channel information. This results in empty additional file data (Team ID and Channel ID) for some files on the dashboard. Such files usually belong to archived channels or to channels that have been deleted.
