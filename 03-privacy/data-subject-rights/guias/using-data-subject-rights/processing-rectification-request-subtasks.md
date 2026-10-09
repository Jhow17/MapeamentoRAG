---
title: "Processing rectification request subtasks"
slug: "processing-rectification-request-subtasks"
updated: 2026-09-21T11:02:01Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/processing-rectification-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing rectification request subtasks

For rectification requests, your organization must respond to the Data Subject with confirmation that you corrected errors in their personal data.

Each Subtask fulfills part of this requirement by checking for the Data Subject’s personal data within a specific sector of your data storage, and if the errors are found, correcting them. When all subtasks have been completed, Securiti compiles the results of all of the subtasks into a single report and makes it available to the Data Subject.

Follow this procedure to process a Rectification Subtask and inspect specified objects or records and identify personal data belonging to the Data Subject and correct any errors.

1. On the Worklist tab, open the Subtask.

What you see at the top of the Subtask Action panel depends on the data system type and how [subtask instructions](/latest/docs/customizing-subtask-instructions) are configured in the request type or task template. This determines how you process the subtask. Generally, the top section shows a checklist of what has completed and what you must complete.
2. Do one of the following:

**For automated processing** (user-defined data systems): Securiti shows you a report that tells you it found the incorrect information. The report shows one of three statuses:

For each Success or Declined status reported by Securiti, evaluate the action, and if applicable, verify it by marking its checkbox. Report any Failed statuses to your Securiti administrator.

**For partially automated processing** (monitored - unstructured, monitored - structured, and monitored - scanless, data systems): Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the Data Subject. Securiti does not correct the record; you must do that manually.

For some unstructured data systems, Securiti lets you preview the object. In such cases, Securiti offers a **Preview PD found in object** button. Click the button to see a preview of the file or object, with the PD highlighted as shown below.

![RN_preview_window.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-743748af-96a9-ce1a-1be7-3287ed148f3d(1).png)

For each object, access the service or database and open the object that Securiti identified. Inspect it for the incorrect data identified by the Data Subject.

> [!NOTE]
> **Note**
> 
> You can mark only the attributes you found and manually rectified in the Data System to approve subtasks in the DSR workbench.

**For manual processing** (unmonitored data systems): Securiti identifies the Data System as a location that might contain personal data for the Data Subject. Since Securiti cannot access the Data System, you must do so manually to check for the incorrect data identified by the Data Subject.

Access the Data System and search it for any records matching the Data Subject that contain the incorrect data. If you find such a record, correct it, then mark the checkbox next to it to verify it.
  - **Success**--Securiti located a record for the Data Subject and rectified the incorrect information.
  - **Declined**--Securiti did not locate a record for the Data Subject.
  - **Failed**--Securiti encountered a problem and could not access the Data System.
  - If you do not find the incorrect information in the record or object, verify it by marking its checkbox.
  - If you do find the incorrect information in the record or object:
    1. Correct the record as requested by the Data Subject.
    2. Mark the checkbox next to the record or object to verify it.
3. (Optional) Expand the Optional Documentation area and use the tools there to attach any additional documentation necessary to justify your handling of the subtask.

If you upload .csv files to the subtask, you can redact portions of the file by removing rows and columns. Next to the filename, click **View File**. On the popup, use the tools to remove rows and columns as shown below, then click **Save Changes**.

![Manage CSV interface showing selected rows for deletion and column customization options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1f56597-abc2-9fc5-c8d1-0e5008668653.png)
4. From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the Subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report. |
| Approve | You successfully rectified the incorrect data in the object or record and completed the Subtask. 1. Mark the checkbox to confirm you have reviewed all content for accuracy. 2. Click **Submit** to close the Subtask. |
| Declined | You determined that the object contained the incorrect data identified by the Data Subject, but that your organization is not legally obligated to correct it. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the Data Subject. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the Subtask. |
| No Data | You determined that the object did not contain any personal data for the Data Subject, or did not contain the incorrect data identified by the Data Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object and found no incorrect data for the Data Subject. 2. Click **Submit** to close the Subtask. |

---

### FAQs

#### 1. How does Securiti update fields in our system if we have Robotic Automation configured for Rectification requests?"

In automated processing of a DSR request (monitored - structured/Unstructured data systems), Securiti does not perform automated rectification. In case of a rectification request, Securiti identifies all personal data of the Data Subject and attaches it to the Subtask. It then invites Data System owners to perform data corrections.
