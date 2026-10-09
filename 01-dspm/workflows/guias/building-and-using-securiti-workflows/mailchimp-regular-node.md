---
title: "Mailchimp"
slug: "mailchimp-regular-node"
updated: 2025-10-30T19:05:54Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/mailchimp-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Mailchimp

Mailchimp is a comprehensive marketing platform offering a range of tools and services for businesses and individuals. Originally recognized for email marketing, Mailchimp has expanded its features to include automation, audience management, analytics, and reporting. Users can create visually appealing emails, set up automated campaigns, and segment audiences for personalized communication.

### Mailchimp

Securiti's Mailchimp node in Workflows module allows you to perform the following set of functions:

- Create a new audience or update or delete an existing audience. You can also get details of a specific audience or list all the available audiences.
- Create a new member or update or delete an existing member. You can also get details of a specific member or list all the available members.
- Start, pause or delete an existing automated email. You can also list all available automations or get details of a particular automation.

Please refer to the [node configurations section](/v1/docs/mailchimp) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow in which a company uses Mailchimp for its email marketing campaigns and needs to maintain extensive customer data, including custom fields that are specific to its business operations, such as customer preferences, last purchase date, or loyalty points. The standard Workflow node for Mailchimp in Securiti, however, does not support updating these custom fields directly. To solve this, the Workflow is extended to use Mailchimp's APIs to manage these custom fields effectively.

The Workflow starts by updating the member using Mailchimp node and then using multiple API calls to perform further actions such as updating custom fields, fetching member fields and info etc. The following Nodes are used in this Workflow:

1. Mailchimp Node
2. [HTTP Request Node](/v1/docs/http-request)

#### Updating custom fields in Mailchimp

1. Add the Mailchimp node and update the member against the specified member ID.
2. Add HTTP Request Nodes to perform the following actions:
  - Fetch member
  - Fetch member fields
  - List member tag
  - Update member
  - Get member information
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-05-07_at_1_00_11_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66c9d103-77fb-9abd-655e-795d54b388d6.png)
4. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | The name of the MailChimp data system instance on which to operate |
| Resource | - Audience - Members - Automated Emails |
| Operation | The operation to perform on Mailchimp |
| Create | Create a new audience or member |
| Update | Update an existing audience or member |
| List | List available audiences, members of a specified audience, or automated emails |
| Get Details | Get details for an audience, member, or automated email |
| Start | Start an automated email |
| Pause | Pause an automated email |
| Delete | Delete an existing audience, member, or automated email |
| Audience | The audience to operate on |
| Name | Name of the audience to create or update |
| Permission Reminder | The permission reminder text for the audience |
| Email | The email address of the subscriber to operate on |
| Member | The member of the audience to operate on |
| Workflow | The Mailchimp Workflow to operate on |
| Automated Email | The automated Workflow to operate on |
| Member Attributes | Some or all of: - Status - Personal Details - Email Type - Language - VIP - Location - Signup timestamp - Opt-in IP address - Opti-in timestamp - Tags |
| Contact Attributes | Some or all of: - Company - Address Line 1 - Address Line 2 - City - State - ZIP - Country - Phone |
| Campaign Attributes | Some or all of: - From Name - From Email - Subject - Language |
| Email Type Option | Whether the list supports multiple formats for emails |
| Double Optin | Whether or not to require the subscriber to confirm the subscription via email |
| Marketing Permission | Whether or not the list has marketing permissions (eg GDPR) enabled |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
