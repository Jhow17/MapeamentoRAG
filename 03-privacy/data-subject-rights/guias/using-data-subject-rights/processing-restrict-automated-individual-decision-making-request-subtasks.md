---
title: "Processing restrict automated individual decision-making request subtasks"
slug: "processing-restrict-automated-individual-decision-making-request-subtasks"
updated: 2026-04-05T13:33:02Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/processing-restrict-automated-individual-decision-making-request-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Processing restrict automated individual decision-making request subtasks

For restrict automated individual decision-making requests, your organization must respond to the Data Subject with confirmation that you have stopped processing their personal information for automated decision making. This means that upon receiving a request, you must ensure that the individual's data is no longer subject to automated decision-making processes and inform the Data Subject of this action.

Each Subtask fulfills part of this requirement by checking for the Data Subject’s personal data within a specific sector of your data storage. If found, the Subtask helps notify Data System owners to stop automated decision-making whenever the Data Subject's data is involved.

Follow this procedure to identify data systems containing the Data Subject’s personal data and alert Data System owners to stop using it for automated decision-making. After completing all restriction subtasks, Securiti sends a confirmation to the Data Subject that automated decision-making involving their personal data has ceased.

1. On the **Worklist** tab, open the Subtask.

What you see at the top of the Subtask Action panel depends on the data system type and how [subtask instructions](/latest/docs/customizing-subtask-instructions) are configured in the request type or task template. This determines how you process the subtask. Generally, the top section shows a checklist of what has completed and what you must complete.
2. Do one of the following:

For **automated processing** (user-defined data systems) and **partially automated processing** (monitored - scanless, monitored -unstructured, and monitored structured): The existence of the Subtask indicates that Securiti found the Data Subject’s information within the Data System. For some Data System types, Securiti may also show you a manifest of the object or record where the data was found.

For some unstructured data systems, Securiti lets you preview objects. In such cases, Securiti offers a Preview PD found in the object button. Click the button to see a preview of the file or object, with the PD highlighted as shown below:

![unstructured_screenshot.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59fa3edf-6380-0741-9cb5-f97a7e37bbf0.png)
  1. Use your internal company processes to identify all groups processing the Data Subject’s personal data from that Data System.
  2. Alert all relevant groups to restrict automated decision-making on the Data Subject’s personal data.
  3. Mark the **Confirm automated individual decision-making restriction** checkbox to verify that you have restricted automated decision-making
3. For **manual processing** (unmonitored data systems): Securiti identifies the Data System as a location that might contain personal data for the Data Subject. Since Securiti cannot access the Data System, you must do so manually to check for a record associated with the Data Subject.

Access the Data System and search it for a record matching the Data Subject. If you find such a record:
  1. Use your internal company processes to identify all groups processing the Data Subject’s personal data from that Data System.
  2. Alert all relevant groups to restrict automated decision-making on the Data Subject’s personal data.
  3. Mark the **Confirm automated individual decision-making restriction** checkbox to verify that you have restricted automated decision-making
4. (Optional) Expand the Optional Documentation area and use the tools there to attach any additional documentation necessary to justify your handling of the Subtask.

If you upload .csv files to the Subtask, you can redact portions of the file by removing rows and columns. Next to the filename, click View File. On the popup, click **Edit Data** and mark rows you want to remove and click **Delete**.

![csv_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-905cdde1-c6de-fa27-daa1-ea346187b718.png)
5. From the DSR response status menu, choose a status from the following table and take the matching action.

| Status | Description and action |
| --- | --- |
| Review | There are still things you must do to finish processing the Subtask. Click **Save Changes** to save your changes to the DSR request. |
| Error | You can manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors. > [!NOTE] > **Note** > > You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report. |
| Approve | You successfully stopped the processing of the personal data and completed the Subtask. 1. Mark the checkbox to confirm you stopped the processing. 2. Click **Submit** to close the Subtask. |
| Declined | You determined that your organization is not legally obligated to restrict processing of the personal data. 1. Use the menu at the top of the popup to choose a template category, then choose one of the available templates and click its **Use** button. Securiti includes a message based on the template in the report it sends to the Data Subject. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. 2. (Optional) To send a modified message based on the template, click the **Detach from Template** link, then edit the message to suit. 3. (Optional) Fill in the Internal Notes tab. 4. Click **Submit** to close the Subtask. |
| No Data | You determined that the object did not contain any personal data for the Data Subject. 1. Mark the checkbox to confirm you have reviewed all content in the object or record and found no data for the Data Subject. 2. Click **Submit** to close the Subtask. |
