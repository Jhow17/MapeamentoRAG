---
title: "Drop nulls"
slug: "drop-nulls-regular-node"
updated: 2026-01-12T06:54:44Z
published: 2026-01-12T06:54:44Z
canonical: "helpcenter.securiti.ai/drop-nulls-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Drop nulls

A Drop Nulls node is typically used to remove rows or columns from a dataset where one or more values are missing or null. When you add the Drop Nulls node in a workflow, the rows or columns containing null values are eliminated from the dataset.

By removing rows containing null values, the node ensures cleaner data for subsequent analysis or tasks within the workflow. This can significantly improve the accuracy and reliability of downstream steps. Moreover, by working with smaller, non-null datasets, the workflow can potentially execute faster, especially when dealing with large amounts of data. Some algorithms or tools might not handle null values effectively, so removing them beforehand can ensure compatibility and prevent errors.

Refer to the [Node configurations section](/v1/docs/drop-nulls) to understand the node working and properties.

#### Example use case

Let’s create a workflow where you need to generate daily reports on your sales leads captured in Salesforce. However, some leads might have missing information, leading to incomplete and inaccurate reports. The DropNulls node drops the null values from the data and writes the useful data to a CSV File.

The Salesforce node runs every day via a CRON node and fetches all lead details. Subsequently, the DropNulls node identifies the specific fields containing null values, such as phone number, email address, or company name and then use the Process CSV node to write the data to a CSV file.

The following nodes are used in this workflow:

- [Cron Trigger Node](/v1/docs/cron)
- [Salesforce Node](/v1/docs/salesforce)
- Drop Nulls Node
- [Process CSV Node](/v1/docs/process-csv)

#### Cleaning Salesforce Lead Data and Generating Daily CSV Reports

1. Add the Cron Node such that the workflow executes everyday, followed by the Salesforce node to get all the lead details such as name, id, Email, contact information, etc.
2. Add the DropNulls node to drop the null values from the collected data.

![Screenshot_2024-02-20_at_2_10_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5be5d7cf-7ed3-8dc3-6bd1-a9e6d8bcb35d.png)
3. Add the Process CSV node to write the collected data into a CSV file.
4. Connect the nodes and execute the workflow.

![Screenshot_2024-02-20_at_1_28_45_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df920e13-083c-1b8d-e879-84dcaa086f76.png)
5. Upon successful execution, the workflow node will provide a successful response. After the workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

![Screenshot_2024-02-20_at_1_33_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fb6336f-9b4c-796f-e5a2-4a51802e864f.png)

#### Node configurations

| Parameters |
| --- |
| Expression | Enable the slider to configure a data expression |
| Data expression | Specify the data expression for JSON array to operate on |
