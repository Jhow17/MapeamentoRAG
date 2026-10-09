---
title: "DSR"
slug: "dsr-regular-node"
updated: 2026-01-12T06:57:15Z
published: 2026-01-12T06:57:15Z
canonical: "helpcenter.securiti.ai/dsr-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR

In Securiti, **Data Subject Rights** module is an automated system that facilitates and streamlines the process of responding to Data Subject Requests (DSRs) from individuals seeking to exercise their rights over their data.

The DSR node lets you perform key operations such as creating, deleting, or publishing reports for DSR requests. The following actions can be performed using the DSR node:

- **Submit a DSR request on behalf of the Data subject:** You can create a DSR request by specifying the DSR request type, email address, first and last name of the data subject and selecting the internal form you want to use to submit the request.
- **Delete DSR requests**: You can delete the DSR request by specifying the request ID.
- **Publishing a DSR report**: You can publish a DSR report by specifying the DSR request ID and email notification template that needs to be sent to the data subject.

#### Example Case

In this example, we create a workflow that meets the use case of bulk-publishing DSR reports for all data subjects who submit DSR requests of erasure type. Bulk publishing DSR reports saves time because it lets you share the outcomes of many erasure requests at once instead of one by one.

The **Cron** node initiates the workflow, such that the workflow is executed on the 1st day of every month. The **HTTP Request** node uses a POST API endpoint to retrieve submitted DSR requests from data subjects. Subsequently, the **Function** node executes to retrieve the DSR ID, status, and request types of the submitted DSR requests from the API response.

The **IF** node checks whether the submitted DSR requests are of erasure type and whether the DSR tasks have been completed for those requests. If **both** conditions are true, the DSR node publishes the **DSR** reports by fetching DSR request IDs and specifying template for the DSR report. As soon as the DSR node publishes reports, Securiti sends them to the respective data subjects.

The following nodes are used in this workflow:

- Cron
- HTTP Request
- Function
- IF
- DSR
- NoOp

#### Prerequisites

All the tasks must be completed for DSR requests of type erasure.

#### Publish DSR Reports for Erasure-Type DSR Requests

1. Add the **Cron** node and set the trigger times by adding “Every Day” as the value forMode” and 1 for “Day”. Further, add HTTP Request node to fetch DSR requests using [Rest API POST](/v1/docs/data-subject-rights-api-reference) call.Data Subject Rights API reference
2. The information being fetched from the **HTTP Request** node is passed onto the **Function** node.
3. Use the **Function** node to fetch only the DSR ID, status and type of DSR requests from the fetched results. Further add **IF** node to check for the DSR requests of type Erasure followed by **AND** condition checking the status of those requests.

> [!NOTE]
> **Note**
> 
> If the status is 2, it indicates that task owners have completed the tasks against these requests.

If both conditions are true, the DSR request IDs are passed to the DSR node.
4. Add the DSR node and in the DSR node, specify the DSR request IDs. Further choose **Response Category** as “Erasure Response” and choose template from the **Template** menu. Mark **Suppress Default** toggle to exclude information from the DSR report when the data subject's details are not found in specific data systems. Additionally, you can also mark **Stop Notifying DSR** toggle to skip notifying the data subjects about the request completion.

![Screenshot_2024-02-19_at_9_21_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-022b6c6f-453c-ce96-d79e-6ebc39ed220b.png)
5. Connect the nodes and execute the workflow.

![Screenshot_2024-02-19_at_9_16_18_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d57de5d-f755-d584-7e44-7d711c7d3d30.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response. This is what the success response of the DSR node looks like:

![Screenshot_2024-02-18_at_5_50_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04dba5b0-44c6-0df5-4bec-306629cd997c.png)

#### Node Configurations

| Parameters |
| --- |
| Operation | The type of operation to perform |
| Create | Choose this to create a new DSR request on behalf of the data subject. |
| Delete | Choose this to delete an existing DSR request. > [!NOTE] > **Note** > > Delete the DSR request only after the data subject receives and downloads the generated DSR report. |
| Publish | Choose this to publish a DSR report for submitted DSR requests. |
| Associate DS (toggle) | Enable to associate the DSR with data systems enabled while configuring the DSR form. |
| Create User (toggle) | Enable to create a user account in Securiti’s Privacy Central system. |
| DSR Type | Select one or more DSR types from the menu.The menu shows all system and custom request types defined in the [Request Types page](/v1/docs/configuring-dsr-request-types) of the DSR settings. You can configure these request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant. For more information, see [Configuring DSR request types](/v1/docs/configuring-dsr-request-types) |
| Email | Enter the email address to use in the data subject request. |
| First Name | Enter the first name to use in the data subject request. |
| Last Name | Enter the last name to use in the data subject request. |
| Internal form to use for DSR | Select the internal form you want to use to submit DSR request. |
| ID | Enter the ID of the DSR request you want to delete. |
| Response Category | Select response category to load templates from the menu - Confirmation Request Response - Access Request Response - General - Erasure Response |
| Template | Select the message template you want to attach with the published DSR Report. |
| Suppress Default Message (toggle) | Enable this to suppress the default message in 'user not found' flow. |
| Skip notifying DSR completion to Data Subject (toggle) | Enable this to skip notifying the data subject upon DSR report publication |
| **Additional Data** You can use this option to add additional field on the DSR task form and can also make those field mandatory |
| Field Name | Enter the name of the new field. |
| Field Value | Enter the value of the field. |
| Metadata | Enter the metadata for the DSR request. Must be a valid JSON object. |
