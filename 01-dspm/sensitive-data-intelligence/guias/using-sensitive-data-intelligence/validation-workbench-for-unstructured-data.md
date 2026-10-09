---
title: "Using Validation Workbench for unstructured data"
slug: "validation-workbench-for-unstructured-data"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/validation-workbench-for-unstructured-data"
stale: true
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Validation Workbench for unstructured data

The Validation Workbench helps you review and validate classifications for unstructured data sources. It organizes the review process into sessions so you can focus on a defined set of detections and track the outcome of your review.

Within a session, you can review detections across files, inspect the detected evidence, and see related details such as the data element, file name, file location, and data system instance. You can then confirm the classification, reject it, or update it manually when the detected data element is incorrect.

The Validation Workbench also summarizes review results for each session and provides analytics to help you understand detection accuracy across all reviewed detections and by data element type.

> [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - You must use pod **version 1.143.0** and above to use Validation Workbench for unstructured data.
> - AI Tuning is currently only available for structured data systems.

You can use the Validation Workbench for unstructured data to:

- Review detections across files in a session
- Examine detected evidence before accepting or updating a classification
- Reject incorrect detections and update them individually
- Revisit reviewed files and update classifications
- Monitor detection accuracy for all reviewed detections and by data element type

## Creating a new validation session and using filters

You can create a validation session to review, edit, and validate classifications for unstructured data. These sessions let you add users as co-owners so they can review and edit classifications based on their assigned permissions.

> [!WARNING]
> Important
> 
> Validation sessions in the **Unstructured Validation Workbench** do not impact the future classifications.

To create a new validation workbench session, follow the steps below:

1. From the sidebar, hover over **Sensitive Data Intelligence** and select **Data Classification** > **Validation Workbench**.

![Dashboard displaying data classification and findings by risk severity metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.01.01 PM.png)
2. From the **Data Type** sidebar on the left, choose **Unstructured**.
3. If multiple organizations are enabled, choose the required one from the **Organizations** menu. Selecting an organization displays sessions specific to that organization and creates new sessions within it.
4. To create a new session, from the upper right corner of the page, click **+ New Workbench Session**.![Overview of Validation Workbench showing sessions for structured and unstructured data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.02.45 PM.png)
5. On the **New Workbench Session** popup:

![Creating a new validation workbench session for unstructured data sources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.04.12 PM.png)

> [!NOTE]
> Note
> 
> If you remove yourself from the list of owners during session creation, you lose access to that session.
  1. Enter the session name.
  2. (Optional) Enter the suitable description stating the purpose of the session.
  3. Choose **Unstructured** from the **Data Type** menu.
  4. Add the relevant owners.
6. Click **Save** to create the session. After the session is created, you are redirected to the session’s page.

> [!NOTE]
> Note
> 
> To ensure random sampling and optimal performance, detection limits are applied. The following detections are ingested for review:
> 
> - Up to 30 detections per file
> - Up to 10,000 detections per data system
> - Up to 2,000,000 detections per session
> 
> The total detections shown in the dashboard may be higher, as it includes all detections across your data.
7. Click **Add** (plus icon) to add properties such as **Data System**, **Data Element Type**, and **Scan Job ID**. Then choose the required operator filters to restrict the scope of detections to review. In this example, the filter is configured to display all data elements except **Email Address** and **US Taxpayer ID**.

![Interface for managing unstructured data sources with highlighted data element options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.10.00 PM.png)
8. After applying the appropriate filters, start reviewing and validating the classifications.

![Overview of unstructured data sources with detected sensitive information for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.10.42 PM(1).png)

> [!NOTE]
> Note
> 
> - Once you validate any detection within a session, the filters are locked and can not be changed.
> - A detection can only be validated once, and the validated detection does not show up again in any session. The validated detections can be viewed in their respective sessions.
> - Edits made in a Validation Workbench session are not reflected in the evidence files until they are written back through an active appliance.

## Reviewing and validating classifications

After applying the required filters, you can review the detections, update data elements manually, or mark detections for review later.

To manually update a classification:

1. Click **Edit** (pencil icon).

![Review of unstructured data sources with highlighted phone numbers and sensitive information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.10.42 PM(2).png)
2. Choose the relevant data element type(s) from the **Data Element Type** menu and click **Apply & Save Selection** to apply the selected data element type.

![Interface displaying unstructured data sources with detection options and search functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.10.58 PM.png)

> [!NOTE]
> Note
> 
> To perform a manual bulk edit of **Data Element Types**, use the selection checkboxes on the left side to select multiple detections, and then choose the required data element type.
> 
> ![Data review interface showing names and selection options for unstructured data sources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 11.30.45 PM.png)
3. (Optional) To review detections of secondary importance, mark them **Review Later**.

![Overview of unstructured data sources with highlighted detection elements and review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 11.47.48 PM.png)

> [!NOTE]
> **Note**
> 
> The detections marked as **Review Later** appear again for validation in the session. Any changes made to data elements in those detections are discarded.
4. After you review and update all the detections, click **Complete Review** to validate the classifications.

![Summary of reviewed data elements and their classifications in the validation workbench.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.15.28 PM.png)

A popup appears showing the total number of detections that were:
  - Reviewed
  - Updated Manually
  - Set to review later

### Viewing evidence and metadata for detections

While reviewing the detections, you can view the detected evidence and the metadata for the files. To view the details, click the icon adjacent to the detected entry.

![Review of unstructured data sources with highlighted sensitive information and data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-14 at 10.27.00 PM.png)

#### Viewing metadata for the classification

The **Metadata** tab provides various details about the detection to build a better understanding of the detection’s context.

![Validation Workbench displaying unstructured detections and metadata for document review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metadata_unstructuredvwb.png)

Use the table below to understand the metadata fields displayed in the popup:

| Field | Description |
| --- | --- |
| Path | Displays the location of the detected file in the connected data system. For example, **connector-automation/.** |
| Detection | Displays the detected value during scanning. Examples include **Steve**, **Emmanuel**, and **Lehner.** |
| Data Element Type | Displays the assigned classification to the detection. Examples include **First Name**, **Last Name**, and **City Name**. |
| Best Positive Anchor | Displays the anchor term that provides the strongest supporting evidence for the detection, giving you additional context to understand why the data element was detected. For example, **Account Number**. |
| Anchor Details | Displays the details of where that particular anchor term was detected in the data. For example, **-9 chars, Ln 12.** |
| File Format | Displays the file format of the detected file. For example, **Spreadsheet**. |
| Data System Type | Displays the name of the data system where the file resides. For example, **Azure Blob Storage**. |
| Data System | Displays the name of the data system instance where the file resides. For example, **47048**. |
| First Scan Time | Displays the time when the file was first scanned. For example, **Jan 21 2026, 5:07 pm.** |
| Last Scan Time | Displays the time when the file was last scanned. For example, **Jan 21 2026, 7:15 pm.** |
| Organization | Displays the organization name to which the file belongs. Examples include **Default Organization** and **CC Team**. |
| File Created Time | Displays the time of file creation. For example, **Feb 10 2026, 07:10 pm.** |
| File Modified Time | Displays the time of file modification. For example, **Feb 10 2026, 07:10 pm.** |

#### Viewing evidence for the classification

The **Evidence** tab shows a snippet of the file where the detection occurred. Content is securely fetched from Private Cloud Storage (PCS) using signed URLs. The detected value appears highlighted so you can easily identify it within the file content.

![Validation Workbench displaying unstructured detections and sensitive data review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidencetab_unstructuredvwb.png)

Use the evidence to:

- Confirm that the detected value is correct.
- Understand the context of the detection within the file.

Knowing evidence makes it easier to decide whether to accept the classification or update it manually.

### Setting sample size for detections

Securiti displays 50 detections by default. However, you can choose to view 25, 50, or 100 detections per session to improve review speed and flexibility for large datasets.

To change the number of detections displayed in a session, choose **25**, **50**, or **100** from the **Sample up to** menu, as shown below.

![Overview of unstructured data sources with highlighted detection details and review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.09.49 AM.png)

> [!NOTE]
> Note
> 
> The Validation Workbench displays the selected number of classifications (25, 50, or 100) per session.
> 
> - Click **Accept and Review More** to validate the current set and load the next set of classifications based on the session filters.
> - Click **Accept and Exit Workbench** to validate the current set and save the session progress.

### Customizing columns for detections

You can customize the columns displayed in the detection table by selecting the desired ones from the **Column Selector** menu.

To include or exclude columns:

1. On the right side of the detection table, click **Column Selector** to open the **Select Columns** menu.

![Review of unstructured data sources with highlighted sensitive information and detection details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.10.01 AM.png)
2. Select or clear the columns as desired.

![Reviewing unstructured data sources with highlighted sensitive information and detection types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.18.46 AM.png)

The available options include:
  1. Detection
  2. Data Element Type
  3. Data System
  4. Evidence
  5. Name / Path
  6. Best positive anchor

> [!NOTE]
> Note
> 
> Some detections may not have a positive anchor term. In such cases, the **Best Positive Anchor** column displays empty.
  7. Review Later
3. Click **Apply**.

To reset the column configuration, click **Restore Defaults** option in the **Select Column** menu.

![Overview of unstructured data sources with highlighted sensitive detections and review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.10.33 AM copy.png)

> [!NOTE]
> Note
> 
> - If multiple columns are selected, scroll left or right to view all columns in the table.
> - To change the order of the displayed columns, drag and drop them in the **Select Columns** menu.

## Interacting with existing sessions

On the **Validation Workbench** page, you can view and manage existing sessions. You can also change the number of visible sessions by choosing 10 or 20 rows.

![Validation Workbench displaying unstructured data sessions and their respective details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.44.56 AM.png)

Apply filters to view relevant sessions. To do so, click **Select Filter** (plus icon) and choose the required filter from the menu. Available options include:

- Created Date
- Last Modified

![User interface showing filter options for data types in Validation Workbench.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-07 at 3.50.47 PM.png)

To interact with an existing session, click **More Actions** (three dots icon) to open a dropdown.

![Overview of the Validation Workbench displaying unstructured data sessions and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.45.22 AM.png)

The options include:

- View Session
- Edit Session
- Review More
- Edit Session Details
- View Audit Log
- Delete Session

Not all options may be available. Availability depends on your plan and tenant settings.

![Overview of validation sessions for unstructured data in a data intelligence tool.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.46.36 AM.png)

> [!NOTE]
> Note
> 
> - The following Securiti user roles have full control over session management:
>   - Super Admins
>   - Org Admins
>   - Module Owners
>   - Operators

The descriptions of these options is covered in the table below:

| Option | Description |
| --- | --- |
| View Session | View the classifications already reviewed and validated in a session. While viewing the session, you can review additional classifications or edit the session to review all previously validated classifications. ![Overview of unstructured data sources with highlighted API key and data element types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.47.45 AM.png) |
| Edit Session | Edit the classifications of an existing session. |
| Review More | Review additional classifications within an existing session. |
| Edit Session Details | Edit the details of an existing session. ![Update workbench session for unstructured data sources with session name and description.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 1.50.43 AM.png) > [!NOTE] > Note > > While editing a session, you cannot scope new findings. You can only review and validate the classifications already included in the session. |
| View Audit Log | View the audit logs of an existing session. ![Audit logs displaying user activities and timestamps for system security monitoring.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 2.09.22 AM.png) |
| Delete Session | Delete an existing session. |

## Using the Analytics dashboard

The **Analytics** dashboard provides statistics and insights on the detections reviewed and their relevant precision scores across all classifications. These insights help you monitor classification accuracy and identify if any detections require further review or updates.

![Overview of data detection review metrics in the Validation Workbench interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 2.53.20 PM.png)

It also displays a trendline for the past 12 months, showing the overall accuracy score over time and the total number of detections reviewed to date. This helps you track classification performance and identify areas that may require additional validation.

### Using filters

Above the Analytics grid, you can view trendlines showing statistics. You can apply the filters for the **Last 30 days**, **Last 12 weeks**, and **Last 12 months** to track these stats over time.

![Validation Workbench displaying data detection statistics and review metrics for sensitive data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 2.53.40 PM.png)

### Applying filters and viewing analytics

You can apply filters in the **Analytics** view to narrow down the results and display only the relevant classifications. To view analytics of a filtered classification, follow the steps below:

1. Click **Select Filter** (plus icon) to choose a property for filtering the detections.

![Filter options for data types and properties in the Validation Workbench interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.04.12 PM.png)

The options include:
  1. Data System
  2. Data Element Type
  3. Session
  4. Detections Reviewed
  5. Precision
2. Click **Apply** to filter the results based on the selected property.

The **Analytics** view then displays results according to the applied filters.

> [!NOTE]
> Note
> 
> The trendline remains visible after filters are applied. Its values does not change because it represents insights from the complete dataset of validated detections, not the filtered view.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.04.36 PM.png)

The details of these metrics are explained in the table below.

| Column Name | Description |
| --- | --- |
| Data Element Type | Displays the data element types detected by the system. |
| Precision | Measures how often the system correctly classifies a detection. The value is calculated per data element type. A score from **0–69** indicates low precision, while **70–100** indicates high precision. |
| Detections Reviewed | Displays the number of detections reviewed for each data element type. |
| TP | Displays the number of data elements correctly detected by the system. |
| FP | Displays the number of data elements incorrectly detected by the system. |
| Favorite | Displays the entries marked as favorites at the top of the table. To mark a detection as a favorite, enable the **Favorite** (star icon). ![Validation Workbench displaying data types and detection statistics for sensitive information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.05.32 PM.png) |

> [!NOTE]
> **Note**
> 
> A dash (-) in the **Precision** column indicates that the metric was either not calculated or was invalid for the classification.

### Customizing the visible columns

You can customize the columns displayed in the Analytics table by selecting the desired ones from the **Select Columns** menu.

To include or exclude columns:

1. On the right side of the analytics table, click **Column Selector** to open the **Select Columns** menu.

![Validation Workbench displaying data detection statistics and element types for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.04.55 PM.png)
2. Select or clear the columns as desired.

![Validation Workbench displaying data detection types and their review statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.05.07 PM.png)

The available options include:
  1. Data Element Type
  2. Precision
  3. Detections Reviewed
  4. TP
  5. FP
3. Click **Apply**.

> [!NOTE]
> Note
> 
> To reset the column configuration, click **Restore Defaults** option in the **Select Column** menu.
> 
> ![Validation Workbench displaying data types and detection statistics for sensitive information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.05.19 PM.png)

### Exporting the analytics data to a CSV file

The **Export** option lets you export the **Analytics** dashboard data to a **CSV** file that you can share and review outside the system. The CSV file includes classification details such as reviewed classifications and accuracy scores.

To export the **Validation Workbench** analytics:

1. On the **Analytics** page, click **Export** on the right side of the search bar.

![Validation Workbench displaying data detection statistics and reviewed elements for unstructured data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-15 at 10.05.32 PM copy.png)
2. Securiti sends an email when the file is ready to download. You can also download it from the **My Downloads** page.
