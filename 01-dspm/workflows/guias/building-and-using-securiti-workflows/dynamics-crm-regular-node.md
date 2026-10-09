---
title: "Dynamics CRM"
slug: "dynamics-crm-regular-node"
updated: 2026-01-12T07:02:01Z
published: 2026-01-12T07:02:01Z
canonical: "helpcenter.securiti.ai/dynamics-crm-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Dynamics CRM

A Microsoft Dynamics CRM node within a workflow Automation system streamlines and automates interactions with customer data stored in Microsoft Dynamics CRM. By leveraging the API capabilities of Dynamics CRM, the node executes multiple operations, making it easy to manage customer relationships and ensuring compliance with regulations like GDPR. Following is the set of operations a Dynamics CRM node can perform in a Workflows system:

- Updates GDPR consent for user on Dynamics CRM.
- Gets contact details by email ID.
- Gets a list of all the contacts.

Refer to the [Node configurations section](/v1/docs/dynamics-crm) to understand the node working and properties.

#### Example use case

As an example, let’s create a use case that automates the process of managing user consents for GDPR compliance and synchronously updating customer profiles and consent statuses in Microsoft Dynamics CRM based on the type of consent modification.

This scenario involves using a Consent Management Trigger node that detects changes in consent status and then updates customer records in Microsoft Dynamics CRM accordingly. Depending on the type of consent change, specific business logic is applied using the IF node to check if the consent status is withdrawn.

After the consent status is updated, the Dynamics CRM node updates the customer's consent status and details in their Dynamics CRM profile. It records the nature of the consent change, ensuring that the sales and marketing teams are only engaging with customers under proper consent conditions. The following nodes are used in this workflow:

1. [Consent Management Trigger Node](/v1/docs/consent-management)
2. [IF Node](/v1/docs/if)
3. Dynamics CRM Node

#### Automated consent management with Dynamics CRM integration

1. Add the Consent Management Trigger node that is triggered on any type of update in the consent.
2. Add IF node to check if the consent status is withdrawn and subsequently add the Dynamics CRM node to update consent on the Dynamics CRM platform.

![Screenshot_2024-04-23_at_2_35_15_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cad3b443-6131-7978-fa41-41efc557f6e1.png)
3. Connect the nodes and execute the workflow.

![Screenshot_2024-04-23_at_2_34_54_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e63b204-56e2-c019-31d3-a2f93a705702.png)
4. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the Dynamics CRM data system instance on which to operate. Refer to the Dynamics CRM connector documentation to understand how to set up the connector. |
| Operation | Specify the operation to perform on Dynamics CRM |
| Update Consent | Choose this operation to update GDPR consent for a data subject. |
| List | Choose this operations to list all the contacts. |
| Get | Choose this operation to get contact details by email ID. |
| Create | Choose this operation to create a new contact. |
| Email Address | Specify the email address of the data subject. |
| Consent Status | Specify the consent status to apply to the data subject. |
| Grant | The data subject grants consent |
| Withdraw | The data subject withdraws consent |
| Decline | The data subject declines consent |
