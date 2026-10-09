---
title: "Processing disclosure of subprocessors tasks"
slug: "processing-disclosure-of-subprocessors-tasks"
updated: 2026-04-05T14:36:27Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/processing-disclosure-of-subprocessors-tasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing disclosure of subprocessors tasks

For disclosure of subprocessors requests, your organization must respond to the Data Subject when they request a list of the public and private entities with whom your organization has shared the personal data of the Data Subject. The DSR processing for this request type is similar to that of access requests, except that the report to the Data Subject contains only lists of sub-processors, and not the actual personal data.

Each Subtask fulfills part of this requirement by checking for the Data Subject’s personal data within a specific sector of your data storage, and if found, helping you compile a list of the subprocessors with whom your organization shared it. For each Subtask, we attach that list. When all subtasks have been completed, Securiti compiles the results of all of the subtasks into a single report and makes it available to the Data Subject.

Follow this procedure to process a disclosure of subprocessors Subtask and inspect specified objects or records and identify personal data belonging to the Data Subject. If found, you build a list of the subprocessors with whom your organization shared that data.

1. On the Worklist tab, open the Subtask.

What you see at the top of the Subtask Action panel depends on the data system type and how [subtask instructions](/latest/docs/customizing-subtask-instructions) are configured in the request type or task template. This determines how you process the subtask. Generally, the top section shows a checklist of what has completed and what you must complete.
2. Do one of the following:

**For automated processing** (monitored - scanless, monitored - structured, and user-defined data systems): Securiti automatically extracts and attaches one or more Auti-generated PD reports in the Optional Documentation area. The PD reports show all the personal data associated with the Data Subject.

For each report, open the preview and inspect it to verify that it is indeed the personal data of the Data Subject.

**For partially automated processing** (Monitored - unstructured data systems): Securiti shows you a manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the Data Subject.

For each object, access the service or database and open the object that Securiti identified. Inspect it to verify that it is indeed the personal data of the Data Subject.

For some objects on some unstructured data systems, Securiti lets you preview the object. In such cases, Securiti offers a **Preview PD found in object** button. Click the button to see a preview of the file or object, with the PD highlighted as shown below.

![RN_preview_window.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-743748af-96a9-ce1a-1be7-3287ed148f3d(5).png)

**For manual processing** (unmonitored data systems): Securiti identifies the Data System as a location that might contain personal data for the Data Subject. Since Securiti cannot access the Data System, you must do so manually to check for personal data.

Access the Data System, search it for any personal data of the Data Subject. If you find any, inspect it to verify that it is indeed the personal data of the Data Subject.
3. In the Subtask action panel, expand the Identify Sub-Processors area and use the tools there to build a list of the subprocessors with whom your organization has shared the personal data of the Data Subject.
  - Click **Add a third-party recipient** to create a new recipient entry.
  - For each recipient, enter at least the name and type of the recipient.
4. (Optional) Expand the Optional Documentation area and use the tools there to attach any additional documentation necessary to justify your handling of the subtask.

If you upload .csv files to the subtask, you can redact portions of the file by removing rows and columns. Next to the filename, click **View File**. On the popup, use the tools to remove rows and columns as shown below, then click **Save Changes**.

![Manage CSV interface showing selected rows for deletion and column customization options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1f56597-abc2-9fc5-c8d1-0e5008668653.png)
5. From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the Subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report. |
| Approve | You successfully completed the Subtask. 1. Mark the checkbox to confirm you have reviewed all content for accuracy. 2. Click **Submit** to close the Subtask. |
| Declined | You determined that the object contained personal data, but that the company is not legally obligated to disclose the subprocessors. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the Data Subject. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the Subtask. |
| No Data | You determined that the object did not contain any personal data for the Data Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object and found no personal data for the Data Subject. 2. Click **Submit** to close the Subtask. |
