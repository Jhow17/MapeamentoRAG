---
title: "LoopBack"
slug: "loopback-regular-node"
updated: 2026-01-16T06:19:47Z
published: 2026-01-16T06:19:47Z
canonical: "helpcenter.securiti.ai/loopback-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# LoopBack

LoopBack serves as the final node in workflow design, allowing the workflow to cycle back to a previous step by connecting its output edge to the input edge of an earlier node, creating a continuous loop.

| Parameters |
| --- |
| The node does not have any parameters. |

#### Example use case

As an example use case, we are creating a workflow that processes multiple consent records per iteration/loop in a single workflow execution.

This use case uses the following nodes:

- Cron Trigger Node
- Consent Node
- HTTP Request Node
- LoopBack Node

#### Fetching multiple consents using LoopBack Node

1. Add the Cron trigger node to start the workflow on the set time, for example every 24 hours.

![cron.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99efc91a-9617-cc43-6f1a-209ea2e9b46c.png)
2. Add a Consent node to configure the Operation, such as List for listing all consent, set the start date and time for recording consents, activate the Delta Sync toggle, enable Pagination, and specify the Page Size.

![consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9149c3be-f713-9210-e9c3-5c57ab84108d.png)

> [!NOTE]
> **Note**
> 
> Page Size is a multiple of 1000, so if user input a value not a multiple of 1000 value will be ceiled. For example, 1500 → 2000.
3. Add HTTP Request node and fill up all the fields according to your requirements. For more information, read [HTTP Request documentation](/v1/docs/http-request).
4. Now add the LoopBack node, in such a way that its input edge is connected to the output edge of the HTTP Request node, meanwhile, the its output edge is connected to the input edge of the Consent node, as shown below:

![wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf1f21c9-50a2-f635-dc13-67d9c99ecf85.png)
5. After successfully executing the workflow, the LoopBack Node processes the specified number of consent records per iteration or loop, based on the Page Size, within a single workflow execution.

![loopback.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1362a6e0-e1c0-c0ce-7926-c7f55249f040.png)

For example, if the total records in the specified interval are 1,500 and the Page Size is set to 1,000, the first workflow execution fetches 1,000 records in the first iteration and 500 records in the second iteration. In the next execution, the workflow encounters an error because no consent records are found.

> [!NOTE]
> **Note**
> 
> - When the LoopBack node is used with a node other than the Consent node (only when Pagination is enabled), the loop runs continuously and does not stop automatically. Users need to design the workflow to break the loop. For example, you can use a combination of Function and IF nodes to exit the loop if the previous node returns data that does not meet the specified condition.
> - When log retention is enabled only last iteration data will be shown to the user if the workflow has a loopback node.
> - For workflows with a Loopback node, static data is no longer updated if the execution fails. This prevents failed workflows from overwriting existing data, helping maintain data accuracy by avoiding unintended updates.
