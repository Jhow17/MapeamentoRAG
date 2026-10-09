---
title: "Creating Workflows node expressions"
slug: "creating-workflows-node-expressions"
updated: 2026-01-08T10:25:28Z
published: 2026-01-08T10:25:28Z
canonical: "helpcenter.securiti.ai/creating-workflows-node-expressions"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Creating Workflows node expressions

In workflows, you use node expressions to extract information from the current node or a prior node in order to perform an operation.

1. If you haven't already done so, double-click the workflow node to open the node popup.
2. Next to the parameter for which you want to create the expression, click **Parameter Options** (gears icon) and choose **Add Expression** as shown below.

![Okta interface showing parameters for retrieving user profile data with highlighted options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ne-1.png)

Securiti opens the Edit Expression popup as shown below.

![Interface for editing expressions with variable selector and result display sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ne-2.png)
3. To build the expression using data from a node, use the node trees on the Variable Selector panel to navigate down into the available data, and click the data you want for your expression.

> [!NOTE]
> **Note**
> 
> If the node trees do not show an entry for Output Data, check the following:
> 
> - That you have trained the node by executing it. See [Executing and training workflow nodes](/v1/docs/executing-and-training-workflow-nodes).
> - That the node you are working on is connected to the prior nodes in the workflow. See [Creating and deleting workflow connections](/v1/docs/creating-and-deleting-workflow-connections).

In the example below, we have built an expression that extracts the email address from the Output Data JSON of the DSR Trigger node that precedes this one.

![Editing an expression to extract email from JSON data in a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ne-3.png)
  - Use Parameters from a node to pull in settings from the node configuration.
  - Use Output Data from a node to pull in the actual data revealed by the node training.
4. Check the contents of the Expression and Result boxes to make sure they reflect the intended expression and the corresponding results from the most recent execution, respectively.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
