---
title: "Group By"
slug: "group-by-regular-node"
updated: 2026-01-12T14:26:03Z
published: 2026-01-12T14:26:03Z
canonical: "helpcenter.securiti.ai/group-by-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Group By

A Group by node is used to organize and aggregate data based on specified criteria or keys. This functionality is crucial for simplifying complex data sets into more manageable groups, making further processing and analysis easier and more efficient.

The Group by node essentially categorizes multiple entries into subgroups that share a common attribute or field, facilitating operations like summarization, calculation, or conditional execution based on these groups.

Please refer to the [node configuration section](/v1/docs/group-by) to understand the node working and properties.

#### Example use case

As an example let's create a workflow in which a retail company wants to enhance its marketing efforts by segmenting its customer base into groups based on geographical location. This segmentation allows the company to tailor marketing messages and offers to specific groups, improving engagement and sales. The Group by node in their workflow automation platform plays a critical role in organizing customer data into these meaningful segments.

The workflow starts with a Cron Trigger node that executes at the end of each day and the Salesforce node fetches the data of leads. This data is then grouped using the geographical location of the leads for better data management and visualization. The Process CSV node transforms this structured lead data into a CSV file format followed by the Dropbox node that securely uploads the newly generated CSV file to a designated Dropbox location.

The following nodes are used in this use case:

1. [Cron Trigger Node](/v1/docs/cron)
2. [Salesforce Node](/v1/docs/salesforce)
3. Group By Node
4. [Process CSV Node](/v1/docs/process-csv)
5. [Dropbox Node](/v1/docs/dropbox)

#### Customer Segmentation for Targeted Marketing Campaigns

1. Add the Cron Trigger node and set the time such that the node executes every day.
2. Add Salesforce node to get a list of all the leads. Fetch the important details such as Name, ID and location etc.
3. Add the Group by node to group the data based on the location of the leads.

![Screenshot_2024-05-07_at_12_51_33_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-922b4728-8f4f-0c17-ddc3-bec1293bb25c.png)
4. Write the data to a CSV file using the Process CSV node, followed by the Dropbox node to upload the generated file to Dropbox.
5. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_12_51_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4240947-2544-4eca-7284-69794493f902.png)
6. Upon successful execution, the workflow node provides a successful response both in JSON and table format.

#### Node configurations

| Parameters |
| --- |
| Key | Specify the Key on which to group |
| Output Property | Specify the name of the property in which to write results |
| Remove Key | Enable to remove the key from the grouped results |
