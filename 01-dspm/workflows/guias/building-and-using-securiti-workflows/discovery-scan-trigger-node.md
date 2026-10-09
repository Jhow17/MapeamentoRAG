---
title: "Discovery Scan"
slug: "discovery-scan-trigger-node"
updated: 2025-12-11T08:10:39Z
published: 2025-12-11T08:10:39Z
canonical: "helpcenter.securiti.ai/discovery-scan-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Discovery Scan

A discovery scan is a process in which Securiti scans customers' data systems to identify personal and sensitive data as well as relevant content profiles. This scan can be for structured, unstructured, and streaming data systems. First, we create data system instances and then configure the discovery scans for different data systems available for multi-cloud environments. For more information see, [Discover Scans](/v1/docs/discovery-scans).

A discovery scan trigger node gets triggered whenever the discovery scan is completed. The discovery scan result contains sensitive data elements, content profiles, and so on.

See the Node Configuration section to understand the node's working and properties.

### Prerequisites

To fetch the results of your processed discovery scan, you must [map your discovery scan trigger workflow to your discovery scan](/v1/docs/pausing-reassigning-and-deleting-a-discovery-scan).

### Example use case

As an example, let’s create a Workflow where the discovery scan node is triggered whenever a discovery scan is completed. It sends the scan results to the Spreadsheet file node to generate results in the RTF file and then emails the results to the owners to let them know about the results discovered. This result contains the personal information or sensitive data elements, and content profiles identified during the discovery scan jobs. Here is a breakdown of the Workflow:

- The discovery scan trigger node gets the results of discovery scans that may include sensitive data elements, content profiles, and so on.
- Generates an RTF from the discovery scan result received from the discovery scan trigger node.
- Emails the results (RTF file) to the respective owner.

#### Generating an RTF for the results of the discovery scan and emailing it to the owner

1. Add a discovery scan trigger node linked to the specific data system.

When you do so, choose the target type from the menu as per your requirement. It can be any structured, unstructured or streaming data system.

![ds_trigger_node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-011cbbc7-18bb-a605-2bea-bbfa9f06e1b8.png)
2. From the result of the discovery scan trigger node, process the data into an RTF file using the spreadsheet file node.

![spreadsheetfile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87c71d0b-a9f7-d325-084b-7f0b60de31af.png)
3. Add a Send Email node to send an email with the results of the discovery scan to the relevant owner.

![sendEmail.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55afdfee-f1b1-9990-120c-4d07e5362d46.png)
4. Create the pipeline and activate the Workflow.

![trigger_node_wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa4defd3-1433-7e4e-b072-fee0e42413e2.png)
5. Once you execute the Workflow successfully, it sends an email to the owner with the results of the discovery scan.

### Node Configuration

| Parameter | Description |
| --- | --- |
| Name | (Optional) Name of the discovery scan trigger |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node periodically based on the interval set. |
| Target Type | Select a target type for the discovery scan to trigger the Workflow. To trigger the discovery scan Workflow, you must activate the Workflow to run in the automated mode. See [Workflow node execution modes](/v1/docs/workflow-node-execution-modes) for more information. |
| Operation | List | Choose this operation to list the available discovery scans. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

### Adding a discovery scan trigger node

To automatically trigger the Workflow on any or select target types:

1. In Securiti, open **Sensitive Data Intelligence** module, and choose **Discovery Scans** > **Scan Definitions**.
2. Select a scan, click **Options** (three dots) on the right side of the scan, and choose **Open Scan**.
3. Click the **Responses** tab, and enable the toggle on the upper right side of the **Trigger Workflow** section.
4. To add a Workflow, click **Add Workflows** and on the **Add Trigger Workflow** popup, mark the checkbox for the discovery scan trigger Workflow that you want to map over this discovery scan. This section lists only the saved and active workflows.
5. Click **Add Workflows** at the bottom of the popup to save your changes.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
