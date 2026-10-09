---
title: "IF"
slug: "if-regular-node"
updated: 2026-01-16T06:16:51Z
published: 2026-01-16T06:16:51Z
canonical: "helpcenter.securiti.ai/if-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# IF

In the workflow automation module, IF node is a conditional or decision node. It is a fundamental component that enables you to create branching logic within the workflow. Its primary purpose is to evaluate a condition or a set of conditions and then direct the flow of the workflow based on the result of that evaluation.

The IF node works by assessing a predefined condition, which can be a logical statement, a variable value, or any other criteria that can be evaluated as true or false. For example, it might check if a certain value is greater than another, if a specific checkbox is selected, or if a date has passed. Depending on the outcome of the condition evaluation, the IF node has two or more output paths leading to different nodes. For multiple conditions, the outcome can be combined with an OR or AND to evaluate if any condition is met or all conditions are met respectively.

This branching logic allows you to create complex workflows with multiple possible outcomes, making it a crucial tool for automating business processes, data validation, and other scenarios.

Refer to the [Node Configuration](/v1/docs/if) section to understand the node parameters and description.

#### Example use case

As an example use case, we're outlining a vendor onboarding assessment workflow. The workflow is initiated through the Assessment Trigger Node. This node prompts vendors to provide their contact information and specify their deployment type as either 'cloud' or 'on-premises’. The node is connected to the HTTP Request node that fetches the assessment details.

Then comes the IF Node that stands as a central decision point in the workflow. Based on the responses received via the Assessment Trigger Node, this node determines whether the vendor's deployment is cloud-based or on-premises. This evaluation then leads to two distinct pathways: one for cloud vendors and another for on-premises vendors and the relevant assessments are created.

The following nodes are used in this workflow:

1. [Assessment Trigger Node](/v1/docs/assessments)
2. IF Node
3. [HTTP request Node](/v1/docs/http-request)
4. [Assessment Node](/v1/docs/assessment)

#### Branching the Assessment creation based on vendor type

1. Add the Assessment Trigger node with the name and configure the trigger type to Question Response.
2. Add the HTTP request node to fetch the assessment details based on the Assessment trigger node.
3. Add the **IF Node** to execute conditional logic based on the information gathered through the Assessment Trigger Node. Configure the IF Node to evaluate the response from the Assessment Trigger Node, specifically examining whether the vendor's deployment type is marked as *cloud* or *on-prem*. Based on this evaluation, set up the IF Node to route the workflow to different paths:

![IF-results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34d181d2-ef59-4124-fcd3-aaf001c0430d.png)
  - If the vendor's deployment is identified as *cloud,* define the actions within this path to create a cloud-specific vendor assessment using the appropriate assessment template.
  - If the vendor's deployment is identified as *on-prem*, configure this path to create an on-premises vendor assessment using the corresponding assessment template.
4. Add the Assessment nodes to create the relevant assessment based on the response from the IF node. Both the branches of the IF node are connected to unique Assessment nodes to create the subsequent assessment.
5. Connect the nodes and execute the Workflow.

![Assessment-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-211d554d-7c14-d680-a22b-a0f2e254ac20.png)
6. Upon successful execution, you can view the response in both JSON and table view. Here is how the successful response looks like for IF node:

![IF-parameters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb00d887-65a8-b919-4bd1-c75bc6a2bfa6.png)

#### Node configurations

| Parameters |
| --- |
| Use the Add Condition menu to add Boolean, Number, and String conditions |
| Boolean | Value 1 | Specify the first value to be compared. |
| Operation | Compare the first value to the second. The operation types can be: - Equal - Not Equal |
| Value 2 | Specify the second value to be compared. |
| Number | Value 1 | Specify the first number value to be compared. |
| Operation | Compare the first number value to the second number value. The operation types can be: - Smaller - Smaller or Equal - Not Equal - Equal - Larger - Larger or Equal |
| Value 2 | Specify the second number value to be compared. |
| String | Value 1 | String to compare |
| Operation | Compare the first string value to the second. The operation types can be: - Contains - Equal - Not Contains - Not Equal - Regex |
| Value 2 | String to compare |
| Combine | All | For multiple conditions, specify ALL for **all** the conditions to be met for the value to be true. |
| Any | For multiple conditions, specify ANY for **any** of the conditions to be met for the value to be true. |
