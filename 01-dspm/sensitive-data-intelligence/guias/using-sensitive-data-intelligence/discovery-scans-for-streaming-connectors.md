---
title: "Discovery scans for streaming connectors"
slug: "discovery-scans-for-streaming-connectors"
updated: 2026-09-29T11:18:26Z
published: 2026-09-29T11:18:26Z
canonical: "helpcenter.securiti.ai/discovery-scans-for-streaming-connectors"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Discovery scans for streaming connectors

Streaming data is data in motion. Thousands of sources generate it continuously, and each source sends records of differing size and volume in real time. Configure the discovery scan for streaming data to let Securiti scan the topics on your streaming data systems and identify the sensitive data elements and content profiles that exist in those topics.

To create a discovery scan for a streaming data system such as Kafka, Confluent Kafka, or Amazon MSK, follow the steps below.

## Specifying the scan details and scope

To specify the scan details and scope:

1. From the sidebar, hover over **Sensitive Data Intelligence** and choose **Discovery Scans > Scan Definitions.**
2. Near the upper-right corner of the **Scan Definitions** page, click **+ Create Discovery Scan**, as shown below.

![Overview of scan definitions with active and completed job statuses displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creatediscoveryscanoption_scandefinitions(2).png)
3. In the **Scan Details** area, enter a name and description for the scan.

![Creating a discovery scan for Kafka with job details and scope settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scandetails_streamingdatasystem.png)
4. In the **Scope** area, choose **Kafka**, **Confluent Kafka**, or **Amazon MSK** from the **Select Target** list, then choose the relevant data system instance from the **Select Data System(s)** list.

![Interface for selecting data systems with options for Kafka instances displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectdatasysteminstance_streamingdiscoveryscan.png)
5. In the **Scope** area, use the **Data System Scope** tools to choose which streaming topics to include in or exclude from the scan.

![Kafka data system selection with topic inclusion and exclusion options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemscope_streamingdiscoveryscan.png)

## Configuring advanced settings for a scan

In the **Advanced Settings** area, configure the following settings for your streaming data system.

![Settings for field classification including options for sampling and skipping empty fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_streamingdiscoveryscans.png)

Use the following table to understand these settings:

| Setting | Description |
| --- | --- |
| Sample first 'x' fields | Uses the first 'x' fields for classification, where 'x' is the number of fields you want to include in the scan. For example, you can include the first 100 fields. |
| Sample random 'x' fields | Uses 'x' random fields for classification, where 'x' is the number of random fields you want to include in the scan. For example, you can include any 100 fields. |
| Sampling Limit | Specifies the maximum number of fields to scan. For example, you can scan no more than 10,000 fields. |
| Skip empty fields and fields containing the below values while scanning | Skips empty fields, and fields that contain values such as `Unknown`, `NA`, `Null`, or `Not Applicable`. When you enable this setting, Securiti skips empty fields and any field that contains the words you configure in the dedicated space, which saves scanning time and cost. |
| Perform field classification on fields previously learned | Performs field classification on fields Securiti learned previously and uses any new evidence found in those fields. - If a field has no data, Securiti classifies it as "No match found". - If a field has new data, Securiti classifies that data in the new scan. |
| Include newly discovered topics into the scan scope | Automatically includes all newly discovered topics in the scan scope, while retaining the configuration you set in the **Scope** section. If you include all topics, Securiti adds every newly discovered topic to the scan. You can also specify particular streaming topics to include. |

## Specifying sensitive data specifications

To specify the sensitive data specifications for a scan, follow the steps below:

1. In the **Sensitive Data** area, choose the locality enabled for your tenant.
2. Choose the specific types of data to scan. Click a category to open it, then choose the required data elements and content profiles.

![Data element categories for sensitive data management, including authentication and financial information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedataspecifications_streamingdiscoveryscans.png)

## Configuring the scan schedule

In the **Schedule** area, choose either **Run Manually** or **Run on periodic schedules**, as shown below.

![Settings for scheduling tasks, including frequency and time options for execution.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scheduleoptions_streamingdiscoveryscans.png)

Use the following table to understand the scan schedule options:

| Scan option | Specifications |
| --- | --- |
| Run Manually | Activate and deactivate the scan manually, and start or cancel it whenever you choose. |
| Run on periodic schedules | The scheduled time starts and ends according to your local time or the time set in your device settings. Set the specific time for your scan, choose **Daily**, **Weekly**, or **Monthly** from **Periodic Schedule Frequency**, and specify a time of the day, week, or month. |

### Using a custom cron expression

For custom cron jobs, use the [expression builder](https://crontab.guru/), which provides minute, hour, day of the week, and day of the month settings. Enter the resulting expression in the **Enter Cron** field, as shown below.

![Settings for scheduling a job with a custom cron expression and timezone.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/customcron_streamingdiscoveryscans.png)

> [!NOTE]
> Note
> 
> Securiti does not allow a scan to start immediately after it times out or errors, because Securiti performs back-end checks and remediation actions first. The scan job can take up to an hour to start automatically, with no action required from you. The **Scan Now** option remains disabled for an hour until the system recovers.

## Specifying responses for a scan

Configure the **Responses** section to choose what Securiti does when the scan completes.

1. (Optional) In the **Responses** area, specify one or more email addresses with a relevant email template.
2. (Optional) In the **Responses** area, trigger a discovery scan workflow. To do this, configure a [discovery scan trigger node](/latest/docs/discovery-scan-trigger-node).

![Email notification settings with options for workflow triggers and data asset registration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscanresponses_streamingdiscoveryscan.png)
3. (Optional) In the **Responses** area, scroll to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** to add a new table or topic, or to update all table and topic selections. Mark **Add sections if not present** to add a new topic.
4. From the **Default Governance Status** menu, choose the appropriate status for the metadata being ingested.
5. Mark the **Extract Lineage from SQL** checkbox to extract the lineage of field data assets from the SQL objects included in the schemas or databases in scope.
6. Mark the **Add Dataset in lower case** checkbox to add structured or streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> Note
> 
> To convert a data system that has a unique set of table, view, function, topic, or column names to lowercase URNs in the data catalog, mark **Add Dataset in lower case** for that data system on the structured or streaming data dashboard.
7. Mark the **Always Execute Response** checkbox to ingest the datasets into the Enterprise Data Catalog whether or not they were registered previously. This setting keeps your catalog accurate as your data changes, as shown below.

![Data catalog registration options including governance status and environment settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datacatalog_structureddatadiscovery.png)

Use the following table to understand the governance statuses you can choose for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |

## Saving and activating the scan

After completing all the scan configurations, near the upper-right corner of the page, click one of the following options.

![Interface for creating a Discovery Scan with various options and buttons highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveoptions_discoveryscans.png)

Use the following table to understand the save options:

| Option | Description |
| --- | --- |
| Finish and Activate | Saves and activates the discovery scan immediately. |
| Save | Saves the scan configuration without activating it. |
| Save as Draft | Saves the scan as a draft for completion at a later time. |

For more information, see [Viewing discovery scan results for streaming data systems](/latest/docs/viewing-discovery-scan-results) and [Using the Streaming Data Discovery dashboard](/latest/docs/using-the-streaming-data-discovery-dashboard).
