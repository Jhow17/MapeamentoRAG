---
title: "Creating templates"
slug: "creating-templates"
updated: 2026-01-13T06:06:41Z
published: 2026-01-13T06:06:41Z
canonical: "helpcenter.securiti.ai/creating-templates"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating templates

You can create custom templates for your GenAI pipelines for various use cases with selected data sources, Embeddings generators, LLMs, vector databases as well as firewall profiles.

### Prerequisites

To create your pipeline templates, you must have the following configurations as required:

- [Data sources](/v1/docs/supported-data-sources)
- [Embedding and LLM providers](/v1/docs/configuring-llm-providers)
- [Vector database providers](/v1/docs/configuring-vector-storage-providers)
- [Firewall profiles](/v1/docs/using-firewall-profiles)

### Creating a template

To create your GenAI pipeline template:

1. On **Templates** page, on the top right, click **New Template**.

![Create new template](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Templates_newTemplate.png)
2. Enter the **Template Name**.

![New template - name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New template main Name.png)
3. Enter the **Description**.

![New template - description](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New template main Description.png)
4. To make the template private, select **Mark as Private**. This restricts access to only the template owner.

![New template - mark as private](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New template Mark as private lab.png)
5. To save the details, click **Save as Template**.

![New template - Mark as private - Save](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New template Mark as private Save.png)

Securiti displays the created template.

![Editing a tech document template with various data processing options listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create template main.png)
6. To configure the template, enable the relevant nodes and configure.
  - To learn how to configure the nodes, see [Creating a new pipeline](/v1/docs/creating-a-new-pipeline).
  - To learn how to save and configure the template as a pipeline, see [Creating a pipeline using a template](/v1/docs/creating-templates#creating-a-pipeline-using-a-template).

> [!NOTE]
> Note
> 
> In case a model configured in your GenAI pipeline template is deprecated, Securiti highlights the relevant [Embeddings Generator](/latest/docs/embeddings-generator#reconfiguring-embeddings-model-in-case-of-deprecation) node or [LLM Selection](/latest/docs/llm-selection#reconfiguring-llm-in-case-of-deprecation) node. You must [reconfigure the relevant deprecated models](/latest/docs/replacing-deprecated-models) with updated models.

### Creating a pipeline using a template

To create your pipeline using a template:

1. On the **Templates** dashboard, click the template you want to use to create the pipeline.

The pipeline opens and displays with preconfigured nodes according to the template.
2. Click the ​Options​ (three-dot) menu and Securiti displays the option **Save as Pipeline**.

![Editing a tech document template with various data processing options listed highlighting options menu](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create template options.png)
3. Click ​**Save as Pipeline​​**.

![Save as pipeline button](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/template - save as pipeline.png)
4. Enter the **Title**.
5. Optionally add a **Description**.
6. To add new nodes, enable the relevant nodes:

> [!NOTE]
> **Note**
> 
> The template nodes are the same as pipeline nodes. To view how to navigate your GenAI pipeline nodes, see [Creating a new pipeline](/v1/docs/creating-a-new-pipeline).
  - [Data Loader](/v1/docs/data-loader)
  - [Data Sanitizer](/v1/docs/data-sanitizer)
  - [Embeddings Generator](/v1/docs/embeddings-generator)
  - [Vector Database](/v1/docs/vector-database)
  - [Embeddings Retriever](/v1/docs/embeddings-retriever)
  - [Retrieval Firewall](/v1/docs/retrieval-firewall)
  - [LLM Selection](/v1/docs/llm-selection)
  - [Response Firewall](/v1/docs/response-firewall)
  - [Prompt Firewall](/v1/docs/prompt-firewall)
7. To update further detail in the existing nodes:
  1. Select the node.
  2. Review the existing information added as per the template.
  3. Make updates as required.
  4. Click **Save and Continue**.
8. Once you are satisfied with the provided details in all the nodes, save the details:
  - To save the template, click **Save Template**.
  - To save the template as a pipeline, click **Save as Pipeline**.

## Managing templates

You can edit, clone or delete a template. To access the options, hover over on the relevant template and click the ​**three-dot** menu​​.

![Overview of templates with options to edit, clone, or delete each template.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/template options lab.png)

#### Editing a template

To edit a template:

1. On the three-dot menu, click **Edit**. Securiti displays the **Edit Template** popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(247).png)
2. Edit the template as needed.
3. To save updates, click **Update template details**.

#### Cloning a template

To clone a template:

1. On the three-dot menu, click Clone. Securiti displays the Clone Template popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(248).png)
2. Rename the template as needed.

> [!NOTE]
> **Important**
> 
> Each template must have a unique name.
3. To clone the template, click **Clone Template**.

#### Deleting a template

To delete a template:

1. On the three-dot menu, click **Delete**. Securiti displays the confirmation popup for deletion.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(251).png)
2. To confirm template deletion, click **Delete Template**.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using Gencore AI Gallery](/using-gencore-ai-gallery.md)
- [Creating a new pipeline](/creating-a-new-pipeline.md)
