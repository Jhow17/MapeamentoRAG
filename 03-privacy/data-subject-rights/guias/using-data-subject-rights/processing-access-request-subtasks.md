---
title: "Processing access request subtasks"
slug: "processing-access-request-subtasks"
updated: 2026-09-22T08:22:25Z
published: 2026-09-22T08:22:25Z
canonical: "helpcenter.securiti.ai/processing-access-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing access request subtasks

For Access requests, your organization must respond to the data subject with information about whether it processes their personal data, and if so, copies of the data that you have. In some regulatory environments, you must also respond with information about the types of personal data you have for them, and how you use it.

Each subtask fulfills part of this requirement by checking for the data subject’s personal data within a specific sector of your data storage, and if found, providing copies of that data. For each subtask, we also attach a process record associated with the data system that informs the data subject how their data was being used, as required under some regulatory environments. For more information, see [Understanding process records](/v1/docs/understanding-process-records). When all subtasks have been completed, Securiti compiles the results of all of the subtasks into a single report and makes it available to the data subject.

Follow this procedure to process an Access subtask and inspect specified objects or records and identify personal data belonging to the data subject. If found, you submit that data for inclusion in the report to the data subject, along with a process record that describes how the data was being used.

1. On the Worklist tab, open the subtask.

What you see at the top of the Subtask Action panel depends on the data system type and how [subtask instructions](/latest/docs/customizing-subtask-instructions) are configured in the request type or task template. This determines how you process the subtask. Generally, the top section shows a checklist of what Securiti has completed and what you must complete, as shown below.

![Subtask_panel_Auti.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2078250-05bf-c342-4c51-f8574afd88cb.png)

In various parts of the subtask, you might also see regulatory detail icons as shown below. Click the gavel icon to view information about the privacy regulations that pertain to the task and subtask at hand.

![subtask_regulatory_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37cbd9ce-f36e-af37-0433-b300c02374bd.png)
2. Do one of the following:

**For automated processing** (monitored - scanless, monitored - structured, and user-defined data systems): Securiti automatically extracts and attaches one or more Auti-generated PD reports showing all the personal data associated with the data subject. For each report, Securiti also attaches a file containing the data the report was generated from.

For each report, click Review to open it, then open each CSV attachment inside and inspect it for any of the following extraneous sensitive data in it along with the subject’s personal data.

If you don’t find any extraneous sensitive data in the attachments, click **Verify attachment** and confirm that the report's **include in report** checkbox is marked.

If you do find extraneous sensitive data in any of the attachments, do one of the following:

You can also mask the sensitive data in the CSV file.

**For partially automated processing** (Monitored - unstructured data systems): Securiti shows you a manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the data subject.

For each object, access the service or database and open the object that Securiti identified. Inspect it for any of the following extraneous sensitive data in it along with the subject’s personal data.

For some objects on some unstructured data systems, Securiti lets you preview the object. In such cases, Securiti offers a **Preview PD found in object** button. Click the button to see a preview of the file or object, with the PD highlighted as shown below.

![Screenshot_2024-03-05_at_12_14_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d293369-7255-2e36-0862-7cdd43a3e49a.png)

The **Administrator View** shows the highlighted PD data elements of the data subject. To assign data element types to extraneous sensitive data found in the file, simply select the text and double-click on it. Then, search for the desired data element type, mark it, and click **Apply**. You can follow the same process to undo the assignment of data element types.

![assign_data_element_type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a811191c-7531-79e2-ae4a-6b763e421038.png)

**Redaction for unstructured data reports**

Securiti supports automatic and manual redaction for unstructured data reports for DSR requests of type access or port. The auto-redaction feature automatically redacts PII of individuals other than the data subject from documents containing the personal data of the data subject. This ensures that only the requester's personal information is visible in the final DSR report, while the personal details of others are redacted.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

In manual redaction, you can choose any text in the document or portion of it such as initials, and redact it. Simply select the text, double-click on it, click **Redact Selection** and click **Apply**.

![redact.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3972e0f5-da5f-bca5-cac0-b9353cf63e90.png)

> [!NOTE]
> **Note**
> 
> If auto-redaction is enabled, the Administrator View shows Securiti has already redacted some data elements.

You can also manually undo redaction if the content is mistakenly redacted or if auto-redaction includes some information that needs to be sent back to the data subject. Simply select the redacted text, double-click on it, click **Clear Redaction** and click **Apply**

![Screenshot_2024-04-20_at_9_28_18_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0f28d8e-f4d5-d84e-bfc1-01f619ecdf47.png)

When auto-redaction is enabled, you can also download source files from the DSR workbench, redact content on your local system and upload the redacted copy back to the subtask . To download the source file, in the DSR Workbench, against the respective subtask details, click **Download** (downward arrow).

![Object_download.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73064f85-9a3c-c9e4-4b35-2051b0bd4229.png)

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. For auto-redaction, ensure you have a subscription to Securiti’s **Sensitive Data Intelligence** module, specifically the **Content Classification** feature. DSR Redaction applies solely to unstructured monitored data systems.

In the **Data Subject View** tab, you can also see how the file would appear to the data subject.

![Screenshot_2024-02-28_at_9_49_19_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70ab4110-aa82-a58d-ad9d-c5396d46fe08.png)

If you want to include the list of data elements in the final DSR report, attach it as CSV to the subtask and include the file in the report. Similarly, you can also attach the redacted version of the file as a PDF to the subtask and include it in the final DSR Report.

![Private_preview_export_PDF.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4ffc8d0-73fe-9f4c-02c3-b132eaa511a2.png)

> [!NOTE]
> **Note**
> 
> Securiti supports all file formats for scanning and redacting files within unstructured data systems. For more information on file formats, see [Configuring scanning by file format category](/v1/docs/configuring-file-formats).
> 
> Additionally, Securiti keeps the similar format for Microsoft Office files, PDFs, and .msg files if they're under 10 MBs. For file types where maintaining original formatting is not feasible, Securiti provides a well-structured HTML version of the text extracted by content classification system and sent to the Data Subject Rights module specifically for redaction purposes.

If you do not find any extraneous sensitive data in the preview, upload the object as a document.

> [!NOTE]
> Note
> 
> Securiti performs anti-virus checks on any attachments submitted by the subtask owners through the DSR Workbench.

If you do find extraneous sensitive data in the element:

**For manual processing** (unmonitored data systems): Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for personal data.

Access the data system, search it for any personal data of the data subject. If you find any, upload a document containing it.

> [!NOTE]
> **Note**
> 
> A subtask owner can manually upload up to 30 attachments. Each file can be up to 100 MB in size.

If you upload .csv files to the subtask, you can redact portions of the file by removing rows and columns. Next to the filename, click **View File**. On the popup, use the tools to remove rows and columns as shown below, then click **Save Changes**.

![RN_DSR_edit_CSV.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1f56597-abc2-9fc5-c8d1-0e5008668653(1).png)
  - Your organization’s confidential information
  - Anyone else’s personal data
  - Click **Edit Data** and mark rows containing extraneous or duplicate information and click **Delete**. Further, click Verify Attachment to verify it.

![Verify_attachment.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b85da27-7f91-53dd-0401-e0bb0ecae305.png)
  - Manually create a redacted version of the report as follows:
    1. Access the data system and open the element that the preview is based on.
    2. Create a redacted version of the element that preserves the data subject’s information but removes extraneous sensitive data.
    3. Upload the redacted element as a document.
    4. Remove the original report.
    5. Verify the redacted element by marking its checkbox.
  1. Click **View** against each folder attached and open each CSV attachment inside.
  2. Click **Mask Data** and mark the column or just elements in the column that need to be masked. The system shows you the number of selected columns for masking. Click **Mark as Sensitive** to mask the selected columns or elements

![masking_data.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbf8b6c1-6cc1-acca-6d0a-06a30b7885fa.png)

> [!NOTE]
> **Note**
> 
> In the CSV attachments, any data that has been masked appears with a random array of 6 to 12 asterisks (*)

> [!WARNING]
> **Important**
> 
> Securiti recommends you use the masking tool judiciously. Masking can help you safeguard the sensitive personal information of individuals but over-masking can also interfere with a data subject’s right to access their personal data and exercise their other rights such as the right to rectify inaccurate personal data which can create compliance risks for you.
  - Your organization’s confidential information
  - Anyone else’s personal data
  1. Create a redacted version of the object that preserves the data subject’s information but removes extraneous sensitive data.
  2. Upload the redacted object as a document.
  3. Mark the checkbox next to the document to verify it.
3. Expand the **Processing Details** area and check whether there is a record that addresses how the personal data was being used or processed.

For more information on process records, see [Understanding process records](/v1/docs/understanding-process-records)
  - If so, choose the process record from the menu that matches how the personal data was being used.
  - If not, create a new process record to describe the processing.
4. From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the subtask before proceeding to publish the report. |
| Approve | You successfully completed the subtask. 1. Mark the checkbox to confirm you have reviewed all content for accuracy. 2. Click **Submit** to close the subtask. > [!NOTE] > **Note** > > When you approve a subtask that does not have all of the elements required by the privacy regulations of the state or country of residence for the data subject, Securiti shows you an alert message. Click **Ignore** to continue with the approval, or click **Cancel** to go back and add the required elements. You can still approve the subtask, but if you do so, your response might not fulfill your legal obligations. |
| Declined | You determined that the object contained personal data, but that the company is not legally obligated to produce it. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the data subject. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the subtask. |
| No Data | You determined that the object did not contain any personal data for the sata Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object and found no personal data for the data subject. 2. Click **Submit** to close the subtask. |
