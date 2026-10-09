---
title: "Creating and deleting workflow connections"
slug: "creating-and-deleting-workflow-connections"
updated: 2026-01-08T10:28:41Z
published: 2026-01-08T10:28:41Z
canonical: "helpcenter.securiti.ai/creating-and-deleting-workflow-connections"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Creating and deleting workflow connections

The connections between nodes deliver parameters and data from the output bubble of one node to the input block of the next. Most nodes have one input and one output, although some nodes, for example the If conditional node, have more than one output.

### Connecting two nodes

1. If you have not already done so, place the two nodes you want to connect as described in [Placing and modifying workflow nodes](/v1/docs/placing-and-modifying-workflow-nodes).
2. If necessary, arrange the nodes so that the process flow is generally from the left to the right.
3. Click the output bubble of the node on the left, then drag to the input block of the node on the right and release as shown below.

![Diagram showing connection setup between DSR Trigger and Okta for node creation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/conn-1.png)

### Deleting a connection

1. Hover over the connection you want to delete.

Securiti turns the connection red and shows a delete (X) bubble at its center as shown below.

![Workflow diagram showing DSR Trigger connecting to Okta for profile retrieval.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/conn-2.png)
2. Click the delete bubble at the center of the connection.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
