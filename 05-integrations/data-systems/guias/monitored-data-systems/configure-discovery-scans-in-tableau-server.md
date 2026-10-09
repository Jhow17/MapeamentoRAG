---
title: "Configure discovery scans in Tableau Server"
slug: "configure-discovery-scans-in-tableau-server"
updated: 2026-09-08T06:01:35Z
published: 2026-09-08T06:01:35Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-tableau-server"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Tableau Server

This section describes creating a Discovery scan for Tableau Server. For more information about Securiti discovery scans, see [Understanding discovery scans](/latest/docs/discovery-scans).

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for Tableau Server connectors:

- On the **Create Discovery scan** page under the **Scan Details** section, enter a convenient **Name** and **Description** for the scan job.
- In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Tableau Server** |
| Select Data Systems | Choose the specific data system instances to scan. |
- In the **Data system Scope** section, select Tableau Server sites and projects you want to include or exclude from the scan.
- In the **Scan Conditions** section, select your desired inclusion or exclusion attribute:

This inclusion or exclusion skips the processing of less important files and improves overall scan performance. You may add or remove additional exclusions based on your requirements.

Securiti includes or excludes the files according to the following conditions:
  - **File Name**
  - **File Size**
  - **Created Date**
  - **Last Modified**
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.

## Advanced settings

In the **Advanced Settings**, use the following settings for your data systems. The settings available vary by data system type.

Tableau Server includes settings for both structured and unstructured data as explained in the table below.

| Parameter | Description |
| --- | --- |
| **For Structured Data** |
| Store Sample Data | The option is enabled by default and stores your sample files at your desired location configured during the Connector Activation process. When disabled, Securiti does not store any sample files on Appliance or Cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page. > [!NOTE] > **Note** > > Sample files stored on Cloud support encryption feature. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable this feature for tenant. Files stored on Appliance are not encrypted. |
| Include evidence file for the Discovery scan job | Includes the evidence file for the scan. This option requires private Cloud storage to be turned on. To enable classification on columns and tables, mark the **Perform classification on columns and tables** checkbox. This enables the **Max Detections to Store** field where you can specify the limit per Discovery scan, per Column, and per Data element type. |
| Max Detections to Store | Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the limit according to: - Total detections per scan job (up to 2.5 million) - Total detections per Column (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| Perform classification on columns and tables previously learned | Performs field classification on previously learned columns and leverages any newly found evidence in those columns. If you want to enable this option, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan. |
| Retain manually classified data elements and content profiles | If you want to retain manually classified data elements and content profiles, enable this option. It also appends new classifications as and when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When you do not want to use this option, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |
| **For Unstructured Data** |
| Incremental scan | The scan processes only the new files, objects, issues, pull requests, and commits files in the next scan and skips them in the next scan. The last sync time is compared with the last scan start time. **Limitation** The incremental scan is not supported for Wikis scanned for the Group or Project. Wikis existing in the Group or Project will be scanned on every scan job The incremental scan is not supported for Snippets scanned for the Project and User. Snippets existing in the Project and User will be scanned on every scan job |
| Sampling | Samples % of data files to scan. **For Unstructured data** Specify the number of files and maximum size of files that you intend to include in this scan. **For Semi-structured data** Specify the number of files and maximum size of records that you intend to include in this scan. |
| Document metadata scan | This option scans properties of the files such as file names, types, created by, created on, and so on. |
| Text Extraction | Enable Text Extraction toggle to enable the **Extract text from images using OCR** and **Extract text from compressed and archived files**. This option extracts text from images, zipped and archived files. |
| Extract text from images using OCR | Mark the checkbox for **Extract text from images using OCR** to extract the text from images using the Optical Character Recognition (OCR) technology. Using this feature, Securiti extracts text from different image types such as PNG, BMP, JPG, JPEG, and PDF documents. Securiti then uses this text for data classification, so the image dimensions that you should follow are: - Specify the minimum pixel ratio between 10,000 to 80,00,000 pixels. - Specify the maximum pixel ratio between 90,000 and 1,00,00,000 pixels. - Specify the minimum aspect ratio between 0 to 10. - Specify the maximum aspect ratio between 1 to 10. > [!NOTE] > **Tip** > > For a better understanding, visit the following: > > - [Common aspect ratio for images and videos](https://www.istockphoto.com/blog/best-practices/design/a-guide-to-video-aspect?utm_source=wp_blog&amp;utm_medium=referral&amp;utm_campaign=migration&amp;utm_term=redirect) > - [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes) **Example**: - For an image with the dimension of 1000x748 where 1000 is the width and 748 is the height. - If you divide the width by height it gives you the aspect ratio, which in this case is 1.33 that you can specify as the aspect ratio. The greater the height, the smaller the aspect ratio. - Set the number of PDF pages containing the images to extract the text from. The number of pages can be specified between 1 and 100. ![text_extraction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31aeedb9-39c1-6733-01f2-b8bd4a52da4f(11).png) |
| Extract text from compressed and archived files | (Optional) Mark the **Extract text from compressed and archived files** checkbox to enable extracting text from the files that you have compressed or archived. You can specify the image dimensions for pixel ratio and aspect ratio. |
| Breach Impact Analysis | Enable the **Breach Impact Analysis** toggle to initiate analyzing the security breaches. This option integrates it with the data breach module. This option displays only if an existing breach is detected for that Connector. > [!NOTE] > **Note** > > This toggle is available for all Unstructured data systems. If a Connector does not support the Discovery scan, then you can see the Breach Analysis toggle on the Data system's **Permissions** tab. |
| Enable Duplicate and Cluster Detection | (Optional) Mark the **Enable Similar Document Cluster Analysis** checkbox to enable the identification of duplicate documents in clusters. ![adv-setting-gitlab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5566e95-6077-194a-819c-d689752c89d2.png) > [!NOTE] > **Note** > > The Discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents. |

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for Tableau Server:

- In the **Sensitive Data** section, perform the following steps:
  - `Choose the **Locality** enabled for your tenant. Securiti shows the data element categories, document categories, content profiles for structured and unstructured data for that locality.
  - Under the specific category, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below. ![Form for selecting localities and data element categories for sensitive data discovery.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 3.35.42 PM.png)

![Overview of structured and unstructured content profiles with various compliance categories listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 3.37.11 PM.png)

- (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per Data element type in each document (up to 20,000) |
  - If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
  - If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the Discovery scan job.

## Schedule settings

Perform the following steps to configure Schedule settings for Tableau Server:

- In the **Schedule**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(47).png)

## Responses settings

Perform the following steps to configure Responses settings for Tableau Server:

(Optional) In the **Responses**, choose what responses Securiti takes when the scan completes. You can choose the following available response actions.

- **Send an Email Notification**: Notify about the scan job through emails. You can specify one or more emails with a relevant email template. Enter the email address(es) and select an email template from the menu.
- Enable the **Trigger Workflow** toggle, and click **Add Workflow**.

![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(12).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.

![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(12).png)

For more information, see [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).

Near the upper right corner of the page, click one of the following:

- **Finish and Activate**, which saves and activates the discovery scan immediately.
- **Save**, which saves the scan configuration without activating it.
- **Save as Draft**, which saves the scan as a draft for completion at a later time.

- The Discovery scan takes time to complete the process depending on the data available in the Data system Instance.
- Refer to the matching procedure to view the Discovery scan results.
  - On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  - On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
