---
title: "Configure discovery scans in Confluent Kafka"
slug: "configure-discovery-scans-in-confluent-kafka"
updated: 2025-10-31T13:57:41Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-confluent-kafka"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Confluent Kafka

This section describes creating a discovery scan for Confluent Kafka. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

1. In Securiti, open **Sensitive data Intelligence**, and choose **Discovery Scans > Scan Definitions**.
2. On the **Create Discovery Scan** page **Scan Details** area, enter a convenient name and description for the scan job.
3. In the **Scope** area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Confluent Kafka**. |
| Select Data Systems | Choose the specific Confluent Kafka data system instances to scan. |
| Data System Scope | (Optional) Expand the Data System Scope area, and for each selected data system, choose which topics to include or exclude in the scan. The default is all topics of all selected data system instances. You can also configure the scope of scanning by specifying a regex pattern. |
4. In the **Advanced Settings** area, use the following settings for your Streaming data systems.

| Parameter | Description |
| --- | --- |
| Sample first 'x' fields | Uses first ‘x’ fields for classification, where 'x' represents the number of fields that you want to include in the scan. For example, you may want to include the first 100 fields in this scan. |
| Sample random 'x' fields | Uses 'x' random fields for classification, where 'x' represents the number of random fields that you want to include in the scan. For example, you may want to include any 100 fields in this scan. |
| Sampling Limit | The number of fields' limit to scan. Specify the limit of the number of fields to scan. For example. You may want to scan no more than 10,000 fields. |
| Skip empty fields and fields containing the below values while scanning | Skips the fields containing certain values such as Unknown, NA, Null or Not Applicable, or empty. Enabling this option skip any empty fields and the fields containing the words configured in the dedicated space. This saves time and cost of scanning by not performing any additional scans.Securiti skips any empty fields and the fields containing the words configured in the dedicated space. |
| Perform field classification on fields previously learned | Performs field classification on previously learned fields and leverages any newly found evidence in those fields If you want to enable this option, Securiti performs field classification on fields previously learned and identifies any new entries. If the fields have no data, Securiticlassifies them as 'No match found', and if the fields have new data, that will automatically be classified in the new scan. |
| Include newly discovered topics into the scan scope | Considers all new topics automatically for scanning while maintaining the configurations done in the scope section. Securiti considers all new Streaming topics discovered for scanning which were described in the scope of the scan. If all topics are included then any new topics discovered will be part of the scan. You can also specify any particular Streaming topics to be included in the scan. |
5. In the **Sensitive data** area, choose the locality enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
6. In the **Sensitive data** area, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_structured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b626f22e-f77f-cdbc-adef-0eff29445609(19).png)
7. In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(30).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Custom Cron**

For custom cron jobs, use the [expression builder](/v1/docs/securiti-pods-and-elastic-pods). It has the minute, hour, day of the week, and day of the month settings. When you are done, use that expression in the Enter Cron field.

![cronjob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc9b8076-799b-9c0f-c533-8c0a42fe28c8(3).png)

You can also exclude the times when you don't want the scan to run and specify multiple times weekly, or monthly. Select the hour block(s) in the 24x7 matrix where scanning should be executed. The scan is automatically paused at the beginning of each execution block and resumed at the end.

![exclude_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46(3).png)
8. (Optional) In the **Responses** area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
9. (Optional) In the **Responses** area, trigger a specified Workflow. To do this, see [discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
10. Near the top right side of the page, click **Finish and Activate**. To view discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
