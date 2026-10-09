---
title: "Using Activity Explorer"
slug: "using-activity-explorer"
updated: 2026-09-23T02:27:30Z
published: 2026-09-23T02:27:30Z
canonical: "helpcenter.securiti.ai/using-activity-explorer"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Using Activity Explorer

## Overview

**Activity Explorer** is the **Activity Analysis** dashboard in Data Access Governance that shows you what your users actually did with the data in your data systems. Securiti ingests activity logs from each connected data system and presents every recorded activity in a single data grid. From the grid, you can see who performed an action, which resource it was performed on, what type of action it was, and when it happened.

Use Activity Explorer to investigate specific user behavior, confirm how a data resource is being used, and build the evidence for removing access that is never exercised.

Activity Analysis surfaces this information through three views:

- **Activity Explorer**: every individual activity recorded against your data system resources.
- **Over-Privileged Users**: users who have access to data they have not used within a defined time period.
- **Most Active Users**: the accounts that perform the highest number of actions within a given period.

### Prerequisites

To view **Activity Explorer**, **Over-Privileged Users**, and **Most Active Users** data, you must:

- Be licensed for the Activity Analysis functionality.
- Configure and run activity analysis scans for the data systems you want to analyze.

> [!NOTE]
> Note
> 
> Activity Analysis support varies by data system. For the activities captured for a specific data system, see that data system's article under [Supported Data Systems for Data Access Governance](/latest/docs/supported-data-systems-for-data-access-governance).

To open Activity Explorer:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu bar, click the **Activity Analysis** icon, and choose **Activity Explorer**. The Activity Explorer page opens.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(14).png)
3. Review the data grid. Each row is a single activity recorded against a data system resource, with columns such as Type, Action, User, Resource, and Time.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(14).png)

### Filtering activities

The filter panel at the top of the Activity Explorer page lets you narrow the grid to the activities you care about. You can combine filters to answer a specific question, such as which users ran a DDL query against a given resource last week.

To filter the activities:

1. On the Activity Explorer page, click a filter in the panel at the top of the page. For example, click **User**.
2. Select the **is one of** operator, and then select or type the values you want to match.
3. Click **Apply**. The data grid refreshes to show only the matching activities.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(11).png)
4. Repeat these steps for each additional filter you want to apply. The grid reflects all applied filters together.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(6).png)

The filters available to you depend on the data system. Commonly available filters include:

- **Data System**: limits the grid to a specific data system connector instance.
- **User**: limits the grid to activities performed by specific user accounts.
- **Activity Action**: limits the grid to a specific action, such as Create, Drop, File Accessed, or Directory Accessed.
- **Type**: limits the grid to a query or activity type, such as DDL.
- **Resource**: limits the grid to activities performed on specific data resources.
- **Time**: limits the grid to activities recorded before or after a specified date and time.

> [!NOTE]
> Note
> 
> Activity Explorer records activity on a view as activity on the underlying table. An activity performed against a view therefore appears for both the view and the table it reads from.

### Viewing activity metadata

To see the full context of a single activity, click **View Metadata** on the right side of its row. The metadata panel shows details such as Type, Data system instance, Resource, PD Elements, and Client Country, which lets you confirm whether the activity touched sensitive or personal data and where it was performed from.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 11(4).png)

> [!NOTE]
> Note
> 
> Securiti purges Activity Analysis data in Activity Explorer after 1 year. Export any activity records you must retain for longer.

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

#### Viewing the Most Active Users Data

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
