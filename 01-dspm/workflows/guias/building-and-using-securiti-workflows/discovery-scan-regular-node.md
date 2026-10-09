---
title: "Discovery Scan"
slug: "discovery-scan-regular-node"
updated: 2026-01-09T09:54:25Z
published: 2026-01-09T09:54:25Z
canonical: "helpcenter.securiti.ai/discovery-scan-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Discovery Scan

A discovery scan basically scans all the structured data systems and filters out the sensitive data based on the scan results. This scan is launched both on-demand or periodically. For large data systems, where multiple teams are dealing with data for multiple purposes, discovery scans can be created for the specific portion of the data managed by the team/person.

Securiti provides a node for Discovery scan in the Workflows module that can perform the following set of actions:

- Start/stop a discovery scan
- List discovery scans
- Fetch discovery scan details by ID
- Pause/resume a discovery scan

#### Example use case

In this example, we are creating a Workflow that revolves around responding to assessment answers by triggering discovery scans specific to the mentioned assets. The Discovery Scan Node takes center stage, orchestrating the initiation of these scans, while prior steps collect assessment details and identify the relevant scans. This workflow streamlines the process of proactively scanning and monitoring assets based on assessment responses.

This Workflow begins with an initial trigger event related to responses to assessment questions tied to assets or data systems using the **Assessments Trigger**Node.

Before getting to the Discovery Scan Node, the system gathers details about the assessment itself. This includes information such as the assessment's title, description, date, and the specific assessment question that prompted the trigger event.

The crux of this Workflow is the **Discovery Scan Node**. Once a response is received for an assessment question, the Workflow seamlessly moves into the Discovery Scan Node. The node lists all the discovery scans and another Discovery scan node is responsible for initiating the discovery scan relevant to the asset mentioned in the assessment.

The following nodes are the part of this workflow:

1. Assessments Trigger Node
2. Assessments Node
3. IF Node
4. Discovery Scan Node

Jump to the [Node Configuration](/v1/docs/pausing-reassigning-and-deleting-a-discovery-scan) section to understand the node parameters and descriptions.

#### Initiating Discovery Scan based on the Assessment response for an Asset

1. Create an Assessment Trigger node for the assessment linked to the specific data system (asset). Refer to the [Assessments Trigger node](/v1/docs/assessments) for understanding the working of this node.
2. Add an Assessment node that fetches the details of the assessment triggered in the previous step.
3. Fetch discovery scans using the List operation. Use the IF node to put a condition where the asset is set as the same asset that is associated with the assessment. In case the output is true, it goes to the next step.
4. Finally, provide the discovery scan ID after selecting Start in the operation and start the discovery scan linked to the asset.

![discovery-scan-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-973e32af-1648-ab3c-042f-47b41bf11a0f.png)
5. Connect the nodes and execute the workflow.

![discovery-scan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbd11e4b-e643-e0f1-939c-4dfd70512f05.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![discovery-scan-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72efe239-62c6-2bc0-8ac8-28df357d2ac4.png)

#### Node configurations

| Parameters |
| --- |
| Operation | Specify the operation that needs to be performed using the Discovery scan node. |
| List | Select this option to list all the discovery scans. |
| Get | Select this option to fetch a discovery scan against the specified ID. |
| Start | Select this option to start a discovery scan against the specified ID. |
| Stop | Select this option to stop a discovery scan against the specified ID. |
| Pause | Select this option to pause a discovery scan against the specified ID. |
| Resume | Select this option to resume a discovery scan against the specified ID. |
| Discovery Scan ID | Specify the unique ID of the discovery scan, for example, 1234. |
| Scan Job ID | Specify the scan job ID if the operation selected is stop, pause or resume. |
