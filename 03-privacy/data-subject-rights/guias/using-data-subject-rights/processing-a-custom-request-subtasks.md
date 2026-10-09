---
title: "Processing a custom request subtasks"
slug: "processing-a-custom-request-subtasks"
updated: 2026-09-22T08:23:26Z
published: 2026-09-22T08:23:26Z
canonical: "helpcenter.securiti.ai/processing-a-custom-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing a custom request subtasks

When handling custom requests, your organization's response depends on the purpose and nature of the request type received. For privacy-related requests, such as Opt-in requests, confirm the user's choice and provide any additional details required by law. If a request aligns with specific regulations (e.g., Access Requests under particular laws), ensure your response satisfies both legal requirements and Data Subject expectations. For all other non-privacy requests, like support inquiries, focus on providing a clear and timely resolution or acknowledgment, depending on the nature of the request. This topic outlines three cases based on how the custom request type is configured and processed.

### Case 1: Enabling DSR Automation for custom request types

When DSR Automation is enabled for a custom request type, it functions similarly to [a port request](/v1/docs/processing-port-request-subtasks) except that attaching files in the DSR Workbench is optional. For more information on enabling DSR Automation, see [Creating a custom request type](/v1/docs/creating-a-custom-request-type).

Securiti creates tasks and subtasks in the DSR workbench against each structured, unstructured or user-defined Data System involved in the DSR processing. Each Subtask fulfills part of this requirement by checking for the Data Subject’s personal data within a specific sector of your data storage, and if found, providing copies of that data.

> [!NOTE]
> **Important**
> 
> Securiti doesn’t support custom request types for scanless data systems. Also, for custom request types, you won’t see the regulatory summary at the Subtask level, but you can view the regulatory details at the DSR request level.

![Screenshot_2025-03-06_at_10_51_06_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6aad868-fc7e-e848-5a09-6d97c89d6a6d.png)

Follow this procedure to process a custom request and inspect specified objects or records and identify personal data belonging to the Data Subject. If found, you submit that data for inclusion in the report to the Data Subject.

1. On the **Worklist** tab, open the Subtask.

What you see at the top of the Subtask Action panel depends on the type of Data System, and determines how you process the Subtask.
2. Do one of the following:

**For automated processing** (monitored - structured, and user-defined data systems): Securiti shows you a report containing links that let you preview the file, object, or table containing the personal data.

To process structured data reports for custom requests, follow the same steps defined for [DSR port request](/v1/docs/processing-port-request-subtasks).

**For partially automated processing** (monitored - unstructured data systems): Securiti shows you a manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the Data Subject.

To process unstructured data reports for custom requests, follow the same steps defined for the [DSR port request](/v1/docs/processing-port-request-subtasks).

> [!NOTE]
> **Note**
> 
> Securiti lets you control whether to include or exclude data files in a published DSR report for custom request types. You can omit structured data files by simply approving the Subtask without selecting the Include in Report checkbox in the DSR Workbench. Additionally, uploading attachments in the DSR Workbench is also optional.

![Screenshot_2025-03-06_at_10_53_12_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4cc68d2f-bb06-431f-46e8-fa8283ac820d.png)

Securiti supports automatic and manual redaction for unstructured data reports for custom DSR requests. To redact unstructured data reports for custom requests, follow the same steps defined for DSR port request.

For **manual processing** (unmonitored data systems): Securiti identifies the Data System as a location that might contain personal data for the Data Subject. Since Securiti cannot access the Data System, you must do so manually to check it for personal data. Access the Data System, search it for any personal data of the Data Subject. If you find any, upload a document containing it and mark the checkbox next to it to verify it.

> [!NOTE]
> **Note**
> 
> For consistency across systems, uploading attachments is completely optional in both monitored and unmonitored Data System subtasks. Securiti also performs anti-virus checks on any attachments submitted by the subtask owners through the DSR Workbench.

### Case 2 : Enabling task per data system for custom request types

When the **Task per Data System** option is enabled for a custom request type, Securiti creates a task (and Subtask) for each Data System ( structured, unstructured or user-defined) involved in the DSR processing, providing a detailed breakdown per system.

Since Securiti cannot access these data systems as no automation is involved, you can manually check for the Data Subject's personal data in them. Upload any found data as a document and verify by marking the checkbox next to it.

![Screenshot_2025-03-06_at_11_19_31_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f47c98ed-3bc5-2dd1-2335-7e5183bf4170.png)

### Case 3: Disabling both options for custom request types

When you disable both DSR Automation and task per Data System for a custom request type, Securiti creates a single task (along with a Subtask) in the DSR Workbench for the entire DSR request. This Subtask is automatically assigned to the DSR owner which you can further reassign. You can upload attachments manually and approve or decline the Subtask as needed.

![Screenshot_2025-03-06_at_11_22_14_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb4f6a23-106b-5374-2036-ca5277038dfd.png)

> [!NOTE]
> **Note**
> 
> Since the task and Subtask in this case are not linked to any Data System, Securiti names the task after the custom request type submitted and labels the Subtask accordingly. For example, a 'Right to Know' custom request type results in a task named 'Right to Know' and a Subtask named 'Subtask for Right to Know”.

When a Data Subject submits a DSR request with multiple custom types, Securiti creates one task labeled Multiple request types and two subtasks for each type. For instance, if the DSR request includes *custom one* and *custom two* as request types, the task is labeled *Multiple request types* and subtasks as *Subtask for custom one* and *Subtask for custom two*.

![Screenshot_2025-03-06_at_11_23_18_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81c3817f-bf9c-0f07-e401-abf0e1143707.png)

From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the Subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report. |
| Approve | You successfully completed the Subtask. 1. (Optional) Mark the checkbox to confirm you have reviewed all content for accuracy. 2. Click **Submit** to close the Subtask. |
| Declined | You determined that the object contained personal data, but that the company is not legally obligated to produce it. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the Data Subject. For more information about customer messaging templates, see [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates). 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the Subtask. |
| No Data | You determined that the object did not contain any personal data for the Data Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object and found no personal data for the Data Subject. 2. Click **Submit** to close the Subtask. |
