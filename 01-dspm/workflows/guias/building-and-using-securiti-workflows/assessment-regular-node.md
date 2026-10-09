---
title: "Assessment"
slug: "assessment-regular-node"
updated: 2026-02-08T12:38:19Z
published: 2026-02-08T12:38:19Z
canonical: "helpcenter.securiti.ai/assessment-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Assessment

In Securiti, the Assessment Automation module lets you manage assessments that you conduct within your own organization. These assessments can be used to evaluate the company’s internal departments and positions, processes and collect information to enrich data catalog items or information about a reported breach incident.

The Assessment Node facilitates key assessment operations, including creation, retrieval, and listing of internal and vendor assessments. Here's a brief overview:

**Getting an Assessment:** Retrieve an assessment based on either the Assessment ID or Data Map entity ID. This flexibility allows you to access assessments through multiple identification methods, depending on your requirements.

**Listing Assessments:** To list assessments, you need to provide a 'From Date' and 'To Date,' which define the period for listing assessments. This feature enables you to filter assessments based on specific time frames, enhancing data retrieval efficiency.

**Creating an Assessment:** When creating an assessment, you must specify essential details such as assessment type, template, title, and other relevant parameters. This customization capability ensures that assessments are tailored to your specific needs. The Assessment Node supports the creation of both Internal and Vendor assessments.

#### Example Use Case

In this use case, we're outlining a vendor onboarding assessment workflow. The workflow is initiated through the **Assessment Trigger Node**. This node prompts vendors to provide their contact information and specify their deployment type as either 'cloud' or 'on-premises.' This initial data collection sets the stage for the entire workflow.

Once the assessment details are collected, they are seamlessly passed to an **HTTP Node**, which efficiently processes and retrieves the necessary information for further evaluation.The I**F Node** stands as a central decision point in the workflow.

Based on the responses received via the Assessment Trigger Node, this node determines whether the vendor's deployment is cloud-based or on-premises. This evaluation then leads to two distinct pathways: one for cloud vendors and another for on-premises vendors.

Following this divergence, the workflow branches into different Create Assessment nodes. These nodes specialize in generating vendor assessments tailored to the specific deployment type identified by the Assessment Trigger Node. Consequently, cloud or on-premises assessments are automatically created and seamlessly sent to the respective vendor contacts.

Here's where the **Assessment Nodes** come into play. As the workflow diverges based on deployment type, it seamlessly branches into different Create Assessment nodes. These specialized nodes generate vendor/internal assessments precisely tailored to the specific deployment type identified by the Assessment Trigger Node. According to the previous response, the Assessment nodes ensure that the assessments created are automatically aligned with the vendor's deployment.

1. Assessments Trigger Node
2. HTTP Request Node
3. IF Node
4. Assessments Node

Refer to the [Node Configuration section](/v1/docs/creating-an-internal-assessment) to understand the node parameters and descriptions.

#### Creating assessments for vendor/customer

1. Create a workflow trigger node with a meaningful name e.g. Customer Workflow along with the type of the trigger set to **Question response**.

![Assessment-01.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b8397d7-f4a3-ea09-d3e8-c5e4f2402553.png)
2. Add the [HTTP request node](/v1/docs/http-request) to fetch the assessment ID from the response of the [Assessment trigger](/v1/docs/assessments) node. Use the Assessment node to create an assessment against the fetched assessment ID.
3. Within the assessment template, integrate the **IF Node** to execute conditional logic based on the information gathered through the Assessment Trigger Node.
4. Configure the IF Node to evaluate the response from the Assessment Trigger Node, specifically examining whether the vendor's deployment type is marked as 'cloud' or 'on-premises.' Based on this evaluation, set up the IF Node to route the workflow to different paths:
  - If the vendor's deployment is identified as 'cloud,' define the actions within this path to create a cloud-specific vendor assessment using the appropriate assessment template.
  - If the vendor's deployment is recognized as 'on-premises,' configure this path to create an on-premises vendor assessment using the corresponding assessment template.
5. Add the details in the Assessment Node to create a new assessment. Use the **Create** operation and **Vendor** as an assessment type. Mention the assessment details either manually or using expressions by taking the values from responses of previous nodes.
6. Execute the workflow and on any event trigger, the workflow node provides a successful response.

![Assessment-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8dc4ce4-244e-d166-f60a-4be2ddcf2873.png)
7. Once the workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like:

![Assessment-03.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f21d107-e1eb-5b45-b636-aabaa3da1cd5.png)

#### Node Configurations

In order to fill up the fields in the Assessment trigger node, look at the table below for details about the properties:

| Parameters |
| --- |
| Operation | Specify the operation that is to be performed using the operation. |
| Create | Select this option to create a new assessment. |
| Get | Select this option to get an assessment by an assessment ID |
| List | Select this option to get a list of assessments from the specified duration. |
| Assessment type | Internal | Select this option if you want to create an internal assessment. |
| Vendor | Select this option to send the vendor an assessment invitation. |
| Template | Specify the template to create the assessment with. |
| Title | Specify the assessment title. |
| Owner | Specify the email address of the assessment owner. |
| Link | Enable this toggle if you want to link a data map entity to the assessment. |
| Entity ID | Specify the ID of the data map entity to attach the assessment to. |
| Entity Type | Specify the type of the data map entity to attach the assessment to. |
| Vendor | Specify the name of the vendor. |
| Collaborator Name | Specify the name of the vendor collaborator on the assessment. |
| Collaborator Email | Specify the email address of the vendor collaborator on the assessment. Separate multiple collaborator emails using commas. |
| Vendor Manager | Specify the email address of the vendor co-owner on the assessment. |
| Message | Specify the message to go with the invitation. |
| Get By | Assessment ID | Select this option to get an assessment by Assessment ID. |
| Data Map Entity ID | Select this option to get an assessment using the data map entity ID. |
| ID | Specify the ID (Assessment/Data Map Entity) against which the assessment needs to be fetched. |
| From Date | Specify the start date of the period for which the assessments need to be listed. By default, data is fetched from the last 24 hours. |
| To Date | Specify the end date of the period for which the assessments need to be listed. |
| Delta Sync (toggle) | Enable this toggle if you want to use the last saved timestamp of the last execution as the start time for the next execution. |
| Assessment Respondents | Enter one or more email addresses of the respondents you want to notify and assign the assessment to. > [!NOTE] > Note > > 1. This field can be populated as a variable from other nodes in the workflow. > 2. This field is optional to maintain compatibility with existing assessment workflows. |  |

> [!NOTE]
> **Note**
> 
> Delta Sync only works with the Cron trigger enabled and active.
