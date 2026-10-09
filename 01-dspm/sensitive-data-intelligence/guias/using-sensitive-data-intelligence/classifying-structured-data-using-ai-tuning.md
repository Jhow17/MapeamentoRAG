---
title: "Classifying structured data using AI Tuning"
slug: "classifying-structured-data-using-ai-tuning"
updated: 2026-09-23T06:33:56Z
published: 2026-09-23T06:33:56Z
canonical: "helpcenter.securiti.ai/classifying-structured-data-using-ai-tuning"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Classifying structured data using AI Tuning

Structured Data Element AI Tuning lets you correct data element misclassifications across structured columns at scale. When a column is misclassified, you can select it as a reference, review all columns with similar header and content, and apply the correct data element type across all of them in a single feedback session. The correction applies to existing scanned columns and all future scans.

> [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - You must use pod version 1.135.0 and above to use Structured Data Element AI Tuning.
> - Document Type AI Tuning is not available for Securiti Sovereign tenants.

Once AI Tuning is completed and classifications are updated, Securiti learns from this feedback to improve the accuracy of future scans. If the updated columns are part of a Validation Workbench session or a Structured Data Insights policy, they are also updated in their respective session or policy.

> [!NOTE]
> **Note**
> 
> - AI Tuning applies only to data elements. If a data element is updated, the detected content profiles remain unchanged.
> - For instance, if the Address data element is updated from Street Address to Postal Address, any existing content profile that detects documents with SSN + Address + Name remains unchanged.

For more information, see [Using the Validation Workbench dashboard](/latest/docs/validation-workbench-for-structured-data) and [Impact on Structured Data Insights](/latest/docs/using-structured-data-insights-policies), respectively.

## Supported columns

Structured Data Element AI Tuning supports columns from structured data systems with sample data collected during discovery scans.

> [!NOTE]
> Note
> 
> AI Tuning is not available for CLOB columns.

## Column similarity in AI Tuning

The concept of similarity in AI Tuning is not based on columns that were previously classified in the same way. Instead, it refers to how similar two columns are based on their semantic meanings.

Column similarity is determined using two key attributes:

| Attribute | Description |
| --- | --- |
| Header similarity | Closely resembles the column names or headers |
| Content similarity | Similarity of actual sample data across the columns |

These two features generate a signature that represents the meaning of a column. Column similarity is determined by comparing these signatures. The columns visible towards the right of the impact zone are closely similar to the reference column than the reference columns towards the left of the impact zone.

## Accessing and using Structured Data AI Tuning

You can access Structured Data AI Tuning from either of the following dashboards:

- **Review Classification** option in the **Structured Data Discovery New Experience** dashboard
- **Review Classification** option in the **Validation Workbench for Structured Data** dashboard

Always look out for the **AI Tuning** indicator on a column under consideration, as it leads you to the AI Tuning pop-up.

![Database column details including encryption and data element type information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningicontonavigatetotheaituningpopup_sdd.png)

To understand how you can work with AI Tuning, follow the steps below:

- The top section of the pop-up shows the names of **Data** **System**, **Database**, **Schema**, **Table,** and **Column** of the selected reference column for which AI Tuning is working.

![Data visualization showing column similarities in Google BigQuery for AI tuning.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/databasedetails_aituning.png)
- The **scatter plot** shows similar columns to the reference column along the x-axis and header similarity along the y-axis.
- Adjust the **movable tuning square** to adjust the scope of the impact zone.
- The blue shaded area, controlled by moving the tuning square, represents the **Impact Zone**.

![Graph displaying data element types and their similarity in a database context.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/impactzonegraph_aituning.png)
- Columns that fall within the **impact zone** are updated with the new data elements based on the feedback provided. These columns are also listed under the **Impacted Columns** grid below:

![Data visualization showing impacted columns and their similarity in a database context.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/impactedcolumnsplotandgrid_aituning.png)
- The size of the blue shaded zone impacts AI Tuning time; larger zones include more columns, requiring more time for classification.

> [!NOTE]
> **Note**
> 
> To maintain clarity and visibility, only a sample of up to 300 classified columns is shown, although the actual number of columns updated through AI Tuning may exceed this if more are scoped.
- On the top right corner of the scatter plot, the **gear** shows the reference column name, data element types, and sample data of the reference column, as shown below:

![Data visualization showing impacted columns and their similarity in Google BigQuery.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/referencecolumnindicator_aituning.png)
- The **Current Data Element Types** widget lists the top data element types detected in the scatter plot, color-coded for visual distinction, as shown below:

![Graph illustrating data element types and their similarity in a database context.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/currentdataelementtypeswidget_aituning.png)

> [!NOTE]
> **Note**
> 
> The order indicates frequency from top to bottom.

### Applying filters to update classifications

To use filters in the AI Tuning popup:

1. Click + to access the filter panel and add or remove selected filters on properties to narrow down the scope of the **Current Data Element Types** widget and **Impacted Columns**.

![Interface for filtering columns in Google BigQuery database settings and data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfiltersonfeedback_aituning.png)

> [!NOTE]
> Note
> 
> You can only select the data elements that belong to the organization of the selected reference column.

Use the following table to understand the available filters:
  1. | Filter | Description |
| --- | --- |
| Column | Limits the feedback scope to columns whose names match the specified value. |
| Data System | Limits the feedback scope to columns within a specific data system. |
| Database | Limits the feedback scope to columns within a specific database. |
| Schema | Limits the feedback scope to columns within a specific schema. |
| Table | Limits the feedback scope to columns of a specific table. |
2. (Optional) In the **Tune the Data Element Type** section, click the **search bar** to assign a relevant data element to update classifications. The columns scoped on the similarity basis are updated as per the data elements selected.

Compare the values in the **Current Element Data Types** column with the updated data element types to understand how AI Tuning modifies the impacted columns. For example, here we want to assign a custom data element type to these columns, such as `Custom Employee ID`. To learn more about how to add custom data elements, see [Adding custom data elements](/latest/docs/classifying-structured-data-using-ai-tuning#adding-custom-data-elements).

![Data tuning interface displaying employee ID classification and impacted columns for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/appliedcustomdatatype_aituning.png)
3. (Optional) At the upper-right, click **Reset** to modify the impact zone or restore the scatter plot to its default view, as shown below:

![Graph displaying data element types and their similarity in a database context.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/resettingappliedfeedback_aituning.png)

### Adding custom data elements

After defining the scope of your Custom Data Element Types, you might find that a specific data element does not appear in any column. To address this, you can create custom data elements.

Securiti keeps a record of these custom data elements and includes them in future feedback cycles, based on your preferences set during their creation.

To create custom data elements:

1. In the **Tune the Data Element Type** section, click the search bar to check your data element in the list. If your data element is unique and not available in the drop down list then click **Create Custom** as shown below.

![Interface for tuning data elements in Google BigQuery with highlighted options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creatingcustomdatatype_aituning.png)
2. In the **Add Custom Data Element Type** popup, add information such as data element name, data element category, description etc, as shown below.

![Form for adding a custom data element type in a database system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addingcustomdataelement type_aituning.png)
3. Select Yes or No radio boxes as per your preference for Element Type, Special Category Exclude from evidence collection, Identifiability, and Uniqueness, as shown below.

![Settings for adding a custom data element type in Google BigQuery interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/identifiabilityanduniqueness_addingcustomdataelementtype_aituning.png)
4. Click **Save & Continue** to create your custom data element.
5. Once the custom data element is created, Securiti shows you a popup message **Data Element created successfully** and the data element type gets assigned to the reference column, as shown below.

![Data tuning interface displaying employee ID classification and impacted columns for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/appliedcustomdatatype_aituning.png)

### Using the Impacted Columns grid

The **Impacted Columns** grid displays columns within the impact zone, including the count of columns, data element types, tables, and databases.

- The first row shown is the chosen reference column, as shown below:

![Table displaying impacted columns with custom employee IDs and sample data entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/impactedcolumnsgridview_aituning.png)
- (Optional) Click the **Metadata** to get detailed information about the metadata and sample data of a column, as shown below:

![Overview of impacted columns in employee records with data types and sample data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewmetadataandsampledata_impactedcolumns.png)

### Saving the updated classifications

Click **Apply Feedback** to view the summary of all the data elements applied to the existing classifications in the AI Classification Updates pop-up. Then click **Apply Feedback** to complete the process, as shown below:

> [!WARNING]
> Important
> 
> AI tuning feedback updates are processed asynchronously and may take a few minutes to appear across different tabs or views. If multiple feedback entries apply to the same column, Securiti resolves them based on similarity and confidence metrics, rather than submission time.

![AI tuning interface showing data element classification and feedback application options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingupdatedclassifications_aituning.png)

## Viewing the updated feedback

After you apply AI Tuning feedback, Securiti updates the classification across the platform. You can view the updated feedback across:

- Graph Explorer
- Structured Data Insights Policy
- Structured Data Discovery dashboard

> [!NOTE]
> Note
> 
> The processing is asynchronous, so allow a few minutes for the change to appear in the dashboards.

### Viewing feedback in Structured Data Discovery

To view the updated feedback in Structured Data Discovery dashboard:

1. Navigate to the **Settings** > **AI Tuning** > **Tuning History** page.
2. Click the **Columns Updated** count against the relevant record to view the columns impacted by an AI Tuning feedback.

![Overview of tuning history with highlighted AU Business Number and related data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnsupdatedoption_tuninghistory(1).png)

This opens the **Structured Data Discovery** page with applied filters, as shown below:

![Data discovery interface showing columns, filters, and classification sources for database management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filtersappliedaspercolumnsupdated_sdd.png)

### Viewing feedback in the Structured Data Insights Policies

When an AI Tuning session is completed, all structured data insights policies are re-triggered so that policy findings reflect the updated classifications. If the AI-tuned columns are part of any policy findings, they are also updated accordingly.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(704).png)

For more information, see [Impact of AI Tuning on Structured Data Insights Policies](/latest/docs/impact-of-ai-tuning-on-structured-data-insights-policies).

### Viewing feedback in the Graph Explorer

To view the updated feedback in the **Structured Data Discovery** dashboard:

1. Navigate to the **Graph Explorer** dashboard.
2. Search for the impacted **Column**.
3. It shows the updated **Data Element Type** based on the manual classification.

![Graph Explorer interface displaying NPI_Number and related data elements for querying.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filterupdatedaitunedcolumn_graphexplorer(1).png)

## Viewing Analytics Dashboard in Validation Workbench

The Validation Workbench Analytics provides statistics and insights on total reviewed classifications and precision scores across all detections, helping you track and improve classification precision for columns classified manually or through AI Tuning.

![Validation Workbench displaying data types and their precision metrics for sensitive data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewinganalyticsinvwb_structuredvwb.png)

For more information, see [Using the Validation Workbench dashboard](/latest/docs/validation-workbench-for-structured-data).

## Related

- [Using Validation Workbench for structured data](/validation-workbench-for-structured-data.md)
