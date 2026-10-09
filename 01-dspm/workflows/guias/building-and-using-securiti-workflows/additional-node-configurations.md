---
title: "Additional Node Configurations"
slug: "additional-node-configurations"
updated: 2026-01-08T14:54:40Z
published: 2026-01-08T14:54:40Z
canonical: "helpcenter.securiti.ai/additional-node-configurations"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Additional Node Configurations

You can change the look and feel of the nodes and configure additional properties such as notes and retries using the Node section next to Parameters.

Look at the following table to understand all the properties of the Node:

| Parameters | Description |
| --- | --- |
| Note | Specify a note to add for the node. |
| Node Color | Specify the node color for the node icon on the workflow editor page. Select color from the canvas and select OK. |
| Always Output Data | Turn this toggle on if you want the data to be returned every time the node is executed. If no data is returned as an output, the result will be empty |
| Retry on Fail | Turn this toggle on to retry node execution upon failure |
| Max Tries | Specify the number of maximum tries upon failure |
| Wait Between Tries | Specify the time in milliseconds to wait for before retrying upon failure |
| Continue on Fail | Turn this toggle on if you want an activated workflow to continue running even if the node fails. In this case, it simply passes through the input data so the workflow has to be set up to handle the case that different data gets returned. |

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
