---
title: "Creating, saving, and deleting workflows"
slug: "creating-saving-and-deleting-workflows"
updated: 2026-01-12T14:44:49Z
published: 2026-01-12T22:00:08Z
canonical: "helpcenter.securiti.ai/creating-saving-and-deleting-workflows"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Creating, saving, and deleting workflows

When you open the workflow workspace, it automatically creates a blank workflow. You can create a new workflow starting there and then save it, or you can load a workflow that you saved previously.

To open the Workflow Editor page where you create and configure workflows:

- In Securiti, open **Workflows** and choose **+ New Workflow**.

### Creating a new blank workflow

To create a new blank workflow:

1. Choose **+ New Workflow** from the **Workflows Dashboard** or from the dropdown menu on the **Workflow Editor** page that lists all existing workflows. If you select it from the Workflow Editor page, the platform warns you that you’ll lose any unsaved changes in the current workflow.
2. Click **Yes** to confirm.

### Creating a workflow from the library

To create a workflow starting from the Securiti library of pre-made workflow templates:

1. In Securiti, open **Workflows** and choose **Workflows > Library**.

![Workflows for consent remediation in Salesforce, Dynamics, and Marketo displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/wf-library.png)
2. On the template you want to use, choose **Options** (three dots) **> Clone**.
3. Modify the clone to suit, then save it under a new name.

### Saving a workflow

To save the workflow that you are currently working on:

- From the top-right corner of the page, click **Save** (floppy disk icon).

If you have not previously saved the workflow, Securiti prompts you for a name, description (optional), a group for the workflow and assign multiple owners. Enter a name, group and choose owners, then click **Create Workflow**.

![Creating a new workflow for unsubscribing emails with relevant details and owners.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/wf-save.png)

### Loading a workflow

To load a workflow you created earlier:

- From the workflows list, click a workflow.

If there are any unsaved changes to the workflow currently in the canvas, Securiti prompts you to confirm. Click **OK** to proceed.

### Cloning a workflow

To clone a Workflow:

1. From the top-right corner on Workflow Editor page, click **Options** (three dots) for the workflow you want to clone, then click **Save Workflow As**.
2. On the Save Workflow popup, enter a name for the clone, then click **Save**.

### Downloading a workflow

To download a workflow as a .json file:

1. From the workflow list, click the workflow you want to download to open it in the canvas.
2. From the left panel, click **Export Workflow**.

Securiti downloads the workflow to your downloads folder.

### Activating a workflow

To activate a workflow so that it is always running:

1. From the workflow list, click the workflow you want to activate to open it in the canvas.
2. Near the upper right corner of the canvas, click the **Active** toggle to activate it.

> [!NOTE]
> **Note**
> 
> When reactivating a workflow with existing static data, a toggle appears.
> 
> - Enable the toggle to reset the static data and start the workflow afresh.
> - Disable the toggle to retain the static data and continue the workflow from the previous state.

### Configuring workflow credentials

To create credentials that workflow nodes can use to access application APIs for which you have not configured a connector:

> [!NOTE]
> **Note**
> 
> You don't need to use this feature for data systems for which you have configured a Securiti connector. For those data systems, workflow nodes usually let you choose the connector from a menu. In most cases, you use this feature only with data systems for which you don't have a connector, or for generic node such as crypto where you want to use your own keys.

1. From the left panel, click **Credentials** (key icon).
2. On the Credentials popup, click **+ Add New**.
3. On the Create New Credentials popup, use the **Credential Type** menu to choose the application for which you are adding credentials.
4. Use the tools on the Create New Credentials popup to configure the credentials for the application, and to choose which nodes within the workflow you allow to use the credentials.
5. Near the lower left corner of the Create New Credentials popup, click **Create**.

### Deleting a workflow

1. From the workflow list, click the workflow you want to delete to open it in the canvas.
2. From the left panel, click **Delete Workflow**.

> [!NOTE]
> **Note**
> 
> If the Delete menu is absent, it is probably because you are trying to delete a workflow that you don't own. You can only delete your own workflows.
3. On the Delete Workflow popup, click **Yes** to confirm.

## Related

- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
