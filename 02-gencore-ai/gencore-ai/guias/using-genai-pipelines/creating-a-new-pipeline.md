---
title: "Creating a new pipeline"
slug: "creating-a-new-pipeline"
status: "update"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/creating-a-new-pipeline"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating a new pipeline

To create a new pipeline:

1. On the **GenAI Pipelines** dashboard, click **New Pipeline**. Securiti displays the **Discover** GenAI pipeline **Templates popup**.

![GenAI pipelines - create new pipeline](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipelines-create new pipeline(1).png)
2. Choose any of the following methods to create a pipeline:

Securiti displays the popup for creating the pipeline.
  1. **Using templates**: To continue creating a pipeline from an existing template:
    1. Search for and select a template from the gallery.
    2. To browse more templates, click **Browse Templates**. The Templates dashboard displays.

![Browse_genAI_pipeline_templates_Browse_133p.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6bf962e7-8b39-8558-4885-6951c96aa57c(1).png)
  2. **Without templates**. To continue creating a pipeline without the help of a template, click **Skip Template Selection.**

![Browse_genAI_pipeline_templates_Skip_Template_lab_133p.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7831f903-4fe5-80f1-e7ef-d2be78e98695(1).png)
3. Provide the **Title** for the pipeline. This is the name of the pipeline.
4. Optionally provide a **Description** to the pipeline.
5. To save the pipeline, click **Save** or opt out of the pipeline creation by clicking **Cancel** or **Close (x)**.

![Create_pipeline_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf15d94a-1503-09f3-6646-17e566fd19e3(1).png)

Securiti creates your pipeline and takes you to the **Wizard** view. This view lets you configure the pipeline step by step.

![Pipeline wizard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New pipeline created blank.png)

Securiti shows you the following additional details in the **Wizard** view:

| Shortcut | Description |
| --- | --- |
| Builder | Opens the [**Builder**](/v1/docs/pipeline-builder) page of the pipeline. This page shows the graphical view of the pipeline configuration. |
| Status | Opens the [**Status**](/v1/docs/pipeline-status) page of the pipeline. This page shows the status of the ingested files. |
| Run | You can use the **Run** button to [execute the pipeline](/latest/docs/creating-a-new-pipeline#executing-the-pipeline). You can choose to execute: - the ingestion stages of a pipeline to load content and provide an output - the completely configured pipeline |
| Test | [Tests the pipeline](/latest/docs/creating-a-new-pipeline#testing-the-pipeline) using the provided prompt. You can ask questions from the assistant. The assistant answers the questions using the data that is processed and stored in the Vector database, using the LLM provider configured in the pipeline. |
| More Options | You can manage the wizard view with options to manage the wizard. |
| Header | The header provides additional details for the created pipeline. |

The canvas is divided in two sections:

- **Navigation:** On the left side you can find a list of the different stages that you can configure in a pipeline.

From here you can select the stage that you want to configure or view.

> [!NOTE]
> **Note**
> 
> When you hide a stage, the pipeline wizard adjusts the numbering of the stages.
  - The check mark indicates that the stage is configured.
  - Click **Remove** (minus icon) to eliminate a stage if it is not required.
  - Click **Add** (plus icon) to add a stage back.
  - Click the **Hide Inactive** toggle to hide stages that you decide to eliminate from the pipeline.
- **Configuration Pane**: On the right side, you can find the configuration form for the selected stage.

You can choose to add the information for all stages or choose specific ones. By default, the pipeline displays the **Data Loader** stage.

The mandatory stages you must configure are:

- **Data Loader**: In this stage you can configure the source from which the data is loaded and ingested into the pipeline.
- **Embeddings Generator:** In this stage you configure the embeddings provider.
- **Vector Database**: In this stage you configure the vector database provider.
- **LLM Selection**: In this stage you configure the LLM provider.

## More Options

You can manage the wizard with further options as follows:

- **Scheduled Run**: Lets you schedule your pipeline execution.
- **Save as Template**: Lets you save your pipeline as a template.
- **Settings**: Lets you edit the pipeline title and description.
- **Issues**: Directs you to the Findings page.
- Audit log: Directs you to the audit log page for the pipeline.

## Header

The header provides the following information about the created pipeline.

![Pipeline header details showing status, version, files, volume, findings, and last modified date.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI pipeline header all.png)

- **Status**: The status of the pipeline. The status can be one of the following:

| Status | Description |
| --- | --- |
| Draft | The pipeline is not configured completely. |
| Scheduled | The pipeline is scheduled for execution. |
| Loading | The pipeline is in the loading state. |
| Complete | The pipeline execution is complete. |
| Error | The pipeline incurred error in execution. |
| Canceled | The pipeline execution is canceled. |
| Timeout | The pipeline incurred a timeout error. |
| Cancelling | The pipeline is in the process of cancelling. |
- **Status Version**: The status version comprises the version number followed by the date it was last modified.
- **Files**: The number of files ingested into the pipeline.
- **Volume**: The volume of the data ingested into the pipeline.
- **Findings**: The findings against the files ingested into the pipeline.
- **Last modified**: The day the pipeline was last modified.
- **Owner**: The owner of the pipeline.

To hide the header, click **Hide**.

To display the header after hiding, select **More Options>Show pipeline details**.

## Testing the pipeline

You can test your GenAI pipelines using either the Securiti-hosted environment or your self-hosted appliances directly from the pipeline test prompt. From the test window, select the environment you want to use and route your queries accordingly. Securiti displays the active appliance in the Test header so you can confirm where your test is running. You can switch between environments, and the conversation context resets automatically.

To test your pipeline, in your GenAI pipeline:

1. From the upper right corner of the page, click **Test**, as shown below.

![Test in GenAI pipeline](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Header - Test.png)

Securiti validates the pipeline.
  1. If the validation is successful, Securiti displays a success message.

![Session validation details showing successful checks for various components in the portal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Test prompt - validation successful.png)
  2. if there are issues in the pipeline, Securiti displays the relevant message.

![Error messages indicate session validation and authentication failures in the Gencore portal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Test prompt - validation error(1).png)
  3. If you continue to send prompts without the validation, Securiti displays a pipeline failure message.

![Securiti Copilot displays a pipeline failure message and validation error notification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline failure message after validation error.png)

To view the detail, click the **Options** (three-dot) menu as shown below.

![Error message indicating a pipeline failure and invalid username for Vector Store Provider.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline failure message after validation error exp.png)

If you are using a [self-hosted appliance](/latest/docs/self-hosted-user-portal-firewall-deployment) and Firewall is enabled at the pipeline level but not deployed on the appliance, the test prompt displays a message stating this instead of a policy violation message.

![Error message indicating firewall is enabled but not deployed on the portal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline failure - FW not deployed(2).png)

1. Once Securiti successfully validates the pipeline, to choose the environment, click **Settings**. By default, the environment is Securiti **SaaS**.

![Gencore Portal interface displaying settings and messaging options for user interaction.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Test chat - Settings.png)
2. Securiti displays a popup for selecting your environment.

![User interface for selecting a portal in the Gencore pipeline.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Test - portal menu popup(1).png)
3. In case of entitlement enforcement, enter your **User Email**.

![User email input field and Gencore portal selection for testing the pipeline.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/test prompt - entitlement user email.png)
4. Select the environment to test your pipeline in by clicking on the **Gencore Portal** menu.

![Input fields for Gencore Portal with options in GenAI pipeline.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Gencore portal menu - expanded.png)

You can choose between:

| Environment | Description |
| --- | --- |
| Securiti hosted | Your default Securiti environment. |
| Self-hosted | Your self-hosted environment. |
5. Select the environment and click **Continue**.
6. Ask your queries to test the pipeline.

### Re-ingestion of data

In case of **Completed** pipelines, data must be re-ingested in case of changes in the following pipeline nodes:

- Data Loader
- Data Sanitizer
- Embeddings Generator
- Vector Database

When any of the nodes is updated, Securiti displays a message for re-ingestion in the Test Prompt.

![Warning message indicating re-ingestion is required in the Gencore Portal interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/data reingestion message in test prompt.png)

To view the message in detail, click on the **Options** (three-dot) menu.

![Warning about re-ingestion required, with session validation results displayed below.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reingestion message in test prompt expanded.png)

## 

## Executing the pipeline

You can use the Run button to execute:

- the ingestion stages of a pipeline to load content and provide an output
- the completely configured pipeline

> [!NOTE]
> **Important**
> 
> If an error occurs during pipeline execution, Securiti displays a relevant error message. If the error is caused by API execution, the message includes a correlation ID to assist with troubleshooting. For API-related errors, contact your Customer Success Manager or Account Representative.

You can choose to execute the pipeline as follows:

- To manually execute the pipeline, click **Run** > **Run now**.
- To automate pipeline execution based on the provided schedule:
  - Click **Run** > **Automated, on periodic schedule**.
  - In the **Schedule** popup, the option **Run on periodic schedule** is selected.
    - Select **periodic schedule frequency**.
    - Define relevant details: Daily, Weekly, Monthly, Custom Cron
  - Click **Save**.

> [!NOTE]
> **Important**
> 
> - The Run button should only be available if all the enabled ingestion stages are in configured state.
> - Having the Run button disabled means that the ingestion stages can not be executed, therefore, any scheduled jobs will not be executed.
> - If a stage is in Configured state and the user makes a change that may render a configuration invalid (e.g., deleting all sources, deleting all masking rules, unselecting embeddings provider, vector storage, etc), the stage will be sent to un-configured state and the Run button is disabled.

## Scheduling pipeline execution

To schedule the execution of your pipeline:

1. Click More **Options>Schedule Run**. Securiti displays the Schedule popup.
2. Select **Run on periodic schedule**.

![Periodic Schedule](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Schedule - Periodic.png)

1. Select relevant details:
  1. Select **periodic schedule frequency**.
  2. Define relevant details: Daily, Weekly, Monthly, Custom Cron
  3. To save the details, click **Save**.
2. To switch the setting back to manual execution, select **Manual**.

![Options for scheduling tasks include manual or periodic scheduling with a save button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Schedule pipeline - manual.png)

## Saving pipeline as a template

After configuring the nodes, to save your pipeline as a template:

1. Click **More Options>Save as Template**.
2. Enter the **name** for the template.
3. Enter the **description** for the template.
4. To save the changes, click **Save as a template**.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

On Securiti's Findings page, you can view stats related to different policies such as file quarantine and file retention findings.

The log that Securiti maintains of all actions taken by various users, and by the Securiti system. Different users have different levels of access to the audit log. For users of type Super Admin, DPO, and Operator, the audit log shows all log entries. For users of type User or Module Owner, the audit log only shows log entries directly related to the user and their activities.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using GenAI pipeline templates](/using-genai-pipeline-templates.md)
- [Pipeline Status](/pipeline-status.md)
- [Managing pipelines](/managing-pipelines.md)
