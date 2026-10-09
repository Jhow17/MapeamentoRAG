---
title: "Configure discovery scans in Kafka"
slug: "configure-discovery-scans-in-kafka"
updated: 2025-10-31T14:03:23Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-kafka"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Kafka

This section describes creating a Discovery scan for Kafka. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

1. In Securiti, open **Sensitive data Intelligence**, and choose **Discovery Scans > Scan Definitions**.

> [!NOTE]
> **Note**
> 
> You can resize the width of columns appearing under the **Discovery Scans List** page. To do so, move the cursor to the edge of the Column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the Column and release the mouse button.
2. In the **Scan Details** area, give the Discovery scan a name and a description.
3. In the **Scope** area, choose **Kafka** from the **Select Target** menu and choose the relevant Data system Instance from the **Select Data system(s)** menu.
4. In the **Scope** area, use the **Data system Scope** tools to choose which Streaming topics to include or exclude from the scan.

![streaming_data_system_scope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57f920cd-5051-9595-e93a-20b2f1a8a736(1).png)
5. In the **Advanced Settings** area, use the following settings for your Streaming data systems.

| Parameter | Description |
| --- | --- |
| Sample first 'x' fields | Uses first ‘x’ fields for classification, where 'x' represents the number of fields that you want to include in the scan. For example, you may want to include the first 100 fields in this scan. |
| Sample random 'x' fields | Uses 'x' random fields for classification, where 'x' represents the number of random fields that you want to include in the scan. For example, you may want to include any 100 fields in this scan. |
| Sampling Limit | The number of fields' limit to scan. Specify the limit of the number of fields to scan. For example. You may want to scan no more than 10,000 fields. |
| Skip empty fields and fields containing the below values while scanning | Skips the fields containing certain values such as Unknown, NA, Null or Not Applicable, or empty. Enabling this option skip any empty fields and the fields containing the words configured in the dedicated space. This saves time and cost of scanning by not performing any additional scans.Securiti. Skips any empty fields and the fields containing the words configured in the dedicated space. |
| Perform field classification on fields previously learned | Performs field classification on previously learned fields and leverages any newly found evidence in those fields If you want to enable this option, Securiti performs field classification on fields previously learned and identifies any new entries. If the fields have no data, Securiticlassifies them as 'No Match found', and if the fields have new data, that will automatically be classified in the new scan. |
| Include newly discovered topics into the scan scope | Considers all new topics automatically for scanning while maintaining the configurations done in the scope section. Securiti considers all new Streaming topics discovered for scanning which were described in the scope of the scan. If all topics are included then any new topics discovered will be part of the scan. You can also specify any particular Streaming topics to be included in the scan. |
6. In the **Sensitive data** area, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
7. In the **Sensitive data area**, choose the specific types of data to scan for. Click a category to open it and select specific elements as shown below.

![sensitive_data_streaming_ds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7334a54e-1fee-baea-4521-a9d2aefa4c7b.png)
8. In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(58).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Custom Cron**

For custom cron jobs, use the [expression builder](/v1/docs/securiti-pods-and-elastic-pods). It has the minute, hour, day of the week, and day of the month settings. When you are done, use that expression in the Enter Cron field.

![cronjob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc9b8076-799b-9c0f-c533-8c0a42fe28c8(5).png)

You can also exclude the times when you don't want the scan to run and specify multiple times weekly, or monthly. Select the hour block(s) in the 24x7 matrix where scanning should be executed. The scan is automatically paused at the beginning of each execution block and resumed at the end.

![exclude_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46(5).png)
9. (Optional) In the **Responses** area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
10. (Optional) In the **Responses** area, enable the **Trigger Workflow** toggle, and click **Add Workflow**.

![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(3).png)

On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.

![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(3).png)

For more information, see [discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
11. (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - Mark the **Add Dataset in lower case** checkbox to add the structured or Streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> **Note**
> 
> If you want to convert your Data system (that has a unique set of names (tables, views, functions, topics, or columns) to lowercase Uniform Resource Names (URNs) in the data catalog, you can mark the **Register Dataset in the lower case** option for your current Data system from the structured or Streaming data dashboard.
  - Mark the **Always Execute Response** checkbox to ingest the datasets to the Enterprise Data Catalog regardless of whether it has already been registered before. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.
12. Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
