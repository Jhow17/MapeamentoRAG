---
title: "Approving and publishing reports"
slug: "approving-and-publishing-reports"
updated: 2026-08-30T07:51:10Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/approving-and-publishing-reports"
stale: true
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Approving and publishing reports

Once all subtasks for a DSR request have been processed, its owner approves and publishes the response. Doing so causes Securiti to send the data subject an email containing a link to the finished report. The DSR owners can also generate and preview the DSR report before sending it to the data subject. They can preview and regenerate the report multiple times if they find discrepancies before approving and sending it.

DSR request owners and Securiti admins can also view reports for previously processed DSR requests.

1. If you have not already done so, open the DSR request in the [DSR workbench](/v1/docs/opening-dsr-requests-in-the-dsr-workbench-1). Click the **Reports** tab.

The tab shows you a list of the reports that comprise the DSR request. For DSR requests of type access and port, you can either publish the report directly to the data subject or generate and preview it before sending.

To generate and preview the DSR report before sending it to the data subject:
  1. On the **Reports** tab, click **Generate Report**. On the **Generate Report** popup, use different options to apply the desired settings to the DSR report and click **Generate Report**.

![Screenshot_2025-02-25_at_6_21_35_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60217ec8-72a4-60a9-85b8-6e21929ea2df.png)

> [!NOTE]
> **Note**
> 
> The Generate Report button appears only for DSR requests of type access or port. For all other request types, the button does not appear in the Reports tab. It also does not appear if all subtasks are declined or no data is found. Additionally, once the report generation is in progress, you cannot make changes to the subtask, generate another report in parallel, publish the report or apply a batch update.
  2. Once Securiti completes the report generation process, click **Preview Report** to view the final report. In case of any discrepancies, click Generate Report again to generate a new report.

> [!NOTE]
> **Note**
> 
> If you make any changes to the subtask, such as adding new attachments or changing the process record, Securiti discards the old report. In this case you must generate a new report and publish it to send to the data subject.
  3. Once done, click **Approve and Publish Report** to send the final report to the data subject. If you have already generated the report, the **Approve and Publish Report** popup shows the **Regenerate Report** option.Use this option to generate a new report with the same or different settings, publish it, and replace the old report.

![Screenshot_2025-02-25_at_6_24_58_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd7e98a4-7280-5d4f-d021-211d1c060e67.png)

> [!NOTE]
> **Note**
> 
> For publishing a DSR report specific to a custom request type, Securiti does not provide the **Generate Report, Preview Report, Merge PDFs**, and **Generate a Consolidated Report** options.
> 
> If a data subject submits multiple request types within a single DSR request, these options become available only when one of the request types is access or port.
2. To approve and send a report to the data subject without previewing , click **Approve and Publish Response** near the upper right corner of the report pane.

![Screenshot_2025-02-25_at_6_30_54_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-094ba678-6424-9e43-5877-1f9656544428.png)

Securiti shows you the Approve and Publish Report popup as shown below.

![Screenshot_2025-02-25_at_6_31_12_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11359e0c-d575-62f1-cbe4-70f5ae0a33c7.png)
3. Apply the following settings, then click **Publish Report**:

| Setting | Description |
| --- | --- |
| Override the default system message | If every subtask across a DSR request is marked No Data, Securiti appends a default "User Not Found" message to the published report. Mark this checkbox to replace that message with a template of your choice instead. Marking this checkbox makes choosing a template mandatory, since Securiti needs a template to append in its place. If you leave this checkbox cleared, Securiti appends the default message automatically, and you do not need to choose a template. |
| Regenerate Report | Use this option to generate a new report with the same or different settings, publish it, and replace the old report. |
| Merge PDFs | Merge the subtask PDF attachments, whether redacted or additional, into a single PDF file. |
| Generate a consolidated report | Mark this checkbox to consolidate the reports for all of the subtasks into a single .pdf file. Otherwise the report is a **.zip** file containing separate reports for each subtask. You can further choose to show or hide columns in the "Specific Pieces of Personal Information" section normally included in DSR reports generated in response to access and port DSR requests. - **Include PD Attribute type**: Mark this checkbox to show “Categories of Personal Information” column. - **Include system headers**: Mark this to include the “Type of Information” column in the respective section. - **Include PD Value**: Mark this checkbox to show the “ Specific Personal Information” column from the respective section. ![dsr_img2](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c72b7adf-3214-486b-e9c2-bed782c7dad5.png) |
| Skip notifying DSR completion to Data Subjects | Mark this checkbox to skip sending notifications to your data subjects when publishing the DSR report |
| Suppress process records | Mark this checkbox if you want to omit the “Categories of Personal Information Collected and Used” section normally included in reports to data subjects in response to access and confirmation DSR requests. You might use this option if you already have processes that share that information with data subjects via other channels. |
| Approval Email | You can preview and customize the email you need to send the data subject when completing a DSR request. The preview shows the exact template selected based on the request type and the language in which the request is submitted. You can continue to manage these templates from **Settings > Notification Templates**. For more information, see [Configuring email notification templates](/latest/docs/configuring-dsr-email-notification-templates). > [!NOTE] > Note > > This applies to external DSRs and internal DSRs where a privacy account is associated with the data subject. |
| Response template menu | Use the menu to choose a template category, then choose one of the available templates and click its **Use** button. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates. |

> [!NOTE]
> **Note**
> 
> You can skip sending email notifications to your data subjects only for external DSR requests. You cannot skip sending email notifications for internal DSR requests. DSR completion email notification is always sent to the data subject if the auto publish setting is enabled on the DSR form as shown below.
> 
> ![Screenshot_2022-11-24_at_5_10_18_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7420259e-1c01-acfa-7f02-d1ec750fea7a.png)

---

### FAQ

#### 1. Why is the “Report sent” request stage only showing half way complete?

If the **Report Sent** bar shows halfway completed, it indicates that the data subject has not downloaded the report from their Privacy Central account. Once the data subject downloads the report, the bar shows full progress.
