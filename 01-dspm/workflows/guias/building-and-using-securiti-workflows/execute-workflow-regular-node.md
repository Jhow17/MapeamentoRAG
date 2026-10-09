---
title: "Execute Workflow"
slug: "execute-workflow-regular-node"
updated: 2026-02-12T14:29:25Z
published: 2026-02-12T14:29:25Z
canonical: "helpcenter.securiti.ai/execute-workflow-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Execute Workflow

Execute workflow node in Securiti is used to execute another workflow within a workflow. This node facilitates the creation of centralized logic, enabling the reuse of common sets of actions across multiple workflows. Modularization not only simplifies maintenance but also promotes collaboration by allowing different teams or individuals to work on independent components that can be seamlessly integrated into a cohesive automation solution.

Breaking down complex workflows into smaller, reusable modules can lead to more optimized memory usage. Since each modular workflow focuses on specific tasks or actions, it allows for better resource management, preventing unnecessary memory overhead associated with executing an entire monolithic workflow. This results in improved performance and responsiveness of the automation system. This can be particularly beneficial in scenarios where memory constraints are a consideration, leading to a more streamlined and resource-efficient automation process.

Refer to the [Node Configurations section](/v1/docs/execute-workflow) to understand the node properties and descriptions.

#### Example use case

Consider a workflow example that fetches a list of users using an API. Based on the produced results the workflow branches further based on the roles of the users. For example, if the role of the user is super admin, the workflow goes to another workflow that handles the data of users for that specific role. The other workflows then fetch the user details and writes data in the database based on the roles of the users.

The following nodes are used in this workflow:

1. [HTTP Request Node](/v1/docs/http-request)
2. [Unwrap Node](/v1/docs/unwrap)
3. [Switch Node](/v1/docs/switch)
4. Execute Workflow Node

#### Executing Workflows based on the user roles

1. Start the workflow by adding an **HTTP request node** to fetch the details of the user using the Get users API.
2. Add the **unwrap node** to convert the data object into a list item.
3. Add the switch node to route the workflow based on the user roles. Add the role names and set the output to the respective node.
4. Connect the Execute workflow node by providing the IDs of the relevant workflows as per the user roles.

![Screenshot_2023-12-12_at_2_42_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-414642c6-d22e-ebc1-51e7-ff912533f0b6.png)
5. Connect the nodes and execute the workflow.

![Screenshot_2023-12-12_at_2_42_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a075cde4-6821-3ba9-f0ec-383399dec3a9.png)

> [!NOTE]
> **Note**
> 
> - Executions are displayed in the Execution Listing that are initiated through the Execute Workflow node. This applies specifically to executions triggered by active workflows.

#### Node configurations

| Parameters | Description |
| --- | --- |
| Source |  | Where to load the workflow from |
| Database | Choose this option if the source of the workflow is database and you need to incorporate another workflow from the database. |
| Parameter | Choose this option to select a Workflow from the parameters. |
| Workflow ID | Specify the workflow ID that is to be used within the workflow. For example, 1234. *You can find this ID in the Workflow URL.* |
| Workflow JSON | Specify the JSON of the workflow that needs to be used. |
