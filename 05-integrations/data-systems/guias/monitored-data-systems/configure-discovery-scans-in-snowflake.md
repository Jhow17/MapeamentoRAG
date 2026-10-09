---
title: "Configure discovery scans in Snowflake"
slug: "configure-discovery-scans-in-snowflake"
updated: 2026-08-10T11:24:50Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-snowflake"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Snowflake

This section describes creating a Discovery scan for Snowflake. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for Snowflake connectors:

- On the **Create Discovery scan** page, under **Scan details**, enter a convenient name and description for the scan job.
- In **Scope**, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Snowflake**. |
| Select Data system(s) | Choose the specific Data system instances to scan. |
- In the **Data system Scope**, use the Data system tools to choose which databases, schemas, tables, and views to include or exclude from the scan. teThe exact tools vary by Data system type.

## Advanced settings

In the **Advanced Settings**, use the following settings for your Structured data systems:

| Parameter | Description |
| --- | --- |
| Sample random ‘x’ rows | This setting enables the random sampling process, which collects the data Column wise and in a random manner. You can set a minimum of 1 Row and a maximum of 500 rows for sampling. > [!WARNING] > **Important** > > - Random sampling is a resource-intensive operation, depending on the Table size and the data source's access latency. > - Securiti does not support random sampling on views. The process applies to tables only. |
| Sampling Limit | This defines the size of the table sample (i.e, the number of rows) that is collected for classification by randomly fetching them. - For random 'x' rows, you can set a minimum of 1 row and a maximum of 500 rows for sampling. |
| Skip empty fields and fields containing the below values while scanning | Skips any empty fields and the fields containing the words configured in the dedicated space. Enabling this option lets Securiti skip the fields containing certain values such as Unknown, NA, Null or Not Applicable, and so on. This saves time and cost of scanning by not performing any additional scans. |
| Sync masking policies | Enable the option to automatically sync the masking policies each time a scan job is run on the Data system. |
| Sync roles | Enable the option to automatically sync the data source roles each time a scan job is run on the Data system. |
| Include newly discovered tables and schemas into the scan scope | Considers all new tables and schemas automatically for scanning while maintaining the configurations done in the scope section. Selecting this option lets Securiti automatically include newly discovered tables and schemas in the scope of the scan. |
| Store Sample Data | The option is enabled by default and stores your sample files at your desired location configured during the connector Activation process. When disabled, Securiti does not store any sample files on Appliance or Cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page. > [!NOTE] > **Note** > > Sample files stored on Cloud support encryption feature. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable this feature for tenant. Files stored on Appliance are not encrypted. |
| Full scan of String data type (CLOB) columns | Scans every field of a string data type Column for every Data element type. These data types include: - JSON - ARRAY - STRUCT - STRING If you want to initiate Table training for specific tables and columns, see [Table training for structured data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems). > [!NOTE] > **Note** > > Mark the checkbox if you want to enable Clob classification. Securiti maps Clob elements in any Column as "All Data Elements" under the Table Training tab. |
| Full Scan | Mark the checkbox for the **Full Scan** option to include all rows for CLOB data matching the string types selected in the **Full scan of String data type columns** option above. This option is marked by default. |
| Sample Scan | Mark the check box for **Sample Scan** to select sample of rows you want to include in the columns that have data types matching the string types selected in the **Sample scan of clob data type Column** option. > [!NOTE] > **Note** > > **Sample Scan** option limits the number of rows for scanning the CLOB data matching the string types you selected. |
| Sample first ‘x’ rows | This setting collects the sample of the CLOB columns type with simple "LIMIT" query and classifies the first ‘x’ rows discovered. You can set a minimum of 1 Row and a maximum of 100,000 rows for sampling. For example, you may want to include the first 1000 rows of your Table in the scan. |
| Sample random ‘x’ rows | This setting enables the random sampling process which collects the data CLOB columns wise and in a random manner. You can set a minimum of 1 Row and a maximum of 500 rows for sampling. |
| Skip empty fields and fields containing the below values while scanning | Mark this checkbox to skip the rows that have empty values in all the CLOB columns fetched during the sampling. Enabling this option lets Securiti skip the fields containing certain values such as Unknown, NA, Null or Not Applicable, and so on. This saves time and cost of scanning by not performing any additional scans. |
| Include evidence file for clob scanning in the Discovery scan job | Includes the evidence file for the scan. This option requires private Cloud storage to be turned on. To enable classification on columns and tables, mark the **Perform classification on columns and tables** checkbox. This enables the **Max Detections to Store** field where you can specify the limit per Discovery scan, per Column, and per Data element type. |
| Max Detections to Store | Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the limit according to: - Total detections per scan job (up to 2.5 million) - Total detections per Column (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| Perform classification on columns and tables previously learned | Performs field classification on previously learned columns and leverages any newly found evidence in those columns. If you want to enable this option, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan. |
| Retain manually classified data elements and content profiles | If you want to retain manually classified data elements and content profiles, enable this option. It also appends new classifications as and when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When you do not want to use this option, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |
| Allow Exact Data Profiles | Mark the checkbox if you want the Exact Data Profiles to be used as a validator in structured discovery scans. You can use Exact data matching (EDM) profiles to identify if records from a known dataset Match any of the records given in an EDM index for your Data system. In the **Scan Depth of Exact Data Scanning**, specify the top number of rows as the scan depth. |

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for Snowflake:

- In the **Sensitive data** section, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - Choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_structured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b626f22e-f77f-cdbc-adef-0eff29445609(42).png)

## 

## Schedule settings

Perform the following steps to configure Schedule settings for Snowflake:

- In the **Schedule**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(47).png)

## Responses settings

Perform the following steps to configure Responses settings for Snowflake:

(Optional) In the **Responses**, choose what responses Securiti takes when the scan completes. You can choose the following available response actions.

- **Send an Email Notification**: Notify about the scan job through emails. You can specify one or more emails with a relevant email template. Enter the email address(es) and select an email template from the menu.
- Enable the **Trigger Workflow** toggle, and click **Add Workflow**.

![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(12).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.

![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(12).png)

For more information, see [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- **Register data assets into the Data Catalog**: Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
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
- **Synchronize Data Assets in Third Party Data Catalogs**: To add the schemas, tables, and columns to the third-party data catalog, choose the relevant Integration from the list. Mark the **Create asset in third party data catalog if they do not exist** checkbox to create new assets in the third party data catalog.

Near the upper right corner of the page, click one of the following:

- **Finish and Activate**, which saves and activates the discovery scan immediately.
- **Save**, which saves the scan configuration without activating it.
- **Save as Draft**, which saves the scan as a draft for completion at a later time.
