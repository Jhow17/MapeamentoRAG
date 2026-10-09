---
title: "Google BigQuery"
slug: "google-bigquery"
updated: 2026-09-24T08:01:56Z
published: 2026-09-24T08:01:56Z
canonical: "helpcenter.securiti.ai/google-bigquery"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Google BigQuery

This section describes the Data Access Governance features supported for Google BigQuery and the steps to configure these functionalities.

### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Google BigQuery:

#### Access Intelligence

- Privilege Analysis - Not Supported
- Activity Analysis - Not Supported

#### Access Control

- Column Masking Properties
- Row Filtering Properties
- Permissions Management Properties - Tables and Column level permission management

#### Cross Border Transfer Policies

- Supported (Based on Data Location)

#### Example Supported Use Cases

The supported example use cases include:

#### Access Control

For your Google BigQuery users, Groups, Domains and Service accounts, you can:

- Allow or Deny the access to columns by applying **Fine-Grained Reader Role** to principals
- Define masking rules on columns by applying **Masked Reader** Role to principals
- Restrict access to rows by configuring row level filters on tables for principals

### Configuring Google BigQuery Data Access Governance

This section describes the configuration process for Data Access Governance feature sets for Google BigQuery.

#### Configuring Cross Border Data Transfer Policies for Google BigQuery

Cross-border data transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows. Cross-border transfer policies can be used to incorporate a wide range of embedded global regulatory insights, enabling the analysis of data access scenarios that might result in compliance breaches. Automated data mapping determines the location, type, and access point of data, while the policy engine cross-references this information with relevant regulations. If a violation is detected, such as personal data stored in Germany being accessed from Singapore, the system issues an alert and initiates corrective actions.

Supported Data Access Governance Feature Sets

The following Cross Border Transfer Policy type is supported for Google BigQuery:

- Cross Border Transfer Policies Based on the **Data Location** (Supported for Google BigQuery as a structured data system)
- Cross Border Transfer Policies Based on the **Data Access Location** (Not Supported).

> [!NOTE]
> Note
> 
> If Data Access Governance features for Google BigQuery are not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

**Prerequisites for Cross Border Transfer Policies based on Data Location**

To get Cross Border Transfer alerts and recommendations based on the Data Location, you must:

- Set up a [Securiti pod or elastic pod](/latest/docs/podcustom-installation-guides).
- Configure and [activate the Google BigQuery connector](/latest/docs/google-bigquery-connectors).
- Perform a [discovery scan for your Google BigQuery connector instance](/latest/docs/configure-discovery-scans-in-google-bigquery).
- Define Data Subject Types, e.g. employees, job applicants, prospects, partners, etc. for the Google BigQuery asset in the data mapping automation module.
- Define an Institute in the data mapping automation module. Specify the Primary Covered Entities e.g., Educational Institutions, Medical Industry, and Secondary Covered Entities e.g., Public Universities, Healthcare Providers, etc.

**Viewing Cross-Border Transfer Findings**

Cross-border transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows.

To view the Cross Border Transfer findings:

- In Securiti, near the upper left corner, click the jewel icon, and choose Findings.
- From the left panel, choose Cross Border Transfer.

You can view the following on the Cross Border Transfer Findings page:

- **Open Findings** : A newly detected finding that requires attention.
- **Suppressed** : A finding that has been manually acknowledged but intentionally ignored.
- **Fixed** : A finding that has been addressed or no longer applies. ![Overview of findings related to cross-border data transfers and compliance status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (13).png)
- You can view counts for **Open, Fixed,** and **Suppressed findings**, with their trendlines based on the past week to 12 months.
- You can view the counts for **Total Findings** and **Open Findings**.

The Group by button gives three grouping attribute options: Policy, Data Source, and Regulations.

Below the widgets, there is a search bar to sort the findings based on the Policy, Data System, or Asset. Click + to filter the Findings based on Asset Name, Data System Type, Finding Name, Finding ID, Policy, Regulations, or Status.

You can suppress the Findings and change the assignee for a particular Finding. To suppress a Finding or change its assignee, select the Finding, and click the Suppress Finding button. The status of the finding will be changed to Suppressed. To change the assignee, select the finding, click the Change Assignee button, and select the user in the popup to which you must assign the finding.

![Overview of findings related to cross-border data transfers and compliance status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (16).png)

For each Finding, you can view the Evidence related to the potential violation. To view the evidence related to a Finding, click View Evidence in the Evidence column in the grid.

**Managing Cross Border Transfer Policies**

You can manage the out-of-the-box policies to:

- View the out-of-the-box policies and details associated with them such as Regulation, Cross Border Type, Responses, etc.
- Activate or Deactivate the policies.
- Edit the policies to change the Response of the policies.

To access the out-of-the-box Cross Border Transfer Policies, click Manage Policies on the Cross Border Transfer Findings page, or in Securiti, near the upper left corner, click the jewel icon, choose Policies, and from the left panel choose Cross Border Transfer

**Filtering the Cross Border Transfer Policies**

You can sort and filter the Cross Border Transfer Policies based on the following properties: Cross Border Type, Date Created, Date Modified, Policy ID, Regulation, Policy Name, and Status.

**Editing the Cross Border Transfer Policies**

You can Edit the Responses of out-of-the-box Cross Border Transfer Policies to configure the actions that Securiti will trigger if any potential violation occurs. You can define the response actions as per your organisation's workflows such as alerting the Data Governance Officers if sensitive data is accessed outside the regulatory jurisdiction in which your business is operating.

![Overview of policies related to cross border data transfer and compliance regulations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (17).png)

- To edit the policy, at the right end of its tile choose (⋮) and click **Edit**.
- In the Responses section, the Generate Findings toggle is already enabled. Choose the relevant severity level ranging from Very High, Medium to Very Low.
- You can set the severity of the Cross Border Transfer Findings as per your requirements, and Findings are generated whenever a policy violation is detected.
- Optionally, configure email notifications for specific users by enabling the toggle in the Send an Email Notification area, selecting the email addresses, the email template, and specifying the Notification Limit.
- Optionally, enable the Trigger Workflow toggle to trigger a workflow for a file insights policy. Near the upper right corner of the page, click Update. ![Settings for generating findings and email notifications in a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (18).png)

#### Interactive Demo

To see these steps in action, watch the video below:

[Embedded content](https://app.storylane.io/demo/d2oemaw49ygy?embed=inline)

#### Creating data access control policies for Google BigQuery (Self-Hosted)

This access control policy type lets you grant granular permissions to your Google BigQuery Tables and Columns.

#### Prerequisites

To create a data access control policy for Google BigQuery (self-hosted) you must:

- [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/v1/docs/managing-data-system-connectors).
- Note that the user service account you use to configure the connector must have the following permissions/roles:
  - Big Query Admin
  - Big Query Data Owner
  - Policy Tag Admin
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Access** **Permissions** tab, so that this data system is available for selection when you create the policy.

![Settings page for BigQuery GCP with options for data access control and permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bigquery.png)
- Mark the checkbox for the **Enable Database Column Masking Policy**. When enabled and saved, the **Sync Masking Policy** option appears, which syncs masking policies from Google BigQuery to Securiti.
- Enable the BigQueryDataPolicy API for the target project.
- Enable Google Cloud Data Catalog API for the target project.
- Perform a discovery scan for the Google BigQuery instance. Note that the dataset you want to scan must not contain policy tags applied on the columns as well as any existing row filter policies on tables.

#### Creating data access control policies

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage **Data Access Governance** policies.
3. Near the upper right corner of the page, click **Create Policy**.
4. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Google BigQuery**.
  3. (Optional) Choose a template for the policy.
  4. Click **Get Started**.
5. Enter a name for the policy.
6. (Optional) Add a description for the policy.
7. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.
  1. From the **Actions** column, click on the graph icon to add the scope. Once you click the graph icon, the Graph Explorer window opens. You are presented with a blank canvas where you can begin defining your graph search criteria in the following ways:
    - By clicking the **+** sign in the upper left corner of the upper row of the dashboard.
    - By clicking the **Begin Your Search** button at the center.
    - By loading an existing filter from **Saved Views** from the upper right corner of the page
  2. Click + or the Begin Your Search button at the center of the page. The filter menu has three panels as described below:

| Panel | Description |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
  3. From the center panel, click on the **Column** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node.
  4. After selecting the property, you can choose the operator to select what criteria to match on from the menu. Select the **contains** operator, and type the value as **Google BigQuery**. You can also search **Google BigQuery** in the search bar to filter the databases.
  5. Select the database from the data grid on which you must apply the policy.
  6. Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  7. You can also see the policies that has same data objects in the data scope of the current policy. The access rules of the current and other overlapping policies will be aggregated and pushed as a single access rule to the data system.
8. In the **Access Rules** area, click **+ Add a Privilege Rule** to add a rule. **In the Add a Privilege Rule window**:
  1. Provide the Rule Name.
  2. (Optional) Add description.
  3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the access rule is applied. You can select Roles as Principals.
  4. You can select one of these as Principal:
    - Users
    - Groups
    - GCP domains
    - GCP Service Accounts
  5. You must select at least one principal type to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the Users area, select the users from the menu. You can also add the users using the menu or use Graph Query button. You must also select the GCP Role as Principal, and assign the **Fine-Grained Reader** role.
  6. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Select **ALL PRIVILEGES** option. Note that the Principals that you select for granting the privileges would be assigned the role of Fine Grained Reader and able to see the **Column** selected in the scope. The principals that do not have the Role would not be able to access the column (Read or Write) and will be displayed a "Access Denied" error.
  7. Click the **Create Rule** button to add an access rule.
  8. If you have selected the **Tables** in the **Data Scope**, you can define filtering rules to configure row-level filtering conditions for the Principals. To add a filtering rule:
    - In the **Access Rules** area, click on the **Filtering tab**.
    - Click on the **+ Add a filtering Rule** button to add the rule.
    - In the **Add a Filtering Rule** window, provide the **Rule Name**.
    - (Optional) Add the description.
    - In the **Principals** area, click **+ Add a Principal** to add the Principals as shown above.
    - In the **Row Filtering Condition**, select the filtering condition. You can select the **General Filtering** conditions such as **Include all rows** and **filter out all rows** or **Advanced Filtering** condition such as **Conditional filtering**. The **Include all rows** condition provides access to all the rows to the selected principals. The **Filter out all rows** condition restricts access to all the rows.
  9. If you have selected **Conditional filtering,** you must specify the condition based on **Column by Name** or **Column by Element**.

Click **Add a Filtering Rule** button to add multiple filtering rules.
    - From the **Return rows where** area, click on the + Icon. To add a condition based on the column name, select the **Column By Name** option. Type the column name such as City in the middle panel. Select the operator value from the right panel. You can select the **Constant** option. Once you have selected the Constant, you must provide the value of the Constant. For Example, for the column name ‘City’ you have selected, you provide ‘’Los Angeles’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principal will have access to all the rows in the table for which the value of the column name ‘City’ is ‘’Los Angeles’’.
    - To add a condition based on the data elements, select the **Column By Element** option. Select the data element such as the Email address in the middle panel. Note that the data elements must be discovered in the discovery scan. Select the operator value from the right panel. Select the **Constant** option. Once you have selected the Constant option, you must provide the value of the Constant. For Example, for the data element ‘Email Address’’ you have selected, you provide ’'jane@example.com', and 'michael@example.com’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principals will have access to all the rows in the table for which the values of the column ‘Email Address’ are ‘’jane@example.com'’ or 'michael@example.com’’.
    - Click the **Create Rule** button. You can add multiple conditions separated by ‘**AND**’ and ‘**OR**’ operators.
  10. If you have selected the **Column** in Data scope, you must configure the masking rule to create an access control policy. To configure a masking rule:
    - Click on the **+ Add a Masking Rule** button to add the rule.
    - Enter the **Rule Name**.
    - (Optional) Add description.
    - In the **Principals** area, click **+ Add a Principal**. You can select one of these as Principal:
      - Users
      - Groups
      - GCP Roles
      - GCP domains
      - GCP Service Accounts
    - You must select at least one Principal type to create a masking rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the **Users** area, select the users from the menu. You can also add the users using the or use Graph Query button. You must also select the **GCP Role** as Principal, and assign the **Masked Reader** role to the user for which you must mask the selected column data. The users with the **Fine-Grained Reader** role assigned will be able to see all the data.
    - In the **Masking Behaviour** area, you must configure the type of masking to mask the selected columns to only the specified principals.

> [!NOTE]
> **Note**
> 
> Note that if you apply a built-in masking function on a column that does not contain values of the specific type that the masking function is expecting, the masking will fall back onto Hash (SHA-256). For example if you apply Email masking on a Column containing dates, the masked values shown will be in Hash (SHA-256).
      - If you have selected the **Custom Value** option, you must provide the value by which data will be masked. For example, if you have entered “**##**” as the **Custom Value**, and selected the email column in the **Data Scope**, the values of the email column will be masked for the specified Principal.
      - You can also use built-in masking functions such as Hash (SHA-256), Default Masking etc. To use the built-in masking functions, select the Built-In Masking Function option from the menu. And select the type of masking you want to apply from the Built-In Masking Function option. You can select the following masking functions:

| Masking Function | Description |
| --- | --- |
| Default Masking | The uppercase alphabets are replaced with ‘N’. Lowercase alphabets are replaced with the ‘n’. Integers are replaced with 0. Special characters are replaced with X. |
| Email Masking | The data system selected while creating the policy. |
| First Four | The first four characters will be displayed, and the remaining part of the string will be masked by *. |
| Last Four | The last four characters will be displayed, and the remaining part of the string will be masked by *. |
| Hash (SHA-256) | This replaces the characters with the random 256 bits string (16 characters). |
| Nullify | Nullifies the value. |
| Date year mask | The year in the date will be masked. For example in the date 11-03-2023, ‘2023’ will be masked (11-03-####) |
      - You can also apply **Advanced Masking** such as **Masking Functions**, and use the **Expression Builder** to define conditions. You can define masking behavior if the expression returns a **True** value and which type of masking must be applied **if** the expression returns a false value. Note that these masking functions are the custom masking functions that you configure in Google BigQuery.
      - Click the **Create Rule** button.
9. Activate the **Enable policy after saving** toggle. When activated, the policy will be enforced as soon as the policy information is saved.
10. Click the **Create Policy** button to create the policy.

#### Access Policy Preview and Backup

You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. For each of the policy, that you create, update, or delete, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. These controls let you enforce the data access control policies on your data systems in a secure manner, ensuring that you realize the impact of the policies before enforcement.

#### Policy Preview

When you click **Create Policy** button, the **Policy Preview** will be generated. Policy Preview presents you with the entities such as Databases, Tables, Columns, etc. and privileges, row filters, and masking functions that will be implemented upon successful enforcement of the policy. Note that the policy execution will start only if you **Accept** the Policy Preview.

![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(1).png)

> [!NOTE]
> **Note**
> 
> No backup will be created in the case of preview being rejected in policy creation.

If you accept the **Policy Preview**, the backup of the policy will be automatically generated and you can access it via **Backups** page. Securiti also generates Policy Preview and Backup when you update or delete the access control policies.

![Overview of backup systems with statuses and details for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/backup1.png)

#### Backups

This section describes the configurations steps for creating a policy Backup manually and restoring a Backup.

#### Creating a Policy Backup manually

To create a Policy Backup:

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage **Data Access Governance** policies.
3. Near the upper right corner of the page, click three dots and select **Backups**.

![Overview of policy types with a focus on Data Access Control and its details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.49.50 PM (2)(2).png)
4. Near the right corner of the page, click **Manual Backup**.
5. On the **Manual Backup** popup, enter the following information
  1. Add **Backup Name** to suit.

![DAG_BigQuery_Backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1cb54c28-1bd8-0de4-dd28-dd915935b629.png)
  2. Select the data system from the **Data System Type** menu.
  3. From the **Data System** menu, select the Data System instance.
  4. Click, **Create Backup** button.

#### Restoring a Policy Backup

To restore a Policy Backup:

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage **Data Access Governance** policies.
3. Near the upper right corner of the page, click three dots and select **Backups**.

![Overview of policy types with a focus on Data Access Control and its details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.49.50 PM (2)(2).png)
4. Near the right corner of the user row, click Options (three dots) > **View Backup**.

![Backup management interface showing various backup statuses and data systems available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/backup options.png)
5. The Backup Policy page will show you the privileges, row filters, and masking functions and entities, included in the backup, when this backup was taken.
6. Near the upper right corner of the page, click the **Restore Backup** button If you want to revert the current state of the data system and restore the data system to the state when this backup was created.

![Restore_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45fb49e9-de41-3f4b-8ef4-9479afa25bd5(1).png)
7. Click the **Restore Backup** button on the confirmation popup to restore the backup. The policies for that particular data system that were not included in the backup that you want to restore to, will be deactivated from the Policies page.

#### Policy Backup upon policy deletion

If you delete an active policy, the Policy Preview will be generated. Securiti will not delete the policy instantly, the policy will only delete the policy once you Accept the Preview for deletion.

![Delete_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ccb4fc06-6f52-0d86-0158-170d241ce2a1(1).png)![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(1).png)

Once you **Accept** the **Policy Preview**, the execution will start, and the policy will be deleted from the **Policies** page. Securiti automatically takes the backup for the policy. In the Backup Preview, you will not see any privilege rules, row filters, and masking applied on entities affected by the deleted policy, as there are no active privileges, filters, and masking conditions defined on these entities currently.

#### Interactive Demo

To see these steps in action, watch the video below:

[Embedded content](https://app.storylane.io/demo/2moo0obwzwdn?embed=inline)
