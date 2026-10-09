---
title: "Active Directory"
slug: "active-directory"
updated: 2026-07-31T04:32:29Z
published: 2026-07-31T04:32:29Z
canonical: "helpcenter.securiti.ai/active-directory"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Active Directory

This section describes the Data Access Governance features supported for Active Directory and the steps to configure these functionalities. The following is a list of Active Directory that are supported for Data Access Governance features:

#### Supported Data Access Governance Feature Sets for Active Directory

The following is the list of the features supported for Active Directory:

### Access Control

- Users assignment to Active Directory User Groups

### Example Supported Use Cases

The supported example use cases include:

#### Access Control

- **Add** or **Remove** Users to the Active Directory User Group.

### Configuring Data Access Control Policies for Active Directory

This access control policy type lets you add or remove Users from Active Directory User Groups.

#### Prerequisites

- [Configure an Active Directory Server](/latest/docs/identity-providers-idp-providers-for-identity-sync).

#### Creating data access control policies

1. In Securiti, open **Data Access Governance**, then click the three dots icon to expand the navigation bar. Choose **Policies>Data Access Policies**.

- ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/active-directory-image-bdchw7jq.png)

1. Near the upper right corner of the page, click **+ Create Policy** button.
2. On the **Create a New Policy** popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Active Directory**.
  3. Select the **Organization**.
  4. Click **Get Started**.
3. Enter a name for the policy.
4. (Optional) Add a description for the policy.
5. Enable the **Activate Policy** toggle to enforce the policy once you create it.
6. In the **Data Scope** area, use the tools to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.
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

- 
  1. Click on three dots on the Active Directory node near the top left, click **Add Property** to add a property. Select the **Group Name** from the list of properties associated with the node.
  2. Select the Active Directory Group from the data grid to which you must Add or Remove Users.
  3. Near the upper right corner, click on the **Use Query**.

1. In the **Group Membership Conditions** area, click **+Add a Group Membership Condition** to define conditions for adding or removing users to an Active Directory Group. In the **Add a Membership Condition** popup:
  1. Provide the Rule Name.
  2. (Optional) Add description.
  3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the membership condition is applied.
  4. Select **Users.** You must select Users as a Principal to add or remove from the specified Active Directory Group. In the Users area, select the users from the menu.
  - ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/active-directory-image-zaft4nd3.png)
  1. In the **Actions** area, you must choose if users should be added to or removed from the target groups.
  2. Select **Add** to add a user to the specified Active Directory Group. Choose **Remove** option to withdraw the user from the specified Active Directory Group.
  3. Click **Create Rule** to add the Membership Condition
2. You can add multiple Membership Conditions. Click options (three dots) on a Membership condition to **Edit** or **Delete** the condition Rule. You can also Activate or Deactivate the rule condition by enabling or disabling the toggle.
3. Click **Create Policy** .

### View Active Directory Users using Access Graph Explorer

- Navigate to the left panel and hover over **Data Access Governance → Data Command Graph → Access Graph Explorer**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1781168987830.png)

- In **Access Graph Explorer**, click **+** to start building a query.
- In the first selector, choose **Active Directory User Identity**. This sets the query to look for Active Directory users.
- Click **Run Query** to display results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3.png) The table, after running the query, shows all Active Directory users that match the query, including (in default display):

- **Username**
- **Provider Type**
- **Provider Account ID**
- **User Type**
- **User ID**

The rest of the available columns include:

- **Account Expiry Time**
- **Email**
- **AD ID**
- **Country Code**
- **Country Name**
- **Department**
- **Display Name**
- **Distinguished Name**
- **External**
- **Job Title**
- **Manager Distinguished Name**
- **Manager Name**
- **Organization**
- **RID**
- **SID**

### View Active Directory User Group Membership using Access Graph Explorer

- In **Access Graph Explorer**, click **+** to start building a query.
- In the first selector, choose **Active Directory User Identity**. This sets the query to look for users synced from Active Directory.
- Under **Active Directory User Identity**, click **Is Member Of** and select **Active Directory User Group**. This adds a relationship to show the groups each user belongs to.
- Click **Run Query** to display results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2.png) The table The table, after running the query, shows all Active Directory user groups associated with the selected users, including (in default ) :

- **AD ID**
- **Description**
- **Display Name**
- **Distinguished Name**
- **Organization**
- **RID**
- **SID**

The rest of the columns include:

- **Group Name**
- **Provider Type**
- **Provider Account ID**
- **Group Type**
- **Group Unique ID**
