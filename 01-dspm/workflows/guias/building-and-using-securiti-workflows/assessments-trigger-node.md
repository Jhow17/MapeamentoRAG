---
title: "Assessments"
slug: "assessments-trigger-node"
updated: 2026-01-05T07:26:02Z
published: 2026-01-05T07:26:02Z
canonical: "helpcenter.securiti.ai/assessments-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Assessments

In Securiti, the Assessment Automation module lets you manage Internal assessments that you conduct within your own organization. These assessments can be used to evaluate the company’s internal departments and positions, collect information to enrich data catalog items or information about a reported breach incident.

The Assessment Trigger node is triggered every time a question gets a response, a risk is flagged or an assessment is published based on the trigger type selected. You can create a trigger on either of the events or for any of the events triggered from the aforementioned list.

> [!NOTE]
> **Note**
> 
> You must set your Workflow to run in the automated mode for the assessments trigger node to work automatically. To learn about how to run the Workflow in the automated mode, see [workflow in automated mode](/v1/docs/workflow-node-execution-modes) section.

You can then use this node for any further processing on the data once the trigger is activated.

#### Example Use Case

In this use case, we're outlining a vendor onboarding assessment Workflow. The Workflow is initiated through the **Assessment Trigger Node**. This node prompts vendors to provide their contact information and specify their deployment type as either 'cloud' or 'on-premises.' This initial data collection sets the stage for the entire Workflow.

Once the assessment details are collected, they are seamlessly passed to an **HTTP Node**, which efficiently processes and retrieves the necessary information for further evaluation.

The **IF Node** stands as a central decision point in the Workflow. Based on the responses received via the Assessment Trigger Node, this node determines whether the vendor's deployment is cloud-based or on-premises. This evaluation then leads to two distinct pathways: one for cloud vendors and another for on-premises vendors.

Following this divergence, the Workflow branches into different **Assessment Nodes**. These Nodes specialize in generating vendor assessments tailored to the specific deployment type identified by the Assessment Trigger Node. Consequently, cloud or on-premises assessments are automatically created and seamlessly sent to the respective vendor contacts.

In summary, the Assessment Trigger Node serves as the catalyst for this technical Workflow, efficiently kickstarting the vendor onboarding process by collecting crucial vendor information and categorizing them based on their deployment type. This classification then drives the creation and delivery of customized assessments, ensuring a streamlined and personalized onboarding experience.

1. Assessment Trigger Node
2. HTTP Request Node
3. IF Node
4. Assessment Node

> [!NOTE]
> **Note**
> 
> Refer to the [Node Configuration section](/v1/docs/understanding-user-roles-and-permissions-before-conducting-assessments) to understand the node parameters and descriptions.

#### Adding a workflow trigger to create assessments for vendor/customer

1. Create a Workflow trigger node with a meaningful name e.g. Customer Workflow along with execution mode set to **Event mode**, and the type of the trigger set to **Question response.**

![Screenshot_2025-01-06_at_12_56_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9a76ed1-d5f6-5860-ea0e-a1672cc1a242.png)
2. Add the [HTTP request node](/v1/docs/http-request) to fetch the assessment ID from the response of the Assessment trigger node (the JSON response contains the assessment ID - see step 7 below). Use the [Assessment node](/v1/docs/assessment) to create an assessment against the fetched assessment ID.
3. [Add conditional logic in the assessment template](/v1/docs/understanding-user-roles-and-permissions-before-conducting-assessments) as explained in the section below.
4. Within the assessment template, integrate the IF Node to execute conditional logic based on the information gathered through the Assessment Trigger Node.
5. Configure the IF Node to evaluate the response from the Assessment Trigger Node, specifically examining whether the vendor's deployment type is marked as 'cloud' or 'on-premises.' Based on this evaluation, set up the IF Node to route the Workflow to different paths:
  - If the vendor's deployment is identified as 'cloud,' define the actions within this path to create a cloud-specific vendor assessment using the appropriate assessment template.
  - If the vendor's deployment is recognized as 'on-premises,' configure this path to create an on-premises vendor assessment using the corresponding assessment template.
6. Execute the Workflow and on any event trigger, the Workflow node provides a successful response.

![Assessment-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8dc4ce4-244e-d166-f60a-4be2ddcf2873(1).png)
7. Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![Assessment-Trigger-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e06fb4fd-6926-e73e-9645-5ad039e2e944.png)

#### Adding conditional logic in the Assessment template

For Question Response and Risk assessment types, you must map the Workflow over the question or risk field in the assessments template. To automatically trigger the Workflow when trigger type is set as **Question Response** or **Risk**:

- In Securiti, open the Assessment Automation module and choose Assessments >Templates.
- Select your required template, click Options (three dots) on the right side of the template, and choose Edit Template.
- Click Edit on the upper right side of the question that needs mapping to the trigger Workflow.

#### Trigger workflow on the basis of Risk

- To trigger the Workflow on the basis of risk, click **+ Add New Question Logic** on the bottom of the question section.
- Click the Logic menu, select **Set Risk** and set values to suit your logic from the If Condition, If Response and Set Risk Level menus.
- Mark the **Trigger Workflow** checkbox, select the assessments trigger Workflow from the menu on the right side that you created to map over this risk type. Save your template to put the criteria into effect.

#### Trigger workflow on the basis of Question Response

- To trigger the Workflow on the basis of question response, click **+ Add New Question** Logic on the bottom of the question section.
- Click the Logic menu, select **Trigger Workflow** from the menu and select values to suit your logic from the If Condition, and If Response menus.
- Choose the trigger Workflow that you created to map over this question from the **Trigger Workflows** menu on the right side. Click **Add Response Logic** to save your logic for the question.

> [!NOTE]
> **Note**
> 
> You can add multiple question logics in your assessment template and map them over to the assessment trigger Workflow to trigger the Workflow automatically when the question owners interact with these questions. Securiti also lets you delete these question logics.

#### Trigger workflow on the basis of Assessment Completion

- **[V1]** After the responses are good to go, owner publishes the assessment.
- **[V2]** After the responses are reviewed, reviewer approves the assessment. The assessment moves to Complete stage.

Any of the above can then trigger a linked PIA (Privacy Impact Assessment), etc.

#### Node configurations

In order to fill up the fields in the Assessment trigger node, look at the table below for details about the properties:

| Parameters | Description |
| --- | --- |
| Name | Specify the name of the node |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node periodically based on the interval set. |
| Type | Any | The node is triggered on modification in any of the entity in the catalog |
| Question Response | The node is triggered on a question response |
| Risk | The node is triggered on a risk flagged |
| Publish | The node is triggered on assessment publishing |
| Stage Change | The node is triggered whenever an assessment changes stage. > [!NOTE] > **Note** > > Please note that this option is available only for Assessment v2. |
| Operation | List | Choose this operation to list the available assessments. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
