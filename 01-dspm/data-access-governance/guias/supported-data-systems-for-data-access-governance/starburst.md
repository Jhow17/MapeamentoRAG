---
title: "Starburst"
slug: "starburst"
updated: 2026-09-25T10:57:08Z
published: 2026-09-25T10:57:08Z
canonical: "helpcenter.securiti.ai/starburst"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Starburst

This section describes the Data Access Governance features supported for Starburst and the steps to configure these functionalities.

#### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Starburst:

### Access Intelligence

- Privilege Analysis
  - Database, Schema, and Table permissions granularity
- Activity Analysis
  - Database, Schema, Table, and View level activities reporting

#### Access Control

- Column Masking Properties
- Row Filtering Properties
- Permissions Management Properties

#### Cross Border Transfer Policies

- Alerts and recommendations based on the Data Access Location and Data Location

> [!NOTE]
> Note
> 
> If Data Access Governance features for Starburst are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The supported example use cases include:

### Access Intelligence

- Identify and report on which Starburst Users have access to Databases and what their permissions are on those Databases
- Identify and report on which Starburst Users have access to Tables containing Sensitive Data and what their permissions are on those Tables
- Identify and report on which Starburst User Groups facilitate access to Databases and Tables containing sensitive data

### Activity Analysis

- Filter and report on users that have performed Create, Modify, Insert etc. actions on your Starburst resources
- Identify which type of SQL queries are being executed by your users on your Starburst resources such as Data Definition Language (DDL), Data Control Language, and Data Manipulation Language (DML)
- Identify and report the activities performed by a specific user on a specific data resource
- Filter and report the user activity based on the Data Resources
- Filter and report the user activity based on the IP addresses and Time

#### Configuring Starburst Data Access Governance

This section describes the configuration process of Data Access Governance features for Starburst

### Configuring Access Intelligence Privilege Analysis

To see the Starburst Access Intelligence information you must:

#### Prerequisites

To see the Starburst Access Intelligence information you must:

1. [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
2. [Configure and activate the connector](/v1/docs/activate-the-starburst-connector-in-securiti).
3. Perform a discovery scan on your Starburst instance.
4. You must be logged into the Securiti platform through an account that has admin role permissions for that cloud account and has all the privileges of the Starburst cloud infrastructure.

#### Configuring your Starburst Access Scans for Access Intelligence

To see the Starburst Access Intelligence information you must:

**1. Configure an IAM Metadata Source for your data system.**

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![DAG_IAM_Metadata_Sources.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eed5ccd0-db1f-8eba-5df1-31eb893adccb(2).png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Starburst Metadata Source.
  2. Select Apache Ranger in **Source Type**. You must add Apache Ranger as the metadata source if access controls are managed using the Ranger Admin Console.
    - If you have selected Apache Ranger in Source Type, then you must provide following parameters:

> [!NOTE]
> **Note**
> 
> Apache Ranger Metadata Source is a mandatory requirement and is necessary for the Access Scan Definition to be functional.
      1. Enter the **Pod Name**.
      2. Provide the **Apache Ranger Service Name**.
      3. Enter **URL to Ranger Admin**.
      4. Provide **Connection Timeout** in milliseconds.
  3. If you have selected **Starburst Activity Data - Web Integration UI** as a **Source Type**, then you must provide the Pod Name, URL, and Connection timeout etc. For more details on configuring the metadata source for Starburst Activity Data, see the Activity Analysis documentation.
  4. In the **Authentication Details** area, select the **Authentication Type**, based on the source and authentication type selected, enter details. For more information, see data system specific access intelligence documentation.
  5. Click Create **New IAM Metadata source**.

**2. Configure an Access Scan Definition for your data system**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select Starburst in the **Data System**.
  3. Specify the **Host** and **Port**.

![DAG_Starburst_CN_ASD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef96221c-4d1a-eb99-9dfc-8b307f8c4c0d.png)
  4. In the **IAM Metadata Sources**, select the metadata sources that you have created for a particular data system. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  5. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.

**3. Enable the Access Scan**

If you have not selected the associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan toggle on the Starburst Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

**4. Launching the Access Scan**

- On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
- Click the three dots option, and select the **Scan Now** option.

#### Using Access Intelligence with Starburst

Below are example use cases to familiarize you with how to leverage Securiti's Data Command Graph to identify access and risk in your Starburst tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identifying Starburst Users that have access to specific Databases and what their permissions are on those Databases.

To identify users that have access to specific Databases and their permissions:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Database**. Set the **Attribute** to the **Database Name**. Set the operator to the **Equals**.

![DAG_Snowflake_Access_to_DB_Users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df5fce3d-600b-93e5-8375-d7806f0ce086.png)
3. Select the **Database** for which you want to identify the users that have access to the Site.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.

![dag_Starburst_users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f495644d-8513-582d-bf74-a78f21f2250a.png)
6. Click on any user for which you want to see the permissions and privileges.
7. Click on the **Policy Element** node to see the **Privilege** and **Privilege Category**.

![dag_Starburst_Privileges.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1de82fd0-d208-7a31-b320-fb302d7efe24.png)

#### Identifying Starburst Users have access to Tables containing Sensitive Data and what their permissions are on those Tables.

To identify the users that have access to Tables containing sensitive data :

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **Table**. Set the Attribute to the **Data System Type**. Select **Starburst**.
3. On the filter menu, set the **Entity** to **Data Element**. Set the Attribute to the **Non-Personal Data**. Select **True**.

![Dag-Starburst.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76fa4a94-9cbf-8795-2003-a58fad3737f1.png)
4. Click **Apply**.
5. Click on the **Table** node to see the Tables that have contain sensitive data.
6. Click on the **User Principal** node to see the users that have access to these tables.
7. Click on any user for which you want to see the permissions.
8. Click on the **Policy Element** node to see the list of permissions.

#### Identifying Starburst User Groups facilitate access to Databases and Tables containing sensitive data

To identify the user groups that facilitate access to Tables containing sensitive data :

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **Table**. Set the Attribute to the **Data System Type**. Select **Starburst**.
3. On the filter menu, set the **Entity** to **Data Element**. Set the Attribute to the **Non-Personal Data**. Select **True**.

![Dag-Starburst.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76fa4a94-9cbf-8795-2003-a58fad3737f1.png)
4. Click **Apply**.
5. Click on the **Table** node to see the Tables that have contain sensitive data.
6. Click on the **User Group** node to see the users that have access to these tables.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Configuring Access Intelligence Activity Analysis

To see the Starburst Access Intelligence information there are some prerequisites

#### Prerequisites for Activity Analysis

To configure activity analysis for your Starburst Enterprise, there are some prerequisites:

- The Query overview tab must be enabled on your Starburst Enterprise web portal. If not enabled, see the [Starburst documentation](https://docs.starburst.io/latest/admin/backend-service.html) to enable it.
- The user account you use to configure the connector must be an authorized user and must be a part of the following configurations:
  - **insights.authorized-users**

OR
  - **insights.authorized-groups**
- Perform a discovery scan for your Starburst instance.

#### 1. Configure an IAM Metadata Source for Activity Analysis using Apache Ranger:

To configure an IAM Metadata Source using **Apache Ranger** as a **Source Type**:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Metadata Source for Apache Ranger.
  2. Select **Apache Ranger** in the **Source Type**.
  3. In the **Connection Information** area, Select the Pod in the **Pod Name**.

![Ranger_Metadata_source.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13304637-3136-fc0c-058b-84677eca14e0.png)
  4. Enter the **Apache Ranger Service Name**. For example, starburst-enterprise
  5. In the **URl**, enter the URL to Starburst Web UI
  6. In the **Connection Timeout**, enter the timeout in milliseconds.
  7. In the Authentication Details area, select **Basic** as Authentication Type
  8. Enter the **Username** and **Password**.
  9. Enable **Disable TLS Verification** to reduce the strictness of the validation procedures applied when setting up an SSL/TLS connection. Note that this option should be used only in controlled environments when connecting to a trusted Starburst Enterprise server. Turning off Transport Layer Security (TLS) verification doesn't impact the encryption of the session.
  10. Click **Create New IAM Metadata** source

#### 2. Configure an IAM Metadata Source for Activity Analysis using Starburst Activity Data Web UI:

To configure an IAM Metadata Source using **Starburst Activity Data Web UI Integration** as a **Source Type**:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Starburst Metadata Source.
  2. Select **Starburst Activity Data - Web UI Integration** in the **Source Type**.
  3. In the **Connection Information** area, Select the Pod in the **Pod Name**.

![Starburst_Metadata_source.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb775e7b-58fa-47e2-8f18-989c1cbf338b.png)
  4. In the **URL**, provide the URL to Starburst Web UI
  5. In the **Connection Timeout**, enter the timeout in milliseconds.
  6. In the Authentication Details area, select **Basic** as Authentication Type
  7. Enter the **Username** and **Password**.
  8. Enable **Disable TLS Verification** to reduce the strictness of the validation procedures applied when setting up an SSL/TLS connection. Note that this option should be used only in controlled environments when connecting to a trusted Starburst Enterprise server. Turning off Transport Layer Security (TLS) verification doesn't impact the encryption of the session.
  9. Click **Create New IAM Metadata** source

#### 3. Configure an Access Scan Definition using Apache Ranger and Starburst Activity Data Metadata Sources

To configure an Access Scan Definition that utilizes the both Metadata sources (Apache Ranger and Starburst Web UI) that you configured in Step 1 and 2:

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **Starburst** in the **Data System**.
  3. Enter the **Host** and **Port**.
  4. In the **IAM Metadata Sources**, select both the metadata sources that you have created for Starburst and Apache Ranger. If you have not configured a metadata source, then you must click + Add New to add a metadata source.

![MDS_updated.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84f05e64-1f10-e73e-2838-28036e4fbd6f.png)
  5. Enable the **Activity Analysis** checkbox.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.

#### 4. Enable the Access Intelligence Scan

Enable the Access Intelligence Scan toggle on the Data System Connector Page. Navigate to the Permissions tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

#### 5. Launching the Access Scan

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle. Click the three dots option, and select the **Scan Now** option.

#### Using Activity Analysis with Starburst

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify activity of your users.

#### Filter and report on users that have performed CREATE action on your Starburst resources

To filter the users that have performed CREATE action:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu bar, click **Activity Explorer**. This will open the Activity Explorer page.

![Activity_Explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-deb98f66-5bbb-5f39-0e97-3bac4607d123.png)
3. The activity explorer page presents you the data related to the activities that your users performed on the data system resources. From the filter panel available on the top of the page, click **Action**. Select the **is one of** operators. Select the **Create** action.

![Activity_Analysis_Create.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e8447124-b648-de4a-a43b-3932e43ca2ab(1).png)
4. Click on the **Apply** button. All the queries in which your users have performed “CREATE” action will be displayed in the data grid.
5. Click on the View **Metadata** on the right side of the query entry for which you want to see the details. You can view details such as **Type**, **Data system instance**, **Resource**, **PD Elements**, **Client Country**, etc.

![Instance_Explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fedc529-ecd3-dfdb-0633-a52a9a5169c6.png)

> [!NOTE]
> **Note**
> 
> Activity Explorer will display user activity for both the View and the underlying table.

#### Identify Data Definition Language (DDL) queries/Configuration Activities performed by your users on your Starburst resources

To filter the DDL queries that your users executed:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu bar, click **Activity Explorer**. This will open the Activity Explorer page.
3. From the filter panel available on the top of the page, click **Type**. Select the **is one of the operators**. Select the **DDL** option.

![Activity_Analysis_DDL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ba2cfd5-4dc7-8cdd-fd47-692915b64c4a.png)
4. All the queries of DDL type that your users executed will be displayed in the grid. You can also see the relevant Action for these activities such as **Drop**, **Create**, etc. in the **Action** column.
5. Click on the View **Metadata** on the right side of the query entry for which you want to see the details. You can view details such as **Type**, **Data system instance**, **Resource**, **PD Elements**, **Client Country**, etc.

#### Identify and report the activities performed by a specific user

To filter the activities performed by a specific user:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu bar, click **Activity Explorer**. This will open the Activity Explorer page.
3. From the filter panel available on the top of the page, click **User**. Select **is one of** operators. Provide the name of the specific user.
4. Click on the **Apply** button. This will display all the activities performed by a specific user in the grid.
5. If you want to see all the activities performed by a specific user on a specific resource, Click on the **Resources** filter. Select the is **one of operators**. Provide the name of the data resource.

![Activity__specific_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9dd17fc-ff6a-5108-1697-15bf3f23a7b7.png)
6. Click on the **Apply** button.

You can see all the activities performed by a specific user on a data resource.

### Configuring Cross Border Data Transfer Policies for Starburst

To configure a Cross Border Transfer Policy for your Starburst instance, there are some prerequisites:

#### Prerequisites

- [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
- [Configure and activate the connector](/v1/docs/activate-the-starburst-connector-in-securiti).
- Perform a discovery scan on your Starburst instance.
- [Configure an IAM Metadata source for the relevant data system connector](/v1/docs/configuring-access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources)
- [Configure an Access Scan Definition for your Starburst instance](/v1/docs/grant-permissions-and-obtain-credentials-in-starburst).

> [!NOTE]
> **Note**
> 
> Cross Border Data Transfer Policies for Starburst utilize the metadata gathered from Starburst Activity Analysis. Therefore, it is mandatory to configure Activity Analysis for Starburst to receive alerts for your cross border data transfers using policies. For more information on Starburst Activity Analysis, see [Configuring Activity Analysis for Starburst](/v1/docs/grant-permissions-and-obtain-credentials-in-starburst).
- Define **Data Subject Types**, e.g. employees, job applicants, prospects, partners, etc. for the Starburst asset in the data mapping automation module. See [creating and editing data subjects](/v1/docs/using-data-mapping-automation).
- Define an Institute in the data mapping automation module. Specify the **Primary Covered Entities**e.g., Educational Institutions, Medical Industry, and **Secondary Covered Entities** e.g., Public Universities, Healthcare Providers, etc. See [creating and editing institutions](/v1/docs/creating-and-editing-institutions)

#### Cross border transfer policies

#### Viewing cross-border transfer findings

Cross-border transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows.

To view the cross-border transfer findings, click on the **Cross-Border Transfer** from the left panel. The widgets at the top show you the metrics for **Open Findings**, and count for **Fixed and Suppressed Findings**. The trendlines for the **Open Findings and Closed Findings by Status** show you the weekly, monthly, quarterly, and yearly trends.

Below the widgets, there is a search bar to sort the findings based on the rule name, description, or issue.

Below the search bar, the tiles show you the counts for the **Total Rules with Findings** and **Open Findings**. You can view and group these findings based on:

- Rule
- Owner
- Policy
- Data Source

To group the findings, click on the Group by drop-down menu on the right side, and select the parameter based on which you must sort the findings.

![crossborderFindings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7cbcf02-0cca-833d-5d6a-bd13565cc4f3(1).png)

You can also sort the alerts and findings based on the:

- Status
- Severity
- Finding ID
- Subscription
- Owner

Click on the Column selector to select the columns you want to see and rearrange them by dragging and dropping.

You can suppress the findings and change the assignee for a particular finding. To suppress a finding or change its assignee, select the finding, and click on the **Suppress Finding** button. The status of the finding will be changed to **Suppressed**. To Change the Assignee, select the finding, click on the **Change Assignee** button, and select the user in the popup to which you must assign the finding.

### Configuring data access control policies for Starburst

This policy type lets you configure granular access permissions across your Starburst database.

#### Prerequisites

- [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/v1/docs/activate-the-starburst-connector-in-securiti).
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Access** **Permissions** tab, so that this data system is available for selection when you create the policy.

![Data Access Control settings with options for repository name and plugin versions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(15).png)
  - Select the Plugin Version from the Dropdown menu.
  - In the plugin folder, locate the **install.properties** files.

![install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66d75246-550d-4f75-2420-6ff249d2a407(5).png)
  - Add your **repository name** in the install.properties file.

![Reporsitry_name_install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fc87371-3212-f9bd-0136-5861d1277abb(4).png)
- [Perform a discovery scan for your Starburst instance](/v1/docs/data-systems-connector).
- Configure an Active directory Server.

#### Creating data access control policies

1. In Securiti, open **Data Access Governance**, then choose **Policies>Data Access Policies**.
2. Near the upper right corner of the page, click **Create Policy**.
3. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Starburst_onprem**.
  3. Click **Get Started**.
4. Enter a name for the policy.
5. (Optional) Add a description for the policy.
6. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.

> [!NOTE]
> **Note**
> 
> If you delete a data system instance for which you have defined an access control policy and selected associated data objects such as databases, schemas, etc. in scope, Securiti changes its state to "Not in Use" on the Policies page. The policy is automatically deactivated. Note that the privileges enforced by the policy on the data system will not be removed, as Securiti will no longer have an active connection with the data system.
  1. From the Actions column, click the graph icon to add the scope. Once you click the graph icon, the Graph Explorer window opens. The canvas opens, letting you define your graph criteria.:
    - By clicking the **+** sign in the upper left corner of the upper row of the dashboard.
    - By clicking the **Begin Your Search** button at the center.
    - By loading an existing filter from **Saved Views** from the upper right corner of the page
  2. Click + or the Begin Your Search button at the center of the page. The filter menu has three panels as described below:

| Panel | Description |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
  3. From the center panel, click on the **Database** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node. Set the operator to **equals**. Select **Starburst**.
  4. Add **Database Name** property to the Database Entity.
  5. Select the database from the data grid on which you must apply the policy.
  6. Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  7. Click options (three dots) on the right side of the **Database** node and click **+ Add Relationship**.
  8. Select the **Database Schema** node. Click on the Database Schema entity from the left panel. Select the Database Schema for which you want to implement the privileges. Apply the **increment (+ icon)** operator. You can also add the Tables to the scope of the policy as shown above. Note that if you have selected Tables in the data scope, then you can select the table-level privileges in the Access Rules.

#### Adding a Privilege Rule:

In the **Access Rules** area, click **+ Add a Privilege Rule** to add a rule. In the Add a Privilege Rule window:

1. Provide the Rule Name.
2. (Optional) Add description.
3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the access rule is applied.
4. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the Users area, select the users from the menu. You can also add the users using the menu or use Graph Query button. You can also select Active Directory Users and Groups.
5. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Note that the privileges shown are the native Starburst privileges.. The privileges displayed are dependent on the data resources you select in the **Data Scope**. If you have selected **Database Schema** in the **Data Scope**, then the Schema level privileges are displayed.

![DAG_Starburst_Privileges.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3a1bcf4-9e08-11f7-cd3f-007035915238.png)
6. You can select **Allow** to Grant the selected privileges, or you can select **Deny** to revoke privileges.
7. Click the **Create Rule** button to add an access rule.

#### Adding a Filtering Rule

If you have selected the Tables in the Data Scope, you can define filtering rules to configure row-level filtering conditions for the Principals (users and groups). Row-Level Filtering fine-grained access control method that restricts access to specific rows of data in the table in the data system.

To add Filtering rule:

1. In the **Access Rules** area, click on the **Filtering tab**.
2. Click on **+ Add a filtering Rule** button to add the rule.
3. In the **Add a Filtering Rule** window, provide the **Rule Name**.
4. (Optional) Add the description.
5. In the **Principals** area, click **+ Add a Principal** to add the Principals as shown above.
6. In the **Row Filtering Condition**, select the filtering condition. You can select the **General Filtering** conditions such as **Include all rows** and **filter out all rows** or **Advanced Filtering** condition such as **Conditional filtering**. The **Include all rows** condition provides access to all the rows to the selected principals. The **Filter out all rows** condition restricts access to all the rows.
7. If you have selected **Conditional filtering,** you must specify the condition based on **Column by Name**, or **Column by Element** or **User Attribute**.
  - From the **Return rows where** area, click on the **+** Icon. To add a condition based on the column name, select the **Column By Name** option. Type the column name (<"column name">) such as "City" in the middle panel. Select the operator value from the right panel. Provide the value of the Constant. For Example, for the column name ‘City’ you have selected, you provide ‘’Los Angeles’’ as the Value of the Constant. Upon successful execution of the policy, the Principal will have access to all the rows in the table for which the value of the column name ‘City’ is ‘’Los Angeles’’. If you have selected the **User Attribute** option, you must select the attribute that the policy will compare with the selected column name. For example, for the column name ‘City’’ previously selected, you select the City as the **Attribute**, and in the Active Directory, for the selected Principal, the value of the City attribute is “Tokyo". Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the City is Tokyo.

![DAG_TRINO_Column_by_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5ec9ad4-6b7e-8b5e-3624-06a652bd776e(2).png)
  - If you have selected the **User Attribute** option, you must select the attribute that the policy will compare with the table data For example, for the column name ‘City’’, you select the City as the **Attribute**, and in the Active Directory, for the selected Principal, the value of the City attribute is “Paris". Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the City is Paris.
  - To add a condition based on the data elements, select **Column By Element** option. Select the data element such as the Email address in the middle panel. Note that the data elements must be discovered in the discovery scan. Select the operator value from the right panel. Provide the value of the Constant. For Example, for the data element ‘Email Address’’ you have selected, you provide ’'john.doe@securiti.ai' as the Value of the Constant. Upon successful execution of the policy, the Principals will have access to all the rows in the table for which the values of the column ‘Email Address’ are ‘’john.doe@securiti.ai'’. Click **Create Rule** button. You can add multiple conditions separated by ‘AND’ and ‘OR’ operators.

![Row_filtering.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e327fed-73b8-852e-d51e-6cd4e6bffa39(3).png)

#### Adding a Masking Rule

If you have selected the Column in Datascope, you must configure the masking rule to create an access control policy. To configure a masking rule:

1. Click on the **+ Add a Masking Rule** button to add the rule.
2. Enter the **Rule Name**.
3. (Optional) Add description.
4. In the **Principals** area, click **+ Add a Principal**.
5. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the **Users** area, select the users from the menu. You can also add the users using the or use **Graph Query button**.
6. In the **Masking Behavior** area, you must configure the type of masking to mask the selected columns to only the specified principals.
  - If you have selected the **Custom Value** option, you must provide the value by which data will be masked. For example, if you have entered “**##**” as the **Custom Value**, and selected the email column in the **Data Scope**, the values of the email column will be masked for the specified Principal.
  - To provide access to users and groups to a masked column, you must select them as Principals, and select **Unmasked** from the Masking Behaviour area.
  - You can also use **Built-in masking functions** such as Hash. To use the built-in masking functions, select the Built-In Masking Function option from the menu. And select the type of masking you want to apply from the Built-In Masking Function option. You can select the following masking functions:

| Masking Function | Description |
| --- | --- |
| Partial mask: show last 4 | Shows only the last four characters of the full column value |
| Partial mask: show first 4 | Shows only the first four characters of the full column value |
| Hash | Replaces all characters with a hash of the entire cell's value |
| Nullify | Replaces all characters in the cell with a NULL value |
| Mask | Replace lowercase alphabetic characters with 'x', uppercase alphabetic characters with 'X', and digits with '0'. |
  - Click the **Create Rule** button.
7. Activate the **Enable policy after saving** toggle. When activated, the policy will be enforced as soon as the policy information is saved.
8. Click the **Create Policy** button to create the policy.
