---
title: "Configure discovery scans in Salesforce Customer Data Platform"
slug: "configure-discovery-scans-in-salesforce-customer-data-platform"
updated: 2026-07-01T09:40:04Z
published: 2026-07-01T09:40:04Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-salesforce-customer-data-platform"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Salesforce Customer Data Platform

This section describes creating a Discovery scan for Salesforce Customer Data Platform. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for Salesforce Customer Data Platform connectors:

- On the **Create Discovery scan** page under the **Scan Details** section, enter a convenient **Name** and **Description** for the scan job.
- In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Salesforce Customer Data Platform.** |
| Select Data Systems | Choose the specific Data system instances to scan. |
- In the **Data system Scope** section, select choose which Salesforce CDP Data Lake Object (Tables) and Salesforce CDP Data Model Object (Views) to include or exclude from the scan. The default is all tables and views of all selected Data system instances.

## Advanced settings

In the **Advanced Settings**, use the following settings for your Structured data systems. The settings available vary by Data system type.

- Mark the checkbox for **Store Sample Data** to store your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on the appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page.

> [!NOTE]
> **Note**
> 
> - For Standard Pod deployments, you can enable this option without restrictions.
> - For EPod V2 deployments, Securiti checks whether PCS is configured:
>   - If PCS is not configured, you cannot enable this option and an error is displayed.
>   - If PCS is configured, you can enable the option and store sample files in PCS.
- **Include newly discovered tables and schemas into the scan scope**: Considers all new tables and schemas automatically for scanning while maintaining the configurations done in the scope section. Selecting this option lets Securiti automatically include newly discovered tables and schemas in the scope of the scan.

- Mark the checkbox for **Scan of string data type (CLOB) columns** to Scan every field of a string data type column for every data element type. The string data types include VARCHAR, JSON, TINYTEXT etc. These data types vary for each data system.

- In the **Classification preferences for successive scans** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Perform classification on columns and tables previously learned | Performs field classification on previously learned columns and leverages any newly found evidence in those columns. When enabled, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan. |
| Retain manually classified data elements and content profiles | Mark the checkbox if you want to retain manually classified data elements and content profiles. It also appends new classifications as and when appropriate. When a new classification matches the manual classification, Securiti retains the manual classification. When disabled, Securiti overrides all system and manual classifications of tables and columns during a successive scan and performs new classifications to identify newly added columns or tables. |

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for Salesforce Customer Data Platform:

- In the **Sensitive data** section, choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(33).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(33).png)
- (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per Data element type in each document (up to 20,000) |
- If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
- If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the Discovery scan job.

## Schedule settings

Perform the following steps to configure Schedule settings for Salesforce Customer Data Platform:

- In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(82).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(76).png)

## Responses settings

Perform the following steps to configure Responses settings for Salesforce Customer Data Platform:

(Optional) In the **Responses** section, apply the following settings:

- Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
- Enable the **Trigger Workflow** toggle, and click **Add Workflow**. ![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(20).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(20).png)

For more information, see [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- Near the top right side of the page, click **Finish and Activate**.

A Discovery scan takes time to complete the process depending on the data available in the Data system Instance.
- Refer to the matching procedure to view the Discovery scan results.
  - On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  - On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
