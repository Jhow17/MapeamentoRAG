---
title: "Using Data Command Graph"
slug: "data-access-governance-data-command-graph"
status: "update"
updated: 2026-09-23T05:27:36Z
published: 2026-09-23T05:28:16Z
canonical: "helpcenter.securiti.ai/data-access-governance-data-command-graph"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Using Data Command Graph

Securiti’s Data command graph (DAG Command Graph) is a knowledge graph that provides you detailed insight into the access configurations across your data systems. It provides a graphical representation of the relationships between users, user groups, roles, IAM policies, and the relationships between those entities and the data resources in your data systems. The Data Command Graph lets you apply filters and visualize your data systems, various identities associated with these data systems, policies associated with the data resources, and explore the relationships between them.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Using the Data Command Graph

The Data Command Graph is the default landing page when the Data Access Governance module is opened.

The Data Command Graph allows you to understand what level of access users have in your data systems and the data resources within those systems. Using the command graph, you can learn about users or service accounts with access to sensitive data contained within databases, tables, sites, files, and more.

The Data Command Graph consists of the following elements:

- Data Command Graph
- Data Command Graph Table View
- Access Graph Explorer
- Saved Views

The circular graph shows you the following info:

| Resources | Description |
| --- | --- |
| Entities | Entities are the Data and IAM objects discovered in your data systems |
| Lines connecting the entities | Represents the relationships between entities |
| Entity Counts | Represent how many instances of that entity match the current search filters |

The Data Command Graph Table View below the Command Graph lets you view the attributes of a given entity and all the instances of that entity. Clicking on an entity in the circular chart switches the grid context to that entity.

Click on a cell in the grid to bring up an instance visualizer view of that instance of that entity. The instance inspector shows you the following information:

- A flattened view of all of the entities and counts with relationships to the selected instance.
- A grid showing the instances and attributes of the related entities.

### Filtering the entities

You can apply filters to quickly view the graphical representation of the underlying data. To apply filters, you must:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click + to open the filter menu.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(20).png)
3. On the filter menu, select (+) and add attributes from the respective menus and click **Apply**.

The applied filter appears in the first row of the Command Graph and the circular graph shows you the entities, their relationships, and respective counts of the respective filter. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(16).png)

### Deleting the applied filters

You can delete the applied filters as per your requirement. To delete the applied filters:

- In the filter search bar, from the end of the filter, click the **Clear Search** to delete the applied filters. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(5).png)
- Another way of deleting the nodes from query is to click three dots **(⋮) icon** and click **clear filter.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(4).png)

### Saving filters

To save a view for your set filters and results:

1. On the Data Command Graph, near the upper right corner of the page, click **Save View**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(2).png)
2. On the **Save View** popup, add a name, and description, select a group of filters or add a new one, and then click **Save View** to save your created filter.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(2).png)
3. Click **Saved Views** near the upper right corner of the page to view your saved filters in their respective groups.

> [!NOTE]
> **Note**
> 
> You must select a group of the filter and add the name of the filter to save it for later use. However, adding the description is optional.

The **Data Command Graph** and **Access Graph Explorer** present you the following nodes:

| Node | Description |
| --- | --- |
| Identity Source | This node represents the provider of the IAM information for each connected data system. |
| User Principal | This presents a user account in the data system A User Principal could be an IAM sourced who is authenticated via an Identity Source such as AD, Okta, etc., or a local account in the data system. The local account represents the native data system user account such as SharePoint Online user. A Federated account user principal is an IAM sourced who is authenticated via an Identity Source such as Active Directory. |
| User Group Principal | An IAM User Group. This is a group of users or service accounts or other user groups, as configured in the identity provider, and available in the data system or account. The user group Principal node therefore has relationships with the User, Service Account, Role, and user group Principals, as well as the IAM Identity Provider. |
| Role | An IAM role. This entity represents a role within the IAM Identity Source or Data System. The Role Principal node has relationships with the Policy Object, User Principal, Identity Source, and User Group Principal. |
| Policy Object | This represents an access control object ranging from simple grants to complex policy definitions. The Policy Object node has relationships with the Role Principal, User Principal, and Policy Privilege Bundle nodes. The Policy Object node has relationships with the Database Cluster, Object Storage, and Account. |
| Policy Element | This is a representation of individual policy statements derived from the Policy Object, consisting of a principal, privilege/permission, and the resource scope. An Policy Object can result in one or more of these Policy Elements. |
| Policy Privilege Bundle | This node represents a bundle of permissions or privileges defined and used in some data systems. For instance, this would represent a Role Definition in a Microsoft Sharepoint account, which in turn contains granular permissions that have been associated with an entity in Sharepoint (such as a Site, Library, etc.) These privilege bundles have relationships to the policy objects where they are used or referenced. |
| Service Account Principal | A service account is typically a user account provisioned for use by automated jobs, scripts, etc. Service Account Principal node is related to the Identity Source (where it is defined) and to User Group Principals (to which it may belong). |
| Database | A database is a named collection of one or more database schemas that are in turn the named collection of tables, views, etc. |
| Database Schemas | A database schema is a named collection of logical structures of data such as tables, views, functions, etc. |
| Table | A table is a named collection of data represented in rows and multiple columns per row with each column having a specific data type. |
| Site | A Site is a collection of unstructured data used by some data systems like SharePoint for file organization and access. |
| Data Object | A Securiti abstraction for an object that holds a set of data fields - such as an SQL table containing a list of columns. |
| Data Element | An element of data identified by Securiti’s Sensitive Data Intelligence Module |
| Content Profile | Content Profiles are a set of rules that Securiti uses to identify types of document content |
| Data System | A Securiti abstraction for systems that hold data. These could be relational databases that hold structured data, NoSQL databases, object stores such as AWS S3, unstructured data stores such as file systems or SaaS file-sharing services, etc. |
| IaaS Cloud | A managed cloud service such as AWS (Amazon Web Services), GCP (Google Cloud Platform) or Microsoft Azure |
| Region | The geographic location in which the resources offered by the managed cloud service are located. |
| Account | An account in a managed cloud service. |

Reporting Dashboards in the Data Access Governance (DAG) module let you view the access and privilege information using system and custom dashboards. It lets you visualize data stored across different modules in the form of widgets created in the Data Command Graph module. The widgets are saved queries in the Data Command Graph, which can be viewed on custom dashboards. To learn more, see [Using Reporting Dashboard](/latest/docs/using-graph-reporting-dashboards).

## Using Access Graph Explorer

The Access Graph Explorer in Securiti lets you create and apply both custom or out-of-the-box queries (Saved Views) to identify which users, groups, or roles have access to sensitive data across your systems. It helps you visualize access patterns and access configurations to provide visibility into the access pathways across your data estate, for example in AWS, by showing whether access is direct or inherited through groups, along with the associated permissions. It also allows you to identify AWS IAM users that have access to AWS S3 Buckets containing sensitive data.

> [!NOTE]
> Note
> 
> If Access Graph Explorer is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

![Access_Graph_Explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e6262ea-ce31-8f34-b2d0-bbf2cc6cf66b.png)

### Viewing Saved Views in Access Graph Explorer

Saved views in Access Graph Explorer are the out-of-the-box views that present you the graph queries relevant to particular use cases related to privilege analysis for different data systems. To access the Saved Views:

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** from the left menubar.

![Saved_Views_DAG_Access_Graph_Explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4df2909f-d2ef-1568-dff7-ce3f5ff22c3c.png)
2. Click on the **Saved Views** button on the upper right side of the page.
3. On the **System Views** tab, navigate to the relevant Data System queries areas, For example, **Snowflake Queries** area. You can see the queries that help you perform privilege analysis for your Snowflake instances.
4. Click on the query **Users with Any access to Tables containing Column Classification**. Click on the **User Principal** node to see the users in the data grid.

### Creating custom queries in Access Graph Explorer

To create custom queries specific to your use-cases such as Identifying which users and user groups have access to specific File and their permissions on specific Files in Microsoft 365 environment such as OneDrive:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Group Principal** Entity. Click three dots with the **User Group Principal** Entity, and select **+ Add Property**. Choose the **Provider Type** property. Select **Office365**. Click **Apply**.
4. Click three dots with the **User Group Principal** Entity, and select **Add Relationship**. Select **User Principle**.

![DAG_OneDrive_User_Group.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f98f87dc-9223-f1d4-4d72-58ca0d77ab80.png)
5. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Select **Resource Access**. Click three dots with the **Resource Access** Entity, and select **Add Relationship**. Select **Files**. Add **File Name** Property for Files Entity.
6. Select the **Files** for which you want to identify the users that have access to. You can also write the File Name in the search box.
7. Click **Apply**.
8. Click on the **User Principal** node to see the users in the data grid.
9. Click on the **Resource Access** node to see the **Privilege** and **Privilege Category**.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/latest/docs/reporting-dashboard).

### Over-Privileged Users and Most Active Users

Securiti as part of its Activity Analysis functionality, provides visibility into Over-privileged Users and Most Active Users.

Over-privileged users are those with access to data they have not used within a defined time period. This allows your security and IAM teams to minimize unnecessary user access, thereby reducing security risk.

Most Active Users are accounts that perform the highest number of actions within a given period.

#### Prerequisites

To view the Over-privileged Users and Most Active Users data, you must be licensed for this functionality and configure and perform activity analysis scans for your data systems of interest.

To configure the Activity Analysis for Starburst as an example, see [Configuring Access Intelligence Activity Analysis](/latest/docs/starburst#activity-analysis).

#### Viewing the Over-Privileged Users Data

To view the Over-Privileged users data:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu bar, click **Activity Analysis** icon. Choose **Over-Privileged Users**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(34).png)
3. From the filters available at the top, click on **Date Range**. Select the timeframe during which you want to identify users who have not used the access to which they are entitled, e.g., **Last 7 days**. Then, click **Apply**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(26).png)

You can also see the count of Databases, Database Schemas, and Tables these users have access to.

> [!NOTE]
> **Note**
> 
> The Most Active Users page displays the action count for both the View and the underlying Table.

For any user account, click the **View Metadata** button to see details of the Databases, Schemas, and Tables the user has access to but has not utilized.

![DAG_Overprovisioned_users_ViewMetadata.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac63d3a1-c046-4001-1e49-803a3ea1209b.png)

You can also apply Filters based on User Accounts, Databases, Database Schemas, and Tables.

### Viewing the Most Active Users Data

To view the Most Active users data:

1. In Securiti, open Data Access Governance.
2. From the left navigation menu bar, click **Activity Analysis** icon. Choose **Most Active Users**.
3. Near the upper right corner of the page, click **Most Active Users**. This will open the Most Active Users page.
4. You can see the list of Most Active Users displayed on the grid. You can also see the number of **Users** and total number of **Actions** performed by these users i.e **Total Privilege**s. For each user, you can see the count for the **Total Privileges**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(13).png)

#### Identifying the Most Active Users in a specified time

To identify the Most Active Users in a specified time:

1. On the **Most Active Users** page, click the **Date Range** filters available at the top. Select the timeframe for which you want to identify which users have performed the most actions (e.g., Last 7 days), and click **Apply**. This will show you the list of most active users in the specified timeframe.
2. For any user displayed on the grid, click **Metadata Explorer** to see the Databases, Schemas, and Tables on which the selected user has performed the **Actions**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(12).png)

> [!NOTE]
> **Note**
> 
> The Over-provisioned Users feature treats activity on a view as activity on the underlying table. If a user has access to the table but only queries the view (and never directly queries the table), they will not be considered over-provisioned.

#### Searching for the Number of Actions Performed by a Specific User in a Specified Timeframe

You can also search for the number of past actions performed by the specific users you identified as most active. This lets you identify the timeframe in which a specific user has performed the most actions. To search for Actions performed by a specific user in specified time:

1. Click the **User Account** filter. Select “**is one of**” operator and select the user. You can also type the name for user. Click **Apply**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(12).png)
2. Click the **Date Range** filter. Select the timeframe e.g., **Last 365 days**. Click **Apply**.

The Data Command Graph provides a graphical view of important information and the relationships between data systems after connecting to cloud accounts. It shows the discovered assets across your cloud accounts, covering both IaaS and SaaS platforms, and helps you understand how your data systems, assets, and resources are interconnected, supporting better visibility, governance, and risk management.
