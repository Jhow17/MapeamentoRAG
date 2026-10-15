---
title: "Inferred lineage"
slug: "inferred-lineage"
updated: 2026-07-18T10:34:06Z
published: 2026-07-18T10:34:06Z
canonical: "helpcenter.securiti.ai/inferred-lineage"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Inferred lineage

**Scenario**

As a compliance officer, you must trace how sensitive data flows through systems to meet regulatory requirements. When lineage isn’t documented, especially in older systems, you face blind spots that threaten audit readiness. Inferred Lineage fills these gaps by detecting potential data flows and connections. This enables better oversight and ensures no system falls outside your compliance view.

Inferred lineage lets you document lineage from systems where explicit documentation of data flow from producers to consumers is not available. This removes the limitation of lineage extraction using third-party plugins or SQL parsing using the Sensitive Data Intelligence module.

For more information, see [How Inferred Lineage Helps Solve Metadata Gaps](https://securiti.ai/blog/inferred-lineage-modern-enterprise-data-management/).

With Inferred lineage, you can uncover possible lineage relationships across structured and unstructured datasets. You can gain a comprehensive understanding of data movement and dependencies, even in situations where explicit documentation is lacking or incomplete. This deficiency may stem from various reasons such as legacy systems lacking tracking capabilities, undocumented data flows, or complex transformations.

### Why Inferred lineage?

When dealing with large amounts of data, especially in databases where tables and columns are interconnected, understanding how data flows and relates to each other is crucial. Inferred lineage helps in this regard by analyzing the structure and contents of the tables and columns to infer possible connections or lineage between them.

### How is inferred lineage captured?

First, ensure that all your datasets are registered in the Enterprise Data Catalog and that an active Pod is available for execution. Configure the settings to create a new Inferred Lineage. Assign ownership, and provide a name and description for the lineage. Select datasets from the producer and consumer menus, set relevant date and sort columns for producers and consumers where applicable.

Configure advanced parameters by choosing the operation type (infer lineage or find duplicates) and setting your objective (High recall, Balanced, High precision). Set normalization levels, add values to the exclusion list, and define cardinality and candidate settings. If needed, enable auto-registration for lineage, set thresholds, and choose between merging or replacing lineage. Otherwise, keep this toggle disabled if you want to merge or reject edges, manually, later.

Save the configuration and either execute immediately by clicking **Save & Execute** or save without executing by clicking **Save Configuration**. Monitor the execution via the inferred lineage dashboard, checking progress, access logs, and generated edges for detailed insights and troubleshooting.

### Prerequisites

- You must make sure the datasets for which you need to document lineage are registered in the Enterprise Data Catalog.
- You must have an active Pod available to execute inferred lineage processes.
- To perform actions on Inferred Lineage, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).
  - Create Inferred Lineage
  - Execute Inferred Lineage
  - Read Inferred Lineage
  - Update Inferred Lineage
  - Create Inferred Lineage Job
  - Read Inferred Lineage Job
  - Update Inferred Lineage Job
  - Create Inferred Lineage Result
  - Read Inferred Lineage Result
  - Update Inferred Lineage Result

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Scope

Currently, the inferred lineage is supported for the following [private cloud storage](/v1/docs/system-settings-configuring-private-cloud-storage) and the structured and unstructured data systems:

**Private cloud storage:**

- AWS S3
- Google Cloud Storage

**Data systems:**

- Oracle
- Apache HBase
- Apache Hive
- Cloudera Impala
- MS SQL
- NFS
- Amazon S3
- SMB
- S3 Compatible Storage connectors

### Limitations

Currently, you cannot generate inferred lineage for streaming sources given how dynamic those datasets are. For the unstructured supported data systems i.e. SMB, NFS and Amazon S3, you can only select .CSV, .TSV, and .XML files as producers and consumers.

Moreover, inferred lineage does not support JSON files. Consequently, you cannot select JSON files as producers or consumers.

### Opening Inferred lineage dashboard

The inferred lineage dashboard shows you valuable insights into the lineage relationships within your data environment.

- In Securiti, open Enterprise Data Catalog, then from the left navigation menu, choose Inferred lineage.

The first row of the dashboard shows you the following three widgets:

| Edges | Description |
| --- | --- |
| Execution runs | This widget displays information about the execution runs of the inferred lineage process. It shows you the count of successful and failed runs and the timestamps of each run. You can use this widget to track the progress of the inferred lineage process and to ensure that it runs smoothly. |
| Edges created | The **Edges Created** widget summarizes the total number of edges created, along with their dates. |
| Edges | The **Edges** widget displays the total committed and rejected edges, along with their corresponding dates. |

Below the widgets, you can view the section for configured inferred lineage. In this section, you can search for the created inferred lineages and explore their details.

### Filtering inferred lineages

You can filter the configured lineages using the following three ways:

1. Search bar

The search bar lets you search for inferred lineage by name, producer, or consumer.
2. Menus

You can select values from the following menus to filter specific inferred lineages:
  1. Click the down arrow for the menu upon which you want to filter results.
  2. Enter value.
  3. Click Apply to see the filtered results.
  - Producer
  - Consumer
  - Operation
  - Objective
  - Normalization
  - Owner

### Exploring configured inferred lineages

Below the search options, you can view the total count of configured inferred lineages, along with a detailed list of configured lineages.

For each created inferred lineage, you can view its:

- Inferred lineage name
- Producer
- Consumer
- Operation
- Objective
- Normalization
- Owner
- Execution count

From the inferred lineage list, click the down arrow for any created lineage you want to view the execution details.

### Creating inferred lineage

To configure inferred lineage:

1. Near the upper right corner of the page, click **New Inferred Lineage**.
2. On the **Inferred Lineage Configuration** page, configure the following settings:

| Setting | Description |
| --- | --- |
| Ownership | You can change the owner of the lineage by following the below steps: 1. Click **Edit Owner**. 2. Select the owner from the list or enter the name in the search bar. |
| Basic Information | Name | Enter the name of the inferred lineage to be generated. |
| Description | Enter the description of the inferred lineage to be generated. |
| Producers and Consumers | Producers | - Select dataset from the producer menu which acts as sources in the creation of inferred lineage. > [!NOTE] > **Note** > > - You can select multiple datasets as producers. The producer menu shows only those datasets that are registered in the Enterprise Data Catalog. > - In the case of SMB, NFS, and Amazon S3, you can only select .CSV, .TSV, and .XML files as producers. Each chosen dataset lets you access a date and sort menu to select relevant values. - Select the value from the **Select Date Column** menu. > [!NOTE] > Note > > When selecting a column in the ​**Select Date Column**​​ menu, it can be either a formal date type (for example, 2025-10-30) or a string that contains date values. - Select the value from the **Select Sort Column** menu. > [!NOTE] > **Note** > > - You can select number columns or date/time columns from the dataset. > - When you select a column to be used for filtering purposes. The top million rows will be exported based on a descending order using the column selection. When performing this selection, select columns that will result in corresponding transactions from the producers/consumers to increase the efficacy of the algorithm. |
| Consumers | - Select the dataset from the consumer menu that is consumed in the creation of inferred lineage. > [!NOTE] > **Note** > > - You can select multiple datasets as consumers. The consumer menu shows only those datasets that are registered in the Enterprise Data Catalog. > - In the case of SMB, NFS, and Amazon S3, you can only select .CSV, .TSV, and .XML files as consumers. > [!NOTE] > **Important** > > Upon deleting a discovery scan with tables identified as Producer and/or Consumer, their selection will become disabled. As a result, you will need to either delete this particular row or initiate the discovery scan again to reselect those tables as Producer and Consumer. |
| Specify a period for inferred lineage analysis | Enable this option to input dates in the From and To fields to scope the lineage to the specified time period. |
| Advanced parameters | Operation | Under the **Operation** option, you can select either **Infer Lineage** or **Find Duplicates**. - Select **Infer Lineage** to infer or deduce the lineage relationships between different datasets. OR - Select **Find Duplicates** to initiate a process where the system identifies and flags duplicate data entries within the specified datasets or data repositories. |
| Objective | This option lets you set the objective of the inferred lineage. You can specify any one of the following values: - High recall It aims to maximize the identification of true relationships between datasets, even if it results in a higher rate of false positives. - Recall Similar to high recall, this objective focuses on maximizing the identification of true relationships between datasets but with a slightly lower tolerance for false positives. - Balanced This objective strikes a balance between precision and recall. It aims to identify true relationships while also minimizing false positives and false negatives. - Precision It prioritizes maximizing the precision of the inferred lineage. It focuses on minimizing the inclusion of false positives, ensuring that the identified relationships between datasets are highly accurate, even if it means potentially missing some connections. - High precision This objective emphasizes maximizing the precision of the inferred lineage to an even greater extent than the standard precision objective. |
| Normalization | This option controls the extent to which data normalization is applied before inferring lineage. You can set the normalization to **High**, **Low** or **None**. - When you set the value to **High**, the normalization process is applied rigorously and extensively to the data before inferring lineage relationships. - When you set the value to **Low**, it implies a less aggressive or comprehensive approach to normalization compared to the high. - When you set the value to **None**, no normalization is performed on the data before inferring lineage relationships. |
| Exclusion list | In the exclusion list, add values that you want to remove from columns prior to processing. These are case-insensitive. |
| Cardinality | Cardinality refers to the number of unique values in a dataset column. It measures the diversity or uniqueness of data within that column. - Set the cardinality in any positive integer. |
| Candidates | This option refers to potential matches or candidates that meet certain criteria when comparing datasets or columns. - Enter the number in any positive integer. |
| Auto-register for lineage | Enable this option to register lineage in the Enterprise Data Catalog after execution. - Set the minimum threshold value and maximum threshold value between 0 and 1. - From the **Default Behavior for Auto-Registering** menu, select **Merge Lineage** or **Replace Lineage**. The merge lineage option adds upstream lineage to consumers. The replace lineage option overwrites existing upstream lineage. |
| Saving & Canceling | Save & Execute | Click this button to start the execution as soon as the information is saved. |
| Save Configuration | Click this button to save the information and not execute it. |
| Cancel | Click this button to cancel all configurations. |
3. Click **Save**.

> [!NOTE]
> **Note**
> 
> You can click the **Cancel** button to simply cancel the configured settings.

### Editing configured inferred lineage

1. On the Inferred Lineage dashboard, choose the configured lineage from the list that you want to edit.
2. Near the right corner of the list, click **Options** (three dots) > **Edit**.

### Executing configured inferred lineage

Securiti provides two options for executing inferred lineage.

| Approach | Description |
| --- | --- |
| Using a Spark Appliance | The execution of inferred lineage depends on the availability of Spark Appliances. Securiti first attempts to run inferred lineage using a Spark Appliance. If one or more Spark Appliances are available, the execution runs on the first active Spark Appliance found. |
| Using Securiti Cloud | If no Spark Appliance is available or all Spark Appliances are inactive, inferred lineage does not run by default. In this case, you must use the inferred lineage execution option through Securiti Cloud. > [!NOTE] > Note > > If you want inferred lineage to run on the Securiti Cloud, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for activation. |

1. On the inferred lineage dashboard, choose the configured lineage from the list that you want to execute.
2. Near the right corner of the list, click **Options** (three dots) > **Execute**.

The execution of the lineage gets started and you can monitor the progress as well as logs to troubleshoot any issues.

- Click the down arrow to view the following execution details.

| Execution details |
| --- |
| Requested at | Refers to the date and time when the creation of the lineage was requested. |
| Started at | Indicates the date and time when the creation process started executing. |
| Duration | Represents the amount of time taken for the creation process to complete. |
| Status | Represents the amount of time taken for the creation process to complete. The possible states are as follows: - Canceled - Executing - Failed - Completed |
| Edges resolved | The number of edges successfully resolved or established as part of the lineage creation process. It quantifies the extent to which the lineage was successfully inferred. |
| Rollback | Indicates whether a rollback mechanism was triggered or performed during the lineage creation process. Rollback refers to the ability to revert or undo the changes made during the lineage creation process, particularly if any errors or issues occur. If the **Rollback** column is marked with a tick, it indicates that the rollback has already been completed. Further rollback actions cannot be performed. If the Rollback column displays a cross mark, it indicates that the rollback has not yet been executed. To rollback an executed inferred lineage: 1. Click **Options** (three dots) > **Rollback Execution**. 2. The execution gets rollback successfully, and the **Rollback** column status gets updated with a tick mark. > [!NOTE] > **Note** > > You can only rollback an inferred lineage that is executed successfully and has the status Completed. |

When the inferred lineage execution starts you can monitor the following details:

#### Access logs

The access logs let you view logs generated during the execution. Logs are crucial to help you understand the sequence of events, identify any errors or anomalies, and troubleshoot issues if needed.

To download access logs:

- Near the right corner of the created lineage expanded section, click the download icon to download logs.

#### Generated edges

You can examine the number of edges generated during the execution. This information will give you insights into the complexity and scope of the inferred lineage.

To view generated edges:

1. At the right side of the access logs download icon, click the icon to view the metadata details.
2. On the metadata details popup, at the bottom center of the popup, click the **Generated Edges** button.
3. On the generated edges page, you can view the following details:
  - At the top, you can view the execution details.
    - At the top right corner of the page, click **Download CSV** to download the CSV file that contains information about the execution results.
  - The left navigation section shows you a list of edges generated with a search bar. The navigation section is grouped by **Producers** and **Consumers**. This facilitates you to see the lineage from/to a dataset/column. (A producer column may have lineage to multiple consumer columns, a consumer column may have lineage from multiple producer columns).
  - Click on any generated edge to view the following details:
    - Consumer column name
    - Producer dataset name
    - Producer column name
    - Consumer dataset name
    - Confidence

#### Filtering edges

The search bar lets you search for the created edges by it column names. You can also select values from the following menus to filter specific edges:

- Producer column
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter the keyword or phrase.
  4. Click **Apply** to see the filtered edge.
- Consumers
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter the keyword or phrase.
  4. Click **Apply** to see the filtered edge.
- Edges
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter the keyword or phrase.
  4. Click **Apply** to see the filtered edge.
- Group by

Select **Consumer Column** or **Producer Column** to group results based on producers or consumers.

#### Committing or rejecting edges

1. Expand each edge to view the following details:
  - Producer name/consumer column
  - Consumer dataset name/producer dataset name
  - Confidence
  - Auto-committed status
2. Select the checkbox for the edge that you want to commit or reject.
3. On the bottom side of the page, a popup appears, commit or reject the edge from that popup.

> [!NOTE]
> **Note**
> 
> The edge gets auto-committed if the **Auto-Register for Lineage** toggle is marked while configuring the lineage.
> 
> You cannot reject any edge if **Auto-Register for Lineage** toggle is marked. You can only commit the one that falls within the min and max threshold and can choose what to do with the rest.

### Viewing inferred lineage results

To view committed results:

1. Open the Enterprise Data Catalog dashboard.
2. Search or navigate to one of the producer(s) and/or consumer(s) you selected while configuring inferred lineage.
3. Click **Lineage** option to view inferred lineage results as shown below:

![inferred_lineage_-_results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab50a4e6-ece5-307c-2bea-126b1b2994eb.png)

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

A Spark Appliance is a compute component that uses Apache Spark to run large-scale data processing tasks such as discovery, lineage, and analytics. It allows these operations to run within the customer's environment instead of the cloud when available.

## Related

- [Datasets](/datasets.md)
