---
title: "Create policies using Graph Explorer"
slug: "create-policies-using-graph"
updated: 2026-08-05T07:40:28Z
published: 2026-08-05T07:40:28Z
canonical: "helpcenter.securiti.ai/create-policies-using-graph"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Create policies using Graph Explorer

Policies in Securiti's Sensitive Data Intelligence module serve as the foundation for enforcing consistent, automated, and compliant data management practices across an organization’s digital ecosystem. They help you define structured guidelines for identifying, labeling, and securing sensitive information, while also enabling automated remediation actions.

To streamline the policy creation process, the Graph Explorer offers a query interface where you design and apply targeted searches across data sources. Together, these capabilities empower you to efficiently create and manage File Insights, Data Labeling, and Structured Data Insights policies.

For more information, see [Using Graph Explorer](/latest/docs/using-graph-explorer) and [Managing queries in the Graph Explorer](/latest/docs/managing-queries-in-the-graph-explorer).

## Procedure:

To create a query:

1. To create a query, click **+** sign in the upper left corner of the top row to choose your root entity, as shown below.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(862).png)
2. Next, click **Options** (three dots) to add a property or a related entity. Securiti lets you create policies using the following entities in the Graph Explorer. To identify which nodes align with specific policy types, see the table below.

| Policy Type | Graph Node | Graph Property |
| --- | --- | --- |
| File Insights | Files | - |
| Data Labeling | Files | Data System Type |
| Structured Data Insights | Table, Column | - |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(864).png)

1. Click **Add Relationship** to add a related entity, or **Add Property** to apply filter to your entity.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(870).png)
2. Select a value for the selected property and click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(865)(1).png)
3. Once your query is completely configured, in the upper right corner of the top row, click **Run Query**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(869).png)
4. Click on **More Actions** (three dots) on the upper right corner of the top row.
5. Then, click on **Create Policy** to import the query directly to the create policy page of the relevant policy based on your query, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(868).png)
6. This opens the **Create a New Policy** popup, the policy type is autoselected based on your query, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(867).png)
7. On the policy creation page, fill in the relevant policy details, name, and description. Also, enable the relevant toggles for your policy type.

For more information, see [Policies](/latest/docs/securiti-policies).

### Example Query

File insight example query:

Entity: Files

Property: File Format equals Image

Property: Data System Type is one of Microsoft 365 OneDrive Policy ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-D30G8JA8.png)

Structured data insight example query:

Entity: Table

Property: Data System Type is one of MySQL

Property: Total Columns is less than 05

> [!WARNING]
> Important
> 
> To generate findings for the Table entity, you must first complete a discovery scan for the data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-49JUF0LX.png)
