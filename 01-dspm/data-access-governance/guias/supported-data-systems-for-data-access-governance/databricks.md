---
title: "Databricks"
slug: "databricks"
updated: 2026-09-24T08:06:23Z
published: 2026-09-24T08:06:23Z
canonical: "helpcenter.securiti.ai/databricks"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Databricks

This section describes the Data Access Governance features supported for Databricks and the steps to configure these functionalities.

### Supported Data Access Governance Feature Sets

The following is the list of the features supported for Databricks:

#### Access Intelligence

- Privilege Analysis
  - Database, Schema, and Table Permissions Granularity
- Activity Analysis - Not Supported

#### Access Control

- Column Masking Properties
- Row Filtering Properties
- Permissions Management Properties

#### Cross Border Transfer Policies

- Not Supported

### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which Databricks users and user groups have access to Databases and what their permissions are on those Databases.
- Identify and report on which Databricks users and user groups have access to Tables and what their permissions are on those Tables.
- Identify and report on which Databricks Users have admin privileges in your Databricks Account.
- Identify and report on whether a User’s access to a particular Database, Schema, or Table comes as a result of direct permissions assignment or through their group membership.

### Configuring Databricks Data Access Governance

To see the Databricks access intelligence data there are some prerequisite steps.

### Configuring Access Intelligence Privilege Analysis

To configure the privilege analysis for Databricks, there are some prerequisites

#### Prerequisites

To see the Databricks access intelligence data on the dashboard you must:

1. [Configure and activate the connector](/v1/docs/databricks-connectors). Note that the user account you are using to configure and activate the connector must be Workspace Admin.

> [!NOTE]
> **Note**
> 
> To get information about the users, user groups, and service account principals, the user account that you use to configure the connector must be a Workspace Admin. To view the privileges assigned on data resources such as Catalogs, Schemas, and Tables, we recommend that you use a user account with elevated privileges or resource ownership to view all the privileges assigned.
  - Access Intelligence supports customer self-hosted connectors.
2. [Perform discovery scan for your Databricks instance](/v1/docs/configuring-discovery-scans-in-databricks).
3. Supported Authentication for Access Intelligence Scans
  - Access Token

#### Configuring your Databricks Access Scans for Access Intelligence

**1. Configure an IAM Metadata Source for Databricks**

1. In Securiti, open **Data Access Governance,** from the left menu bar.
2. Click **IAM Metadata Sources** in **Settings**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**. ![Form for creating a new IAM metadata source with connection details and authentication.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/databricks iam.png)
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Databricks Metadata Source.
  2. Select **Databricks Onprem** in **Source Type**.
  3. In the **Connection Information** area, provide following details:
    1. Select the Pod in the **Pod Name**.
    2. Select the **Driver Files**.
    3. In the **Host**, provide Databricks server hostname.
    4. In the **Port**, enter the Databricks server port.
    5. In the **HTTP Path**, provide the path of the endpoint to be used for HTTP/HTTPS requests.
    6. Enable **Use SSL** option if you want to use SSL configuration
  4. In the Authentication Details area, select Authentication Type. For Databricks, **Access Token** based Authentication is supported.
    - Select **Access Token**.
    - Provide the **Access Token**.
  5. Click Create **New IAM Metadata source**.

**2. Configure an Access Scan Definition for Databricks**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select Databricks in **Data System** to scan for IAM related metadata.
  3. Enter the **Host** and **Port**.
  4. In the **IAM Metadata Sources**, select the metadata sources that you have created for a particular data system. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  5. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.

**3. Enable Access Intelligence Scans**

If you have not selected the associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan on the Databricks Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to link the ASD with the data system connector.

**4. Launching the Access Scan**

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

#### Using Access Intelligence with Databricks

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Databricks tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identifying Users with Access to a specific Database(s) using the Data Command Graph

You can perform privilege analysis for **Databricks** using the Access Graph Explorer. Access Graph Explorer presents you with the popular views without the need to select the entities and add parameters. To see the popular views, you must:

To identify the users that have access to a specific database:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select **Database** Entity. Choose the **Database Name** property. Set the operator to the **Equals**.

![Data command graph displaying database connections and access intelligence metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/data 1.png)
3. Select the **Database** for which you want to identify the users that have access to the Site.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.
6. Click on the **Policy Element** node to see the permissions.

#### Identifying Databricks Users that have Access to Tables containing Sensitive Data and their permissions are on those Tables using Data Command Graph

To identify the users that have access to Tables containing sensitive data:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Table**. Set the **Attribute** to the **Data System Type**. Set the operator to the **Equals**.

![Data command graph illustrating relationships between various data systems and elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/data 2.png)
3. Select **Databricks**.
4. Click **Apply**.
5. Add another Entity for Data Element. On the filter menu, set **Entity** to **Data Element**. Set the **Attribute** to the **Non-Personal Sensitive Data**. Set the operator to the **Equals**. Select **True**. Apply the filters.
6. Click on the **User Principal** node to see the users in the data grid.
7. Click on the **Policy Element** node to see the permissions.

![Databricks_Data_Element.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89ed1815-3304-c097-7d43-0f8b788d01b2.png)

#### Identifying Users with Access to a Table(s) containing sensitive data using the Access Graph Explorer

To identify the users with Access to a Table(s) containing sensitive data:

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** by selecting three dots on the top right side of the page.
2. Navigate to the **Saved Views** panel on the top right side of the page.
3. On the **Popular Views** tab, navigate to the **Databricks Queries** area. You can see the queries that help you perform privilege analysis for your Databricks instances.
4. Click on the query **Users with Direct Assignment Access to Tables with Sensitive Data**. Click on the User Principal node to see the users in the data grid.

![Access Graph Explorer interface displaying data elements and their relationships in a database.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1783610661603.png)

#### Determining if a User’s access to a table comes as a result of their membership in a group or if it is directly assigned using the Access Graph Explorer

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** by selecting three dots on the top right side of the page.
2. Navigate to the **Saved Views** panel on the top right side of the page.
3. On the **Popular Views** tab, navigate to the **Databricks Queries** area. You can see the queries that help you perform privilege analysis for your Databricks instances.
4. Click on the query **Users with Group Assignment access to Tables containing Sensitive Data**.

![Access Graph Explorer displaying data elements and their relationships in a database schema.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.25.41 PM (2).png)
5. Click on three dots with the **User Principal** entity in the query area. Click **+ Add Property** button.
6. Select the property to specify a specific user such as Username.
7. Click on the **User Principal** node.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Configuring Data Access Control Policies for Databricks

This access control policy type lets you grant granular permissions to your Databricks Catalogs, Schemas, and Tables.

### Prerequisites

- [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/v1/docs/databricks-connectors). Note that the user account you use to configure the connector must be the owner of the data resources such as Catalogs, Schemas, and Tables on which you must apply access control policies.
- To define the conditional row filtering and masking conditions based on the user attributes, you must synchronize the Active Directory with Securiti. For more information see, [Configuring Active Directory Servers](/v1/docs/supported-identity-providers-idp-providers-for-identity-sync).
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Access** **Permissions** tab, so that this data system is available for selection when you create the policy.

![Settings page for Data Access Control with options to enable governance features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/databricks.png)
- Mark the checkbox for **Create AD Users Mapping Table** checkbox in the data system’s **Permissions** tab. When enabled and saved, user mapping tables are created in the data system that allow users to create custom row filters and conditional masking.
- Mark the checkbox for **Enable Database Row Filter Policy** in the data system’s **Permissions** tab. When enabled, the **Sync Row Filter Policy** option will appear which syncs row filter policies from Databricks to Securiti. Note that to sync the row-level policies, you must create **_secfilter** schema in your Databricks Catalog, and define your custom user-defined functions.
- Mark the checkbox for the **Enable Database Column Masking Policy**. When enabled and saved, the Sync Masking Policy Option appears, which syncs masking policies from Databricks to Securiti. To sync the masking policies, you must create **_secmask** schema in your Databricks Catalog, and define your custom user-defined masking functions.
- Perform a discovery scan for the Databricks instance.
- Perform an access scan for the Databricks instance to identify the user principals and identities.

#### Creating data access control policies

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage Data Access Governance policies.
3. Near the upper right corner of the page, click **Create Policy**.
4. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Databricks**.
  3. (Optional) Choose a template for the policy.
  4. Click **Get Started**.
5. Enter a name for the policy.
6. (Optional) Add a description for the policy.
7. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.

> [!NOTE]
> **Note**
> 
> If you delete a data system instance for which you have defined an access control policy and selected associated data objects such as databases, schemas, etc. in scope, Securiti changes its state to "Not in Use" on the Policies page. The policy is automatically deactivated. Note that the privileges enforced by the policy on the data system will not be removed, as Securiti will no longer have an active connection with the data system.
  1. From the Actions column, click on the graph icon to add the scope. Once you click the graph icon, the Graph Explorer window opens. You are presented with a blank canvas where you can begin defining your graph search criteria in the following ways:
    - By clicking the **+** sign in the upper left corner of the upper row of the dashboard.
    - By clicking the **Begin Your Search** button at the center.
    - By loading an existing filter from **Saved Views** from the upper right corner of the page
  2. Click + or the Begin Your Search button at the center of the page. The filter menu has three panels as described below:

| Panel | Description |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
  3. From the center panel, click on the **Database** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node.
  4. Select the database from the data grid on which you must apply the policy.
  5. Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  6. Click options (three dots) on the right side of the **Database** node and click **+ Add Relationship**.
  7. Select the **Database Schema** node. Click on the Database Schema entity from the left panel. Select the Database Schema for which you want to implement the privileges. Apply the **increment (+ icon)** operator. You can also add the Tables to the scope of the policy as shown above. Note that if you have selected Tables in the data scope, then you can select the table-level privileges in the Access Rules.
8. In the **Access Rules** area, click **+ Add a Privilege Rule** to add a rule. **In the Add a Privilege Rule window**:
  1. Provide the Rule Name.
  2. (Optional) Add description.
  3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the access rule is applied.
  4. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the Users area, select the users from the menu. You can also add the users using the menu or use Graph Query button. Note that you can add the Active Directory users and Securiti Tenant users. A Tenant User is the User that can access the Securiti Data Command Center. You can also select User Principals and User Group Principals identified during access scan as principals (entities on which privilege apply) while configuring an access rule for Databricks. You can also select these identities if detected in Active Directory during an Access Scan. Note that you must perform an access scan to identify the user principal in Databricks.
  5. You can also add Active Directory **Groups** as a Principal.
  6. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Note that the privileges displayed are the native Databricks privileges. The privileges displayed are dependent on the data resources you select in the **Data Scope**. If you have selected **Database Schema** in the **Data Scope**, then the Schema level privileges are displayed.

You can select **Allow** to **Grant** the selected privileges, or you can select **Revoke** to remove privileges. Note that the revoke **All Privileges** option will remove all the existing privileges of the principals.
  7. Click the **Create Rule** button to add an access rule.
  8. Note that if you have selected the **Tables** in the **Data Scope**, you can define filtering rules to configure row-level filtering conditions for the Principals (users and groups). To add a filtering rule:
    - In the **Access Rules** area, click on the **Filtering tab**.
    - Click on the **+ Add a filtering Rule** button to add the rule.
    - In the **Add a Filtering Rule** window, provide the **Rule Name**.
    - (Optional) Add the description.
    - In the **Principals** area, click **+ Add a Principal** to add the Principals as shown above.
    - In the **Row Filtering Condition**, select the filtering condition. You can select the **General Filtering** conditions such as **Include all rows** and **filter out all rows** or **Advanced Filtering** condition such as **Conditional filtering**. The **Include all rows** condition provides access to all the rows to the selected principals. The **Filter out all rows** condition restricts access to all the rows. Note that if you use Filter out all rows condition to restrict access for a particular user, the function also prevents other users from accessing all the rows. To provide access to other users, you must define the Include all rows condition. You can also select the User-defined Function. Note that if you have selected the **User-Defined Function (UDF)** as a **Row Filtering Condition**, you must select the UDF from the **Row Filtering Condition**. User-defined functions (UDFs) are the custom row filtering conditions that you define in the Databricks.

![User selection and filtering options for data access in a user-defined function interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 9.02.09 PM (2).png)
  9. If you have selected **Conditional filtering,** you must specify the condition based on the **User Attribute**, **Column by Name**, or **Column by Element**.

Click **Add a Filtering Rule** button to add multiple filtering rules.
    - From the **Return rows where** area, click on the + Icon. Select the **User Attribute** from the left panel if you want to apply a condition based on the **Active Directory** user attributes. Select the attribute and Operator such as **Equal**, **Not Equal**, **Less than** etc. Provide the value in the field below **Constants**. Note that SQL syntax is not supported. You must provide the value in JSON String format. For example, “New York”. Note that if you have selected the **City** as the User Attribute, and provided “New York” as a Constant value, the policy upon execution evaluates if the selected user attribute i.e, City in this case has the same value as that of the provided Constant (“New York”) in the Active Directory mapping table. If this condition is true, then the selected Principal can access the table rows.
    - To add a condition based on the column name, select the Column By Name option. Type the column name such as City in the middle panel. Select the operator value from the right panel. You can select the **Constant** or **Attribute** options. If you have selected the Constant, you must provide the value of the Constant. For Example, for the column name ‘City’ you have selected, you provide ‘’Los Angeles’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principal will have access to all the rows in the table for which the value of the column name ‘City’ is ‘’Los Angeles’’.
    - To add a condition based on the data elements, select the **Column By Element** option. Select the data element such as the Email address in the middle panel. Note that the data elements must be discovered in the discovery scan. Select the operator value from the right panel. You can select the **Constant** or **Attribute** options. If you have selected the Constant, you must provide the value of the Constant. For Example, for the data element ‘Email Address’’ you have selected, you provide ’'jane@example.com', and 'michael@example.com’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principals will have access to all the rows in the table for which the values of the column ‘Email Address’ are ‘’jane@example.com'’ or 'michael@example.com’’. If you have selected the **Attribute** option, you must select the attribute that the policy will compare with the selected column name. For example, for the data element ‘Email Address’’ previously selected, you select the Email Address as the **Attribute**, and in the mapping table, for the selected Principal, the value of the Email Address attribute is “michael@example.com’. Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the Email Address is michael@example.com.
    - Click the **Create Rule** button. You can add multiple conditions separated by ‘**AND**’ and ‘**OR**’ operators.
  10. If you have selected the Column in Datascope, you must configure the masking rule to create an access control policy. To configure a masking rule:
    - Click on the **+ Add a Masking Rule** button to add the rule.
    - Enter the **Rule Name**.
    - (Optional) Add description.
    - In the **Principals** area, click **+ Add a Principal**.
    - Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the **Users** area, select the users from the menu. You can also add the users using the or use **Graph Query button**. Note that you can add the Active Directory users and Securiti Tenant users. A Tenant User is the User that can access the Securiti’s Data Command Center.
    - You can also add Active Directory **Groups** as a Principal.
    - In the Masking Behaviour area, you must configure the type of masking to mask the selected columns to only the specified principals.
      - If you have selected the **Custom Value** option, you must provide the value by which data will be masked. For example, if you have entered “**##**” as the **Custom Value**, and selected the email column in the **Data Scope**, the values of the email column will be masked for the specified Principal. You can also view the masking function under the **_secgen** schema in Databricks.
      - Note that if you have selected a user as a Principal and applied a masking behavior such as Custom Value, the null masking will be applied for all other users. They will not be able to see any data in the specified column. To provide access to all other users, you must select them as Principals, and select Unmasked from the Masking Behaviour area.
      - You can also use built-in masking functions such as Hash (SHA-256), Default Masking etc. To use the built-in masking functions, select the Built-In Masking Function option from the menu. And select the type of masking you want to apply from the Built-In Masking Function option. You can select the following masking functions:

| Masking Function | Description |
| --- | --- |
| Default Masking | The uppercase alphabets are replaced with ‘N’. Lowercase alphabets are replaced with the ‘n’. Integers are replaced with 0. Special characters are replaced with X. |
| Email Masking | The data system selected while creating the policy. |
| First Four | The first four characters will be displayed, and the remaining part of the string will be masked by *. If the length of the value is equal to or less than four characters, then the value will be masked by SHA-256 hash function. |
| Last Four | The last four characters will be masked. |
| Hash (SHA-256) | This replaces the characters with the random 256 bits string (16 characters). |
| Nullify | Nullifies the value. |
      - You can also apply **Conditional Masking** based on the **User Attribute**, **Column By Name**, and **Column By Element**, and use the Expression Builder to define conditions. You can define masking behaviour **if** the expression returns a **True** value and which type of masking must be applied if the expression returns a false value.
      - Click the Create Rule button.

#### Access Policy Preview and Backup

You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. For each of the policy, that you create, update, or delete, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. These controls let you enforce the data access control policies on your data systems in a secure manner, ensuring that you realize the impact of the policies before enforcement.

#### Policy Preview

When you click **Create Policy** button, the **Policy Preview** will be generated. Policy Preview presents you with the entities such as Databases, Tables, Columns, etc. and privileges, row filters, and masking functions that that will be implemented upon successful enforcement of the policy. Note that the policy execution will start only if you **Accept** the Policy Preview.

![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e.png)

> [!NOTE]
> **Note**
> 
> No backup will be created in the case of preview being rejected in policy creation.

If you accept the **Policy Preview**, the backup of the policy will be automatically generated and you can access it via **Backups** page. Securiti also generates Policy Preview and Backup when you update or delete the access control policies.

![Backups.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99db3867-2f24-c01c-9725-621ffab467f9.png)

#### Backups

This section describes the configurations steps for creating a policy Backup manually and restoring a Backup.

#### Creating a Policy Backup manually

To create a Policy Backup:

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage Data Access Governance policies.
3. Near the upper right corner of the page, click three dots and select **Backups**.

![Overview of policy types with a focus on Data Access Control and its details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.49.50 PM (2)(1).png)
4. Near the right corner of the page, click **Manual Backup**.
5. On the **Manual Backup** popup, enter the following information
  1. Add **Backup Name** to suit.

![Create_Backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a3a1ec2-8bfe-ba5c-6f9a-90f4a0a31d07.png)
  2. Select the data system from the **Data System Type** menu.
  3. From the **Data System** menu, select the Data System instance.
  4. Click, **Create Backup** button.

#### Restoring a Policy Backup

To restore a Policy Backup:

1. In Securiti, open **Policies** by clicking on the Jewel icon from the left pane**.**
2. Click **Data Access Control** from the left navigation bar to view and manage Data Access Governance policies.
3. Near the upper right corner of the page, click three dots and select **Backups**.

![Overview of policy types with a focus on Data Access Control and its details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.49.50 PM (2)(1).png)
4. Near the right corner of the user row, click Options (three dots) > **View Backup**.

![Backup management interface displaying total backups and specific backup details for Databricks.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 8.51.38 PM (2).png)
5. The Backup Policy page will show you the privileges, row filters, and masking functions and entities, included in the backup, when this backup was taken.
6. Near the upper right corner of the page, click the **Restore Backup** button If you want to revert the current state of the data system and restore the data system to the state when this backup was created.

![Restore_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45fb49e9-de41-3f4b-8ef4-9479afa25bd5.png)
7. Click the **Restore Backup** button on the confirmation popup to restore the backup. The policies for that particular data system that were not included in the backup that you want to restore to, will be deactivated from the Policies page.

#### Policy Backup upon policy deletion

If you delete an active policy, the Policy Preview will be generated. Securiti will not delete the policy instantly, the policy will only delete the policy once you Accept the Preview for deletion.

![Delete_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ccb4fc06-6f52-0d86-0158-170d241ce2a1.png)

![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e.png)

Once you **Accept** the **Policy Preview**, the execution will start, and the policy will be deleted from the **Policies** page. Securiti automatically takes the backup for the policy. In the Backup Preview, you will not see any privilege rules, row filters, and masking applied on entities affected by the deleted policy, as there are no active privileges, filters, and masking conditions defined on these entities currently.
