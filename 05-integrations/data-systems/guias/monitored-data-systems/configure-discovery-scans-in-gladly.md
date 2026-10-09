---
title: "Configure discovery scans in Gladly"
slug: "configure-discovery-scans-in-gladly"
updated: 2026-07-01T03:37:30Z
published: 2026-07-01T03:37:30Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-gladly"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Gladly

This section describes creating a Discovery scan for Gladly. For more information about Securiti discovery scans, see [Understanding discovery scans](/latest/docs/discovery-scans).

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for Gladly connectors:

- On the **Create Discovery scan** page, under **Scan details**, enter a convenient name and description for the scan job.
- In **Scope**, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Gladly**. |
| Select Data system(s) | Choose the specific Data system instances to scan. |
- In the **Data system Scope**, use the Data system tools to choose which inbox(es) to include or exclude from the scan. The exact tools vary by Data system type.

## Advanced settings

In **Advanced Settings**, use the following settings for your Structured data systems:

- Mark the checkbox for **Store Sample Data** to store your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on the appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page.

> [!NOTE]
> **Note**
> 
> - For Standard Pod deployments, you can enable this option without restrictions.
> - For EPod V2 deployments, Securiti checks whether PCS is configured:
>   - If PCS is not configured, you cannot enable this option and an error is displayed.
>   - If PCS is configured, you can enable the option and store sample files in PCS.

- Mark the checkbox for **Include evidence file for CLOB scanning in discovery scan job** to Include the evidence file for the scan option, private cloud storage to be turned on.

Marking this checkbox enables the **Max Detections to Store** field, where you can specify the limit per discovery scan, per column, and per data element type.

These limits influence the number of data elements that are collected in evidence files for a discovery scan job. The maximum limits for each control are as follows:
  - Per Discovery Scan Job: 2.5M
  - Per Column: 500K
  - Per Data Element Type: 100K

- **Scan Data From**: Select the date from which to scan data, from the calendar.

The Gladly application APIs require a start date for scanning. Securiti does not process data prior to this date. This applies to the following tables: Conversation, ConversationItems, Customers, Tasks, TaskComments.

- In the **Classification preferences for successive scans** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Perform classification on columns and tables previously learned | Performs field classification on previously learned columns and leverages any newly found evidence in those columns. When enabled, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan. |
| Retain manually classified data elements and content profiles | Mark the checkbox if you want to retain manually classified data elements and content profiles. It also appends new classifications as and when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When disabled, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for Gladly:

- In the **Sensitive Data** section, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - Choose the specific types of data to scan for. Click a category to open it and select specific element types as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-30 at 9.14.24 AM.png)

## Schedule settings

Perform the following steps to configure Schedule settings for Gladly:

- In the **Schedule**, choose either **Run Manually** or **Run on periodic schedules**, as shown below: ![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(52).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(47).png)

## Responses settings

Perform the following steps to configure Responses settings for Gladly:

(Optional) In the **Responses**, choose what responses Securiti takes when the scan completes. You can choose the following available response actions.

- **Send an Email Notification**: Notify about the scan job through emails. You can specify one or more emails with a relevant email template. Enter the email address(es) and select an email template from the menu.
- **Trigger Workflow**: Notify about the scan job by triggering a Workflow. To do this configure a [Discovery scan trigger node](/latest/docs/trigger-nodes).

Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
