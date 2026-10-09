---
title: "Using the Universal Data Explorer"
slug: "using-the-universal-data-explorer"
updated: 2026-09-02T08:49:52Z
published: 2026-09-02T08:49:52Z
canonical: "helpcenter.securiti.ai/using-the-universal-data-explorer"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Universal Data Explorer

The Universal Data Explorer provides a graphical representation of key information and relationships across data systems. It serves as a blueprint of discovered assets and shows information about the following:

- Data systems
- Discovery scans
- Files
- Objects
- Tables
- Policies
- Classification etc.

> [!NOTE]
> **Note**
> 
> - If the Universal Data Explorer is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - The Universal Data Explorer is designed for exploring scan-specific data. To view all assets across your tenant regardless of scan status, we recommend using Securiti’s [Inventory](/latest/docs/using-the-inventory-dashboard) and [Graph Explorer](/latest/docs/using-graph-explorer) to browse assets and visualize their relationships.

> [!WARNING]
> **Important**
> 
> The Universal Data Explorer is currently only available on the US production cloud hosted on AWS. The support for the EU production cloud and GCP will be made available soon.

#### Prerequisites for the Universal Data Explorer

You must integrate your cloud account into Securiti and log in to the Securiti platform using an account that has admin role permissions for that cloud account, along with full privileges for the IaaS cloud infrastructure.

For more details on integration with IaaS clouds with Securiti, see [AWS](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later), [GCP](/v1/docs/creating-a-gcp-iaas-instance-version-1124-and-later), [Azure](/v1/docs/integrating-securiti-with-microsoft-azure), or [OCI.](/v1/docs/integrating-securiti-with-oracle-cloud-infrastructure)

Once you have integrated your IaaS cloud with Securiti, the platform collects metadata of all assets within the cloud account and displays it as a graphical representation in the Universal Data Explorer for easy visualization and analysis.

#### Understanding the Universal Data Explorer

To access the Universal Data Explorer in Securiti, open **Sensitive Data Intelligence**, and choose **Data Explorers >** **Universal Data Explorer**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UniversalDataExplorerMenu.png)

The circular graph in the middle section of the page shows you the Universal Data Explorer.

The relationship graph comprises the following two primary elements:

#### 1. Circular chart

- Entities - static metadata for the various nodes
- Lines connecting entities represent the relationships between them
- Counts on each entity represent how many instances of that entity match the current search filters

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDEPage.png)

**Scanned Document Count** and **Scanned Document Size** tiles refer to the scanned documents versus scanned document size out of all self-hosted unstructured data systems.

**Scanned Table Count** and **Scanned Table Size** tiles refer to the scanned table count and scanned table size out of all self-hosted unstructured data systems.

> [!NOTE]
> **Note**
> 
> Securiti shows these counts based on the data system. When performing multiple scans for the same resource, these counts do not change as the resource size does not increase.

The following table lists the entity groups and the associated subtypes in each group:

| Groups | Subtypes |
| --- | --- |
| Cloud | Hosting |
| Data | Column |
| Data System |
| Database |
| Discovery Scan |
| Discovery Scan Jobs |
| Files |
| Sites |
| Table |
| Topic |
| Control | Finding |
| Policy |
| Regulation |
| Rule |
| Standard |
| Management | Account |
| Region |
| AI | AI Agent |
| AI Model |
| Compute | Block Storage |
| Data Classification | Content Profile |
| Data Element |

Each entity (Universal Data Explorer) has several attributes related to it that you can use to filter the scope of the Universal Data Explorer. For example, an Access Role may have the attributes of the access role name and type.

#### Viewing entities and their relationships

1. In Securiti, open **Sensitive Data Intelligence** and from the left panel, choose **Data Explorers >** **Universal Data Explorer**.
2. Click any entity on the Universal Data Explorer. The graph shows you the selected entity highlighted in the respective color, and the connecting line between the entities shows you the level of relationship with other entities.

#### 2. Data grid

The grid at the bottom lets you view the attributes of a given entity and all the instances of that entity. Clicking an entity in the circular chart switches the grid context to that entity.

![dcgEntitiestable.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ab31330-5425-11f6-0fb9-681828eb7ebf.png)

Click a cell in the grid to bring up an instance inspector view of that instance of that entity. The instance inspector shows you the following information:

- A flattened view of all of the entities and counts with relationships to the selected instance
- A grid showing the instances and attributes of the related entities

![dcgRelationships.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4da77a0-dc8f-cf6a-b3c2-9025ab1dd627.png)

#### Filtering the Universal Data Explorer

The Universal Data Explorer shows statistics for the IaaS cloud resources (considered entities in the Universal Data Explorer). It also lets you apply filters on these resources and relationships among resources at different levels.

To open the Universal Data Explorer, in Securiti open **Sensitive Data Intelligence**, and from the left panel, choose **Data Explorers >** **Universal Data Explorer**.

The top row of the dashboard is the filter bar, where you can apply entity-level and attribute-level filters to view valuable information. The second row displays the details of the scanning data of the data system being scanned. Near the left side of the page is the **Saved Views** panel, which shows you the list of all your saved views.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDETiles.png)

#### Filtering entities and their attributes

You can apply quick filters to quickly view the graphical representation of the underlying data.

#### Enabling and disabling expensive graph queries

The Universal Data Explorer features an **Activate Graph Metrics** toggle to optimize page load performance. With this control, Securiti disables automated graph metric calculations by default for tenants with large volumes of metadata. You can load this detailed data on-demand for your current session by enabling the **Activate Graph Metrics** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDEActivateGraphMetrics.png)

> [!NOTE]
> **Note**
> 
> - The **Activate Graph Metrics** toggle is designed as a performance optimization for tenants with very large data volumes. For all other tenants, the toggle is hidden and graph metrics remain enabled by default.
> - Enabling this toggle for tenants with very large data volumes can result in slower page load times.

Once activated, these additional columns become available in the **Column Selector.** A purple vertical indicator next to these metrics highlights them as on-demand graph metrics.

![dcgExpensiveIconColumnSelector.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cd9f585-c292-f282-3be6-ea53930b5fc3.png)

#### Applying filters

1. On the Universal Data Explorer, near the upper left corner of the page, click **+** to open the filter menu.
2. On the filter menu, select entity, attribute operator, and attributes from the respective menus and click **Apply** as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDEFiltersFull.png)
3. The applied filter appears in the first row of the dashboard. The circular graph shows you the entities, their relationships, and the respective counts of the filter. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDEFilters.png)

> [!NOTE]
> **Note**
> 
> - If you apply a filter for one of the subtypes within a type, such as the **Data Element** subtype under **Data Classification**, it only displays the counts for the **Data Element** subtype. Counts for other subtypes within the same type, like **Content Profile**, will not be updated. However, counts for nodes or types outside of the **Data Classification** type will still be updated.
> - You can apply the following attribute operators on entities to apply filters:
>   - is one of
>   - is not one of
>   - is equal to
>   - is not equal to
>   - contains
>   - does not contain
>   - starts with
>   - does not start with
>   - is empty
>   - is not empty
> - To return the non-active data systems, use the **Data System state is empty** filter.

#### Using content profile filters

Securiti lets you identify which columns directly contributed to a table's content profile classification. You can filter the **Column** and **Table** entities by content profile using the **Columns Content Profile** and **Content Profile** filters. Consider the following when using content profile filters:

- The **Columns Content Profile** filter shows only the columns where that content profile is directly assigned at the column level.
- The **Content Profile** filter operates at the table level and returns all tables with that content profile enabled, including only the columns that directly contribute to that table's overall content profile.

> [!WARNING]
> Important
> 
> This behavior applies only to data scanned in Securiti release 1.149 or later. For the previously scanned data, the **Content Profile** filter continues to show all the columns in the table.

If you want to view all the columns in a table, apply the **Table Name** filter without any reference to content profiles.

![Overview of data systems and columns in the Universal Data Explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tablenamefilter_ude.png)

If you want to find which columns triggered a content profile on a table, apply the **Content Profile** filter. This displays only the contributing columns.

![Data Explorer interface showing table and column details with selected content profiles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/contentprofile_ude.png)

If you want to view columns with a content profile natively assigned, use the **Columns** **Content Profile** filter for a precise, column-level view of content profile assignments.

![Data Explorer interface showing table and column properties with selected content profiles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnscontentprofile_ude.png)

#### Viewing reviewed and validated columns of a Validation Workbench session

If you have reviewed columns from your database tables in Validation Workbench, Securiti lets you see them in the Universal Data Explorer.

To view reviewed and validated columns, apply the **Session ID** filter from the **Columns** quick filters on the upper-left side of the page. This displays column data along with the associated **Session ID** and **Session Name** from the relevant Validation Workbench session.

![dcgSessioIdName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c393857-ac09-ea1d-a6f9-ae880bcd3d3e.png)

For more information, see [Using the Validation Workbench to review and validate classifications](https://helpcenter.securiti.ai/docs/using-the-validation-workbench-to-review-and-validate-classifications).

#### Saving and accessing saved views of filters

1. On the Universal Data Explorer, near the top right side of the page, click **Options** (three dots) and choose **Save**.
2. On the **Save Filter** popup, add a name, description, and then click **Save View** to save your created filter. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDESaveViewPopup.png)

> [!NOTE]
> **Note**
> 
> You must add the name of the filter to save it for later use. However, adding the description is optional. You can add a description of a maximum of 120 characters.
3. Click **Saved Views** to view your saved filter in the left **Saved Views** panel. ![savedViewCustomFilters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b59e6f53-8b44-b360-0f50-7b83ee487389.png)

#### Clearing the applied filters

1. On the Universal Data Explorer, near the upper right corner of the filter menu, click the **Clear Search** icon to clear the applied filter.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UnivDEClearSearch.png)

#### Adding multiple filters to the existing filter

1. On the Universal Data Explorer, near the upper left corner of the page, click the plus sign **+** to open the filter menu. Enter entities and attributes to add multiple filters to the applied filter. For more information, see [Applying filters](/v1/docs/managing-queries-in-the-graph-explorer).
2. On the left side of the page, select any entity from the Entities menu and then apply the increment ( + ) or decrement ( - ) operator to select or deselect the entity attribute.
3. At the bottom of the page, a popup appears that shows the number of entities selected. Click **Apply Filters** to update the filter with selected entities and their attributes.

![applydcgFilters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-400fe5af-694c-e8fb-2da9-6b10058fb13a.png)

#### Connecting a new or existing pod for Data Discovery

This section provides instructions on how to connect to a pod for data discovery or classification.

> [!NOTE]
> Note
> 
> - You can choose from the following Data Systems to connect a pod for data discovery:
>   - AWS S3
>   - Google Cloud
>   - Google BigQuery
>   - Azure Blob
>   - Azure Files
> - To use bulk actions such as **Connect Data System** or **Add Discovery Scan**, all selected data systems must share the same region, data system state, and account name.

1. From the Entities panel on the left side, choose **Data** > **Data System**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(327).png)
2. Select the checkbox from the **Data Systems** list and click **Connect Data System** from the popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(328).png)
3. This opens the pod configuration popup, on which you can configure your scan.
4. Select the cloud provider, deployment type (Pod or Elastic pod), pod name, region, and number of maximum nodes in the case of the elastic pod.
5. Click **Connect**.

The Securiti platform includes a wide range of techniques for sensitive data detection that includes powerful artificial intelligence (AI) and machine learning (ML) detection techniques. The customers' requirements may vary as to whether they intend to detect sensitive data or classify data as sensitive.

## Related

- [Discovery scans](/discovery-scans.md)
- [Pods deployment](/pods-deployment.md)
