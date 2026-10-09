---
title: "Building and using Securiti workflows"
slug: "building-and-using-securiti-workflows"
updated: 2026-01-06T09:06:59Z
published: 2026-01-06T09:06:59Z
canonical: "helpcenter.securiti.ai/building-and-using-securiti-workflows"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Building and using Securiti workflows

A workflow is a pipeline that you can construct by stitching together triggers, data systems and processing nodes. You use workflows to accomplish complex data processing tasks in Securiti. A workflow is either triggered on the occurrence of a specific event or manually started by the user or periodically via a CRON node, and completes after the execution of every connected node in the workflow. The output of each node is passed onto the next node for processing.

You can either execute individual nodes to execute discrete components or nodes within the overall workflow or execute the whole workflow that refers to the end-to-end process of running and completing all the defined steps or nodes within a workflow.

### Nodes in a workflow

A workflow is created by a combination of multiple nodes that are connected together to execute in such a way that each node performs an individual task. The nodes can be categorized as shown below:

#### Trigger Nodes

A trigger node gets triggered based on the conditions or the interval set in the node configuration. Unlike the regular nodes, the trigger nodes get triggered when the node detects the specified event or condition.

![Screenshot_2024-01-29_at_1_08_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec75f681-7957-92e2-9bc4-33236309da83.png)

#### Regular Nodes

A regular node works in a regular fashion and is used to perform operations such as functions like data manipulation, filtering, conditional branching, database interactions, or any other action needed to complete the automation process.

![Screenshot_2024-01-29_at_1_50_03_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e904b76-3fd2-1db7-905d-5998122f3aaf.png)

#### Conditional Nodes

A conditional node in a workflow acts as a decision point where the direction of the process is determined based on specified conditions. These conditions guide the workflow along different paths based on the data evaluation.

![Screenshot_2024-01-29_at_1_51_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3951f49e-dc4f-5e0c-97ea-b6987d1df15a.png)

#### Data system Nodes

Data system nodes refer to the nodes that handle the processing, storage, or management of sensitive data within the Securiti platform. These nodes play a crucial role in implementing security measures, such as access controls, encryption, or data masking, to ensure compliance with privacy regulations and protect sensitive information.

![Screenshot_2024-01-29_at_1_53_05_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2455f05-7283-1fa6-f191-993743740c67.png)

### Why use Workflows?

Automation through workflows is essential in streamlining and optimizing complex business processes. By defining and automating sequential tasks within a workflow, organizations can significantly reduce manual intervention, minimize errors, enhance efficiency, and ensure consistency in operations.

Workflows basically automate routine and repetitive tasks which not only accelerates productivity but also improves overall accuracy and compliance. Additionally, automation enables better visibility into processes, facilitating data-driven decision-making. In a rapidly evolving landscape, the need for automation through workflows is important for staying competitive, agile, and responsive to changing demands.

### Examples

#### Vulnerability Management Workflow for New Asset Additions in Dynamic IT Environments

In a dynamic IT environment, you can create a workflow that ensures the security of new assets added to an organization's catalog through automated vulnerability management. Initiated by the addition of a new asset, Securiti seamlessly integrates with ServiceNow to generate a ticket for IT/security teams. Real-time responsiveness is guaranteed as Securiti detects trigger events, and teams are notified via Slack about the new Zendesk ticket. The workflow promotes a proactive and systematic approach to vulnerability management, accelerating response times to security threats and enhancing overall security posture through the seamless integration of Securiti and ServiceNow.

#### Streamlined Assessment Workflow for Cloud and On-Premises Deployments

In this vendor onboarding assessment workflow, initiated through the Assessment Trigger Node, vendors are prompted to provide contact information and specify deployment type such as **cloud** or **on-prem**. This data collection sets the stage for the process that utilizes an IF Node as a central decision point, determining deployment type and branching into distinct pathways for cloud and on-premises vendors. Following this divergence, specialized Assessment nodes generate assessments for each deployment type, ensuring automatic alignment with the vendor's specifications. This streamlined workflow enhances efficiency in vendor assessments to make the onboarding process seamless and enable the businesses to swiftly evaluate and integrate new vendors based on their deployment preferences.

#### Managing Unmonitored Data Access through Streamlined User Data Retrieval and Processing

In this example, a workflow is designed to handle user data stored in unmonitored data systems that Securiti does not directly connect with or scan. These systems are designated as placeholders, prompting Securiti to alert subtask owners when DSR requests are received. Upon submission of an access request, the workflow is triggered to generate tasks and subtasks for the relevant unmonitored data system. Using an HTTP Request node, the workflow retrieves the data subject's information through a POST API endpoint. The fetched data, presented in the form of a CSV file, is then processed by a Process CSV component, and the resulting CSV is attached to the subtask for further action. This streamlined process ensures that even data residing in unmonitored systems is appropriately assessed and managed in response to data subject requests.

## Related

- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
