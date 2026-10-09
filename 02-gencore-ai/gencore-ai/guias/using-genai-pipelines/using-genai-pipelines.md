---
title: "Using GenAI pipelines"
slug: "using-genai-pipelines"
status: "update"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-genai-pipelines"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using GenAI pipelines

**Scenario**

As a Data Security Officer, you're tasked with securing Generative AI pipelines across the organization. To keep your company’s AI use safe, checking every request and response in the AI tools takes a lot of time. Additionally, it is easy to miss something. With **GenAI pipelines**, you configure firewall nodes to control requests sent in prompts, the data retrieved, and the responses provided. You embed these secure workflows directly into portals or chat apps. This ensures safe, governed AI usage without constant manual oversight.

Securiti’s Gencore AI lets you visually create the pipelines and workflows required to continuously load unstructured and semi-structured data, from file and object stores to SaaS applications like Jira, Confluence, Slack, and Zendesk, and safely prepare it for use by GenAI models.

The **GenAI Pipelines** dashboard gives you a centralized platform to access information and status on the created pipelines. Securiti protects AI pipelines by operating in-line with AI requests and responses. As requests flow through the pipeline, Securiti performs real-time inspection and policy enforcement before they reach the large language model (LLM). Similarly, responses are inspected before they are returned to the application or user. This lets Securiti detect and block policy violations, redact sensitive information, and monitor AI interactions in real time.

Using GenAI pipelines, you can build intelligent data pipelines tailored to specific use cases. Each pipeline is composed of [configurable nodes](/latest/docs/creating-a-new-pipeline) that lets you connect with data sources to [ingest](/latest/docs/data-loader) optionally [sanitize](/latest/docs/data-sanitizer) data, set up providers for [LLMs and embeddings providers](/latest/docs/configuring-llm-providers), and [vector stores](/latest/docs/configuring-vector-storage-providers). Additionally, you can also enforce safeguards through different Firewall nodes (Retrieval firewall, Response firewall, Prompt firewall). Beyond data processing, these pipelines can be seamlessly integrated as widgets, within dedicated user portals, or embedded in messaging applications.

The **GenAI Pipelines** dashboard gives you a centralized platform to access information and status on the created pipelines.

![GencoreAI_pipeline.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbbb0238-4675-6690-0aaa-6e1e301dd013(1).png)

To open the **GenAI Pipelines** Dashboard, in Securiti, open Gencore AI and select **GenAI Pipelines**.

![Overview of GenAI Pipelines showing data systems, statuses, and file volumes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines main(2).png)

The widgets at the top of the dashboard give the following information.

| Widget | Description |
| --- | --- |
| Total Pipelines | The number of created pipelines. This count includes completed pipelines as well as the one under development. |
| Completed | The number of pipelines that are executed successfully. |
| Data Systems | The number of data systems that the pipelines are executed for. |
| Data Consumed | The amount of data consumed by the pipelines. |
| Total Volume | The total volume of data that is processed. |
| Total Files Ingested | The total number of files that are processed by the pipelines. |

From the upper right corner of the GenAI Pipelines dashboard you can access shortcuts to:

- [Create a new pipeline](/latest/docs/creating-a-new-pipeline)

![Create new pipeline](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines-create new pipeline.png)
- Access [Templates](/latest/docs/using-genai-pipeline-templates)

![GenAI pipelines - Templates](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines-Templates.png)
- Access [Audit Log](/latest/docs/managing-pipelines#audit-logs)s for the pipelines

![GenAI pipelines dashboard - Audit Log](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines options - Audit Log.png)
- Access [Firewall profiles](/latest/docs/using-firewall-profiles)

![GenAI Pipelines dashboard - Firewall Profiles](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines options - Firewall Profiles.png)
- Create widgets

![GenAI pipeline - create widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines-create widget.png)

At the top of the grid you can use a search bar where you can search pipelines by name.

The grid provides information on individual pipelines:

- **Name**: Name of the pipeline.
- **Data Systems**: The types of data systems configured in the pipeline.
- **Files**: The count of files ingested by this pipeline.
- **Volume**: The volume of data being ingested into the pipeline.
- **Status**: The current status of the pipeline. The possible statuses are:
  - **Draft**: The pipeline is created but configuration is not completed.
  - **Scheduled**: The pipeline is scheduled for running.
  - **Loading**: The pipeline is in the data loading stage.
  - **Completed**: The pipeline is successfully executed.
  - **Error**: There are errors and the pipeline failed to complete.
  - **Cancelled**: The pipeline execution is cancelled by the user.
  - **Cancelling**: The pipeline is in the process of cancellation.
  - **Timeout**: The pipeline execution exceeded the allotted time.
  - **Purging**: The pipeline is being purged.
  - **Deleting**: The pipeline is being deleted.
- **Created Date**: The data and time of the creation of the pipeline.
- **Last Modified**: The data and time when the pipe was last modified.
- Findings: Displays the violation counts if there is any against any Firewall for the respective pipeline. If the count of findings is greater than zero, a link displays that directs the user to the findings page.
- Owner: The current owner of the pipeline. By default, the creator of the pipeline becomes the owner.
- To the right of each pipeline, you can view:
  - **Instance explorer:** To view the graphical representation of the network connected to the pipeline, click the instance explorer.

![Pipeline_right_detail_Instance_explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6deb847e-82e1-e65d-e3a2-6fcdf70dd3dc(1).png)

Here you can access:

> [!NOTE]
> **Note**
> 
> This column should be shown if your tenant has [Graph Explorer](/v1/docs/using-graph-explorer) module enabled
    - **Instance explorer** to view details related to:
      - Data systems
      - Files
      - Gencore AI Model
      - Embeddings model
      - Vector database
      - Data loader
      - Embeddings generator
      - Query agents
      - Data elements
      - Content profile

![Pipeline_right_detail_Instance_explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93ae9d2c-df53-7528-8fab-0deae957a5d3(1).png)
    - **Metadata explorer** to view details related to:
      - Pipeline ID
      - Title
      - Display name
      - Owner
      - Organization email

![Pipeline_right_detail_Metadata_explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5433e25a-ae40-7640-43a5-f1f759706d67(1).png)
    - **Test results** to view the results for the pipeline testing.

![Pipeline_right_detail_Scan_Test_Results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e63851ad-9eb5-b020-b4de-379a1d538875(1).png)

It displays the pipeline test results page.

![Pipeline status - results](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline status results.png)
  - **Three-dot menu**: This menu contains options to:

> [!NOTE]
> **Note**
> 
> To learn more about options for managing pipelines, see [Managing pipelines](/v1/docs/managing-pipelines).
    - Edit the pipeline details.
    - View Audit Logs for the pipeline.
    - Clone the pipeline.
    - Purge the pipeline.
    - Cancel the pipeline.
    - Delete the pipeline.

At the top of the grid you can use a search bar where you can search pipelines by name.

From the upper right corner of the GenAI Pipelines dashboard you can access shortcuts to create new pipelines and view templates to be used for creating these pipelines.

### Pipelines with deprecated models

In some cases, the models configured in GenAI pipelines may become deprecated and discontinued. In case a pipeline is affected, the GenAI pipelines dashboard displays the relevant message.

![GenAI pipelines - affected pipelines](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/genAI pipelines - affected pipelines.png)

To view the pipelines having deprecated models, click ​**View affected pipelines**​​. Securiti displays the affected pipelines.

![view affected pipelines](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/genAI pipelines - click view aff pipelines.png)

> [!NOTE]
> Important
> 
> When a model in a pipeline is deprecated, Securiti prompts you to reconfigure the pipeline. For more information, see [LLM selection](/latest/docs/llm-selection#reconfiguring-llm-in-case-of-deprecation) node.

### Creating GenAI pipeline widgets

You can create custom widgets to gain insights on your pipeline behaviour. You can create widgets for an overall insight into all your GenAI pipelines or based on a filter.

To create a widget:

1. On GenAI pipelines dashboard, click **Create Widget**. The **Widgets** popup displays.

![GenAI pipelines - create widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines-create widget(1).png)
2. In the **Widgets** popup, enter a name for the widget.

![Widgets_main_Name_labelled_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6087767e-21b7-f8f5-cb1b-ef8fc2cb26b9(1).png)
3. Select the **Group** dropdown.

![Widgets_main_Group_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1c88a2ce-d77a-1163-5bed-6dc431bc8cfe(1).png)
4. To create or select a group:
  - To create a new group:
    1. Click **Add New**.

![Group_expanded_Add_New.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-473be715-f644-237d-22aa-b0968fcd1ccb(1).png)
    2. Enter a name for the new group.

![Group_new_name_labelled_copy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e543d72-fd01-3652-75ca-c9b5183f08de(1).png)
    3. Press **Enter**. The group is selected.

![Group_new_name_press_enter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7762c0c1-9f49-bcc2-1133-1f0abd92f812(1).png)
  - To select an existing group, click on the relevant group title.

![widget_selected_group.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f873976a-0d1d-b094-0cd2-88fedc1ea792(1).png)
5. Click **Add Widgets**.

![Main_with_group_Add_widget_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5df15bca-efb8-29d9-57c1-a44caf298523(1).png)

To create widgets based on filter:

1. On **GenAI Pipelines** dashboard, select filters. ![GenAI pipelines - filter for widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines filter for widget.png)
2. Click **Create Widget**.

![create filter for widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines filter for widget - create.png)
3. Repeat the process for creating widgets.

### Accessing Gencore AI widgets

To access and view Gencore AI custom widgets:

1. Go to Securiti **Dashboard>Reporting**.
2. Click **Custom** and select your widget.

![Reporting_dashboard_GenAI_widgets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e178d46d-de54-159b-b8a4-4660d8733b02(1).png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

This firewall uses policies to assess queried data by the LLM before providing it to the LLM.

This firewall uses policies to assess responses for prohibited outputs.

This firewall uses policies to assess prompts and access patterns for suspicious or prohibited inputs.

On Securiti's Findings page, you can view stats related to different policies such as file quarantine and file retention findings.

The Owner is the owner of your assessment; you can also have a Co-owner for that assessment. You can only assign the Owner role to a user accessing the current assessment organization. No Guest User (internal or external) can assume the role of an Owner.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.

In Securiti, an organization is a functional grouping that lets some group within your company to have their own Securiti account, separate from the Securiti accounts of all other organizations within your Securiti tenant, each with its own set of Securiti elements. For example, each organization has its own data systems and connectors, its own assessments, its own DSR forms and DSR requests, its own workflows, and its own data maps and data catalog.

## Related

- [Getting Started with GenAI pipelines](/getting-started-with-genai-pipelines.md)
- [Creating a new pipeline](/creating-a-new-pipeline.md)
- [Using firewall profiles](/using-firewall-profiles.md)
