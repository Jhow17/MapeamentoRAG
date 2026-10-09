---
title: "Salesforce"
slug: "salesforce-regular-node"
updated: 2025-11-04T04:48:22Z
published: 2025-11-04T04:48:22Z
canonical: "helpcenter.securiti.ai/salesforce-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Salesforce

The Salesforce node within Securiti provides a way to seamlessly connect your workflows with the capabilities of Salesforce's CRM platform. Salesforce is a cloud-based platform that helps businesses manage their relationships and interactions with customers and prospects. It provides a comprehensive suite of tools and functionalities designed to streamline sales, marketing, customer service, and collaboration efforts within an organization.

Using the Salesforce node, you can perform the following actions:

- Fetch important customer, case, lead, opportunity, or custom object information from Salesforce.
- Dynamically create new cases, leads, or other Salesforce records.
- Delete a particular lead, customer or record from the database

Refer to the [Node configurations section](/v1/docs/salesforce#node-configurations) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow that executes at the end of each day and fetches the data of leads collected using the Salesforce node. This data is then stored into a CSV file that gets uploaded on Dropbox to keep track of all the generated leads.

The **Process CSV** node transforms this structured lead data into a CSV file format. The **Dropbox** node then securely uploads the newly generated CSV file to a designated Dropbox location. This creates a historical record of leads, offering a centralized and easily accessible view of lead generation trends over time. By automating the retrieval and storage of lead data into a centralized CSV file, businesses can maintain a comprehensive repository of acquired leads

The following nodes are used in this Workflow:

1. Cron Trigger Node
2. Salesforce Node
3. Process CSV Node
4. Dropbox Node

#### Optimizing lead tracking with automated daily reports

1. Add the Cron Trigger node and set the time such that the node executes every day.
2. Add Salesforce node to get a list of all the leads. Fetch the important details such as Name, ID, Contact information etc.

![Salesforce-HC.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47182b5e-767e-4499-bca7-2fadddb9e036.png)
3. Write the data to a CSV file using the Process CSV node, followed by the Dropbox node to upload the generated file to Dropbox.
4. Connect the nodes and execute the Workflow.

![Screenshot_2024-02-20_at_7_07_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8077e927-a0f2-19ab-5fae-e80f91e99530.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

> [!NOTE]
> **Note**
> 
> - The **List** operation applies only the first item filter and runs once per execution.
> - When using **Update** or **Upsert**, up to 2,000 records can be updated per batch. This limit may be lower if items contain multiple records. If more than 2,000 records are available, only the first 2,000 (or fewer, depending on batch composition) are processed. This is a Salesforce limitation.
> - For **Upsert** operation:
>   - The response includes success flag, created flag, errors and a counter for updated records.
>   - If an error occurs during the record retrieval step, the Workflow execution will fail immediately with the first encountered error.
>   - If an error occurs during the update or create step, it will be reflected in the response alongside successful Workflow executions.

#### Node configurations

| Parameters |
| --- |
| Data System Name | Specify the datasource name for Salesforce. |
| Object | Specify the Salesforce object to operate on. The object can be any of the Salesforce objects such as: - Lead - Contact - Case - Account - Attachment - User |
| Operation | List | Choose this option to list all the documents |
| Update | Choose this option to update the existing documents on Salesforce. |
| Upsert | Choose this option to create or update documents on Salesforce. |
| Create | Choose this option to create a new document. |
| Get | Choose this option to get a specific record against the provided ID. |
| Delete | Choose this option to delete a record. |

| List Parameters |
| --- |
| Fields | List the fields to fetch, separated by commas with no spaces. |
| Filter | Enable this toggle to apply filter on records. |
| Use Raw Filter | Enable this toggle to apply multiple filters on records. > [!NOTE] > **Note** > > - Valid Type(s) for multiple filters are: > - Id (object Id), string, picklist, multipicklist, textarea, address, phone, email, url → string > - boolean → boolean or bool > - double, date, datetime, time → number > - For multipicklist, separate the options with a semicolon (;). > - You can use the **in** and **equal** operators in raw filters. The **in** operator supports string, number, and boolean values. If no operator is defined, the **equal** operator is applied by default. |
| Key | Specify field to apply filter on. |
| Type | Specify the type of field. It can be either String, Boolean, or Number. |
| Value | Specify field value to use as a filter. |
| Delta Sync | Enable this toggle to specify the number of records to fetch per iteration in a single Workflow execution. |

| Create Parameters |
| --- |
| Add Field | Click this button to specify records to create. |
| Field | Specify the field name. |
| Value | Specify the value to be used. |

| Update Parameters |
| --- |
| Update By ID | Enable this toggle to update records by ID. |
| Record ID | Specify the ID of the subject to be updated. |
| Use raw filters | Enable this toggle to apply multiple filters on records. |
| Raw Filters | Enable this toggle to apply multiple filters on records. > [!NOTE] > **Note** > > You can use the **in** and **equal** operators in raw filters. The **in** operator supports string, number, and boolean values. If no operator is defined, the **equal** operator is applied by default. |
| Update Key | Specify the primary key to update on. |
| Type | Specify the type of field. It can be either String, Boolean or Number. |
| Update Key Value | Specify the value of the primary key to update on. |
| Update Data | Specify the data to update. |

| Upsert Parameters |
| --- |
| Upsert Supported | Enable this if using a supported field. Usually external id field and primary keys are supported |
| Allow Multiple Updates | Enable this toggle to update up to 2,000 records per item. > [!NOTE] > **Note** > > If the toggle is disabled, only one matching record is updated, and no error is returned if multiple records exist. |
| Upsert on Field | Specify field ID to insert or update the data. |
| Use raw filters | Enable this toggle to apply multiple filters on records. > [!NOTE] > **Note** > > Raw filters for the upsert operation currently support only the `equal` operator. The `in` operator is not supported at this time. |
| Type | Specify the type of field. It can be either String, Boolean or Number. |
| Field Value | Specify the Value of upsert id field to insert or update data. |
| Upsert Data | Specify the data to be upserted. |

| Get Parameters |
| --- |
| Record ID | Specify record ID to operate on. |

| Delete Parameters |
| --- |
| Record ID | Specify record ID to operate on. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
