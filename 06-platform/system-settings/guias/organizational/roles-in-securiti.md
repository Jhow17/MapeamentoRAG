---
title: "Using Roles in Securiti"
slug: "roles-in-securiti"
updated: 2026-09-24T14:23:03Z
published: 2026-09-24T14:23:03Z
canonical: "helpcenter.securiti.ai/roles-in-securiti"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Using Roles in Securiti

A **Role** is a set of permissions that you assign to a user. It lets the user perform only the specific operations defined in the Securiti application. A role defines the permissions across modules and limits users to authorized actions. It lets you apply proper access control by creating roles that match your business use cases and team structures.

A **Permission** is an explicit access control for actions within any feature of the Securiti platform. It lets a user perform create, read, update, or delete (CRUD) actions, depending on the module. Permissions can also follow a parent–child relationship, where selecting one permission automatically selects related permissions.

For example, selecting a manager-level or administrator-level permission can auto-select all CRUD permissions for that module.

Securiti provides you with two types of roles:

| Role type | Description |
| --- | --- |
| Default roles | Securiti offers specific default roles that are pre-generated roles that are usually module-specific and contain predefined permissions. You can assign these default roles when creating a new user. They provide access to specific functionalities, and while most permissions are fixed, a limited set of permissions can be edited within these roles. For more information, see permissions with default roles. |
| Custom roles | Custom roles let you create new roles with selected permissions from each module. You can combine permissions from multiple modules into a single role. This lets you define roles tailored to your users and business use cases. For more information, see [Fine-grained permissions with custom roles](/latest/docs/rbac-permissions). |

## Roles and Permissions from older RBAC

A role contains a list of permissions, and each module defines its own set of permissions under Role-Based Access Control (RBAC). The new RBAC framework introduces fine-grained, module-level permissions, while still supporting Access Profile permissions from the older RBAC framework. These include the following permissions:

| Role title | Role description |
| --- | --- |
| Module User | It has the view-only permission for all the data within the selected modules. |
| Module Owner | It has the create/read/update/delete permissions for all the data within the selective modules. |

**Important**

> [!WARNING]
> Important
> 
> Only a few modules support permissions from Access Profiles due to specific use cases. All other modules now support the new RBAC framework. For the Access Profile supporting modules, see the list below:
> 
> - Data Mapping Automation
> - Data Subjects Rights
> - Data Breach Management
> - Cookie Consent Management
> - Universal Consent Management
> - Mobile App Consent Management
> - Privacy Center

## View Roles page

The Roles page displays all the available roles and the number of users assigned to each role.

To access the Roles page:

1. Open the Roles page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-246tedsj.png)

It displays all the available roles with relevant information.
  1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
  2. From the Platform Services section in the new navigation, select **Settings**.
  3. From the Settings menu, choose **Organizational > Access Management > Roles**.

### Create a new role

Securiti lets you create your own custom roles where you can select fine-grained permissions in different modules.

To create a new custom role:

1. Open the **Roles** page.
  1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
  2. From the Platform Services section in the new navigation, select **Settings**.
  3. On the left navigation under the Organizational, choose **Access Management > Roles**.
2. On the top right of the **Roles** page, click **+ Create a Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-k1m0cwvt.png)

1. On the **Create Role** page:
  1. Configure the following parameters:

| Parameter | Description |
| --- | --- |
| Role Name | Enter the convenient name of the role. The role is identified by this name across all use cases. |
| Description | Enter a summary to describe the role’s purpose. |
| Make Role Eligible for Service Account Use | Mark this to make this custom role available for Service Accounts. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-N6JDPPRE.png)
  2. Under the Permissions section in the left panel, click the module for which you want to assign the permissions.
    1. It opens the permissions in the right panel, available for the selected module
  3. In the right panel, mark the checkboxes for permissions that you want to assign to this role.
    - Modules that are not supported for new RBAC show you only Module Owner and Module User permissions.

> [!NOTE]
> Note
> 
> If you select permissions from the module not supported in the new RBAC, you can’t select the permissions for modules supported in the new RBAC.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IOOS8D7P.png)
    - Modules that are supported for the new RBAC show you fine-grained permissions.

> [!NOTE]
> Note
> 
> If you are using the default role, you might not be able to edit specific permissions due to predefined restrictions. For more information, see [permissions with default roles](/latest/docs/rbac-permissions-with-default-roles).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VT0SQCJ5.png)
    - Each permission you select might contain a dependent permission within the same module or other modules. For more information on permissions and their dependent permissions based on a specific module, see [permissions with a custom role](/latest/docs/rbac-permissions).
2. Once select all the permissions you need, click **Save Role**.

It redirects you to the Roles page. The role you created appears at the top of the listing roles.

### Edit or delete a role

After creating a role, you can update the role details or delete it.

To update an existing role:

1. Select a role from the Roles list.
2. On the right side of the role, click **Option (three dots)** and click **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-v03vleb5.png)
3. It displays the same Create Role page. Modify the details and click save.

It updates the role with the updated details.

### Clone a role

The **clone role** feature lets you make a copy of an existing role. This helps when you want to make a slightly different change in a role that has several permissions. You can clone and make the changes to create a new role.

To clone a role:

1. Select a role that you want to clone.
2. On the right side of the role, click **Option (three dots)** and select **Clone**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-f89thqdd.png)

1. A **Clone role** popup appears. Update the details of the new cloning role.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-z2e05t40.png)

1. When finished, click **Clone**.

It clones the role.

It does not let you update the permissions on the **Clone role** tab. To update the permissions, see Edit role.

### Apply filters

Filters help you list down specific data on your Roles dashboard. It helps you search the roles or users with some conditions or specific information. It also lets you save your applied filter.

To apply a filter on the roles:

1. To select the filter, click on the plus (+) button at the start of the **Roles** page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-3ay4khl0.png)

It displays the search filter popup.

1. Apply the filter using the following values:

| Filter attribute | Description |
| --- | --- |
| Role Name | It lets you enter the role name to search through all available roles. |
| User | It lets you select a specific user to view the roles assigned to that user. |
| Role | It lets you select roles from the list of roles to meet the selected condition. |
| Created on | It lets you select a role creation date or a date condition to list the roles meeting this condition. |

It also provides several conditions to meet in the search filter.

| Filter condition | Description |
| --- | --- |
| Is equal to | It lets you filter roles that exactly match the entered value. |
| Is not equal to | It lets you filter roles that do not match the entered value. |
| Contains | It lets you filter roles that include the entered value anywhere in the name. |
| Does not contain | It lets you filter roles that exclude the entered value from the name. |
| Starts with | It lets you filter roles that begin with the entered value. |
| Does not start with | It lets you filter roles that do not begin with the entered value. |
| Is one of | It lets you filter users that match any value from a selected list. |
| Is not one of | It lets you filter users who do not match any value from a selected list. |
| Before | It lets you filter records created before the selected date. |
| After | It lets you filter records created after the selected date. |
| Between | It lets you filter records created within a specific date range. |

1. Once finished, click **Apply** to view results with this filter.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-x6ojgfae.png)

It displays the filtered roles.

1. To clear the filter, on the right side of the filter button, click **Clear Search**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-icz7uehm.png)

1. Below the filter, use the search bar to search for the roles at runtime. It filters the roles as you type.
2. Use the Role, User, and Created on filter located right below the search bar. It lets you quickly filter the roles.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-awgfekog.png)

The Roles table displays all the roles with the following information:

| Parameter | Field description |
| --- | --- |
| Role Name | It displays the name of the role assigned during the creation process. |
| Role type | It displays the type of role from the following: - System role (Default role) - Custom role |
| Users | It displays the total number of users currently using this role. |
| Created on | It displays when this role was created. |
| Column selector | The column selector lets you list only specific columns. To update it: 1. On the right side of the column titles, click column selector. 2. In the popup, mark the columns you want to display. 3. Click Apply to show the selected columns. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-o05g86kh.png) |

### Save filter

When applying complex filters that provide you with accurate information, Securiti lets you save your applied filters so you do not need to reapply the complete filter.

To save a search filter:

1. Use the filter feature to apply a condition and list specific roles.
2. Click on **Save View** on the top right of the screen.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-7rv5wlhb.png)

It opens up the Save View popup.

1. In the **Save View** area, enter the following details.

| Parameter | Description |
| --- | --- |
| Group | From the menu, select the group where you want to save the view. If you do not have a group: 1. Click on the **Select a group** menu dropdown and click **Add New**. 2. In the **Enter Group Name** textbox, enter a name for your new group, then press Enter to save it. |
| Name | Enter a name to identify your saved view. |
| Description | Add a short description to explain the purpose of the view. |

It saves the filter.

### Load filter

After saving a filter, you can load the filter. It directly applies the saved filter to the filter tab and displays data accordingly.

To load a saved filter:

1. At the top right of the screen, click **Saved Views**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/roles-in-securiti-en-image-q6qjya4m.png)

It opens the saved filters on the left side of the screen.

1. Click on any filter name, and it applies the filter automatically.

## List of default roles

Securiti provides the following default roles that have access to specific permissions in the new RBAC. For more information, see [permissions with default roles](/latest/docs/rbac-permissions).

| Role name | Role description |
| --- | --- |
| Super Admin | An administrator with access to all Securiti functions and features across all organizations. |
| Organization Admin | An administrator with access to all Securiti functions and features within the organizations they belong to. |
| Operator | A user with access to all functions and features except creating and managing Securiti users. **Note** For Assessments, this role cannot bulk export assessments but can export them individually. |
| DPO | A Data Protection Officer responsible for ensuring the safety and security of personal data. |
| MODULE OWNER | A user with full access to a module, including creating, updating, deleting, and managing all its functions. |
| USER | A user with read-only access, limited to viewing data across modules. |
| Data Classification Manager | Manages data classification activities, including applying and reviewing classification rules across datasets. |
| SDI Evidence Analyst | Reviews and analyzes evidence collected from Sensitive Data Intelligence (SDI) scans. |
| SDI Analyst | Analyzes sensitive data intelligence findings and supports remediation tasks. |
| SDI Classification Reviewer | Reviews and validates classification results generated by SDI processes. |
| Discovery Scan Manager | Manages discovery scans, including scheduling, monitoring, and reviewing scan outcomes. |
| MODULE OWNER Self Service Portal User Profile ROLE | A user with full control of the Self Service Portal module. |
| GUEST Self Service Portal User Profile ROLE | A guest user with restricted access to the Self Service Portal module. |
| MODULE OWNER Data map User Profile ROLE | A user with full control of the Data Mapping module. |
| USER DSR User Profile ROLE | A user with read-only access to the Data Subject Rights module. |
| MODULE OWNER Data Breach User Profile ROLE | A user with full control of the Data Breach Management module. |
| DATA USER | A user with read-only access to datasets across supported modules. |
| GUEST Data map User Profile ROLE | A guest user with restricted access to the Data Mapping module. |
| USER Data map User Profile ROLE | A user with read-only access to the Data Mapping module. |
| USER Self Service Portal User Profile ROLE | A user with read-only access to the Self Service Portal module. |
| MODULE OWNER DSR User Profile ROLE | A user with full control of the Data Subject Rights module. |
| GUEST DSR User Profile ROLE | A guest user with restricted access to the Data Subject Rights module. |
| GUEST Control User Profile ROLE | A guest user with read and update access to a control they're assigned to, its assigned risk, and comments. |
