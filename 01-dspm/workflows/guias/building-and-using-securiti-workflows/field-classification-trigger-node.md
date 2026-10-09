---
title: "Field Classification"
slug: "field-classification-trigger-node"
updated: 2025-10-30T19:12:04Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/field-classification-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Field Classification

Classification refers to training a model to make predictions or identify personal or sensitive information from different data systems. These data systems can be structured, unstructured, or streaming. There are various algorithms and techniques used for classification, including decision trees, support vector machines, k-nearest neighbours, and neural networks.

A Field Classification (FC) trigger node operates on classifications found in a structured data store. It lists columns by filtering for specific data elements if specified in the filter. Once listed, it can be used to send this classification to the respective owner of the data system.

#### Example Use Case

As an example, let’s create a Workflow where the FC trigger node which is triggered whenever a classification is run and generates the results in the form of personal or sensitive information identified after the classification job. In this use case, we can use the classification results to populate a GCP data catalog. Here is a breakdown of the Workflow:

1. The FC trigger node is triggered whenever a new classification is found in a structured data system. It can be new data elements or changes in the existing data elements. The FC trigger node gets the results of that classification which may include sensitive data elements.
2. Populate a GCP data catalog node for the respective classification results.

#### Populating a GCP data catalog from the FC trigger nodes results

1. Add a Field Classification Trigger node and list the data elements that you are interested in to get identified. You can also set the page size and interval and unit of time whether minutes or hours.

![fctrigger-config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be2c5f7c-0fb1-387a-6395-7adf2328f1cd.png)
2. From the result of the Field Classification Trigger node, analyze the results via the GCP data catalog node.
3. Create the pipeline and activate the Workflow.

![fctrigger-nodes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12c6846c-89de-c11b-b923-c7e08167b91d.png)
4. Once you execute the Workflow successfully, it sends an email to the owner with the results of the discovery scan. This is what the success response looks like.

![fctrigger_gcp-results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ffd72e0-88a0-2f41-9dd0-3981f59845f9.png)

#### Node Configuration

| Parameter | Description |
| --- | --- |
| Name | Specify the name of the FC trigger Workflow |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node based on the interval set. |
| Datasource | From the Datasource list, choose a specific data source to fetch the classification for. |
| Match Data Elements | If you want the data elements to be matched with the classification, enable the **Match Data Elements** toggle. When enabled, it accepts a list of data elements to match incoming classifications. "Contains Data Elements" flag is raised only if incoming classifications contain matching Data Elements. |
| Data Element Type | Select the data elements from the **Data Element Types** list. |
| Operation | List | Choose this operation to list the available assessments. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |
| Additional Filter | Specify any additional filters (if any) |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
