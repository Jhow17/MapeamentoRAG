---
title: "Configure discovery scans in SAP HANA"
slug: "configure-discovery-scans-in-sap-hana"
updated: 2026-07-01T09:33:47Z
published: 2026-07-01T09:33:47Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-sap-hana"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in SAP HANA

This section describes creating a Discovery scan for SAP HANA. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for SAP HANA connectors:

- On the **Create Discovery scan** page, under the **Scan details**, enter a convenient name and description for the scan job.
- In **Scope**, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **SAP HANA**. |
| Select Data system(s) | Choose the specific Data system instances to scan. |
- In the **Data system Scope**, use the Data system tools to choose which databases, schemas, tables, and views to include or exclude from the scan. The exact tools vary by Data system type.

## Advanced settings

In the **Advanced Settings**, use the following settings for your Structured data systems:

- Under the For field classification section, configure the following settings:

| Setting | Description |
| --- | --- |
| Sample first ‘x’ rows | This setting collects the sample of the table and views with simple "LIMIT" query and classifies the first ‘x’ rows discovered. |
| Sampling Limit | This defines the size of the table sample (i.e, the number of rows) that is collected for classification, either by selecting the first rows or by fetching them randomly. You can set a minimum of 1 row and a maximum of 10,000 rows for sampling. |
| Store Sample Data | The option is enabled by default and stores your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page. > [!NOTE] > Note > > - For Standard pod deployments, you can enable this option without restrictions. > - For EPod V2 deployments, Securiti checks whether PCS is configured: > - If PCS is not configured, you cannot enable this option and an error is displayed. > - If PCS is configured, you can enable the option and store sample files in PCS. |
| Include empty database tables | Enable the **Include empty database tables** toggle to include tables with 0 rows for classification. If you disable the **Include empty database tables** option, discovery scan doesn't include empty tables for classification specifically if table headers are being classified. For more information, see [Customizing system data element types](/latest/docs/data-elements-customizing-system-data-element-types). Enabling this option disables the Skip empty fields and the fields below checkbox. |
| Skip empty fields and the fields below | Mark this checkbox to skip the rows that have empty values in all the CLOB columns fetched during the sampling. Enabling this option lets Securiti skip the fields containing certain values such as Unknown, NA, Null or Not Applicable, and so on. This saves time and cost of scanning by not performing any additional scans. |
| Include newly discovered tables and schemas into the scan scope | Considers all new tables and schemas automatically for scanning while maintaining the configurations done in the scope section. Selecting this option lets Securiti automatically include newly discovered tables and schemas in the scope of the scan. |

- Mark the checkbox for **Scan of string data type (CLOB) columns** to Scan every field of a string data type column for every data element type. The string data types include VARCHAR, JSON, TINYTEXT etc. These data types vary for each data system.

- Mark the checkbox for **Include evidence file for CLOB scanning in discovery scan job** to Include the evidence file for the scan option, private cloud storage to be turned on.

Marking this checkbox enables the **Max Detections to Store** field, where you can specify the limit per discovery scan, per column, and per data element type.

These limits influence the number of data elements that are collected in evidence files for a discovery scan job. The maximum limits for each control are as follows:
  - Per Discovery Scan Job: 2.5M
  - Per Column: 500K
  - Per Data Element Type: 100K

- In the **Classification preferences for successive scans** section, configure the following

settings:

| Setting | Description |
| --- | --- |
| Perform classification on columns and tables previously learned | Performs field classification on previously learned columns and leverages any newly found evidence in those columns. When enabled, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan. |
| Retain manually classified data elements and content profiles | Mark the checkbox if you want to retain manually classified data elements and content profiles. It also appends new classifications as and when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When disabled, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for SAP HANA:

- In the **Sensitive data** section, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - Choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_structured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b626f22e-f77f-cdbc-adef-0eff29445609(48).png)

## Schedule settings

Perform the following steps to configure Schedule settings for SAP HANA:

- In the **Schedule**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(84).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(78).png)

## Responses settings

Perform the following steps to configure Responses settings for SAP HANA:

(Optional) In the **Responses**, choose what responses Securiti takes when the scan completes. You can choose the following available response actions.

- **Send an Email Notification**: Notify about the scan job through emails. You can specify one or more emails with a relevant email template. Enter the email address(es) and select an email template from the menu.
- Enable the **Trigger Workflow** toggle, and click **Add Workflow**. ![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(21).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.

![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(21).png)

For more information, see [discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- **Register data assets into the Data Catalog**: Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:
    - | Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - Mark the **Extract Lineage from SQL** checkbox to enable or disable the field data assets lineage to the data catalog. Enabling this option extracts the lineage from SQL objects included inside schemas or databases in scope.
  - Mark the **Add Dataset in lower case** checkbox to add the structured or Streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> **Note**
> 
> If you want to convert your Data system (that has a unique set of names (tables, views, functions, topics, or columns) to lowercase Uniform Resource Names (URNs) in the data catalog, you can mark the **Register Dataset in the lower case** option for your current Data system from the structured or Streaming data dashboard.

For more information about structured data dashboard, see [Using the Validation Workbench to review classifications](/latest/docs/using-validation-workbench-to-review-and-validate-classifications).
  - Mark the **Always Execute Response** checkbox to ingest the datasets to the Enterprise Data Catalog regardless of whether it has already been registered before. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.

Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
