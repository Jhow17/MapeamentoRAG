---
title: "Previewing and downloading DSR report, subtask reports, and attachments"
slug: "previewing-and-downloading-dsr-and-dsr-subtask-reports"
updated: 2026-08-09T18:22:51Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/previewing-and-downloading-dsr-and-dsr-subtask-reports"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Previewing and downloading DSR report, subtask reports, and attachments

You can download the reports for individual subtasks for completed Access and Port DSR requests, download all attachments in a subtask, task, or DSR, and can also preview and download the overall report for such DSR requests.

> [!NOTE]
> **Note**
> 
> The download of overall reports is only available for DSR requests for which the report has been published to the data subject after the deployment of Securiti release 1.51.

### Enabling previewing and downloading

1. in Securiti open **System Settings** and choose **Data Subject Rights > DSR Settings.**
2. Scroll to the **DSR Reports** section, then click **Edit** (pencil icon).

![Settings for Data Subject Rights, including download options and retention policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 10.14.52 AM.png)
3. Under **Download Configuration**, mark the checkboxes for **DSR Request Report**, **DSR Subtask Report**, and **Download All Attachments**, then click **Save.**

![Settings for DSR reports, including download options and retention policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 10.14.39 AM.png)

> [!NOTE]
> Note
> 
> Only Super Admins can enable or disable these settings.

### Previewing and downloading reports for DSR subtasks

1. Open a completed DSR request for which you are an owner, then open the subtask.
2. Next to the Verified subtask Report button, click **Preview** as shown below.

![preview_subtask_attachments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66612933-9d97-e691-e445-ab37378a2619.png)
3. Use the popup to preview and download specific reports or all reports.

### Previewing and downloading subtask reports when a fraction of queries timeout

1. Open a completed DSR **Access** request for which you are an owner, then open the subtask.

> [!NOTE]
> **Note**
> 
> You can only download DSR report for **Access** subtask based on successfully executed queries when a fraction of queries timeout.
2. In case of unsuccessful execution of queries against **Access** request subtask an error message is displayed indicating the number of failed or unsuccessful queries, as shown below.

![Database_error_in_panel.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-77589b62-2a70-3e81-2e7c-8f2f46af82fd.png)
3. You can preview and download the generated report based on the successful queries against the **Access** request subtask, as shown below.

![download_csvs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d83288c8-c3f5-e126-f63a-ae7ec92cfe57.png)

### Previewing and downloading the overall report

You can also preview the final DSR report shared with the data subject.

To preview the final DSR report:

1. Open a completed DSR request for which you are an owner.
2. Click the **Reports** tab.
3. Click the **Preview Report** button, and on the popup click **Download Report**.

![report_preview_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdca6819-94ef-ccc8-8f7f-a72af3630f78.png)

The report contains information in tabular format, improving overall readability. It provides data subjects with a clear overview of the categories of personal data used in the processing activities.The section contains details such as the legal basis for processing personal data of the Data Subject and the specific organizations involved in processing activities. Including the legal basis is important to comply with privacy regulations and establish the lawful reasons behind data processing. Moreover, specifying the organizational units lets data subjects know where their information is being utilized within the organization.

![prcoessing_activities_dtails.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a9e4577-3586-8e5b-405b-743050adc32f.png)

Furthermore, the DSR report also lists the specific personal data elements collected, stored, and retained by your organization.

![dsr_img2](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c72b7adf-3214-486b-e9c2-bed782c7dad5(1).png)

### Downloading all attachments in a subtask, task, or DSR

You can download a zip file of all attachments in a subtask, a task, or a DSR request with a single click, instead of downloading each attachment individually.

> [!NOTE]
> Note
> 
> You can download attachments at the subtask, task, or DSR level if you can open that DSR in the workbench and view its tasks and subtasks. You do not need to be the subtask, task, or DSR owner to download its attachments. Being able to view it is enough.

#### Downloading all attachments in a DSR

1. Open the DSR request in the workbench.
2. Near the upper-right corner, click the **More Actions** (⋮) menu, then click **Download All Attachments**, as shown below.

![DSR access request details with options to download attachments and task progress overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.15.21 AM.png)

This downloads all attachments across every task and subtasks in the DSR.

#### Downloading all attachments in a task

1. On the **Worklist** tab, next to the task you want, click the **More Actions** (⋮) menu.
2. Click Download All Attachments, as shown below.

![Access request interface showing options to download attachments and view reports.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.40.44 AM.png)

This downloads all attachments across every subtask in that task.

#### Downloading all attachments in a subtask

1. Open the DSR in the workbench, then open the task and subtask you want.
2. In the middle of the page, next to the subtask details, click the **More Actions** (⋮) icon, then click **Download All Attachments**, as shown below.

![DSR access request interface showing tasks, subtasks, and download options for attachments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.42.04 AM.png)

This downloads all attachments for that subtask only.

Once you click **Download All Attachments** at any level, Securiti shows a confirmation message that your request has been received. Securiti then emails you a link to download the zip file once it is ready. This link stays active for 24 hours.

![Email notification confirming successful processing of attachment download request.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.47.24 AM.png)

> [!NOTE]
> Note
> 
> Downloaded files are the original, unredacted or unmasked versions of the attachments, even if you apply redaction or masking rules when viewing files in the workbench.

Securiti logs every download request in the DSR audit log, including the user who initiated it, the action, and the timestamp.

![DSR access request details for user Kimberely Fisher, showing download activities and timestamps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.48.43 AM.png)
