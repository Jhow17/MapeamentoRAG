---
title: "Classifying document types using AI Tuning"
slug: "classifying-document-types-using-ai-tuning"
updated: 2026-09-23T06:34:51Z
published: 2026-09-23T06:34:51Z
canonical: "helpcenter.securiti.ai/classifying-document-types-using-ai-tuning"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Classifying document types using AI Tuning

Document Type AI Tuning lets you correct document type misclassifications across unstructured files at scale. When a file is misclassified, you can select it as a reference, review all files with similar name and content, and apply the correct document type across all of them in a single feedback session. The correction applies to existing scanned files and all future scans.

> [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - You must use pod **version 1.150.0** and above to use Document Type AI Tuning.
> - Document Type AI Tuning is not available for Securiti Sovereign tenants.

## Supported document types

Document Type AI Tuning supports text-based files with natively extractable content. Use the following table to understand the supported file formats:

| Category | Supported formats |
| --- | --- |
| PDF | - `PDF` |
| Document | - `DOCX` - `DOTX` - `DOCM` - `DOTM` - `DOC` |
| Presentation | - `ODP` - `OTP` - `PPT` - `PPTX` - `PPTM` - `PPAM` - `PPSM` - `PPSX` - `POTM` - `POTX` |
| Spreadsheet | - `ODS` - `XLSX` - `XLS` - `XLAM` - `XLTM` - `XLSB` - `XLSM` |
| Plain text | - `TXT` |

> [!NOTE]
> Note
> 
> Files that require OCR to extract text, such as scanned images or image-only PDFs, are not supported even if they are saved in a supported format.

## Accessing and using Document Type AI Tuning

You can access Document Type AI Tuning directly from the **Files** grid on the **Unstructured Data Scans** dashboard. **Files** eligible for AI Tuning display an **AI Tuning** (sparkle) icon, as shown below.

> [!NOTE]
> Note
> 
> A file is eligible for AI Tuning only if the following are true:
> 
> - Sample data exists for the file, collected during its scan.
> - A vector exists for the file, generated during the data sync.
> 
> Files that don't meet these conditions, for example, files scanned before AI Tuning was enabled, or files where vector generation failed, don't display the AI Tuning icon.

![List of files with highlighted document types and their respective categories and owners.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aitunedicon_udsdashboard.png)

To classify files using AI Tuning:

1. Open **Sensitive Data Intelligence** and choose **Data Explorers > Unstructured Data Scans**, as shown below.

![Overview of sensitive data intelligence features and document classification options in the application.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/navigatingtounstructureddatascans.png)
2. Locate the file you want to use as a reference, for example, a file misclassified as a `Dissertation` when it should be a `Bank Statement`.
3. Click the **AI Tuning** (sparkle) icon, which opens the **AI Tuning** window, as shown below.

![List of files with highlighted dissertation document and various document types and categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filerequiringfeedbackupdate_uds.png)
4. At the top of the window, verify the **Data System** and file path shown to confirm the correct reference file is selected, as shown below.

![Document classification interface showing file similarity and types for AI tuning.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemandfilename_uds.png)
5. In the **Tune the Document Type** section, use the **Update classification to** menu to select the correct document type. For example, select `Bank Statement` , as shown below.

![Graph illustrating document classification with highlighted bank statement category and similarity metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingupdatedclassification_aituning.png)

If the required document type is not in the list, click **Create Custom** to create a new one, as shown below.

![Graph illustrating document classification based on file name and content similarity.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createcustomdocumenttype_aituning.png)

Enter the details to create the custom document type, as shown below:

![Form for adding a custom document type, including fields for name and category.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addcustomdocumenttypepanel_aituning.png)

Use the following table to understand the fields for a custom document type:

| Field | Description |
| --- | --- |
| Status | Indicates whether the custom document type is active. > [!NOTE] > Note > > The **Active** checkbox is selected by default and cannot be changed during creation. |
| Document Type Name | Enter a unique name for the custom document type. For example, `Bank Statement`. |
| Document Category | Select the category under which the custom document type is classified. For example, `Financial`. |
| Description | Enter a brief description of the custom document type to help identify its purpose. |
| Language | Select the language associated with the custom document type. |
6. Review the scatter plot to understand the scope of your feedback, as shown below.

![Graph displaying document types based on similarity, with highlighted classification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningscatterplot_uds.png)

Use the following table to understand the scatter plot:

| Element | Description |
| --- | --- |
| X-axis | Displays how similar the file content should be to the reference file |
| Y-axis | Sets the minimum similarity between the file name and the reference file name. |
| Similarity threshold | Defines the scope of the feedback. Files that fall within the similarity threshold are included in the feedback session. |
| Current Document Type widget | Displays the top document types detected across similar files in the scatter plot |

1. Drag the similarity threshold on the scatter plot to adjust the scope.

a. Drag inward to narrow the scope to closely matching files.

b. Drag outward to include a broader set of files.
2. To narrow the feedback scope further, click the **Add Filter** (plus) icon to open the filter panel, as shown below.

![Interface showing file selection and document type options for AI tuning feedback.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningfilters_uds.png)

Use the following table to understand the available filters:

| Filter | Description |
| --- | --- |
| **Data System** | Limits the feedback scope to files within a specific data system. |
| **File Name** | Limits the feedback scope to files whose names match the specified value. |
| **File Path** | Limits the feedback scope to files within a specific path. |

For more information on how filters affect feedback scope, see [Understanding AI Tuning feedback scope](/latest/docs/ai-tuning-use-cases).

### Viewing impacted files

Below the scatter plot, the **Impacted Files** section lists every file currently in the feedback scope, along with the **Document Type** Securiti will apply when you submit feedback, as shown below.

![List of impacted files with document types and sample data for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/impactedfilessection_aituning.png)

Two summary tiles show:

Use the following table to understand the **Impacted Files** grid:

| Column | Description |
| --- | --- |
| File Name / Path | Displays the file name and its resource path. |
| Current Document Type | Displays the file's existing document type classification. |
| Updated Document Type | Displays the document type that Securiti applies once you submit feedback. |
| Sample Data | Displays a short preview of the file's extracted text content. |

To view full metadata or sample data for an impacted file:
  - **Files**, which is the total number of files currently in scope
  - **Document Types**, which is the total number of distinct current document types across those files
  1. Click a file entry in the Impacted Files grid to open the file panel.
  2. Click **Metadata** to view file-level details, as shown below. For example, **File Name**, **File Format**, and **Resource Path**.

![Table displaying impacted files with document types and metadata details for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewmetadata_impactedfilesonaituning.png)
  3. Click **Sample Data** to view the extracted text content Securiti used to determine the file's classification, as shown below.

![Table displaying impacted files with document types and sample data for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sampledatatab_impactedfiles_aituning.png)
3. Click **Apply Feedback** to submit the feedback, as shown below.

![AI classification update for document types with a similarity plot and feedback options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfeedback_uds.png)

Securiti applies the corrected document type to all files within the similarity threshold scope.

> [!NOTE]
> Note
> 
> Securiti processes feedback updates asynchronously, so changes might take a few minutes to appear across views.

## Reverting a manually classified document type

After you manually update a file's document type through AI Tuning, Securiti marks the classification in the **Document Type** column, along with an icon indicating it was manually updated.

To revert a manually classified document type back to its original system classification, follow the steps below:

1. In the **Files** grid on the **Unstructured Data Scans** dashboard, locate the file with the manually classified document type.
2. Click the **Revert** (circular arrow) icon next to the document type, as shown below.

![List of documents with highlighted dissertation and compliance report entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reverttheclassifiedfiles_uds.png)

Securiti reverts the document type to its original system-classified value.

## Viewing the updated feedback

After you apply AI Tuning feedback, Securiti updates the classification across the platform. You can view the updated feedback across:

- Unstructured Data Scans dashboard
- Graph Explorer

> [!NOTE]
> Note
> 
> The processing is asynchronous, so allow a few minutes for the change to appear in the dashboards.

### Viewing feedback in the Unstructured Data Scans dashboard

To view the updated feedback in the **Unstructured Data Scans** dashboard:

1. Search for any of the impacted files in the **Files** grid, as shown below.

![Table displaying impacted files with document types and sample data for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/impactedfiles_applyingfeedback.png)
2. The file shows the updated classification applied to it, as shown below.

![Document overview showing file details, data locations, and content distribution statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/updateddocumenttype_uds.png)

### Viewing feedback in Graph Explorer

To view the updated feedback in Graph Explorer:

1. Navigate to the **Graph Explorer**.
2. Click the **Apply Filters** (plus) icon and select the **Discovery Scan Files** entity.
3. Search for the updated file name.
4. The file shows the updated classification applied to it, as shown below.

![List of discovery scan files with highlighted document type and file name.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/updateddocumenttype_graphexplorer.png)

To track the applied feedback details, see [Viewing AI Tuning history](/latest/docs/viewing-ai-tuning-history) and [Viewing AI Tuning audit logs](/latest/docs/viewing-ai-tuning-audit-logs).
