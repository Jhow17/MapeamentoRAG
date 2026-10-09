---
title: "Build your first Securiti workflow"
slug: "build-your-first-securiti-workflow"
updated: 2026-01-08T07:46:44Z
published: 2026-01-08T07:46:44Z
canonical: "helpcenter.securiti.ai/build-your-first-securiti-workflow"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Build your first Securiti workflow

A workflow is a collection of nodes connected together to automate a process. Workflow lets you stitch together nodes carrying different operations of Securiti modules, data systems, and other generic operations such as functions in order to run the desired custom process. The purpose of automating processes is to reduce cost and effort by simultaneously saving your time and bringing down manual errors. Workflow execution is completed only when all nodes have processed their data. It is like a chain reaction, each node passes down the data to its successor node and repetitive tasks are completed expeditiously. After creating a workflow, you can start adding nodes to the workflow canvas to generate a workflow use case for your required scenario.

#### Prerequisites

- To build and successfully execute the following workflow, you must be subscribed to the Securiti Data Subject Rights module. If you do not have access to the DSR module, contact the Securiti Sales Team to avail its access.
- Other than the DSR module, you must have a premium box account to upload the CSV File to that account.

> [!NOTE]
> **Important**
> 
> Consider this workflow as a reference guide on learning how to build a workflow for the first time. Do not use your sensitive or important data in order to try out the following workflow. You must not try this out in your production environment. Do not upload your personal data to third-party file sharing, collaboration, and content management systems such as Box, unless you are absolutely aware and sure about the possible conclusions.

#### Example Usage

A workflow is a combination of different nodes. You can manually initiate a workflow either by utilizing a **Start** node or a **Trigger** node. The workflow starts and executes all connected and active nodes. The following workflow executes three different nodes based on the output provided by the DSR Trigger node. The output is then utilized by the Process CSV node to produce a CSV file based on the data given by the preceding node. The CSV file is then uploaded to the Box account by using the Box node. This example workflow is based on the following nodes as shown below.

- DSR Trigger (Trigger Node)
- Process CSV (Regular Node)
- Box (Regular Node)

![Workflow diagram showing DSR Trigger, Process CSV, and Box integration steps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-1(1).png)

### DSR Trigger

The DSR Trigger node automatically triggers the workflow when you create a DSR event. This event can be a task in the DSR module of any nature.

You can place the Start node here as well to initiate the workflow, but placing any trigger node works fine. The purpose of placing a trigger node is to set off the execution of workflow upon the creation of an event. Double click the node to open it and fill in the following highlighted fields.

![DSR Trigger parameters showing Name, Type, Source, and Status fields for configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-2(1).png)

After filling out the aforementioned fields. Go to the **Data Subject Rights** module and create a DSR Task of any nature such as **Access**, **Do Not Sell**, or **Erasure**. Fill in the form and click on Submit Request.

The DSR Trigger node automatically receives the data from the successful submission of that DSR Task. You can view it on the right side of the DSR Trigger node popup as shown below.

![DSR Trigger interface displaying parameters and results for a reference request.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-3(1).png)

Close this node and add the following node to the canvas. When you select another node from the menu, it automatically attaches to the existing recent node on the canvas.

### Process CSV

Process CSV lets you create (produce) a CSV file from the data of the preceding node and utilize (consume) that data for several purposes. Add Process CSV node to canvas, double click on it, and fill in the following parameters fields.

1. Choose operation value **Produce** from the menu because you are about to create a CSV file from the output data of the preceding node.
2. Add a property name to make it distinguishable.
3. Add the name that you want to give your CSV file with a CSV extension. Adding an extension is a must.
4. Toggle on the Aggregate parameter and click Execute on the top right-hand corner of the node popup.

![Parameters for processing a CSV file, including operation and file name settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-6(1).png)

Process CSV node now executes the workflow by utilizing the data given by the DSR Trigger node to produce a CSV file. You can see the CSV file by clicking **Binary** and then clicking **Show Binary Data** as shown below.

> [!NOTE]
> **Note**
> 
> The **Process CSV** node outputs files in **US-ASCII** encoding by default.

![Workflow interface displaying CSV processing parameters and results with highlighted sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-7.png)

Close this node and select the Box node from the menu by clicking the **+** icon on the top right-hand corner of the canvas.

### Box

Use this node to upload the CSV file into the Box cloud. Double click on the node and fill in the following parameter fields.

1. Select the **DataSource** name from the menu to upload the CSV file against.
2. In **As User** field, select the name of the user.
3. In the **Resource** field, select either a **Folder** or **File** option in which you want to upload the CSV file.
4. Select **Create** option in the **Operation** field because you want to create a CSV file in the folder.
5. Enter the name of the folder in the **Folder Name** field.
6. Assign an ID to the folder using the **Parent ID** field.

![Parameters for creating a folder named JohnCSV in Box Sandbox application.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-4(1).png)

After filling in the aforementioned parameters click on **Execute** and let the execution run its course. After getting the success message, double-click on the node to see the end result as shown below.

![Box workflow parameters showing folder creation details and user information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/first-wf-5(1).png)

After the successful execution of the workflow, you can see all nodes in the canvas surrounded by a colored border with a green bubble showing the number of executions (1 in this example). This indicates that your workflow was successfully executed.

These nodes can be executed in Manual Workflow mode and Automated Workflow mode. See [Workflow node execution modes](/v1/docs/workflow-node-execution-modes) for more information about how to execute a workflow in manual or automated mode.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Regular nodes](/regular-nodes.md)
- [Trigger nodes](/trigger-nodes.md)
