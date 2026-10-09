---
title: "Pardot"
slug: "pardot-regular-node"
updated: 2025-10-30T19:06:53Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/pardot-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Pardot

The Pardot node within Securiti can be used both within privacy integrations and as a standalone component. When used independently, it lets you configure operational parameters such as selecting objects, defining actions, and specifying fields—giving you flexible control to interact directly with Pardot data from within your Workflow.

> [!NOTE]
> **Note**
> 
> - The Pardot node currently supports only the **prospect** object.
> - When using the Pardot node to update Prospect records, you cannot set fields to null. To accommodate this behavior, null values will be ignored during updates. Ensure that any field you intend to clear is handled outside of this integration logic.

When used as part of a Privacy Platform Integrations (PPI), it lets you manage inbound and outbound consent data flows between Pardot and Securiti.

- In the **inbound** flow, it lets you fetch consent-related records from Pardot that don’t include explicit consent states such as granted, withdrawn, or declined. These records are evaluated using the Rules Matrix functionality, which applies jurisdiction-specific logic to derive consent states based on the region associated with each data subject. The derived consent values are then populated into the Universal Consent Management module.
- In the **outbound** flow, it lets you send consent records from the Universal Consent Management module back to Pardot. This ensures that consent data remains in sync and ready to use for marketing or other operational purposes.

> [!NOTE]
> **Note**
> 
> When used as part of a Privacy Platform Integrations (PPI), the workflows generated are read-only.

Refer to the Node Configurations section to understand the node working and properties.

#### Example Use Case

As an example, let’s create a Workflow that executes at the end of each day and fetches the data of leads collected using the Pardot node. This data is then stored into a CSV file that gets uploaded on Dropbox to keep track of all the generated leads.

The Process CSV node transforms this structured lead data into a CSV file format. The Dropbox node then securely uploads the newly generated CSV file to a designated Dropbox location. This creates a historical record of leads, offering a centralized and easily accessible view of lead generation trends over time. By automating the retrieval and storage of lead data into a centralized CSV file, businesses can maintain a comprehensive repository of acquired leads.

The following Nodes are used in this Workflow:

1. [Cron Trigger Node](/v1/docs/cron)
2. Pardot Node
3. [Process CSV Node](/v1/docs/process-csv)
4. [Dropbox Node](/v1/docs/dropbox)

#### Optimizing lead tracking with automated daily reports

1. Add the Cron Trigger node and set the time such that the node executes every day.
2. Add Pardot node to get a list of all the leads. Fetch the important details such as Name, ID, Contact information etc.

![pardot-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-541c402b-dc36-9b8e-036c-6c21c9c20ca2.png)
3. Write the data to a CSV file using the Process CSV node, followed by the Dropbox node to upload the generated file to Dropbox.
4. Connect the Nodes and execute the Workflow.

![pardot-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16c4cfa6-786a-0215-21f3-9483a017d3e2.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

#### Node Configurations

| Parameters |
| --- |
| Data System Name | Specify the datasource name for Pardot. To understand the data system configuration for Pardot, see the Connector documentation. |
| Object | Prospect | Select an object from your Pardot system. An object can be a type of Pardot data you want to interact with through the Workflow node such as a prospect, list, or campaign. Selecting an object defines the scope of the operation such as fetching or updating lead data. Each object includes specific fields you can configure based on your use case. > [!NOTE] > **Note** > > The Pardot node currently supports only the **prospect** object. |
| Operation | List | Choose this option to list all the documents. |
| Update | Choose this option to update the existing documents on Pardot. |
| Upsert | Choose this option to create or update documents on Pardot. |
| List | Fields | List the fields to fetch, separated by commas with no spaces. |
| Filter | Apply multiple filters on records. |
| From Date | Specify a date to fetch records from the selected date to the current time in initial sync, OR if delta sync is disabled. By Default, data will be fetched from the last 24 hours. |
| Delta Sync | Enable this toggle to specify the number of records to fetch per iteration in a single Workflow execution. |
| Update | Update By Email | Enable this toggle to update records by email. |
| Record Email | Enter the email of the object to be upserted. |
| Record ID | Specify the ID of the subject to be updated. |
| Update data | Specify the data to update. |
| Upsert | Record Email | Specify the email of the object to be upserted. |
| Update Data | Specify the data to upsert. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
