---
title: "AI Tuning feedback scenarios"
slug: "ai-tuning-use-cases"
updated: 2026-09-24T14:19:21Z
published: 2026-09-24T14:19:21Z
canonical: "helpcenter.securiti.ai/ai-tuning-use-cases"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# AI Tuning feedback scenarios

AI Tuning feedback lets you correct two types of classifications: data element classifications for columns and document type classifications for files. The similarity threshold you set on the scatter plot determines which columns and files fall within the scope of a feedback session, and the filters you apply narrow that scope further.

Use this article to understand how feedback scope works, how Securiti resolves overlapping feedback entries, and what happens when you delete an entry from Tuning History.

## Controlling where feedback applies

Use filters to decide whether feedback applies to a specific data system, to a subset of columns and files, or across all connected data systems that match the filter conditions.

> [!WARNING]
> Important
> 
> Applying feedback without a **Data System** filter affects all connected data systems with columns or files that match the selected filter conditions.

### Applying feedback to a specific data system

To apply feedback to a single data system:

1. Open the **AI Tuning** panel for the column or file you want to correct. For example, open the panel for the `NPI_Number` column in the **csv_preview_all_pds** table.
2. Select the **Data System** filter and choose the required data system. For example, select `MySQL-HRDatabase`.
3. Select the correct classification, such as **AU Business Number**.

![Data system tuning interface showing classification and similarity of data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbacktoaspecificdatasystem_aituning.png)
4. Click **Apply Feedback**.

Securiti applies the feedback within the scope you defined, as shown below.

![Overview of data system review with highlighted elements for structured detections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbacktoaspecificdatasystem_vwb.png)

Use the following table to understand the scope of this feedback:

| Scope | Behavior |
| --- | --- |
| `MySQL-HRDatabase` | Securiti applies the classification update to **AU Business Number**. |
| All other data systems | Securiti leaves all columns unchanged, because these data systems fall outside the feedback scope. |

### Applying feedback to specific columns or files within a data system

To limit feedback to a specific set of columns or files inside one data system:

1. Open the **AI Tuning** window for the column or file you want to correct. For example, open the window for the `Fname` column in the **Customer** table.
2. Select the **Data System** filter and choose the required data system. For example, select `MySQL-HRDatabase`.
3. Add additional filters. For example, select **Schema is one of** `hr_schema` and **Column is one of** `First_Name`.

> [!NOTE]
> Note
> 
> For unstructured document types, you can use **File Name** and **File Path** filters in addition to **Data System**. For structured columns, you can use **Column**, **Database**, **Schema**, and **Table** filters in addition to **Data System**.
4. Select the correct classification.

![Data tuning interface showing database elements and classification options for data types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbacktospecificcolumnsorfileswithinadatasystem_aituning.png)
5. Click **Apply Feedback**.

Securiti applies the feedback within the scope you defined, as shown below.

![Overview of data systems and element types in a validation workbench interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbacktospecificcolumnsorfileswithinadatasystem_vwb.png)

Use the following table to understand the scope of this feedback:

| Scope | Behavior |
| --- | --- |
| `Fname` in `hr_schema` within `MySQL-HRDatabase` | Securiti applies the classification update. |
| Other columns in `MySQL-HRDatabase` | Securiti leaves these columns unchanged. |
| `Fname` in other schemas within `MySQL-HRDatabase` | Securiti leaves these columns unchanged. |
| All other data systems | Securiti leaves all columns unchanged, because these data systems fall outside the feedback scope. |

### Applying feedback across data systems with matching columns or files

To apply feedback across every connected data system that matches the filter conditions:

1. Open the **AI Tuning** window for the column or file you want to correct. For example, open the window for the `Fname` column in the **Customer** table.
2. Add a filter, such as **Column is one of** `Last_Name`.
3. Select the correct classification.

![Data tuning interface showing column selection and similarity assessment for database elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbackacrossdatasystemswithmatchingcolumnsorfiles_aituning.png)
4. Click **Apply Feedback**.

Securiti applies the feedback within the scope you defined, as shown below.

![Overview of data element types and structured detections in a validation workbench interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfeedbackacrossdatasystemswithmatchingcolumnsorfiles_vwb.png)

Use the following table to understand the scope of this feedback:

| Scope | Behavior |
| --- | --- |
| All columns named `Fname` across all data systems | Securiti applies the classification update. |
| Columns with different names | Securiti leaves these columns unchanged. |

For more information, see [Classifying structured data using AI Tuning](/latest/docs/classifying-structured-data-using-ai-tuning).
