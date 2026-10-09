---
title: "Viewing AI Tuning history"
slug: "viewing-ai-tuning-history"
updated: 2026-09-24T14:20:42Z
published: 2026-09-24T14:20:42Z
canonical: "helpcenter.securiti.ai/viewing-ai-tuning-history"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing AI Tuning history

Completed AI Tuning sessions and their updated classifications appear in the Tuning History page. This page tracks all the AI Tuning feedback, the final updated data element, and the count of total columns updated per feedback.

To effectively use the **AI Tuning History** page:

1. From the left navigation bar, click the **Jewel** icon to open the main menu and select **Settings > AI Tuning**, as shown below.

![Securiti dashboard displaying sensitive data intelligence and AI tuning options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningnavigation_sidebar.png)
2. Click **Tuning History** under the **AI Tuning** category, as shown below.

![Overview of tuning history with data elements and recent updates in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tuninghistory_navigation.png)
3. Select the **Structured Data** tab to view history for column-level AI Tuning, or the **Document Type** tab to view history for file-level AI Tuning, as shown below.

![Tuning history interface displaying structured data and database elements for data classification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structuredanddocumenttype_tuninghistory.png)
4. Use the search bar to find a specific reference column or file.
5. Click **Add Filter** (plus) icon to filter history entries by date changed, user, or type, as shown below.

![User interface showing data classification options and tuning history settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filtersontuninghistory_tuninghistory.png)
6. Go through the reference columns to track the applied changes.
  1. The **Structured Data** tab includes the following columns:

![Overview of tuning history with reference columns and data elements displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddata_columns.png)

Use the following table to understand the columns:

| Column | Description |
| --- | --- |
| Reference Column | Displays the column selected as the reference for the AI Tuning session |
| Applied Filters | Displays the filters applied to the feedback scope during the session |
| Final Data Elements | Displays the data element classification applied to the reference column and similar columns |
| Columns Updated | Displays the total number of columns updated by the AI Tuning session |
| Date Changed | Displays the date and time the feedback was applied |
| User | Displays the user who submitted the feedback |

b. The **Document Type** tab includes the following columns:

![Overview of tuning history with document types and update dates listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/documenttype_columns.png)

Use the following table to understand the columns:

| Column | Description |
| --- | --- |
| Reference File Path | Displays the path of the file selected as the reference for the AI Tuning session |
| Data System | Displays the data system where the reference file resides |
| Applied Filters | Displays the filters applied to the feedback scope during the session |
| Final Document Type | Displays the document type classification applied to the reference file and similar files |
| Files Updated | Displays the total number of files updated by the AI Tuning session |
| Date Changed | Displays the date and time the feedback was applied |
| User | Displays the user who submitted the feedback |

1. Click **More Actions** (three dots) icon > **Delete** to delete a feedback entry, as shown below.

![Overview of tuning history with document types and delete option highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deleteoption_tuninghistory.png)

> [!NOTE]
> Note
> 
> - When you delete a feedback entry, all column and file classifications applied during that session revert to their previous state.
> - For structured data, Securiti also rolls back the related analytics in the **Validation Workbench** and reverts any updated findings in **Structured Data Insights Policies.**
2. For **Structured Data**, click the **Columns Updated** count for a feedback entry to view the impacted columns in Graph Explorer, as shown below.

![Tuning history table displaying data elements and recent updates for various keys.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnsupdated_tuninghistory.png)

a. To view the **Columns Updated** for **Structured Data**, see [Viewing impact of AI Tuning](/latest/docs/classifying-structured-data-using-ai-tuning#viewing-the-updated-feedback). b. To view the **Files Updated** for **Document Type**, see [Classifying document types using AI Tuning](/latest/docs/classifying-document-types-using-ai-tuning).

## Viewing Tuning Audit Logs

To access the Tuning Audit Logs:

1. From the left navigation bar, click the **Jewel** icon to open the main menu and select **Settings > AI Tuning**, as shown below.

![Securiti dashboard displaying sensitive data intelligence and AI tuning options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningnavigation_sidebar.png)
2. Click **Tuning Audit Logs** under the **AI Tuning** category, as shown below.

![Overview of Tuning Audit Logs with user activities and timestamps displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tuningauditlogs_navigation.png)
3. Select the **Structured Data** tab to view logs for column-level AI Tuning, or the **Document Type** tab to view logs for file-level AI Tuning, as shown below.

![Tuning audit logs displaying user activities and system messages for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddataanddocumenttype_tabselection.png)
4. Click **Add Filter** (plus) icon to filter the audit log entries.

The available filters for **Structured Data** include:

Similarly, the available filters for **Document Type** include:
  1. Object Type
  2. Database
  3. Schema
  4. Table
  5. Data System
  6. Date
  7. Activity
  1. Object Type
  2. Data System
  3. Document Type
  4. Date
  5. Activity
5. Click **Refresh** to load the latest log entries, as shown below.

![Tuning audit logs showing user activities and system updates in a structured format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/refreshbutton_tuningauditlogs(1).png)
6. Go through the logs to track the history. It includes the following columns:

![Tuning audit logs showing user activities and system updates for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddata_tuningauditlogs.png)

Use the following table to understand the columns:

| Column | Description |
| --- | --- |
| Time | Displays the date and time the activity was recorded |
| User | Displays the user or system process that performed the activity |
| Activity | Displays the type of action performed, for example, Create, Update, or Sync |
| Object | Displays the object type that was acted on |
| Message | Displays a summary of the activity |
7. Click **View log metadata** (metadata) icon to open the session log details, as shown below.

![Tuning audit logs showing user activities and system updates for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewmetadataicon_tuningauditlogs.png)

To understand how the feedback scope works, see [AI Tuning feedback scenarios](/latest/docs/ai-tuning-use-cases).
