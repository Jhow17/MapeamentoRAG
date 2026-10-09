---
title: "Viewing policy activity, action history and logs"
slug: "viewing-policy-activity-action-history-and-logs"
status: "update"
updated: 2026-09-22T03:36:20Z
published: 2026-09-22T03:36:20Z
canonical: "helpcenter.securiti.ai/viewing-policy-activity-action-history-and-logs"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing policy activity, action history and logs

**Scenario**

As a Data Governance Officer, you need to confirm that your Data Labeling and File Quarantine policies are running correctly across thousands of files. Checking outcomes by opening files one by one is slow and easy to get wrong, especially when a run fails partway through. With **View Activity,** you review **Action History** to see completed, failed, and in-progress runs at a glance, then check **Policy Logs** to pinpoint exactly which files were affected and why. For instance, when a labeling run reports failures, the logs show the exact file and error, so you resolve the issue without manual digging.

## Overview

The **View Activity** option lets you monitor the execution activity of Data Labeling and File Quarantine policies. It combines **Action History** and **Policy Logs** for a selected policy on a single page, so you can monitor policy execution and troubleshoot policy runs without opening individual files.

> [!WARNING]
> Important
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

To view policy activity:

1. From the upper-left corner, click the **Jewel** icon to open the main menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-QC1C483Q.png)
2. Click **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5TKJQ1BO.png)
3. On the **Policies** page, select a supported policy type, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HR38F04V.png)
4. For the desired policy, click **More Actions (three dots)**, and then click **View Activity**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IWVFZ5V1.png)

## Viewing Action History

The **Action History** tab provides an overview of all policy runs, including completed, failed, cancelled, and in-progress executions. You can also review the details of a specific policy run to verify its execution status, scope, and processing results.

To view Action History:

1. On the **Policy Activity** page, from the upper-left corner, select the desired policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HTJ5WZHZ.png)
2. Select the **Action History** tab, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PE3DDKLM.png)

### Filtering Action History

To filter Action History:

1. From the upper-left corner of the **Action History** page, click **Add (plus icon)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0MY52SOG.png)
2. Configure one or more of the following filtering properties:

| Property | Description |
| --- | --- |
| Run ID | Lets you filter policy runs based on the unique identifier of the policy. |
| Status | Lets you filter policy runs based on their status. The following statuses are supported: - `Pending` - `Running` - `Completed` - `Failed` - `Canceled` - `Timed Out` - `Cancellation in Progress` - `Unarchiving` |
| Action Type | Lets you filter policy runs based on the tagging action. The following actions are supported: - `Auto Labeling` - `Manual Labeling` - `Remove Label` - `Auto Quarantine` - `Manual Quarantine` - `Revert Quarantine` - `Remediation` - `Remove Remediation` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U9E73E6I.png)
3. Click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XL1ZW4F9.png)

### Searching for an Action History record

To search for an Action History record:

Enter the run ID in the **Search by run ID** field, as shown below. The table displays the matching policy run.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9BVKH02N.png)

### Refreshing Action History

To refresh Action History:

To the right of the **Search by run ID** field, click **Refresh**, as shown below. The page displays the latest policy run information.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FCSGIRVG.png)

### Viewing Action History metrics

The **Action History** page displays the following metrics that summarize policy runs:

| Metrics | Description |
| --- | --- |
| Total Runs | Displays the total number of policy runs. |
| In progress | Displays the number of policy runs currently in progress. |
| Completed | Displays the number of successfully completed policy runs. |
| Failed | Displays the number of failed policy runs. |
| Cancelled | Displays the number of cancelled policy runs. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q8EE3060.png)

### Viewing Step Details

You can view detailed information about a specific policy run to review its execution.

To view step details of a policy run:

1. On the **Action History** page, click **View** **Details** for the desired policy run, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NBMW8FZ4.png)
2. Review the execution details for the policy run, as shown below. The **Execution Details** page displays the following information:

| Property | Description |
| --- | --- |
| Asset Name | Displays the name of the asset included in the policy run. |
| Asset Type | Displays the type of the asset. |
| Status | Displays the status of the policy run for the asset. |
| Scope | Displays the number of items included in the policy run. |
| Successful | Displays the number of items processed successfully. |
| Failed | Displays the number of items that failed to process. |
| Start Time | Displays the date and time when the policy run started. |
| End Time/ETA | Displays the date and time when the policy run completed or the estimated completion time. |
| Asset ID | Displays the unique identifier of the asset. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FAEMMDN2.png)

## Viewing Policy Logs

The **Policy Logs** tab lets you search and filter log entries by properties such as data system, file name, label, and timestamp, so you can identify specific events and troubleshoot policy execution issues. You can also export filtered log entries for reporting or audit purposes.

To view Policy Logs:

1. On the **Policy Activity** page, from the upper-left corner, select the desired policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-98Y21RPB.png)
2. Select the **Policy Logs** tab, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TA6KW1YP.png)

### Filtering Policy Logs

To filter Policy Logs:

1. From the upper-left corner of the Policy Logs page, click **Add (plus icon)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8J38G5I5.png)
2. Configure one or more of the following filtering properties:

| Policies | Properties | Description |
| --- | --- | --- |
| - Data Labeling - File Quarantine | Data System Type | Lets you filter logs by the type of data system where the file is located. For example, `SMB`. |
| Data System Name | Lets you filter logs by the name of the data system that generated the log entry. For example, `SMB_DataSystem`. |
| Log Level | Lets you filter logs by the severity of the log entry. Securiti supports the following log levels: - `Informational` - `Error` |
| File Name | Lets you filter logs by the name of the file associated with the log entry. For example, `notes.txt`. |
| Timestamp | Lets you filter logs by the exact date and time the log entry was recorded. For example, `03 Sep, 2026 10:50 am`. |
| Data Labeling | Current Label | Lets you filter logs by the label currently applied to the file at the time of the log entry. For example, `Confidential`. |
| Original Label | Lets you filter logs by the label applied to the file before any policy or remediation action. For example, `Confidential`. |
| File Quarantine | Folder Path | Lets you filter logs by the folder path where the file is stored within the selected data system. For example, `/documents/data`. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U0IILOHN.png)
3. Click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MV0OTPFT.png)

### Searching for a Policy Log record

To search for a Policy Log record:

Enter the log message in the **Search by message** field, as shown below. The table displays the matching log entries.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B1QNT4AS.png)

### Exporting Policy Logs

To export Policy Logs:

To the right of the **Search by message** field, click **Export**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CTQB498Y.png)

After Securiti generates the file, you receive an email with a link to download it. The download link expires after 24 hours.

### Refreshing Policy Logs

To refresh Policy Logs:

To the right of the **Export** button, click **Refresh**, as shown below. The page displays the latest log information.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-55WDOK28.png)

### Customizing the displayed columns

To customize the columns displayed on the **Policy Logs** page:

1. In the upper-right corner of the table, click **Column Selector**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7KOUMRL6.png)
2. Select the checkboxes for one or more of the following columns you want to display, and clear the checkboxes for the columns you want to hide:

| Properties | Description |
| --- | --- |
| Timestamp | Displays the date and time the log entry was recorded. For example, `03 Sep, 2026 10:50 am`. |
| Message | Displays the message text associated with the log entry. For example, `Labeling skipped because file format requires a label with protection enabled`. |
| Log Level | Displays the severity of the log entry. Securiti supports the following log levels: - `Informational` - `Error` |
| File Name | Displays the name of the file associated with the log entry. For example, `notes.txt`. |
| Current Label | Displays the label currently applied to the file at the time of the log entry. For example, `Confidential`. |
| Data System ID | Displays the unique identifier of the data system associated with the log entry. For example, `1000`. |
| Data System Name | Displays the name of the data system that generated the log entry. For example, `SMB_DataSystem`. |
| Data System Type | Displays the type of data system where the file is located. For example, `SMB`. |
| File Path | Displays the file path where the file is stored within the selected data system. For example, `/documents/data/notes`. |
| Original Label | Displays the label applied to the file before any policy or remediation action. For example, `Confidential`. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BBQP8KJH.png)
3. Click **Apply** to update the columns displayed in the table, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U8OS39TJ.png)
4. To restore the default column configuration, click **Restore Defaults**, and then click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-05VOM0U7.png)
