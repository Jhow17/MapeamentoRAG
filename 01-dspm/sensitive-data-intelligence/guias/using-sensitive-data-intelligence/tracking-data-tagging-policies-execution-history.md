---
title: "Viewing run history of Data Tagging policies"
slug: "tracking-data-tagging-policies-execution-history"
status: "update"
updated: 2026-09-22T03:41:03Z
published: 2026-09-22T03:41:03Z
canonical: "helpcenter.securiti.ai/tracking-data-tagging-policies-execution-history"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing run history of Data Tagging policies

**Scenario**

As a Data Governance Officer, you need to confirm that your overnight Data Tagging policy runs completed as expected. Manually reviewing thousands of nodes for tagging errors can be time-consuming and error-prone. With Run History, you can review the Scoped, Succeeded, and Failed counts for each policy run and investigate failures. For instance, a run across 10,000 nodes shows 8,500 succeeded and 1,500 failed. In Step Details, you discover that the tagging service was temporarily unavailable for all failed nodes. After the service is restored, you can rerun the policy for the affected nodes.

To view the run history of Data Tagging policies:

1. On the **Policies** page, select **Data Tagging**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5UITYH2Q.png)
2. To view the run history of all Data Tagging policies, in the upper-right corner of the Data Tagging **Policies** page, click **More Actions (three dots)**, and then click **View Run History**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Z434QIEN.png)
  - To view the run history of a specific Data Tagging policy, click **More Actions (three dots)** for the desired policy, and then click **View Run History**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7TZC6N38.png)

### Filtering run history

To filter run history:

1. In the upper-left corner of the **Run History** page, click **Add (plus icon)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KSMAZCA7.png)
2. Configure one or more of the following filtering properties:

| Property | Description |
| --- | --- |
| Action | Lets you filter policy runs based on the tagging action. The following actions are supported: - `Add Tags` - `Remove Tags` - `Remove All Tags` |
| Date Completed | Lets you filter policy runs based on the date when the run completed. |
| Data Started | Lets you filter policy runs based on the date when the run started. |
| Policy ID | Lets you filter policy runs based on the unique identifier of the policy. |
| Policy Name | Lets you filter policy runs based on the policy name. |
| Status | Lets you filter policy runs based on their status. The following statuses are supported: - `Running` - `Completed` - `Failed` - `Timed Out` - `Canceled` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-94QL0HFU.png)
3. Click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9Y6ICHEC.png)

### Searching for a run history record

To search for a run history record:

Enter the run ID in the **Search by run ID** box, as shown below. The table displays the matching run history record.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-E2A2851E.png)

### Exporting run history

You can export the run history as a CSV file for offline analysis, auditing, and reporting.

To export run history:

1. To the right of the **Search by run ID** box, click **Export**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K1EVXLI2.png)
2. In the **Export CSV** popup, enter a name for the file in the **CSV Name** field, as shown below. Securiti automatically appends the `.csv.gz` extension to the file name.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JAGI45HL.png)
3. Click **Export CSV** to generate the file, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A9YI5WA5.png)

After Securiti generates the file, you receive an email with a link to download it. The download link expires after 24 hours.

## Refreshing Run History

To refresh the run history:

To the right of **Export** button, click **Refresh,** as shown below. The page displays the latest run history information.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TQSRPMF7.png)

## Viewing Data Tagging policy metrics

The **Run History** page displays the following metrics that summarize Data Tagging policy runs:

| Metrics | Description |
| --- | --- |
| Total Runs | Displays the total number of policy runs. |
| Runs Completed | Displays the total number of completed policy runs. |
| Tagging Actions | Displays the total number of tagging actions performed across all policy runs. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O3LHZPDM.png)

### Customizing the displayed columns

To customize the columns displayed on the **Run History** page:

1. In the upper-right corner of the table, click **Column Selector**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GJ0XQ5E9.png)
2. Select the checkboxes for one or more of the following columns you want to display, and clear the checkboxes for the columns you want to hide:

| Properties | Description |
| --- | --- |
| Run ID | Displays the unique identifier assigned to the policy run. |
| Policy ID | Displays the unique identifier of the Data Tagging policy associated with the run. |
| Policy Name | Displays the name of the Data Tagging policy associated with the run. |
| Status | Displays the current status of the policy run. The following statuses are supported: - `Running` - `Completed` - `Failed` - `Timed Out` - `Canceled` |
| Action | Displays the tagging action performed during the policy run. The following actions are supported: - `Add Tags` - `Remove Tags` - `Remove All Tags` |
| Started | Displays the date and time when the policy run started. |
| Scoped | Displays the number of nodes in the actionable scope, excluding previously tagged objects. |
| Succeeded | Displays the number of nodes that Securiti tagged or untagged successfully during the policy run. |
| Failed | Displays the number of nodes for which the tagging action failed during the policy run. |
| Correlation ID | Displays the unique identifier that you can use to correlate the policy run with system logs and troubleshoot execution issues. |
| Error Message | Displays the error message if an error occurs during the policy run. |
| Completed | Displays the date and time when the policy run completed. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IOW0QNO7.png)
3. Click **Apply** to update the columns displayed in the table, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6QXLL4W0.png)
4. To restore the default column configuration, click **Restore Defaults**, and then click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9KNW4T03.png)

## Viewing Step Details

To view the step details for a policy run:

1. On the **Run History** page, click **Details** for the desired policy run, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OTPWQ4BW.png)
2. In the **Step Details** popup, review the following information for the policy run:

| Properties | Description |
| --- | --- |
| Note Type | Displays the type of node processed during the policy run. |
| Progress | Displays the processing status of the node. The following processing statuses are supported: - `Running` - `Completed` - `Failed` - `Timed Out` - `Canceled` |
| Started | Displays the date and time when processing started. |
| Scoped | Displays the number of objects scoped for processing. |
| Succeeded | Displays the number of objects processed successfully. |
| Failed | Displays the number of objects that failed to process. |
| Error Message | Displays the error message if an error occurs during processing. |
| Completed | Displays the date and time when processing completed. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-15 at 9.53.33 AM.png)
