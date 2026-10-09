---
title: "Creating an Automation policy"
slug: "creating-an-automation-policy-for-query-type"
updated: 2026-09-23T13:16:59Z
published: 2026-09-23T13:16:59Z
canonical: "helpcenter.securiti.ai/creating-an-automation-policy-for-query-type"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating an Automation policy

To create an Automation policy:

1. From the upper-left corner, click the **Jewel** icon to open the main menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SJ631CK2.png)
2. From the main menu, choose **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-860I99IQ.png)
3. On the **Policies** page, choose **Automation**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TD53BIV7.png)
4. Near the upper-right corner of the page, click **+ Create**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8A419PPZ.png)
5. Enter a **Name** and **Description** for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-X04FCT4Q.png)
6. Set the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I6K9K462.png)
7. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OQJGY1PF.png)
8. (Optional) Add tags relevant to the policy, as shown below. Tags are string values that help you identify the purpose of a policy at a glance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FNUVSGOL.png)
9. Enable the **Activate Policy** toggle to run the policy immediately after creation, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-001WGMZO.png)

> [!NOTE]
> **Note**
> 
> If you leave **Activate Policy** off, Securiti creates the policy and saves its scope, but the policy remains inactive. The policy does not search for matches or generate work items until you enable it.
10. In the **Automation Policy Type** section, choose one of the following policy types:

| Automation Policy Type | Description |
| --- | --- |
| Entity | The **Entity** type lets you turn findings from File Insights, File Quarantine, File ROT, Security Posture, Structured Data, and Test Findings policies into work items. Securiti creates one work item for each entity or group of entities when you configure grouping attributes. |
| Query | The **Query** type lets you turn rows from an existing dashboard widget or saved view into work items. Securiti creates one work item for every row returned by the selected dashboard widget or saved view. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YGFVTSFY.png)

### Configuring an Entity type Automation policy

To configure an Entity type Automation policy:

### Configuring a Query type Automation policy

> [!NOTE]
> Note
> 
> Securiti supports all data-grid widgets, but supports only aggregated saved views. Non-aggregated or non-tabular widgets whose parent node is one of the following do not appear as selectable options:
> 
> - File
> - Column
> - Structured Finding

To configure a Query type Automation policy:

#### Selecting a Dashboard Widget

#### Selecting a Saved View
  1. In the **Automation Policy Type** section, select **Entity**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TU5TBF0S.png)
  2. In the **Entity Type** section, select an entity type and, where applicable, the grouping attributes for the policy. The following table lists the supported grouping attributes:

| Grouping Attributes | Description | Entity Type | Mandatory/Optional |
| --- | --- | --- | --- |
| Asset Name | The **Asset Name** grouping attribute lets you group findings by data asset. When you group findings by Asset Name, Securiti creates one ticket for all findings associated with the same asset. For example, if a File Insights policy identifies 500 sensitive files across four Amazon S3 buckets, Securiti creates four tickets, one for each bucket, and each ticket includes only the files identified in that bucket. | - File Insights - File Quarantine - File ROT | Optional |
| File Owner | The **File Owner** grouping attribute lets you group findings by file owner. When you group findings by File Owner, Securiti creates one ticket for all findings associated with the same file owner. For example, if a File ROT policy identifies 80 obsolete files owned by 12 employees across multiple drives, Securiti creates 12 tickets, one for each file owner, and each ticket includes only the files owned by that person. | Optional |
| Securiti Tag Category | The Securiti **Tag Category** grouping attribute lets you group findings by the tag values within a selected Securiti tag category. When you group findings by Securiti **Tag Category** Securiti creates one ticket for all findings associated with the same tag value. For example, if files have different **Data System Owner** tag values, Securiti creates one ticket for each unique Data System Owner value, and each ticket includes only the files associated with that value. | Optional |
| Cloud Asset | The **Cloud Asset** grouping attribute lets you group findings by cloud asset. When you group findings by Cloud Asset, Securiti creates one ticket for all findings associated with the same cloud asset. For example, if a Security Posture policy identifies 15 misconfigurations across three Amazon Redshift clusters, Securiti creates three tickets, one for each cluster, and each ticket includes only the findings associated with that cluster. | - Security Posture Finding - Test Finding | Optional |
| Rule | The **Rule** grouping attribute lets you group findings by the rule associated with them. When you group findings by Rule, Securiti creates one ticket for all findings associated with the same rule. For example, if the `Encryption at rest must be enabled` rule identifies violations across 40 resources, Securiti creates one ticket that includes all 40 findings associated with that rule. | Security Posture Finding | Optional |
| Data Asset | The **Data Asset** grouping attribute lets you group Structured Data findings by data asset. When you group findings by Data Asset, Securiti creates one ticket for all findings associated with the same data asset. For example, if a Structured Data Insights policy identifies U.S. Social Security Numbers across three databases, Securiti creates three tickets, one for each database, and each ticket includes only the findings associated with that database. | Structured Data Finding | Mandatory |
| Table | The **Table** grouping attribute lets you group Structured Data findings by table within a data asset. When you group findings by Table, Securiti creates one ticket for all findings associated with the same table. For example, if a data asset contains Social Security Number findings in the `customers`, `legacy_orders`, and `support_tickets` tables, Securiti creates three tickets, one for each table, and each ticket includes only the findings associated with that table. | Optional |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BB6ECWDC.png)

> [!NOTE]
> Note
> 
> - You can group entities by up to two grouping attributes.
> - Securiti creates one ticket for each finding by default. Grouping attributes help reduce the number of work items when the policy scopes a large number of findings.
> - For File Insights, File Quarantine, and File ROT, the policy definition provides the scope. These policies do not generate findings themselves. The Automation policy acts on the scoped files and can group them by the following attributes:
>   - Asset Name
>   - File Owner
>   - Securiti Tag Category
> - For example, if 100 files are in scope and grouping by **Asset Name** divides them into two groups, Securiti creates two work items instead of 100.
> - Security Command Center is supported only when you select the **Asset Name** grouping attribute for File Insights.
  3. If you select Securiti **Tag Category** as a grouping attribute, in the **Select** Securiti **Tag Category** section, select the tag category to use for grouping, as shown below. The **Values** column displays the tag values associated with the selected tag category for reference. At runtime, Securiti groups files by their corresponding tag values.

> [!WARNING]
> Important
> 
> The **Select Tag** section is available only when you select Securiti **Tag Category** as a grouping attribute for the File Insights, File Quarantine, or File ROT entity type.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9YA1PPUW.png)
    1. Click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4W35ZIRL.png)

> [!NOTE]
> Note
> 
> - Securiti creates a separate work item for each unique tag value associated with the files in scope. If a file has multiple values for the selected tag category, the file can belong to multiple groups, and Securiti creates a separate work item for each applicable tag value.
> - If files do not have a value for the selected tag category, Securiti groups those files into a separate work item and assigns the work item to the Automation policy owner. This ensures that files without the selected tag value remain visible for remediation.
  4. In the **Scope Rule** section, click **Edit Query** to define the policy scope. This opens Graph Explorer, where you can build a query to select the files you want the policy to evaluate. Review the query results to verify that the selected files match your requirements, and then click **Use Query** to apply the query. For more information, see [Graph Explorer](/latest/docs/using-graph-explorer) and [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DLAH3R8M.png)

> [!NOTE]
> Note
> 
> When you scope File Insights, File Quarantine, or File ROT policies in an Automation policy, Securiti applies an `Active=True` filter to the scope query by default. This filter ensures that the scope includes only active policies.
    - In this example, 173 files match the defined query criteria, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YOZ976JU.png)

> [!WARNING]
> Important
> 
> - For file-based tickets, the **File URL** in the ticket opens the Data Remediation dashboard instead of Graph Explorer.
> - The relevant posture, compliance test, or file findings must already exist so that Graph Explorer can retrieve them when you define the scope. For more information, see [Graph Explorer documentation](/latest/docs/using-graph-explorer).
> - Securiti can automatically carry over a query that you built in Graph Explorer to the policy creation page. For more information, see [Create policies using graph](/latest/docs/create-policies-using-graph).
  1. In the **Automation Policy Type** section, select **Query**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PMF8JH0H.png)
  2. In the **Query** section, click the plus (+) icon next to **Select Query** to open the **Select Query for Automation Policy** panel, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FHD8LX92.png)
  3. In the **Select Query for Automation Policy** panel, select **Dashboard Widget** or **Saved View** as the source, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OT2I1BTY.png)
  1. Select a dashboard from the **Select Dashboard** menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-UGSJDTQE.png) b. Under **Select Widget**, search for or choose the desired widget, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FX206MD9.png) c. Click **Select**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NNXHEPI3.png)
  1. Select a group from the **Select Group** menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-E2AGX3UD.png) b. Under **Select View**, search for or choose the desired saved view, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4LA1NONQ.png) c. Click **Select**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AX324OP7.png)

> [!NOTE]
> **Note**
> 
> Securiti creates one work item for every row returned by the selected dashboard widget or saved view. For example, if a dashboard widget returns 48 rows, Securiti creates 48 Jira or ServiceNow tickets.
11. Click **+ Add Actions** to define the actions that Securiti performs on the work items generated by the policy. You can add the following actions:

> [!NOTE]
> Note
> 
> You can add either a **ServiceNow** or a **Jira Cloud** action to a policy at a time.

### Creating a ServiceNow task

### Creating a Jira Cloud ticket

### Generating a finding in Security Command Center

### Sending an email notification
  - ServiceNow
  - Jira Cloud
  - Security Command Center
  - Email
  1. Select **ServiceNow Instance > Create Task**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GPNKAOJ9.png)
  2. In the **Ticket Details** section, select a table from the **Table Name** menu, as shown below. Securiti retrieves the available tables from your ServiceNow data system account.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-QI9LP8MG.png)
  3. Add a **Description** manually, or click **Insert Variable +** to insert a bind variable, as shown below. A bind variable is a placeholder that Securiti replaces with its corresponding value when it creates the ticket. Some bind variables depend on the selected grouping attribute. For example, a tag-based variable is available only when you group file-based entities by Securiti **Tag Category.**

> [!WARNING]
> Important
> 
> The **Description** is truncated if it exceeds 255 characters after variable substitution.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KZ7MHWTL.png)
  4. By default, the **Active** toggle is enabled to activate the task, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HR5S7NVN.png)
  5. (Optional) In the **Assignee** field, specify an assignee manually, or click **Insert Variable +** to use an available bind variable, as shown below. When you group file-based entities by Securiti **Tag Category**, you can select **Tag: [Tag Category]** to use the corresponding tag value as the assignee. Securiti resolves the tag value when it creates the task.

> [!WARNING]
> Important
> 
> The tag value used as an **Assignee** must be a valid email address and must resolve to a valid user in ServiceNow. If the tag value is missing, invalid, or cannot be resolved, Securiti assigns the task to the Automation policy owner.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5DAWHLSC.png)
  6. Add a **Description** manually, or click **Insert Variable +** to insert a bind variable, as shown below.

> [!WARNING]
> Important
> 
> The **Description** is truncated if it exceeds 4000 characters after variable substitution.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XJSXMCRC.png)
  7. (Optional) Select one of the following **Priority**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TR48U8G8.png)
    - Critical
    - High
    - Moderate
    - Low
    - Planning
  8. (Optional) Enable the **Attach files as CSV** toggle to attach file details to the ticket as a CSV file, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7H918CCS.png)
  9. (Optional) Add **Custom Fields**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-E3PRB1GM.png)
  10. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T967FQ6V.png)
  1. Select **Jira Instance > Create Ticket**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U0Y8BWCI.png)
  2. In the **Project Information** section, select a **Project Key**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HBI09B46.png)
  3. Select one of the following **Issue Types**, as shown below.
    - Bug
    - Epic
    - Issue
    - Story
    - Subtask

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-67ZEMDCW.png)
  4. In the **Ticket Details** section, add a **Summary**, as shown below.

> [!WARNING]
> Important
> 
> The **Summary** is truncated if it exceeds 255 characters after variable substitution.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2F4F3I93.png)
  5. (Optional) Add a **Description** manually, or click **Insert Variable +** to insert a bind variable, as shown below. A bind variable is a placeholder that Securiti replaces with its corresponding value when it creates the ticket. Some bind variables depend on the selected grouping attribute. For example, a tag-based variable is available only when you group the file-based entities by Securiti **Tag Category.**

> [!WARNING]
> Important
> 
> The **Description** is truncated if it exceeds 255 characters after variable substitution.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RDZQG5GX.png)
  6. (Optional) Enable the **Attach files as CSV** toggle to to attach file details to the ticket as a CSV file, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Z3AT51K5.png)
  7. (Optional) In the **Labels** section, select one or more labels, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VFFF2UJB.png)
  8. (Optional) In the **Assignee** field, specify an assignee manually, or click **Insert Variable +** to use an available bind variable, as shown below. When you group file-based entities by Securiti **Tag Category**, you can select **Tag: [Tag Category]** to use the corresponding tag value as the assignee. Securiti resolves the tag value when it creates the task.

> [!WARNING]
> Important
> 
> - The tag value used as an **Assignee** must be a valid email address and must resolve to a valid user in Jira. If the tag value is missing, invalid, or cannot be resolved, Securiti assigns the ticket to the Automation policy owner.
> - The email address associated with the Jira user account must be visible to **Anyone** in the Jira profile settings, as shown below. This lets Securiti identify the corresponding Jira user and assign the ticket to that user.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IS93SH90.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FB36QYGO.png)
  9. Select one of the following **Priority**, as shown below.
    - Highest
    - High
    - Medium
    - Low
    - Lowest
    1. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MH8JS2A9.png)
  10. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M4WYAK39.png)
  1. Select **Security Command Center** instance > **Generate Finding**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RV598513.png)
  1. Select **Email**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WOKU1NGD.png)
  2. To notify specific users, enter their username or email address in the search field and select them from the list. Each selected user appears as a tag below the field, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L7TMQSXS.png)
    1. For file-based entities grouped by Securiti **Tag Category**, you can select **Tag: [Tag Category]** as the recipient. Securiti uses the tag value associated with each group to send the email notification to the corresponding stakeholder. If a file has multiple valid email values for the selected tag category, Securiti sends notifications for the corresponding tag-value groups.

> [!WARNING]
> Important
> 
> The tag value used as a **Recipient** must be a valid email address. If the tag value is missing or invalid, Securiti sends the email notification to the Automation policy owner.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YFITC758.png)
  3. Select an **Email notification template**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XJGO3RKY.png)
  4. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GB2MWPLL.png)
12. Click **Create Policy**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GH6SBLM8.png)
  - After you create the policy, Securiti polls ServiceNow and Jira every 24 hours for changes to generated work items. When Securiti detects a change, it updates the following metadata on the Automation **Policies** page:

For example, if you create an Automation policy at 1 PM, Securiti checks for ticket changes at approximately 1 PM the following day.
    - Updated
    - Summary
    - Priority
    - Ticket owner

## Viewing tickets in ServiceNow and Jira

1. On the Automation **Policies** page, expand the policy to view the ServiceNow or Jira tickets that the policy creates, as shown below.

> [!NOTE]
> Note
> 
> ServiceNow and Jira tickets can take some time to appear. The time required depends on the number of tickets that the policy creates.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4EAAOD5R.png)
2. Click the **Ticket Number** link, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OD0UJNRO.png)
  - Securiti redirects you to the corresponding ServiceNow or Jira account, where you can review the ticket details, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FPBDB5X8.png)

## Viewing findings in Google Cloud Security Command Center

> [!NOTE]
> Note
> 
> - The following finding types appear in Security Command Center (SCC):
>   - Security Posture Findings
>   - Structured Data Findings
>   - Test Findings
> - Security Command Center (SCC) support for File Insights requires the **Asset Name** grouping attribute.

1. On the Automation **Policies** page, expand the policy to view the finding that the policy creates, as shown below. Findings in Google Cloud Security Command Center can take some time to appear.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7Z5II6QJ.png)
2. Click the **Ticket Number** link, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BQ91AGOJ.png)
  - Securiti redirects you to the Google Cloud Security Command Center homepage, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 7.32.19 PM.png)
3. In the Google Cloud Security Command Center console, click **Select a project**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(940).png)
4. Select **All**, and then select the project whose ID matches the connector instance configured in Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(941).png)
  - You can review the corresponding findings, including their summary, source properties, and JSON details, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(943).png)
5. In the **Affected Resource** section, expand **Resource Full Name**, and then click **View Asset Details** to open the relevant connector platform, such as Amazon S3, and review the finding in more detail, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(942).png)
