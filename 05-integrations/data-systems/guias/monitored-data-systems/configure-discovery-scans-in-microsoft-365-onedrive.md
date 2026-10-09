---
title: "Configuring discovery scans in Microsoft 365 OneDrive"
slug: "configure-discovery-scans-in-microsoft-365-onedrive"
updated: 2026-06-22T04:17:12Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-microsoft-365-onedrive"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring discovery scans in Microsoft 365 OneDrive

> [!NOTE]
> **Note**
> 
> You can't run a Discovery scan from the **Permissions** tab in your activated Data system Connector if the Data Inventory and Entitlement Sync Scope section is empty.

This section describes creating a Discovery scan for Microsoft 365 OneDrive. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

> [!CAUTION]
> **Caution**
> 
> We recommend you do not retry running scans in case of "access denied errors" such as that for an inaccessible site or library.

To configure a Discovery scan in Microsoft 365 OneDrive:

1. On the **Create Discovery scan** page **Scan details** section, enter a convenient name and description for the scan job.
2. In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Microsoft 365 OneDrive**. |
| Select Data Systems | Choose the specific Data system instances to scan. |
| Select Primary Scan | Specify any of your older scans as primary or the current one. Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. > [!NOTE] > **Note** > > When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured Data system. Click the **View Scans** link to view the specified scan on the **Discovery Scans List** page. |
3. In the **Data system Scope** section, you can select either **Group(s)** or **User(s)** as the **Discovery scan** scope.

Choose one of the **Scopes** below:
  - If you choose **Group(s)** from the **Specify Discovery scan Scope(s)** menu:
    - Select the OneDrive groups from the **Specify Group(s)** menu to include in the scan. You can select all or multiple site groups from the menu.
  - If you choose **User(s)** from the **Specify Discovery scan Scope(s)** menu:

> [!NOTE]
> Note
> 
> - When you scope a discovery scan to specific users, Securiti scans content stored in each scoped user's personal OneDrive only. This includes files and folders the user owns, uploads, or explicitly adds to their OneDrive. Content that is merely shared with the user, but not added to their OneDrive, is not scanned.
> - The **File Owner** field in Unstructured Data Discovery results reflects the OneDrive site owner, not the original file author. Files created by other users but added to a scoped user's OneDrive are scanned and attributed to the scoped user. If your scan results show file owners beyond the scoped users, this is because OneDrive attributes file ownership based on the last modifier, not the creator. This is expected behavior.
    - Enter the user's name in the **Specify User(s)** field and select it or choose all from the menu to include in the scan. You can also select all or multiple users.

To increase the scope of OneDrive users, you can select up to 10,000 OneDrive users for scanning through a CSV file.

> [!NOTE]
> **Note**
> 
> For more than 10,000 users, Securiti shows an error `CSV file contains more than 10,000 items, Max csv size limit is 10k`.
      1. To see the CSV file format supported by Securiti, click **View Sample**. A sample CSV file that includes the OneDrive users is downloaded to your system’s **Downloads** folder. You can create your CSV files using the sample that you have downloaded.

![OneDriveUsersSample.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dbec8ce9-6ef5-4fcc-2477-cebd061f14cb.png)
      2. To upload a CSV file, click **Upload CSV** and choose a CSV file from your system.

> [!NOTE]
> **Note**
> 
> The CSV file should be in the above format which can be user email IDs or user names.

![dsScopeOneDrive.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4973fd6-78f2-0522-9a66-408995858d59.png)

Once you upload the CSV file, it shows you the users list on the **User(s) Added** popup.
      3. On the **User(s) Added** popup, select the users from the list by following methods.
        1. Mark the checkboxes for users from the list you want to include in the scan.

![1-by-1-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b5c04e6-abf7-4bd3-fec8-9d3957d83e93.png)
        2. To include all users:
          1. On the top left in the popup, mark the checkbox.

It opens a menu.
          2. Click **Select all across all pages** or **Select all on this page** or **Select none**, depending on your requriement.

![all-checkboxes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34459235-0913-1135-882e-e70dc5cd9b33.png)
        3. You can also add new users if those are not available in the CSV list.
          1. On the top right in the **User(s) Added** popup, click **Add a User.**

![click_Add_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b9136f26-42f9-9ff3-b58f-6b44755defad.png)
          2. Search the user that you want to add in the list and click down-arrow icon.

It shows you the user(s) against the name you searched if those are available in the system.

![OneDriveUsersLeftCheckbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea592957-d285-e33a-40b9-2f135fdf8d45.png)
          3. Mark the checkbox for this user to add in the list.
        4. Once you have selected users to add in the scan, scroll down and click **Save and Continue.**

It leads you to **Data system Scope** section where you can make changes to the user(s) csv and can include or exclude users by clicking on **Edit Selection** icon. You can also remove the CSV file by clicking on **Remove** icon.

![edit-selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb3d757d-94cb-6639-30c2-351f14f3d261.png)
4. Under the **Scan Conditions** section, select your desired inclusion or exclusion attribute:

For the **Folder Path** scan condition, you can use the following Prefix and Regex operators:

> [!NOTE]
> **Note**
> 
> - The Folder Path scan condition does not work on files within the OneDrive library that correspond to the scoped group.
> - If your folder name has spaces in it, ensure that the folder path contains the correct folder name with spaces. See an example below.
> 
> Documents/OCR Folder
  - **Object Extension Category**
  - **Folder Path**
  - **Object Name**
  - **Object Extensions**
  - **Object Size**
  - **Created Date**
  - **Last Modified**
  - **Prefix Match**: When using **Prefix Match** operator, add your root directory as a prefix in your folder path. See the example below.
  - If the path to your folder is: “My files/FolderX/FolderY”, replace **My files** with **Documents** as the root directory. The updated folder path looks as below.

*Documents/FolderX/FolderY*
  - **Regex Match**: When using regex, regular tokens or folder names can be used to search the root directory.

If you want to Match the folder that contains the word "FolderX". Use the folder name for the regex pattern. See the example.

**FolderX** or '*FolderX*'

![Folder-path-condition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d757da5-59f0-019e-b691-394d27af09c3.png)

Perform the following steps to obtain the folder path from your OneDrive.
    1. In your Microsoft 365 OneDrive, click **More details** in the flyout menu to the right and record its folder path that would look similar to the example below.

![More_details_OneDrive.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f84833dd-5162-d4da-36ec-7d47f14d9426.png)

**<*https://datasubjectrequest-my.onedrive.com/personal/devuser_datasubjectrequest_net/Documents/OCR folder*>**

Record the part after the drive name, which is "devuser_datasubjectrequest_net."
    2. If your folder name has spaces, specify the path with spaces as shown in example below.

*Documents/OCR Folder*

Enter the path under Scan Conditions alongside other required information to perform scanning.
5. In the **Advanced Settings** section, use the following settings for your Structured data systems. The settings available vary by Data system type.
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.
  2. Under the **Sampling** section, perform the following settings:

    1. Mark the checkbox for **Unstructured data** to select the sample of unstructured data using the percentage and size of the dataset.

> [!NOTE]
> **Note**
> 
> If you don’t mark the checkbox for Unstructured data, Securiti scans 100% of the files with a limit of 10 GB, which are part of this discovery scan scope. Marking the **Unstructured** **data** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of unstructured files that you want to include in the scan. Securiti uses probability approach to select files based on the specified percentage and scans only the selected files. > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Add the size of each file that you want to include in the scan. For instance, if you set the unstructured sampling to 1MB, but a file is 3MB and contains personal or sensitive data, Securiti scans only 1MB of that file. |
    2. Mark the **Semi-structured** data checkbox and specify the percentage of files and the maximum number of records to include in this scan.

> [!NOTE]
> **Note**
> 
> If you don’t enable the **Semi-structured data** checkbox, Securiti scans 100% of these file types with no size or record limit. Marking the **Semi-structured** data checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of semi-structured files that you want to include in the scan. These file types include: - AVRO - PARQUET - XLSX - CSV - TSV - ORC > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of semi-structured scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan upto | Specify the sample of records from semi-structured data that you want to include in the discovery scan. For example, if you specify a sample of 100 records in a discovery scan, Securiti shows 100 rows were detected for data elements under the discovery scan results. > [!NOTE] > **Note** > > There is a limit to scanning 100,000 records in the case of semi-structured data. |
  3. Mark the **Scan MPIP Encrypted Files** checkbox if you want to decrypt and scan your OneDrive files protected by Microsoft Purview sensitivity labels. To learn more about creating sensitivity labels for applying encryption, see [Microsoft documentation.](https://learn.microsoft.com/en-us/purview/encryption-sensitivity-labels)

> [!NOTE]
> Note
> 
> - Enabling this option increases discovery scan time because the scanner must retrieve, decrypt, and process each protected file before analysis. Expect longer scan durations compared with scans of unencrypted content.
> - Securiti evaluates the file size condition before decrypting files with encrypted labels. Although encrypted files are usually compressed, their size might increase during decryption.
    - **Prerequisites for scanning MPIP-encrypted files:**
      - You must activate the Microsoft Purview Information Protection (Cloud) connector in the same Securiti tenant. For more information, see [Activate the Microsoft Purview Information Protection connector](/v1/docs/activate-the-microsoft-purview-information-protection-connector-in-securiti).

> [!CAUTION]
> Warning
> 
> If the MIP connector is activated in a different tenant, scanning doesn't include files with encryption labels.
      - You must upgrade your pod version to release 1.138 or higher.
  4. Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

Common image types include JPG, PNG, BMP, JPEG, and so on.

> [!NOTE]
> **Note**
> 
> Text extraction from images using OCR is available only in environments where pods have been deployed. Securiti, then utilizes the extracted text for data classification.

Marking the **Extract text from images using OCR** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Min/Max megapixels | Set the minimum and maximum megapixels between 0.1 to 50, as Securiti skips images that exceed this limit, while the minimum default value is set to 0.01 and the maximum default value is set to 8. |
| Min / Max Aspect Ratio | Set the minimum and maximum aspect ratios between 0.2 (e.g., 1' × 5') and 10, as Securiti skips images that are too thin or shallow, making them unsuitable for scanning. The minimum default value is set to 0.2, and the maximum default value is set to 5. **Example** For an image with dimensions of 1000×748 (where 1000 is the width and 748 is the height, the aspect ratio is calculated by dividing the width by the height, which in this case becomes 1.33. We can adjust it according to the recommended setting to achieve the recommended aspect ratio between 0.2 to 5. > [!NOTE] > **Tip** > > For a better understanding of image dimensions and > > aspect ratios, visit the following: > > [Common aspect ratio for images and videos](https://marketing.istockphoto.com/blog/aspect-ratio/) > > [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes) To use OCR settings for efficient scanning > > performance, see [Use case examples of text extraction from images](/latest/docs/scan-conditions-to-use-ocr-settings). |
| Number of pdf pages | Set the number of PDF pages between 1 and 100 in the PDF document that should be scanned by our OCR engine. |
  5. Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
  6. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  7. Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

Username

    - Email
    - Passport Number
    - Driver License Number
    - US SSN
    - TSA Precheck Number
    - US Tax Payer ID
    - US DoD ID Number
    - US VISA Number
    - US Alien Registration Number
    - IN Aadhaar Card Number
    - IN PAN Number
    - BR CPF
    - AU Medicare Number
    - AU Tax File Number
    - NZ NHI

A popup appears about the data elements that are automatically enabled for DSR processing.
  8. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
6. In the **Sensitive data** section, apply the following settings:
  1. Choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(23).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(23).png)
7. (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

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
8. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(64).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(58).png)
9. (Optional) In the **Responses** section, apply the following settings:
  1. Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. Enable the **Trigger Workflow** toggle to specify a specified Workflow. Then, click **Add Workflows**. To do this, configure a [Discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
10. (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections, or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - (Optional) In the Responses area, to extract your unstructured Schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register Schema** checkbox.
11. Near the top right side of the page, click **Finish and Activate**.
12. Refer to the matching procedure to [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).
  1. On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  2. On the **Scan Scope** Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

**Job Scan Stats** might show the difference between the estimated files and the actual files scanned. Files count and file size can also show the difference due to the use of API.

> [!NOTE]
> **Note**
> 
> Securiti uses *getOneDriveUsageAccountDetail API* that includes data for all users, including deleted users, who lack a license, or possess a license but are not provisioned. As a result, the data size reported by this API might not accurately reflect the data size scanned

#### Resolve the Redis memory issue due to Job Scan Stats storage

The Discovery scan process within the Sensitive Data Intelligence module leverages **Redis memory** to manage and store Scan statistics. These statistics are displayed on the Discovery Scans page to provide insights into scan activities and results. This feature helps optimize performance and enables real-time visibility into scan progress and outcomes.

If you prefer not to use Redis memory for storing Scan statistics, this feature can be disabled. To do so, contact the Securiti support team at [support@securiti.ai](mailto:support@securiti.ai).

> [!NOTE]
> **Note**
> 
> Securiti manages displays owners' field for OneDrive files displayed in **Data Command Graph** and **Unstructured Data Discovery** results by following a structured fallback logic, especially when email addresses or display names are missing or incomplete.
> 
> - If the user creates a file:
>   - Securiti first uses the user’s email address.
>   - If the email is not available, it falls back to the user’s display name.
> - If the system generates a file:
>   - Securiti displays the application’s display name, since application-created files typically don't have an associated email.
> - If neither user nor application-generated details are available:
>   - Securiti uses information from the drive owner:
>   - First, it uses the drive owner’s email address.
>   - If that is not available, it falls back to the drive owner’s display name.
