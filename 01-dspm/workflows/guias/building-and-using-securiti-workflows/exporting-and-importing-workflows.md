---
title: "Exporting and importing workflows"
slug: "exporting-and-importing-workflows"
updated: 2026-07-29T14:31:52Z
published: 2026-07-29T14:31:52Z
canonical: "helpcenter.securiti.ai/exporting-and-importing-workflows"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Exporting and importing workflows

You can export and import workflows to and from JSON files.

### Exporting a workflow

To export a workflow:

1. In Securiti, from the left navigation bar choose **Workflows**.
2. On the Workflows Dashboard, click the workflow you want to export.
3. From the left panel choose **Export Workflow** as shown below.

![Workflow editor displaying Marketo Consent Workflow with execution options and status details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/export-workflow.png)

Securiti downloads the workflow to your Downloads folder as a JSON file.

> [!NOTE]
> Note
> 
> If you enter secrets, such as API keys or tokens, directly into open fields on generic nodes, for instance, **HTTP Request** node headers or **Set** node values, Securiti does not mask or redact these values on export. They appear in plaintext in the exported workflow JSON. To keep secrets out of exports, configure them using the node's dedicated **Credentials** option instead of an open field.

### Importing a workflow

1. In Securiti, from the left navigation bar choose **Workflows**.
2. From the left panel choose **Import** **Workflow** as shown below.

![Workflow editor displaying Marketo Consent Workflow with execution options and status details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/import-workflow.png)

Securiti opens a file manager window.
3. Navigate to the JSON file containing the workflow and click **Open**.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
