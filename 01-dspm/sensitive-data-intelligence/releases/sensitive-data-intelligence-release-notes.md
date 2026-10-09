---
title: "Sensitive Data Intelligence release notes"
slug: "sensitive-data-intelligence-release-notes"
updated: 2026-09-22T13:31:01Z
published: 2026-09-22T13:31:01Z
canonical: "helpcenter.securiti.ai/sensitive-data-intelligence-release-notes"
area: dspm
modulo: sensitive-data-intelligence
tipo: release
data_captura: 2026-10-06
---

# Sensitive Data Intelligence release notes

## 1.151

### Release updates - September 2026

#### Introducing Document Type AI Tuning for unstructured data

Securiti now lets you correct document type misclassifications across unstructured files at scale using AI Tuning. Using an AI-assisted feedback workflow, you can select a reference file and apply the correct document type across all semantically similar files in a single session.

The following pages under **System Settings** > **AI Tuning** now include a **Document Type** tab alongside the existing **Structured Data** tab:

- Tuning Configuration
- Tuning History
- Tuning Audit Logs

> [!WARNING]
> Important
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - You must upgrade to pod versions 1.151.0 or later to use this feature.

The Document Type AI Tuning popup appears as shown below.

![Graph illustrating document classification based on file name and content similarity.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/documenttypeaituning.png)

For more information, see [Classifying document types using AI Tuning](/latest/docs/classifying-document-types-using-ai-tuning).

#### Introducing new RBAC permissions for Document Type AI Tuning

Securiti has introduced new Role-Based Access Control (RBAC) permissions for AI Tuning of document types. These permissions let you control who can view and manage document type tuning sessions independently, without requiring access to broader AI Tuning configuration settings.

> [!NOTE]
> Note
> 
> To manually update or revert a document type classification for individual files, you must have the **Update Unstructured Data** permission.

Use the following table to understand the RBAC permissions for AI Tuning of document types:

| **Permissions** | **Explanation** | **Dependent permissions** |
| --- | --- | --- |
| `Create Document Type AI Feedback` | Lets you submit AI tuning feedback for document types via the in-product AI Tuning popup. | **Sensitive Data Intelligence**: - `View Document Type AI Feedback` - `View Document Type AI Tuning Settings` |
| `Delete Document Type AI Feedback` | Lets you delete document type AI tuning feedback entries on the **Tuning History** page. | **Sensitive Data Intelligence**: - `View Document Type AI Feedback` - `View Document Type AI Tuning Settings` |
| `View Document Type AI Feedback` | Lets you view document type AI tuning feedback entries on the **Tuning History** page. | **Sensitive Data Intelligence**: - `View Document Type AI Tuning Settings` |
| `Manage Document Type AI Tuning Settings` | Lets you manage access to the document type **Tuning Configuration** resource. | **Sensitive Data Intelligence**: - `View Document Type AI Tuning Settings` **Securiti Platform**: - `View Private Cloud Storage` |
| `View Document Type AI Tuning Settings` | Lets you view document type AI tuning configuration on the **Tuning Configuration** page. | None |

For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).

#### Enabling sensitive data detection for Czech content

Securiti has introduced support for the Czech language in Sensitive Data Intelligence. You can now detect personal data such as names, contact details, and location data in Czech content, across both data element detection and data classification (FR-4210).

The Czech language option appears as shown below.

![List of active localities and languages for tenant entitlements in data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/czechlanguagesupport_dataelements.png)

For more information, see [Supported localities and languages for data classification](/latest/docs/data-classifications).

#### Grouping Blob Scanning settings under Advanced Settings

Securiti has introduced a dedicated **Blob Scanning** section for structured connectors that support blob scanning. It now groups existing settings, including OCR text extraction and text extraction from compressed and archived files, under this section. Securiti hides these settings until blob scanning applies, so you only configure options that take effect.

> [!NOTE]
> Note
> 
> The **Perform Blob Scan** option is currently available for MongoDB and IBM DB2 only.

These settings only appear once you mark the **Perform Blob Scan** checkbox, as shown below.

![Settings for blob scanning and data extraction options in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/blobscanning_discoveryscans.png)

For more information, see [Discovery Scans](/latest/docs/discovery-scans).

#### Viewing unstructured sample data in the Evidence Viewer

Securiti now lets you view unstructured sample data in the **Evidence Viewer**. On the **Unstructured Data Scans** and **Data Remediation** dashboards, expand a file in the **Files** grid and click **View Evidence**, then open the new **Sample Data** tab. The tab displays the file content extracted during the scan, as shown below. Securiti uses this content for Document Type AI Tuning, so you can review the content scope that AI Tuning works from.

Sample data is available for `PDF`, `Document`, `PowerPoint`, `Plain Text`, and `Spreadsheet` files.

> [!WARNING]
> Important
> 
> Sample data is available only for files scanned in Securiti release 1.151 or later, and only when **Collect Evidence** is enabled. For files scanned before this release, the **Sample Data** tab displays “Sample data not available”.

![Evidence viewer displaying data elements and sample data for a discovery scan.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sampledatainevidenceviewer.png)

For more information, see [Accessing evidence files in Securiti](/latest/docs/managing-evidence-files-and-downloads).

#### Viewing policy execution activity

Securiti now provides a consolidated **View Activity** option for Data Labeling and File Quarantine policies. This view brings **Action History** and **Policy Logs** together in a single location, helping you monitor policy execution and investigate policy runs efficiently.

You can use **View Activity** to:

- Track the progress of running policies.
- Review the status and details of each policy run.
- Analyze policy execution logs.

> [!WARNING]
> Important
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The **View Activity** option appears as shown below.

![Overview of policy activity showing completed actions and run details for data remediation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image6(7).png)

For more information, see [Viewing policy activity, action history and logs](/latest/docs/viewing-policy-activity-action-history-and-logs).

#### Exporting run history for Data Tagging policies

Securiti now lets you export **Run History** records for Data Tagging policies as a `CSV` file for offline analysis, auditing, and reporting. After Securiti generates the export file, you receive an email containing a link to download the file. The download link expires after 24 hours.

The **Export** option appears as shown below.

![Overview of run history with completed tagging actions and export options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image7(4).png)

For more information, see [Viewing run history of Data Tagging policies](/latest/docs/tracking-data-tagging-policies-execution-history).

#### Transitioning Structured Data Insights Findings

Securiti has begun transitioning the Structured Data Insights policy to a new architecture that does not generate findings. Starting with Securiti release 1.152, you can view and manage your policy outcomes on the **Data Remediation** page. You can also view data scoped by your existing Structured Data Insights policies.

![Overview of findings with structured data insights and current status updates displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4(12).png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### API updates

Use the following table to understand the API updates made for Sensitive Data Intelligence in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `privaci/v1/admin/classification/ai_tuning/unstructured_document_type/feedback` | POST | We have added this API endpoint in the current release. It lets you submit Document Type AI Tuning feedback. |
| `privaci/v1/admin/classification/ai_tuning/unstructured_document_type/feedback/:id` | DELETE | We have added this API endpoint in the current release. It lets you delete the specified Document Type AI Tuning feedback entry. |
| `privaci/v1/admin/classification/ai_tuning/unstructured_document_type/feedback/files/impacted` | POST | We have added this API endpoint in the current release. It lets you fetch the files impacted by a Document Type AI Tuning feedback entry. |
| `privaci/v1/admin/classification/ai_tuning/vectors/unstructured_document_type/:file_id/similar` | GET | We have added this API endpoint in the current release. It lets you fetch the files similar to the specified file. |
| `privaci/v1/admin/classification/ai_tuning/vectors/unstructured_document_type/embeddings` | DELETE | We have added this API endpoint in the current release. It lets you delete the vector embeddings generated for Document Type AI Tuning. |
| `privaci/v1/admin/policy/data_tagging_policy/run_history_export` | POST | We have added this API endpoint in the current release. It lets you export run history of Data Tagging policies. |

For more information, see [Sensitive Data Intelligence API reference](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html).

---

## 1.150

### Release updates - August 2026

#### Expanding tax form document type detection

Securiti has expanded system document type detection to include 25 tax forms across the following countries:

- Australia
- Canada
- Colombia
- India
- Ireland
- Malaysia
- New Zealand
- Philippines
- Portugal
- Spain
- United Kingdom
- United States

This update improves classification accuracy for country-specific tax documentation during discovery scans.

![Document categories display with various financial tax forms listed for selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 12.43.04 PM.png)

For more information, see [System document categories and types](/latest/docs/supported-system-document-types).

#### Introducing the new AI Tuning settings experience

Securiti has reorganized AI Tuning pages into a dedicated section under **System Settings** > **AI Tuning,** as shown below. This section includes the following tabs:

| Tab | Description |
| --- | --- |
| Tuning Configuration | Lets you configure AI Tuning settings. |
| Tuning History | Lets you view the history of AI Tuning runs. |
| Tuning Audit Logs | Lets you view audit logs for AI Tuning activity. |

Additionally, data sync no longer starts automatically when you reach the **Configure AI Tuning** step in **Tuning Configuration** tab. You must mark the **Enable AI Tuning for structured data** checkbox to start the sync.

This update gives you a single location to manage all AI Tuning settings and history, and lets you control exactly when data sync begins.

![Configuration settings for AI tuning and data synchronization in a system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningnewexperience.png)

For more information, see [Configuring AI Tuning for structured data systems](/latest/docs/using-ai-tuning-for-classifying-columns).

#### Configuring partial word matching for custom data element types

Securiti now lets you control whether anchor keywords match inside larger words when configuring custom data element types, as shown below. Mark the **Perform sub-word search** checkbox in the **Anchors** section to enable partial word matching. For instance, the keyword `card` also matches `cardboard`. Clearing this option restricts matching to exact whole words only.

> [!NOTE]
> Note
> 
> - For existing custom data element types, **Perform sub-word search** is marked by default to ensure anchor keywords continue matching partial words as before.
> - For new custom data element types, it is cleared by default.

![Configuration settings for data classification, including regex and keyword matching options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/performsubwordsearch_dataelements.png)

For more information, see [Configuring custom data element types](/latest/docs/configuring-custom-data-element-types).

#### Viewing dictionary keyphrases for content profiles

Securiti now lets you see exactly which dictionary keyphrases triggered a content profile detection for a file in the **Unstructured Data Scans** dashboard, as shown below. This gives you the context needed to validate detections, investigate unexpected classifications, and act on accurate classification results.

![Overview of data profiles and duplicates in a box discovery scan interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dictionarykeyphrases_unstructureddatascans.png)

For more information, see [Using the Unstructured Data Scans dashboard](/latest/docs/using-the-unstructured-data-discovery).

#### Viewing positive anchor terms in the Evidence Viewer

Securiti now displays **Best Positive Anchor** terms alongside detection results in the **Evidence Viewer** on the **Unstructured Data Scans** dashboard and the **Data Remediation** dashboard. A dedicated **Best Positive Anchor** column shows the anchor term associated with each detection, as shown below. This gives you additional context to understand why a data element was detected.

![Evidence viewer displaying medical record details and data element categories for anesthesia.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bestpositiveanchor_uds(1).png)

> [!NOTE]
> Note
> 
> - Some detections may not have a positive anchor term. In such cases, the **Best Positive Anchor** column displays empty.
> - Securiti also includes the positive anchor term information in the evidence file generated during discovery scans.

For more information, see [Using the Unstructured Data Scans](/latest/docs/using-the-unstructured-data-discovery) dashboard or [Accessing evidence files for policies](/latest/docs/111).

#### Introducing protected Microsoft Purview Information Protection sensitivity labels

Securiti now lets you apply protected Microsoft Purview Information Protection (MIP) sensitivity labels to files through Data Labeling policies. When you apply a protected sensitivity label, the file inherits the encryption settings and access permissions configured in the label. This helps you protect sensitive files and ensure that only authorized users can access them, even after they are shared outside your organization.

To help you identify protected files, the Data Labeling Remediation dashboard now includes the **Protected by Label** filtering property. Use this property to view files protected with Microsoft Purview Information Protection sensitivity labels, as shown below.

> [!WARNING]
> Important
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

![Data labeling interface showing properties and options for Microsoft Purview labels.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(12).png)

For more information, see [Applying protected Microsoft Purview Information Protection sensitivity labels](/latest/docs/protected-sensitivity-labels) and [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Introducing tag-based grouping in Automation Policies

Securiti now lets you use Securiti **Tag Category** as a grouping attribute for file-based entities, including File Insights, File Quarantine, and File ROT, in Automation Policies, as shown below. With this update, you can group entities by tag values and route remediation tasks to the stakeholders associated with those values.

You can also select a tag value in the **Assignee** and **Recipient** fields to dynamically assign remediation tasks and send email notifications to the stakeholder associated with the tag values.

Additionally, you can combine Securiti **Tag Category** with one other grouping attribute, such as **File Owner**. If a file has multiple values for the selected tag, Securiti creates a separate task for each tag value.

> [!WARNING]
> Important
> 
> The tag value used in the **Assignee** and **Recipient** fields must be a valid email address. If the value is missing or invalid, Securiti assigns the task to the Automation Policy owner.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W63FGWMM.png)

For more information, see [Using Automation Policies](/latest/docs/using-automation-policies).

#### Applying remediation actions at the folder level

Securiti now supports applying remediation actions to all files within a selected folder from the **Folder Browser** view in the Data Remediation dashboards, as shown below. Instead of selecting and remediating files individually, you can now select a folder and apply a supported remediation action, such as **Remediate**, to all files within that folder. This helps you remediate large volumes of sensitive data while reducing manual effort.

> [!WARNING]
> Important
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

![Data labeling interface showing selected files and folder browser options for organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image2(14).png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Improving error visibility for failed remediation actions

Securiti now displays a tooltip with the most recent error log message when you hover over the following failed processing statuses on the Data Remediation dashboard:

- Labeling Failed
- Quarantine Failed
- Revert Failed

The tooltip also provides a **View Audit Log** option, which lets you access the relevant activity logs to investigate and troubleshoot failed remediation actions.

> [!NOTE]
> Note
> 
> - The tooltip is available only when a **Processing Policy ID** or **Data Labeling Policy ID** is associated with the failed remediation action.
> - When you select the **View Audit Log** option, Securiti takes you to the **Policy Activity** page. If **Policy Activity** is not enabled for your tenant, Securiti takes you to the **Policy Logs** instead.

![File quarantine status showing revert failure for specific file operations and audit log access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-19 at 10.24.01 AM.png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### API updates

Use the following table to understand the API updates made for Sensitive Data Intelligence in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `privaci/v1/admin/classification/ai_tuning/structured_data_element/feedback` | POST | We have updated the API endpoint to include `structured_data_element` |
| `privaci/v1/admin/classification/ai_tuning/structured_data_element/feedback/:id` | DELETE | We have updated the API endpoint to include `structured_data_element` |
| `privaci/v1/admin/classification/ai_tuning/structured_data_element/feedback/columns/impacted` | POST | We have updated the API endpoint to include `structured_data_element` |
| `privaci/v1/admin/classification/ai_tuning/structured_data_element/columns_support_status` | POST | We have updated the API endpoint to include `structured_data_element` |
| `privaci/v1/admin/classification/ai_tuning/vectors/structured_data_element/:id/similar` | GET | We have updated the API endpoint to include `structured_data_element` |
| `privaci/v1/admin/classification/ai_tuning/vectors/structured_data_element/embeddings` | DELETE | We have updated the API endpoint to include `structured_data_element` |

For more information, see [Sensitive Data Intelligence API reference](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html).

#### Resolved issues

- Fixed an issue in **Structured Data Discovery New Experience** dashboard where filtering any grid (**Table**, **Column**, **Schema**, **Database**, **Structured**, **Discovery Scan**) by **Exact Data Profile** returned zero results, even when Exact Data Match (EDM) profiles were correctly detected during discovery scans (PRIV-234647).
- Fixed an issue where **Structured Data Discovery New Experience** dashboard tiles and node counts showed zero under an **Exact Data Profile** filter, and where the Exact Data Profile node showed no relationship to the **Table** data (PRIV-234647).

#### Known issue

- In Graph Explorer, a direct `Column-to-Exact Data Profile` relationship is not supported. Use the `Table-to-Column` and `Table-to-Exact Data Profile` relationships together to get the same result.

---

## 1.149

### Release updates - August 2026

#### Introducing passport detection support for new EU localities

Securiti has introduced passport detection, classification, and OCR support for the following localities:

- Austria
- Belgium
- Bulgaria
- Croatia
- Cyprus
- Czechia
- Denmark
- Estonia
- Finland
- Greece
- Hungary
- Latvia

OCR-based passport detection lets you scan images and PDF files to detect passport-related sensitive data. Additionally, Securiti lets you classify passport document types and data elements for these localities during discovery scans, as shown below.

![Data classification settings showing active data element categories and localities list.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/passportdetectionsupport.png)

For more information, see [System data element types](/latest/docs/system-data-element-types) and [OCR-supported document types](/latest/docs/ocs-supported-document-types).

#### Refining content profile filter results in structured data dashboards

Securiti has improved the **Content Profile** filter behavior on the **Structured Data Discovery** and **Structured Data Discovery New Experience** dashboards. The filter now returns all the tables with that content profile enabled, including only the columns that directly contributed to that table's overall content profile. This gives you a more accurate and focused view of your classification results (FR-5505).

> [!WARNING]
> Important
> 
> This behavior applies only to data scanned in Securiti release 1.149 or later. For the previously scanned data, the **Content Profile** filter continues to show all the columns in the table.

![Data discovery interface showing selected columns and their classifications for student records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnscontentprofilefilter(1).png)

For more information, see [Using the Structured Data Discovery](/latest/docs/using-the-structured-data-discovery-classic-dashboard) dashboard and [Structured Data Discovery New Experience](/latest/docs/structured-data-discovery-new-experience) dashboard.

#### Configuring Global Negative Anchor Regexes for system data elements

Securiti now lets you configure **Global Negative Anchor Regexes** for system data elements to reduce false-positive detections in specific contexts. A **Global Negative Anchor** is a term that, if present anywhere in a document, suppresses detection of that data element. You can add, edit, and remove negative anchor regex entries using the same input pattern as **Global Positive Anchor Regexes**, as shown below.

![System settings for data classification, including regex options for anchors and values.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/globalnegativeanchors_dataelements.png)

For more information, see [Customizing system data element types](/latest/docs/data-elements-customizing-system-data-element-types).

#### Retiring the Classic Structured Data Discovery dashboard

**Structured Data Discovery Classic Experience** dashboard will retire soon for the tenants with **Data Command Graph** enabled. The **New Experience Structured Data Discovery** dashboard will be the only structured data explorer page in Sensitive Data Intelligence.

For more information, see [Structured Data Discovery New Experience dashboard](/latest/docs/structured-data-discovery-new-experience).

#### Viewing positive anchor terms in the Unstructured Validation Workbench

Securiti now displays positive anchor terms alongside detection results in the **Unstructured Validation Workbench**, as shown below. A dedicated **Best Positive Anchor** column shows the anchor term associated with each detection, giving you additional context to understand why a data element was detected. The anchor term is also visible in the **Metadata Explorer** for each detection.

> [!NOTE]
> Note
> 
> - Some detections may not have a positive anchor term. In such cases, the **Best Positive Anchor** column displays empty.
> - Securiti also includes the positive anchor term information in the evidence file generated during discovery scans.

![Review of sensitive data detections including email, phone numbers, and identification details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bestpositiveanchors_unstructuredvalidationworkbench.png)

For more information, see [Using Validation Workbench for unstructured data](/latest/docs/validation-workbench-for-unstructured-data).

#### Pausing discovery scans on Private Cloud Storage capacity limit

Securiti has introduced automatic pausing of discovery scan when the configured Private Cloud Storage reaches its capacity limit and evidence files can no longer be stored, as shown below. The scan remains paused until you free up storage space or increase the storage quota. To help you take action promptly, Securiti sends an email notification to the tenant owner explaining the reason for the pause, and logs the event in the audit logs.

For more information, see [Discovery scans](/latest/docs/discovery-scan-trigger-node).

#### Applying filters across multiple nodes in the Data Remediation dashboards

Securiti now lets you apply filters across multiple nodes in the Data Remediation dashboards, as shown below. Instead of filtering one node at a time, you can now apply filters across multiple nodes and navigate between them without losing your filter selections. This helps you identify affected files across multiple locations before taking remediation actions.

![Data labeling interface showing file format and system properties for presentations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image9(3).png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Filtering failed remediation actions by Error Code

Securiti now lets you identify failed remediation actions by using the **Quarantine/Revert Error Code** filtering property in the Data Remediation dashboard, as shown below. The property displays the error code associated with failed quarantine and revert operations, helping you identify the cause of failures and troubleshoot remediation issues without reviewing system logs.

![Error code displayed for failed quarantine or revert operation in data management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4(11).png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Improving file handling during Central Quarantine

We have enhanced Central Quarantine to handle files with unsupported characters in their names or folder paths, as well as files whose destination paths exceed the supported length limit. When these files are moved across data systems, Securiti now stores them using compatible file names or hashed directory paths. This prevents quarantine and revert operations from failing because of destination-specific naming restrictions or path-length limitations.

To help you locate these files, the Data Remediation dashboard now includes the following filtering properties:

- Quarantined File Name
- Quarantine Hashed Directory Path

Use these properties to identify files that were renamed or stored under hashed directory paths during quarantine, as shown below.

![File quarantine interface displaying policies and details of quarantined files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image5(9).png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Adding the Scoped column to Data Tagging policy Run History

Securiti has added the **Scoped** column to the **Run History** page for Data Tagging policies, as shown below. The new **Scoped** column displays the total number of nodes included in the policy scope for each policy run.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0NNFVPP6.png)

For more information, see [Viewing run history of Data Tagging policies](/latest/docs/tracking-data-tagging-policies-execution-history).

#### Viewing duplicate files by file format

We have introduced the **Duplicate File Format** widget in the Duplicate Files dashboard, as shown below. The new widget displays duplicate files grouped by file format, helping you identify the file formats that contain the most duplicate files across your connected data sources.

![Dashboard displaying duplicate file types and formats with relevant statistics and data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image8(3).png)

For more information, see [Using the Duplicate Files dashboard](/latest/docs/duplicate-files-dashboard).

#### Making Central Quarantine generally available

With release 1.149, Securiti has made Central Quarantine generally available to all tenants. As part of this update, the **Quarantine Files Within the Same Data System** action has been deprecated for File Quarantine and File ROT policies, as shown below. You can continue to use this action; however, we recommend using the **Quarantine Files To A Central Quarantine Destination** action for new policies to take advantage of the latest features and enhancements.

![Warning about unsupported feature and instructions for configuring quarantine destination settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image1(10).png)

For more information, see [Creating a File Quarantine policy](/latest/docs/creating-a-file-quarantine-policy) and [Creating a File ROT policy](/latest/docs/creating-a-file-rot-policy).

#### Resolved issues

- Fixed an issue where discovery scans configured with **Exact Data Matching** continued processing files even when the exact data index failed to download, resulting in missed detections. Securiti now stops processing files until the index is successfully downloaded. Download failures are recorded in the **Audit Log**, and canceling the scan stops the retry (PRIV-250586).
- Fixed an issue where tables containing PII data elements were not being classified under the **PII Structured** content profile during structured discovery scans (PRIV-250116).

#### API updates

Use the following table to understand the API updates made for Sensitive Data Intelligence in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/data_discovery/discovery_scan/paginated-datasources?connector_type_id=alfresco_onprem&amp;limit=10&amp;offset=0` | GET | We have added this API endpoint in the current release. It lets you fetch all the paginated datasources for the specified data system. |
| `/privaci/v1/admin/data_discovery/discovery_scan/paginated-data_assets?limit=10&amp;offset=0` | POST | We have added this API endpoint in the current release. It lets you fetch all the paginated data assets associated with specified data system. |

For more information, see [Sensitive Data Intelligence API reference](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html).

---

## 1.148

### Release updates - July 2026

#### Introducing Swedish language support for content classification

Securiti now supports the Swedish language in Sensitive Data Intelligence. It lets you detect personal data, such as names, contact details, location data, and key identifiers in Swedish content (FR-4212).

![List of active localities and languages for tenant entitlements in a data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-05 at 3.31.01 AM.png)

For more information, see [Data classifications](/latest/docs/data-classifications).

#### Managing content profiles for CLOB columns

Securiti now displays content profiles for CLOB columns across different pages, including:

- Structured Data Discovery New Experience dashboard
- Structured Data Discovery Classic Experience dashboard
- Table Training page
- Review Classification popup

With this update, you can:

- View the content profile assigned to each CLOB column directly in the column-level grid
- Apply content profile filters at the column and table level
- Manage content profiles for CLOB columns directly from the Review Classification popup and Table Training page.

![Database column selection interface showing content profiles and data element types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-24 at 4.12.43 PM.png)

For more information, see [Using the Structured Data Discovery dashboard](/latest/docs/using-the-structured-data-discovery-classic-dashboard) and [Structured Data Discovery New Experience dashboard](/latest/docs/structured-data-discovery-new-experience).

#### Introducing Explorer Mode on the Unstructured Data Scans page

Securiti has introduced **Explorer Mode** on the **Unstructured Data Scans** page, replacing the previous **Resource Path** treemap chart. **Explorer Mode** lets you drill down through folder hierarchies, sort results, and apply filters by data system, folder, or file name directly within the view. For instance, you can trace which folders contain sensitive data or identify the exact file path where a detection occurred.

> [!NOTE]
> Note
> 
> Consider the following when using **Explorer Mode**:
> 
> - **Explorer Mode** is available only for data system types that support folder hierarchy, such as Amazon S3, Google Cloud Storage, and SharePoint.
> - Exporting as CSV always exports the flat list of files regardless of whether **Explorer Mode** is enabled.

![Overview of file organization and data distribution in a workspace interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/explorermode_unstructureddatascans(1).png)

For more information, see [Using the Unstructured Data Scans dashboard](/latest/docs/using-the-unstructured-data-discovery).

#### Viewing CLOB column evidence in Validation Workbench

Securiti has enhanced the **Structured Validation Workbench** to support evidence preview for CLOB columns. Each CLOB column now appears as a single record in the Validation Workbench list. Selecting a CLOB column opens the evidence popup, displaying the full evidence preview. You can also assign multiple data elements to CLOB columns.

![Overview of data elements including grades, names, and contact information in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidenceviewer_structuredvwb(1).png)

> [!WARNING]
> Important
> 
> You must upgrade to pod versions 1.148.0 and above to use this feature.

For more information, see [Using Validation Workbench for structured data](/latest/docs/validation-workbench-for-structured-data).

#### Configuring scan scope for Microsoft Outlook discovery scans

Securiti now lets you control the scan scope for Microsoft Outlook discovery scans by choosing whether to include attachments and email body content. Mark the **Scan Attachments** and **Scan Mail Content** checkboxes under **Advanced Settings** to include them in the scan scope, or clear them to exclude specific content types. This gives you greater flexibility to tailor your scan configuration based on your organization's data discovery requirements.

> [!WARNING]
> Important
> 
> - These options are supported for both Hyperdrive and Non-Hyperdrive discovery scans. You must upgrade your pod or outpost version to release 1.148.0 and above to use this feature.
> - Both checkboxes are marked by default on existing scans after upgrading to pod versions 1.148.0 and above.
> - At least one checkbox must be marked to run a scan. Securiti won't let you run a scan if both checkboxes are cleared.
> - These options are only available for the Microsoft Outlook (self-hosted) connector.

![Settings for scanning attachments and mail content in Microsoft 365 Outlook.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-06 at 3.46.25 PM.png)

For more information, see [Discovery scans](/latest/docs/discovery-scans).

#### Introducing the Duplicate Files reporting dashboard

We have now introduced the **Duplicate Files** reporting dashboard that provides a comprehensive view of duplicate files across connected data systems, as shown below. The dashboard surfaces key metrics such as reclaimable storage, duplicate file count, and sensitive duplicate data. It also highlights the top data systems, file owners, and folders with duplicate files. With this update, you can identify areas with the highest duplication, prioritize cleanup efforts, and make more informed data governance decisions.

![Dashboard displaying duplicate files, storage statistics, and sensitive labeled files overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(8).png)

For more information, see [Using the Duplicate Files dashboard](/latest/docs/duplicate-files-dashboard).

#### Filtering files by Data Labeling Policy ID in the Data Remediation dashboard

Securiti now lets you filter files in the Data Labeling remediation dashboard using the new Data Labeling Policy ID filter, as shown below. The **Data Labeling Policy ID** filter displays the policy ID that applies the sensitivity label to the file. It also identifies externally labeled files, where an external source applies the sensitivity label instead of Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B7M0JDPP.png)

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

#### Building flexible Data Labeling policy scope queries

Securiti now lets you define the Data Labeling policy scope queries without requiring the **Files** node to be the root node of your query, as shown below. With this update, you can place the **Files** node anywhere in the query and build more flexible scope queries. It helps you create scope query structures using different node relationships instead of following a fixed query hierarchy.

![Graph Explorer interface displaying AWS S3 data system and asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image2(11).png)

For more information, see [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies).

#### Introducing email notifications for the Data Labeling policies

Securiti now supports **Send an Email Notification** action in the Data Labeling policies, as shown below. With this update, you can configure email notifications to alert the data system owner, selected users, or both. This helps keep relevant stakeholders informed about policy execution and labeling activities.

![Email notification settings for policy changes, including user selection and action buttons.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image6(5).png)

For more information, see [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies).

#### Introducing Saved View in the Automation policies

We have now introduced the **Saved View** feature in the Automation policies that lets you use previously saved scope queries from the Graph Explorer to define the Automation policy scope, as shown below. With this update, you can reuse existing scope queries to configure automation actions for scoped data.

![Dashboard view displaying file counts for various asset types and hosting services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4(9).png)

For more information, see [Using Automation Policies](/latest/docs/configuring-automation-policies).

#### Resolved issues

- Fixed an issue where MIP label extraction on certain CSV files inside a ZIP file caused an out-of-memory error in the scanner (PRIV-243113).
- Fixed an issue where clearing the **Select All** checkbox in the **Unstructured Validation Workbench** did not clear the individually selected detections (PRIV-247103).

---

## 1.147

### Release updates - June 2026

#### Introducing passport detection support for new localities

Securiti has introduced passport detection, classification, and OCR support for the following localities:

- Algeria
- Bangladesh
- Libya
- Morocco
- Somalia
- Sudan
- Thailand
- Tunisia

This lets you classify passport document types and data elements for these localities during discovery scans. Additionally, OCR-based passport detection lets you scan images and PDF files to detect passport-related sensitive data.

![Data elements and classifications for tenant entitlements in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Passport detection support.png)

For more information, see [System data element types](https://helpcenter.securiti.ai/docs/system-data-element-types).

#### Introducing New Zealand visa detection support

Securiti has introduced New Zealand visa detection support, letting you classify visa document types and data elements during discovery scans. OCR-based detection is also supported, letting you scan images and PDF files to detect visa-related sensitive data.

![Overview of data elements and categories in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/NZ Visa support.png)

For more information, see [System data element types](https://helpcenter.securiti.ai/docs/system-data-element-types).

#### Improving scan job evidence report emails

Securiti has enhanced scan job evidence report emails to include a separate evidence file link for each data system when multiple content profiles are configured. Previously, only a single combined evidence file link was generated. This gives you better visibility into scan results across all your data systems.

> [!NOTE]
> Note
> 
> You receive this email only if you enable the **Send an Email Notification** option during the discovery scan creation.

For more information, see [Using the Unstructured Data Scans dashboard](https://helpcenter.securiti.ai/docs/using-the-unstructured-data-discovery).

#### Recategorizing UK NINO to Government Identifiers

We have recategorized the UK National Insurance Number (NINO) from the **Medical** category to **Government Identifiers**. This ensures UK NINO is correctly classified under the appropriate identifier category, improving the accuracy of your data element classifications and scan results.

> [!WARNING]
> Important
> 
> Following this change, Securiti no longer displays UK NINO under the **Medical** category for any previous configurations, such as policies and dashboard reports. You must update these configurations to reflect the recategorisation.

For more information, see [System data element types](https://helpcenter.securiti.ai/docs/system-data-element-types).

#### Removing labels from files in the Data Remediation dashboard

Securiti now lets you remove labels from files through the Data Labeling Remediation dashboard, as shown below. With this update, you can choose to remove specific labels or all labels from the selected files.

> [!NOTE]
> Note
> 
> The label removal process varies by data system type. Google Drive supports multiple labels per file, so you can remove one or more labels from a file in a single operation. Microsoft Information Protection (MIP) supports only a single label per file, so removing the label leaves the file with no label applied.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IXYFWMDF.png)

For more information, see [Using Data Remediation dashboards](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards).

#### Viewing remediation actions for deleted policies

We now let you view files that were quarantined or reverted by policies that have been deleted, as shown below. With this update, you can track past quarantine and revert actions even after the originating policy no longer exists.

> [!NOTE]
> Note
> 
> Users with **Manage Owned** or **View Owned** policy permissions cannot access this view.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-3HNEVW6X.png)

For more information, see [Using Data Remediation dashboards](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards).

#### Tracking Data Tagging policy

Securiti now lets you view the execution history of your Data Tagging policies through the new **Run History** option, as shown below. With this update, you can monitor tagging activity, identify issues, and verify outcomes across your Data Tagging policies without relying on manual tracking.

For each run, the **Run History** displays key details such as the **Policy Name**, **Status**, **Start Time**, and the count of **Processed**, **Succeeded**, **Skipped**, and **Failed** nodes.

Additionally, Securiti lets you click **Details** on any entry to open the **Step Details** view, which shows the progress of individual policy nodes, start time, and any error messages for that run.

> [!WARNING]
> Important
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZXGRSO1T.png)

For more information, see [Configuring Data Tagging Policy](https://helpcenter.securiti.ai/docs/configuring-data-tagging-policy).

#### Introducing Azure Files support for central quarantine

We now support the Azure Files data system for central quarantine in File Quarantine policies, as shown below. With this update, Securiti moves sensitive files to a designated quarantine location within Azure Files when it detects a policy violation.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9HJKW29I.png)

> [!NOTE]
> Note
> 
> To use Azure Files data system for central quarantine in File Quarantine policies, enable the **Allow Quarantine actions on this Data System** option while authenticating the Azure Files connector.

For more information, see [Using Central Quarantine destination](https://helpcenter.securiti.ai/docs/using-quarantine-destinations).

#### Detecting and quarantining duplicate files

Securiti has now added support for detecting duplicate files and managing them through File Quarantine and File ROT policies, as shown below. With this update, you can now use the `Is Duplicate=True` condition in policy scopes to locate duplicate files and move them to designated quarantine locations.

> [!NOTE]
> Note
> 
> - Securiti detects duplicate files only within the selected organization and does not show matching duplicate files that exist in other organizations under the same tenant.
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

![Graph Explorer interface displaying checksums and file counts for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image5(7).png)

For more information, see [Using File Quarantine Policies](https://helpcenter.securiti.ai/docs/using-file-quarantine-policies) and [Using File ROT Policies](https://helpcenter.securiti.ai/docs/using-file-rot-policies).

#### Scoping active policies in Automation policies

Securiti now automatically applies a default `Active=True` filter when you scope File Insights, File Quarantine or File ROT policies in Automation policy, as shown below. With this update, you can scope only active policies when setting up automations.

> [!NOTE]
> Note
> 
> This filter is not mandatory. You can remove it if you want to include inactive policies in the scope as well.

![Automation settings for File Insights with active scope rule and action options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(7).png)

For more information, see [Configuring Automation Policies](https://helpcenter.securiti.ai/latest/docs/en/configuring-automation-policies).

#### API updates

Use the following table to understand the API updates made for Sensitive Data Intelligence in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/policy/labelling_operation` | POST | We have added this API endpoint in the current release. It lets you remove selected label(s) from file(s) in the Data Labeling Remediation dashboard. |
| `/privaci/v1/admin/policy/labelling_operation?ref=remove_all` | POST | We have added this API endpoint in the current release. It lets you remove all label(s) from file(s) in the Data Labeling Remediation dashboard. |
| `/reporting/v1/sources/query?ref=getPolicyNames` | POST | We have added this API endpoint in the current release. It lets you track execution history of a Data Tagging policy. |

For more information, see [Sensitive Data Intelligence API reference](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html).

#### Resolved issues

- Fixed an issue where evidence links were populated even when the evidence upload failed (PRIV-240208).
- Fixed an issue where dictionary counts exceeding three figures were not displaying correctly on the **Dictionary** page (PRIV-240451).
- Fixed an issue where document category descriptions did not provide sufficient context (PRIV-243430).
