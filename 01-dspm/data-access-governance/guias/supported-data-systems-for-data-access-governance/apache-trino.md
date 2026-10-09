---
title: "Apache Trino"
slug: "apache-trino"
updated: 2026-09-24T08:09:47Z
published: 2026-09-24T08:09:47Z
canonical: "helpcenter.securiti.ai/apache-trino"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Apache Trino

This section describes the Data Access Governance features supported for Apache Trino and the steps to configure these functionalities.

### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Apache Trino:

### Access Intelligence

- Privilege Analysis - Not supported
- Activity Analysis - Not Supported

#### Access Control

- Column Masking Properties
- Row Filtering Properties
- Permissions Management Properties

#### Cross Border Transfer Policies

- Not Supported

### Example Supported Use Cases

The supported example use cases include:

#### Access Control

- Allow or Deny the access of your users and groups to Databases, Schemas, and Tables using Privilege rules
- Restrict the access of users and groups to the sensitive data by configuring row level filters based on data elements and column names
- Define masking rules for users and groups to mask the Columns containing sensitive data

#### Configuring Apache Trino Data Access Governance

This section describes the configuration process for Data Access Governance feature sets for Apache Trino.

#### Configuring data access control policies for Apache Trino

This access control policy type lets you grant granular permissions to your Apache Trino Databases, Schemas, and Tables.

#### Prerequisites

- [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/v1/docs/activate-the-apache-trino-connector-in-securiti).
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Access** **Permissions** tab, so that this data system is available for selection when you create the policy.
  - Select the Plugin Version from the Dropdown menu

![Trino DAG interface showing data access control settings and download options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/trino.png)
  - In the plugin folder, locate the **install.properties** files.

![install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66d75246-550d-4f75-2420-6ff249d2a407(3).png)
  - Add your **repository name** in the install.properties file.

![Reporsitry_name_install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fc87371-3212-f9bd-0136-5861d1277abb(2).png)
- Configure the [Active Directory](/v1/docs/system-settings-help-center) to synchronise your Active Directory users.
- [Perform a discovery scan for your Apache Trino instance](/v1/docs/data-systems-connector).

#### Creating data access control policies

1. In Securiti, open **Data Access Governance**, then choose **Policies>Data Access Policies**.
2. Near the upper right corner of the page, click **Create Policy**.
3. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Apache Trino**.
  3. Click **Get Started**.
4. Enter a name for the policy.
5. (Optional) Add a description for the policy.
6. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.

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
  3. From the center panel, click on the **Database** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node. Set the operator to **equals**. Select **Apache Trino**.
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
4. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the Users area, select the users from the menu. You can also add the users using the menu or use Graph Query button. Note that you can add the Active Directory users and Securiti Tenant users. A Tenant User is the User that can access the Securiti Data Command Center. To add the Active Directory user, select **User Principal** node
5. You can also add Active Directory **Groups** as a Principal. If you want to select Active directory groups, choose **User Group Principal** node, and select the User Groups.
6. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Note that the privileges displayed are the native Apache Trino privileges. The privileges displayed are dependent on the data resources you select in the **Data Scope**. If you have selected **Database Schema** in the **Data Scope**, then the Schema level privileges are displayed.

![DAG_TRINO_PRivilege_Rule.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40247bf9-09c2-557d-6ce5-386b99dd63b3.png)
7. You can select **Allow** to Grant the selected privileges, or you can select **Deny** to revoke privileges.
8. Click the **Create Rule** button to add an access rule.

#### Adding a Filtering Rule

If you have selected the Tables in the Data Scope, you can define filtering rules to configure row-level filtering conditions for the Principals (users and groups). Row-Level Filtering fine-grained access control method that restricts access to specific rows of data in the table in the data system.

To add Filtering rule:

1. In the **Access Rules** area, click on the **Filtering tab**.
2. Click on the **+ Add a filtering Rule** button to add the rule.
3. In the **Add a Filtering Rule** window, provide the **Rule Name**.
4. (Optional) Add the description.
5. In the **Principals** area, click **+ Add a Principal** to add the Principals as shown above.
6. In the **Row Filtering Condition**, select the filtering condition. You can select the **General Filtering** conditions such as **Include all rows** and **filter out all rows** or **Advanced Filtering** condition such as **Conditional filtering**. The **Include all rows** condition provides access to all the rows to the selected principals. The **Filter out all rows** condition restricts access to all the rows.
7. If you have selected **Conditional filtering,** you must specify the condition based on **Column by Name**, or **Column by Element** or **User Attribute**.
  - From the **Return rows where** area, click on the **+** Icon. To add a condition based on the column name, select the **Column By Name** option. Type the column name (<"column name">) such as "City" in the middle panel. Select the operator value from the right panel. Provide the value of the Constant. For Example, for the column name ‘City’ you have selected, you provide ‘’Los Angeles’’ as the Value of the Constant. Upon successful execution of the policy, the Principal will have access to all the rows in the table for which the value of the column name ‘City’ is ‘’Los Angeles’’. If you have selected the **Attribute** option, you must select the attribute that the policy will compare with the selected column name. For example, for the column name ‘City’’ previously selected, you select the City as the **Attribute**, and in the Active Directory, for the selected Principal, the value of the City attribute is “Tokyo". Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the City is Tokyo.

![DAG_TRINO_Column_by_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5ec9ad4-6b7e-8b5e-3624-06a652bd776e(1).png)
  - If you have selected the **User Attribute** option, you must select the attribute that the policy will compare with the table data For example, for the column name ‘City’’ previously selected, you select the City as the **Attribute**, and in the Active Directory, for the selected Principal, the value of the City attribute is “Paris". Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the City is Paris.
  - To add a condition based on the data elements, select **Column By Element** option. Select the data element such as the Email address in the middle panel. Note that the data elements must be discovered in the discovery scan. Select the operator value from the right panel. Provide the value of the Constant. For Example, for the data element ‘Email Address’’ you have selected, you provide ’'john.doe@securiti.ai' as the Value of the Constant. Upon successful execution of the policy, the Principals will have access to all the rows in the table for which the values of the column ‘Email Address’ are ‘’john.doe@securiti.ai'’. Click **Create Rule** button. You can add multiple conditions separated by ‘AND’ and ‘OR’ operators.

![Row_filtering.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e327fed-73b8-852e-d51e-6cd4e6bffa39(2).png)

#### Adding a Masking Rule

If you have selected the Column in Datascope, you must configure the masking rule to create an access control policy. To configure a masking rule:

1. Click on the **+ Add a Masking Rule** button to add the rule.
2. Enter the **Rule Name**.
3. (Optional) Add description.
4. In the **Principals** area, click **+ Add a Principal**.
5. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the **Users** area, select the users from the menu. You can also add the users using the or use **Graph Query button**. Note that you can add the Active Directory users and Securiti Tenant users. A Tenant User is the User that can access the Securiti’s Data Command Center.
6. You can also add Active Directory **Groups** as a Principal.
7. In the Masking Behaviour area, you must configure the type of masking to mask the selected columns to only the specified principals.
  - If you have selected the **Custom Value** option, you must provide the value by which data will be masked. For example, if you have entered “**##**” as the **Custom Value**, and selected the email column in the **Data Scope**, the values of the email column will be masked for the specified Principal.
  - To provide access to users and groups to a masked column, you must select them as Principals, and select **Unmasked** from the Masking Behaviour area.
  - You can also use **Built-in masking functions** such as Hash. To use the built-in masking functions, select the Built-In Masking Function option from the menu. And select the type of masking you want to apply from the Built-In Masking Function option. You can select the following masking functions:

| Masking Function | Description |
| --- | --- |
| Partial mask: show last 4 | Shows only the last four characters of the full column value |
| Partial mask: show first 4 | Shows only the first four characters of the full column value |
| Hash | Replaces all characters with a hash of the entire cell's value |
| Nullify | Replaces all characters in the cell with a NULL value |
| Redact | Replaces all alphabetic characters with x and all numeric characters with n |
| Date: show only year | Displays the year portion of a date string, defaulting the month and day to 01/01 |
  - Click the **Create Rule** button.
8. Activate the **Enable policy after saving** toggle. When activated, the policy will be enforced as soon as the policy information is saved.
9. Click the **Create Policy** button to create the policy.
