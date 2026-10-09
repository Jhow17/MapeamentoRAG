---
title: "Breach Management"
slug: "breach-management-regular-node"
updated: 2026-01-09T08:55:02Z
published: 2026-01-09T08:55:02Z
canonical: "helpcenter.securiti.ai/breach-management-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Breach Management

In Securiti, Data Breach Management serves as an automated system for incident response, aiding in compliance with relevant breach notification regulations while minimizing the time and costs associated with remediation. This solution is designed to prevent expensive regulatory penalties and alleviate potential damage to reputation resulting from a data breach.

The Breach Management node manages the key incident operations, such as creating an incident, retrieving incident details, and fetching a list of all incidents. Here are the brief details of each operation:

- **Creating an incident:** You can create a new incident, by specifying details like breach intake form template, incident name, and incident timeline which includes incident occurrence, discovery, report, and deadline. This customization capability ensures that incidents are tailored to your specific needs.
- **Retrieving incident details:** You can retrieve specific incident details based on the incident ID.
- **Listing Incidents:** You can also retrieve a list of all reported incidents using the List option.

#### Example Use Case

In this use case, we are outlining an incident creation workflow. The workflow is triggered by the Start node and a new incident is created using the Breach Management node. This node includes actions to log the details of the incident, such as the breach intake template, incident name, incident timeline, etc. Once the incident is created, the workflow initiates an internal assessment (Data Privacy Impact Assessment (DPIA)) to gather more information on the reported incident and determine whether the incident qualifies as a data breach.. The workflow then sends notifications to the designated assessment owners. These are individuals or teams responsible for conducting the Data Privacy Impact Assessment. The notification includes details about the breach incident, such as what happened, when, and any relevant information needed for the assessment.

This use case requires the following three nodes:

- Breach Management
- Assessment
- Send Email

#### Initiating a Data Privacy Impact Assessment (DPIA) on creating a new incident

1. In the Breach Management node, fill in the fields as per your requirements as shown below:

![breach-management.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc5528ca-a49c-1f29-32a4-8f7fdb2e73c0.png)
2. Add details in the assessment node. Specify the operation as “Create”, choose Assessment Type as “Internal” and Template “Data Protection Impact Assessment”. Further, enter the email id of the assessment owner. Refer to the [Assessment node](/v1/docs/assessment) for details.
3. Further, add details of the assessment owner in the Send Email node. Refer to the [Send Email](/v1/docs/send-email) node for details.
4. Connect the nodes to execute the workflow.

![Screenshot_2023-12-03_at_12_35_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9a26fbb-cdff-f77b-e806-29a98d24b1eb.png)
5. Execute the workflow, and upon creating the incident, the workflow node should generate a successful response. After successful execution, you can examine the results in both table view and JSON format. This is how the success response looks:

![Screenshot_2023-12-03_at_12_48_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fd580f9-1ad2-265e-978f-9f4415548942.png)

#### Node Configurations

| **Parameters** |
| --- |
| Operation | Create | Choose this option to report a new incident. |
| List | Choose this option to view a detailed list of all the reported incident. |
| Get | Select this option to get incident details by an incident ID. |
| Template | For Create, choose the breach intake form template to use from the dropdown. |
| Incident Name | For Create, specify the incident name such as "Sensitive data compromised in public S3 bucket”. |
| Incident ID | For Get, specify the incident ID for which you want to fetch details. |
| Timeline | For Create, click Add Timeline to add dates and times for: |
| Occurrence | Select a date when the incident took place. |
| Discovery | Select a date from the calendar when you discovered the incident. |
| Report | Select a date from the calendar when you reported the incident. |
| Deadline | Set the deadline for responding to the incident. |
