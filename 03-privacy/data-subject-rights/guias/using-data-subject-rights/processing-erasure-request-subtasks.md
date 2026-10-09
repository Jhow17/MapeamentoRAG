---
title: "Processing erasure request subtasks"
slug: "processing-erasure-request-subtasks"
updated: 2026-04-05T13:26:32Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/processing-erasure-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing erasure request subtasks

For erasure requests, your organization must respond to the Data Subject with confirmation that you have erased their personal data from your system.

Each Subtask fulfills part of this requirement by checking for the Data Subject’s personal data within a specific sector of your data storage, and if found, erasing it. When all subtasks have been completed, Securiti compiles the results of all of the subtasks into a single report and makes it available to the Data Subject.

Follow this procedure to process an Erasure Subtask and inspect specified objects or records, and identify personal data belonging to the Data Subject, and erase it.

1. On the Worklist tab, open the Subtask.

What you see at the top of the Subtask Action panel depends on the data system type and how [subtask instructions](/latest/docs/customizing-subtask-instructions) are configured in the request type or task template. This determines how you process the subtask. Generally, the top section shows a checklist of what has completed and what you must complete.
2. Do one of the following:

**For automated processing** (monitored - scanless data systems): Securiti first initiates an access request to test whether the Data System contains instances of the specified identity. If so, it then initiates the erasure request and shows you a report that tells you whether it erased the personal data automatically. The report shows one of four statuses:

For each Success or Declined action reported by Securiti, evaluate the action, and if applicable, verify it by marking its **Confirm User Data Deletion** checkbox.

**For partially automated processing** (Monitored - structured and monitored - unstructured data systems): Securiti shows you an access report or manifest that identifies the records or objects where it found personal data for the Data Subject. But unlike automated processing, Securiti does not erase the record; you must do that manually.

For some unstructured data systems, Securiti lets you preview the object. In such cases, Securiti offers a **Preview PD found in object** button. Click the button to see a preview of the file or object, with the PD highlighted as shown below.

![RN_preview_window.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-743748af-96a9-ce1a-1be7-3287ed148f3d(2).png)

For each object, access the service or database and open the object that Securiti identified. Inspect it for the personal data of the Data Subject.

**For manual processing** (unmonitored data systems): Securiti identifies the Data System as a location that might contain personal data for the Data Subject. Since Securiti cannot access the Data System, you must do so manually to check for the personal data of the Data Subject.

Access the Data System and search it for a record matching the Data Subject. If you find such a record, erase the personal data from it, then mark the **Confirm User Data Deletion** checkbox to verify it.
  - **Success**--Securiti located a record for the Data Subject and erased it.
  - **Scheduled**--Securiti has submitted an erasure request to the SaaS service, but has not received confirmation that it has been completed. For some services, automated erasure tasks may take up to a week, and in some cases up to 30 days, to complete. During the time in which the erasure Subtask is pending, you can manually access the Data System to complete the Subtask. Doing so cancels the queued automatic erasure Subtask.

If you mark the Subtask as Failed, it cancels the queued automatic erasure Subtask tracking, but does not cancel the already-issued erasure request with the SaaS service. In this case, although Securiti do not track it anymore, the SaaS service eventually completes the erase action in due time.
  - **Declined**--Securiti did not locate a record for the Data Subject, or identified a compelling reason for not automatically erasing it.
  - **Failed**--Securiti encountered a problem and could not delete the data.
  - If you do not find personal data for the Data Subject, verify it by marking its checkbox.
  - If you do find personal data for the Data Subject in the record or object:
    1. Erase the personal data from the object or record as requested by the Data Subject.
    2. Mark the **Confirm User Data Deletion** checkbox next to the record or object to verify it.
3. (Optional) Expand the Optional Documentation area and use the tools there to attach any additional documentation necessary to justify your handling of the subtask.

If you upload .csv files to the subtask, you can redact portions of the file by removing rows and columns. Next to the filename, click **View File**. On the popup, use the tools to remove rows and columns as shown below, then click **Save Changes**.

![Manage CSV interface showing selected rows for deletion and column customization options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1f56597-abc2-9fc5-c8d1-0e5008668653.png)
4. From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the Subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report. |
| Approve | You successfully erased all the personal data of the Data Subject and completed the Subtask. 1. Mark the checkbox to confirm you have reviewed all content for accuracy. 2. Click **Submit** to close the Subtask. |
| Declined | You determined that the object did not contain personal data for the Data Subject, or you identified a compelling reason for not erasing it. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the Data Subject. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the Subtask. |
| No Data | You determined that the object did not contain any personal data for the Data Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object and found no personal data for the Data Subject. 2. Click **Submit** to close the Subtask. |

---

### FAQs

#### 1. Does Securiti actually delete data from our system if we have Robotic Automation configured for Erasure requests?"

In automated processing(monitored - structured/Unstructured data systems) of a DSR request, Securiti doesn’t automatically delete any data. It just generates and attaches data deletion steps, also known as deletion scripts or queries and attaches them to subtasks. Data System owners can use the scripts to perform data deletion.
