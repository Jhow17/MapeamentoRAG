---
title: "Using Validation Workbench for structured data"
slug: "validation-workbench-for-structured-data"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/validation-workbench-for-structured-data"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Validation Workbench for structured data

The Validation Workbench lets you review and validate the structured data classifications, either manually or using AI Tuning. Based on your feedback, it provides insights into the precision of detected classifications.

Once data is available from a discovery scan, the Validation Workbench displays randomized rows and columns of data findings for review within the session you created. Samples are fetched based on the scope defined by the session filters. Validation Workbench tracks the precision of every classified data element, giving you insights at a granular level through **Analytics**.

Use the Validation Workbench to ensure the accuracy and reliability of auto-classified data at the data element level by validating it, updating classifications when needed, and classifying similar columns in bulk with AI Tuning. This process refrains you from reviewing everything, helping you focus on targeted improvements.

> [!NOTE]
> Note
> 
> - To use this feature, enable the Data Command Graph and configure Private Cloud Storage (PCS). For more information, see [Configuring private cloud storage](/latest/docs/system-settings-configuring-private-cloud-storage).
> - The Validation Workbench does not support content profiles and exact data profile detection for CLOB scanning or for CLOB data within Structured Data scans.

You can use the Validation Workbench for structured data to:

- Review classifications across columns in a controlled session
- Examine sample data before accepting or updating a classification
- Reject incorrect classifications and update them individually or in bulk
- Extend a session to review more classifications
- Monitor classification accuracy across all reviewed classifications and by data element type

## Validation Workbench interactive demo

To learn how to work with the Validation Workbench for structured data, watch the video below:

You can start validating data classifications, without waiting for the discovery scan to complete, as soon as sample data becomes available during a scan. Based on these insights, you can:

- Share the classification results with data stewards and data owners.
- Improve accuracy by tuning existing data elements.
- Manually update classifications as needed.
- Apply classification feedback to future scans using AI Tuning
- Develop an understanding of risk reduction and enhance data security.
- Monitor classification analytics once a session is completed and gain insights into areas needing further validation.

## Creating a new validation session and using filters

You can create a validation session to review, edit, and validate classifications for structured data. These sessions let you add users as co-owners so they can review and edit classifications based on their assigned permissions.

To create a new validation workbench session, follow the steps below:

1. From the sidebar, hover over **Sensitive Data Intelligence** and select **Data Classification** > **Validation Workbench**.

![Dashboard displaying data classification and findings by risk severity metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-13 at 4.01.01 PM.png)
2. From the **Data Type** sidebar on the left, choose **Structured**.
3. If multiple organizations are enabled, choose the required one from the **Organizations** menu. Selecting an organization displays sessions specific to that organization and creates new sessions within it.
4. To create a new session, from the upper right corner of the page, click **+ New Workbench Session**.

![Overview of the Validation Workbench displaying structured and unstructured data sessions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.37.02 PM(1).png)
5. On the New Workbench Session popup:

![Creating a new validation workbench session for structured data with session details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.35.33 PM.png)

> [!NOTE]
> Note
> 
> If you remove yourself from the list of owners during session creation, you lose access to that session.
  1. Enter the session name.
  2. (Optional) Enter the suitable description stating the purpose of the session.
  3. Choose **Structured** from the **Data Type** menu.
  4. Add the relevant owners.
6. Click **Save** to create the session. After the session is created, you are redirected to the session’s page.
7. Click **Add** (plus icon) to add properties such as **Data System**, **Data Element Type**, and **Scan Job ID**. Then choose the required operator filters to restrict the scope of detections to review.

![User interface for data validation with filter options and data element types displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.46.51 PM.png)
8. After applying the appropriate filters, start reviewing and validating the classifications.

![Validation workbench displaying employee ID data elements for review and editing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.47.18 PM.png)

> [!NOTE]
> Note
> 
> - Once you validate any column(s) within a session, the filters are locked and can not be changed.
> - A column can only be validated once, and the validated columns do not show up again in any session. Similarly, the validated columns can be viewed in their respective sessions.

## Validating classifications manually or with AI Tuning

After you have applied the desired filter, you can review the data elements, edit them manually, mark classifications as secondary importance for review later, or apply the classifications update to the future discovery scans using AI Tuning.

1. Click **Edit** (pencil icon) next to **Data Element Type**.

![Validation workbench displaying employee IDs and data system details for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.47.18 PM(1).png)
2. Choose the required data element type(s) and click **Apply & Save Selection**.

![Validation workbench displaying structured data review options and selected data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 2.47.32 PM.png)
3. To manually edit multiple columns at once, use the selection checkboxes on the left to select multiple columns.

![Validation Workbench displaying employee IDs and data element types for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.17.14 PM.png)
4. To apply the classifications update to the future discovery scans using AI Tuning, select the **AI Tuning** (sparkling icon) for your chosen reference column. For more information, see [Classifying columns using AI Tuning](https://helpcenter.securiti.ai/docs/classifying-columns-using-ai-tuning).

![Validation workbench displaying employee IDs and structured detection review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.07.16 PM.png)

> [!NOTE]
> Note
> 
> - Edits are disabled for columns undergoing AI Tuning. Make changes after the tuning process completes.
> - AI Tuning applies only to columns that are unvalidated, not manually updated, and not validated through the Validation Workbench.
5. (Optional) To review classifications of secondary importance later, mark them **Review Later**.

![Validation workbench session displaying structured data and review options for employee IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.07.38 PM.png)

> [!NOTE]
> **Note**
> 
> - Columns marked as **Review Later** reappear in the session for validation.
> - Any changes made to these columns are discarded.
> - If a column is undergoing AI Tuning, mark it as Review Later since editing is disabled.
6. After you have reviewed and edited all columns, manually or through AI Tuning, on the current page, click **Complete Review** to validate the classifications.

![Summary of data review session showing reviewed and updated employee IDs and actions taken.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.07.58 PM.png)

A popup appears showing the total number of columns that were:
  - Reviewed
  - Updated by AI Tuning
  - Updated Manually
  - Set to review later
7. > [!NOTE]
> Note
> 
> Classifications updated from **Structured Data Discovery** or **Table Training** are automatically marked as invalid in the Validation Workbench. Review and validate them again to maintain consistency and accuracy.

### Viewing table sample data

You can view table-level sample data for every column within the validation Workbench. You can see the context of a column within its table, making it easier to understand relationships and data patterns. Cross-matching sample data across columns helps in validating AI model training as well.

> [!WARNING]
> Important
> 
> You must meet certain prerequisites to view and download evidence files. For more information, see [Accessing evidence files in Securiti](/latest/docs/managing-evidence-files-and-downloads).

> [!NOTE]
> Note
> 
> - You must have appropriate permissions to view the table sample data.
> - A maximum of 30 sample rows per column is available for review to provide a high-level overview of the sample data.

To view table sample data:

1. Click on the **Table Sample Data** on the right of a data element type, as shown below.

![Validation workbench displaying employee IDs and structured detection review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.34.32 PM.png)
2. This opens **Table Sample Data** popup, as shown below.

Here you can view and cross-match the sample data of the complete table to which the selected column belongs.

![Table displaying employee IDs and sample data for reference columns in a database.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.34.51 PM.png)
3. (Optional) To view the details of the selected column within the Table Sample Data popup, hover over the column name. ![Data source details and sample employee ID table displayed on a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.35.13 PM.png)
4. (Optional) To view sample data for larger data sets, increase the number of visible columns, as shown below. ![Table displaying employee IDs and sample data with pagination options at the bottom.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.35.25 PM.png)
5. You can also download this table sample data as a file to share it with the concerned stakeholders.

> [!NOTE]
> Note
> 
> Securiti downloads the table sample data file to your machine with the following file name format:
> 
> `table_name.csv`
> 
> 
> 
> This file format ensures you can identify the source table in case of multiple sample data downloads.

![Table displaying employee IDs and sample data for reference and organization purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.35.33 PM.png)

### Viewing metadata and sample data of classifications

The metadata and sample data for any column provide additional contexts, such as data system type, data element type, database, and table, which help you review and validate the column effectively.

1. To view metadata and sample data of any classification, click the icon on the right side of the data element.

![Validation workbench displaying employee ID data elements for review and editing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.47.57 PM(1).png)

> [!NOTE]
> Note
> 
> Sample data is stored based on the connector type and configuration.
> 
> **For Cloud connectors:**
> 
> - Sample data is stored in the cloud by default.
> - If you configure PCS, sample data is stored in PCS instead.
> 
> For more information, see [Configuring private cloud storage](/latest/docs/system-settings-configuring-private-cloud-storage).
> 
> **For Self-hosted connectors:**
> 
> - Sample data is stored on the appliance by default.
> - If PCS is configured, sample data is stored in PCS unless you choose to store it on the appliance.
  1. The **Metadata** tab is selected by default, where you can see the classification metadata for a relevant discovery scan.

![Validation workbench session displaying employee ID data elements and metadata details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.47.46 PM(2).png)
  2. To view sample data, click the **Sample Data** tab, where you can see the details of the sample data associated with the column.

![Overview of employee IDs and data element types in a structured detection table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 4.57.46 PM.png)
2. To view relationships between different entities in the graph explorer, such as data elements, tables, data systems, and so on, click **Explore**.

![Overview of employee ID data elements and their types in a structured format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 5.05.06 PM.png)

This opens a pop-up and displays the relationships between different entities such as data systems, columns, data elements, and so on.

![Overview of database elements including employee ID and data system connections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 5.05.22 PM.png)

#### Viewing evidence for CLOB columns

> [!WARNING]
> Important
> 
> - To view evidence for CLOB columns, you must configure CORS correctly on your Private Cloud Storage. If CORS is not configured correctly, the evidence preview does not load.
> - AI Tuning is not supported for CLOB columns.

Securiti supports evidence preview for CLOB columns in the structured Validation Workbench. Each CLOB column appears as a single record in the Validation Workbench list.

CLOB columns are identified by the **View Evidence** icon displayed next to the column name in the detection list. To view evidence for a CLOB column:

1. In the Columns list, locate the CLOB column you want to review.
2. Click the **View Evidence** icon next to the column name to open the **Evidence Viewer** popup.

![Overview of structured data review with highlighted passport number and email fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clobcolumnicon_structuredvwb.png)

1. On the **Evidence Viewer** popup, review the first 20 occurrences detected for every data element.
2. To view complete results, click **Download**.

![Evidence viewer displaying data elements related to education and personal identifiers.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidenceviewer_structuredvwb.png)

You can also assign multiple data elements to CLOB columns directly from the **Structured Validation Workbench** panel.

![Data review interface showing columns, tables, and options for saving selections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/multipleselectionsinclobcolumn_structuredvwb.png)

### Setting sample size for columns

Securiti displays 50 sampled columns by default. However, you can choose to view 25, 50, or 100 sampled columns per session to improve review speed and flexibility for large datasets.

To change the number of sample columns displayed in a session, choose **25**, **50**, or **100** from the **Sample up to** menu, as shown below.

![Validation workbench displaying employee IDs and data system details for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.02.54 PM.png)

> [!NOTE]
> Note
> 
> The Validation Workbench displays the selected number of classifications (25, 50, or 100) per session.
> 
> - Click **Accept and Review More** to validate the current set and load the next set of classifications based on the session filters.
> - Click **Accept and Exit Workbench** to validate the current set and save the session progress.

### Customizing columns for detections

You can customize the columns displayed in the detection table by selecting the desired ones from the **Select Columns** menu.

To include or exclude columns:

1. On the right side of the detection table, click **Column Selector** to open the **Select Columns** menu.

![Validation workbench displaying employee IDs and structured data for review and editing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.03.06 PM.png)
2. Select or clear the columns as desired.

![Validation workbench displaying employee IDs and structured data review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.03.34 PM.png)

The available options include:
  1. Table
  2. Sample Data
  3. Data Count
  4. PK
  5. PI
  6. Review Later
3. Click **Apply**.

To reset the column configuration, click **Restore Defaults** option in the **Select Column** menu.

![Validation workbench displaying employee ID data elements for review and adjustments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.04.09 PM.png)

> [!NOTE]
> Note
> 
> - If you have selected multiple columns, scroll left and right to view all the columns.
> - To change the order of the displayed columns, drag and drop them in the **Select Columns** menu.
> 
> ![Validation workbench displaying employee IDs and structured data review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.04.41 PM.png)

## Interacting with existing sessions

On the **Validation Workbench** page, you can view and manage existing sessions. You can also change the number of visible sessions by choosing 10 or 20 rows.

![Overview of validation workbench sessions with details on columns and owners.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.24.07 PM.png)

Apply filters to view relevant sessions. To do so, click **Select Filter** (plus icon) and choose the required filter from the menu. Available options include:

- Created Date
- Last Modified

![User interface showing filter options for data types and properties in a validation workbench.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-07 at 3.51.40 PM.png)

To access additional options for an existing session, click **More Actions** (three dots icon).

![Validation Workbench interface displaying structured and unstructured data sessions for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.13.25 PM.png)

The options include:

- View Session
- Edit Session
- Review More
- Edit Session Details
- View Audit Log
- Delete Session

Not all options may be available. Availability depends on your plan and tenant settings.

> [!NOTE]
> Note
> 
> - The following Securiti user roles have full control over session management:
>   - Super Admins
>   - Org Admins
>   - Module Owners
>   - Operators

Use the table below to understand the descriptions of these options:

| Option | Description |
| --- | --- |
| View Session | View the classifications already reviewed and validated in a session. While viewing the session, you can review additional classifications or edit the session to review all previously validated classifications. ![Validation Workbench session displaying reviewed employee IDs and structured data details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.17.12 PM.png) |
| Edit Session | Edit the classifications of an existing session. |
| Review More | Review additional classifications within an existing session. |
| Edit Session Details | Edit the details of an existing session. ![Update workbench session form for structured data with session name and description fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.18.39 PM.png) > [!NOTE] > Note > > While editing a session, you cannot scope new findings. You can only review and validate the classifications already included in the session. |
| View Audit Log | View the audit logs of an existing session. ![Audit logs displaying user activities and session updates for validation sessions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.19.00 PM.png) |
| Delete Session | Delete an existing session. |

## Using the Analytics dashboard

The **Analytics** dashboard provides statistics and insights on the columns reviewed and their relevant precision scores across all classifications. These insights help you monitor classification accuracy for columns classified manually or through AI tuning. It also helps identify if any column requires further review or updates.

For more information, see [Classifying columns using AI Tuning](/latest/docs/classifying-columns-using-ai-tuning).

![Validation Workbench displaying data types and analytics for reviewed columns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.41.00 PM.png)

It displays a trendline for the past 12 months, showing the overall accuracy score over time and the total number of columns reviewed to date. This helps you track classification performance and identify areas that may require additional validation.

### Using filters

Above the Analytics grid, you can view trendlines showing statistics. You can apply the filters for the **Last 30 days**, **Last 12 weeks**, and **Last 12 months** to track these stats over time.

![Validation Workbench displaying data types and review metrics for sensitive data intelligence.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.41.14 PM.png)

### Applying filters and viewing analytics

You can apply filters in the **Analytics** view to narrow down the results and display only the relevant classifications. To view analytics of a filtered classification, follow the steps below:

1. Click **Select Filter** (plus icon) to choose a property for filtering the detections.

![User interface showing data validation options and filters for data types and elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.41.37 PM.png)

The options include:
  1. Data System
  2. Data Element Type
  3. Session
  4. Columns Reviewed w/o AI Tuning
  5. Columns Reviewed
  6. Precision w/o AI Tuning
  7. Precision
  8. Recall (No Match) w/o AI Tuning
  9. Recall (No Match)
2. Click **Apply** to filter the results based on the selected property.

The **Analytics** view then displays results according to the applied filters.

> [!NOTE]
> Note
> 
> The trendline remains visible after filters are applied. Its values does not change because it represents insights from the complete dataset of validated columns, not the filtered view.

![Data validation overview showing precision and recall metrics for various data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 8.44.22 PM.png)

Use the table below to understand the details of these metrics.

| Column Name | Description |
| --- | --- |
| **Precision** | The Accuracy calculated per data element type. |
| **Precision w/o AI Tuning** | Precision w/o AI Tuning is a measure of how often the system is correct when classifying a column, excluding AI Tuned columns. A higher precision means that a system is usually correct when it says that a given column has a particular Data Element. |
| **Recall (No Match)** | This measures how well Securiti recognizes a Data Element on a column without identifying it as “No Match Found.” A higher score means the system is rarely unable to detect an occurrence of a specified Data Element type. |
| **Recall (No Match) w/o AI Tuning** | This measures how well Securiti recognizes a Data Element on a column, excluding AI tuned columns, without identifying it as “No Match Found". A higher score means the system is rarely unable to detect an occurrence of a specified Data Element type. |
| **Columns Reviewed** | Displays the total number of columns reviewed for the specified data element using the validation workbench, regardless of whether they were edited during the validation process. |
| **Columns Reviewed w/o AI Tuning** | Displays the total number of columns reviewed for the specified data element using the validation workbench, excluding the AI Tuned columns, regardless of whether they were edited during the validation process. |
| **TP** | Displays the columns where data elements have been accurately identified as matches by the system, based on the defined classification criteria. |
| **TP w/o AI Tuning** | Displays the columns where data elements have been accurately identified as matches by the system, based on the defined classification criteria, excluding AI Tuned columns. |
| **FP** | Displays the columns where data elements have been incorrectly identified as matches. These are instances where the system has flagged a data element as a match, even though it does not meet the intended criteria. |
| **FP w/o AI Tuning** | Displays the columns where data elements have been incorrectly identified as matches, excluding AI Tuned columns. These are instances where the system has flagged a data element as a match, even though it does not meet the intended criteria. |
| **FN (No Match)** | Displays the columns that did not have a data element ("No Match") and have now been assigned a specific data element. A manually assigned data element to a column having no detections is considered as False Negative only if the data element was part of the scan scope. |
| **FN (No Match) w/o AI Tuning** | Displays the columns that did not have a data element ("No Match") and have now been assigned a specific data element, excluding the AI Tuned columns. A manually assigned data element to a column having no detections is considered as False Negative only if the data element was part of the scan scope. |
| **Favorite** | Displays the favorite entries at the top of the table. |

> [!NOTE]
> **Note**
> 
> A dash (-) in the **Precision** and **Recall** columns indicates that the metric was either not calculated or was invalid for that classification.

### Customizing columns for detections

You can customize the columns displayed in the Analytics table by selecting the desired ones from the **Select Columns** menu.

To include or exclude columns:

1. On the right side of the analytics table, click **Column Selector** to open the **Select Columns** menu.

![Data validation dashboard showing reviewed columns and performance metrics over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 9.00.40 PM.png)
2. Select or clear the columns as desired.

![Validation Workbench displaying data types and reviewed columns with performance metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 9.00.30 PM.png)

The available options include:
  1. Data Element Type
  2. Precision
  3. Precision w/o AI Tuning
  4. Recall (No Match)
  5. Recall (No Match) w/o AI Tuning
  6. Columns Reviewed
  7. Columns Reviewed w/o AI Tuning
  8. TP
  9. TP w/o AI Tuning
  10. FP
  11. FP w/o AI Tuning
  12. FN (No Match)
  13. FN (No Match) w/o AI Tuning
3. Click **Apply**.

> [!NOTE]
> Note
> 
> To reset the column configuration, click **Restore Defaults** option in the **Select Column** menu.
> 
> ![Validation Workbench displaying data types and review metrics for data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 9.00.56 PM.png)

### Exporting the analytics data to a CSV file

The **Export** option lets you export the **Analytics** dashboard data to a **CSV** file that you can share and review outside the system. The CSV file includes classification details such as reviewed classifications and accuracy scores.

To export the **Validation Workbench** analytics:

1. On the **Analytics** page, click **Export** on the right side of the search bar.

![Validation Workbench displaying data types and export option for data review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 9.06.36 PM.png)
2. Securiti sends an email when the file is ready to download. You can also download it from the **My Downloads** page.

## Related

- [Structured Data Discovery New Experience dashboard](/structured-data-discovery-new-experience.md)
- [Classifying structured data using AI Tuning](/classifying-structured-data-using-ai-tuning.md)
