---
title: "Executing and training workflow nodes"
slug: "executing-and-training-workflow-nodes"
updated: 2026-01-08T10:12:52Z
published: 2026-01-08T10:12:52Z
canonical: "helpcenter.securiti.ai/executing-and-training-workflow-nodes"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Executing and training workflow nodes

When creating a workflow, you usually start by adding at least one node (usually a trigger node), then executing it to collect data. After that, you can use that data to train subsequent nodes. The data that you collect from the training execution shows you what parameters and data are available to use as input for subsequent nodes. You use this information to configure those nodes.

Use this general procedure to execute and train an initial workflow node:

1. If you haven't already done so, open a new blank workflow as described in [Creating, saving, and deleting workflows](/v1/docs/creating-saving-and-deleting-workflows).
2. In the Securiti Workflow Editor, place a node as described in [Placing and modifying workflow nodes](/v1/docs/placing-and-modifying-workflow-nodes).

Usually the first node to place is a trigger node that detects some common event and captures data from it. For example, for a DSR workflow you might place a DSR trigger node.

![DSR Trigger icon with an alert symbol, indicating a potential issue in the workflow.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-1.png)
3. If necessary, double-click the node to open the node popup, and use the popup to configure the node.

For our DSR workflow example, we might set its Type and Source parameters to trigger on DSR access requests opened internally as shown below.

![DSR Trigger parameters including Name, Type, Source, and Status fields displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-2.png)
4. Do one of the following to execute the node:

Securiti shows a spinner over the node, and also shows an "Executing Workflow" banner near the bottom of the workflow canvas to show that the node is executing and waiting for its trigger conditions, as shown below.

![Workflow interface displaying a DSR Trigger element in a grid layout.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-3.png)
  - Hover over the node and click **Execute Node**.
  - Double-click the node and near the upper right corner of the node popup click **Execute Node**.
5. While leaving the Workflow Editor open in a browser tab, perform the action that causes the event to trigger. Use another browser, browser tab, or application for this action.

> [!NOTE]
> **Note**
> 
> Do not close the browser tab for the Workflow Editor. Doing so halts the node execution so that the node would not capture the training data from the execution.

For the DSR example cited above, you would open the DSR Workspace in a separate browser tab and manually open a DSR of type Access using your internal DSR request form as shown below. This action would trigger the DSR trigger node, and cause it to capture data from the DSR request that Securiti creates in response to the form submission.

![WF_create_DSR_to_trigger_node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2dc4c48d-b4fa-0182-e39e-7cff288c2ffe.png)
6. Return to the Workflow Editor tab and inspect the node. It should no longer be executing, and should be surrounded by a colored border with a green bubble showing the number of executions (probably 1 in this example).

![DSR Trigger icon displayed on a grid interface with an execute workflow button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-4.png)
7. Double-click the trigger node to open the node popup.
8. Inspect the Results area of the popup to make sure that the node captured the training data, and that the data contains the parameters you need to configure subsequent workflow nodes.

![DSR Trigger interface displaying parameters and results for access requests in progress.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-5.png)

> [!NOTE]
> **Important**
> 
> Once you have captured training data from the executions, observe these precautions to preserve the training data. Otherwise Securiti discards the training data and you must repeat the procedure to train the node.
> 
> - Do not close the browser tab where the Workflow Editor is open.
> - Do not log out of Securiti.
> - Do not let your Securiti session expire.

Once you have trained the initial node, you can train subsequent nodes using the training data obtained from the procedure above.

1. In the Securiti Workflow Editor, place the next node in sequence as described in [Placing and modifying workflow nodes](/v1/docs/placing-and-modifying-workflow-nodes). Initially, the node has a red triangle that shows that it is not yet properly configured.

For the DSR Workflow example cited in the previous procedure, you might place an Okta node as shown below.

![Workflow diagram showing DSR Trigger and Okta Get Profile actions with alerts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-6.png)
2. If necessary, connect the node to the initial node as described in [Creating and deleting workflow connections](/v1/docs/creating-and-deleting-workflow-connections). The connection makes data and parameters from the prior node available to this one.

> [!NOTE]
> **Note**
> 
> Often, but not always, Securiti automatically connects the node to the last one in the workflow.
3. Double-click the new node and inspect its Parameters tab to see if any required parameters are absent. Such parameters are marked by red borders as shown below.

![Okta parameters section showing data source, operation, and username/email fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-7.png)
4. For each of the required parameters, do one of the following, as appropriate:

For our DSR Workflow example, we might set the DataSource Name parameter to the name of one of our Okta data system instances, and for the Operation parameter we choose **Get Profile**.

For the Username/Email parameter, we open the Edit Expression popup as described above, and use the Variable Selector area to navigate the odes tree to the Output Data produced by the initial node training execution in the previous procedure. In the JSON element, we click email to set as the expression the email address produced by initial node. On the popup, the Expression area shows the expression as something like `{{$node["DSR Trigger"].json["email"]}}`, and the Result area shows the actual email address entered on the DSR request form that triggered the trigger node.

![Expression editor displaying email extraction from JSON data in a workflow.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-8(2).png)

> [!NOTE]
> **Note**
> 
> If the Output Data branch of the tree for the previous node is absent, it might be because:
> 
> - The two nodes are not connected. Make sure the node is connected to the previous one and try again.
> - The previous node has not yet been trained, or has lost its training data. If necessary, repeat the training for the earlier nodes in the sequence.

Back at the node popup, the Username/Email parameter shows a dotted violet border that indicates that it is determined by an expression. The parameter bubble contains the first element of the latest execution.

![Okta interface displaying parameters for user profile retrieval, highlighting username/email field.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-9.png)

> [!NOTE]
> **Note**
> 
> All nodes handle multiple objects. When you use the expression editor, it only shows you the first element of each output, not the entire list. The purpose here is to create an expression, not show the entire data set. The node actually does process all elements, even though the expression editor only shows the first one so you can use it for training purposes.
  - Click the parameter bubble and choose an option from the menu.
  - Click on the parameter bubble to place the text cursor there, then enter a hardcoded value.
  - To the right of the parameter bubble, click **Parameter Options** and choose **Add Expression**, then use the Edit Expression popup to create an expression for the parameter. See [Creating workflow node expressions](/v1/docs/creating-workflow-node-expressions) for more information.
5. Execute the new node as described in the previous procedure.

The node performs its operation using data from the previous node(s) in the workflow. For our example, the Okta node uses the email address extracted by the initial node, and uses it to get the matching user profile from your Okta data system.

![Workflow diagram showing DSR Trigger and Okta Get Profile components with execution status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-10.png)
6. After the execution completes, double-click the trigger node to open the node popup.
7. Inspect the Results area of the popup to make sure that the node obtained required data from the prior nodes and used it to get additional data from its execution.

For our example, the Results area for the Okta node shows the profile data for the Okta user matching the email address it obtained from the trigger node.

![Okta parameters display user profile information including name and email details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/train-wf-11.png)
8. Repeat this procedure to add, connect, and train additional workflow nodes.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
