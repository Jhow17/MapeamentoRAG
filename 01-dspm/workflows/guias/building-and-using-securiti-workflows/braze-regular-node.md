---
title: "Braze"
slug: "braze-regular-node"
updated: 2026-01-09T08:53:43Z
published: 2026-01-09T08:53:43Z
canonical: "helpcenter.securiti.ai/braze-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Braze

A Braze node enables integration between your workflow automation platform and the Braze marketing automation platform. Using the Braze node in Securiti, you can:

- Create or update users by adding attributes, events and purchases.
- Export the existing users using aliases, external IDs or email addresses.
- Delete users using external IDs, Braze ID or user aliases.

See the [node configurations section](/v1/docs/obtain-permissions-and-authentication-credentials-in-braze) to understand the node working and properties.

#### Example use case

As an example let’s create a use case where a workflow fetches the user details using a Braze node and then stores that data in a SQL Server. The Braze node fetches the user details against the external ID after establishing a connection to the Braze data source. Braze node returns the data in JSON format and you can add this data to SQL database using an SQL query.

The following nodes are used in this workflow:

1. Braze Node
2. SQL Server Node

#### Synchronizing Braze user data with SQL Server

1. Add Braze node and add the following configurations to the node such that the node fetches the user details against an external ID.

![Screenshot_2024-04-01_at_10_56_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96c4a953-9058-f06b-9421-62dd7a79800d.png)
2. Add SQL server node to add this data to SQL server using an INSERT query.
3. Connect the nodes and execute the workflow.

![Screenshot_2024-04-01_at_10_55_55_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1843fbd8-183d-3b29-8586-82c199449564.png)
4. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| DataSource | Choose the dataSource name configured on Securiti. See the Braze connector documentation to understand how. |
| Operation | The action to perform: - Export Users - Delete Users - Update/Create Users |
| ID Type | Specify the type of ID to identify Braze user |
| External ID | Specify the ID of users in your apps |
| User Aliases - **Alias Name:** Alias name in Braze - **Alias Label:** Value of the alias label |
| Email Address | Specify the email address of the user |
| Braze ID | Specify the user ID assigned by Braze |
| **Attributes** |
| ID Type | Type of ID to identify Braze user - **External ID:** ID of users in your apps - **Braze ID:** User ID assigned by Braze. Can only be used for update - **User Aliases** - **Alias Name:** Alias name in Braze - **Alias Label:** Value of the alias label |
| Update Existing (toggle) | Toggle on to update existing users only and toggle off to not create new users. |
| First Name | Specify the first name of the user |
| Email | Specify the email of the the user |
| **Custom Attributes** |
| Name | Specify the name of the custom attribute |
| Value | Specify the value of the custom attribute |
| **Events** |
| Name | Specify the name of the event |
| Time | Specify the time the event occurred at |
| App ID | Braze app the event occurred in |
| **Properties** |
| Name | Name of the property |
| Value | Value of the property |
| **Purchases** |
| Product ID | ID of products purchased |
| Currency | Currency in ISO 4217 format |
| Price | Enter price of products purchased |
| Quantity | Enter quantity of products purchased |
| Time | Select date and time from the time and date picker |
| **Properties** |
| Name | Name of the property |
| Value | Value of the property |
