---
title: "Configuration steps for non-admin users in ServiceNow Files"
slug: "configuration-steps-for-non-admin-users-in-servicenow-files"
updated: 2026-09-30T08:03:58Z
published: 2026-09-30T08:03:58Z
canonical: "helpcenter.securiti.ai/configuration-steps-for-non-admin-users-in-servicenow-files"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuration steps for non-admin users in ServiceNow Files

If you are a non-admin user, you must follow these steps to authenticate the ServiceNow Files connector in Securiti.

#### Assign roles to the non-admin user

1. On the ServiceNow dashboard, in the left-hand navigation, select **Organization> Users**.
2. In the User ID Column, click to select the user you want to assign roles.

![unnamed5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e12192ac-99ae-7bef-5012-8790c89aacda.png)
3. Near the bottom of the page, select the **Roles** tab and click **Edit**.

![unnamed4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a64fe022-e14b-8eec-80e4-3688c42c557a.png)
4. On the **Edit Members** page, from "Collection", search and select and the following roles. On the right side of the page, add the following roles to the **Roles List**. Click on **Save**.
  - **<*snc_platform_rest_api_access*>**: The role lets you access the following Platform Rest APIs.
    - Table API
    - Import Set API
    - Aggregate API
    - Attachment API
  - **<*admin*>**: This is the System Administrator role. The role provides access to all system features, functions, and data, regardless of security constraints.
  - **<*snc_read_only*>**: The role prevents you from creating, updating, or deleting records in the Database. Adding this role ensures only read-only access even if the admin role is assigned.

![unnamed3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad8390e1-050d-c509-f25c-47ade3dfc06d.png)

#### Create exception properties for OAuth Tables

For the non-admin user, you must configure Table exemptions (create, update, and delete restrictions) for OAuth Authentication to work.

> [!NOTE]
> **Note**
> 
> If you happen to use Basic Authentication to activate the ServiceNow Files Connector, or do not want to provide write exceptions to the system tables, you may skip this section.

> [!NOTE]
> **Note**
> 
> Since OAuth Authentication step happens via REST API, at the time of Token creation ServiceNow writes a meta value into the "oauth_credential" Table, then returns access and refreshes Token.
> 
> If you do not provide the write exceptions to the tables, OAuth process shows you an error. See this support thread for more information on why you require write access to the system tables.

1. On the ServiceNow dashboard, in the left-hand navigation search filter, enter **<*sys_properties.list*>** and press enter. The right-hand pane under System Properties displays the complete list of properties.

![unnamed2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d4ec31e-106d-40c7-38b7-929d3b6058ba.png)
2. In the search box at the top of the page, search for these properties individually and verify they already exist.
  - **<*glide.security.snc_read_only_role.tables.exempt_create*>**
  - **<*glide.security.snc_read_only_role.tables.exempt_write*>**
  - **<*glide.security.snc_read_only_role.tables.exempt_delete*>**
3. If the above properties do not exist, use the matching procedure below to add them.
  1. Near the upper left corner of the page, click **New**.
  2. Enter the values in the form as shown below.

![unnamed1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-395bec5e-1f66-8e40-07ea-73cac5864641.png)
    - "Name": **<*glide.security.snc_read_only_role.tables.exempt_create*>**
    - "Type": string
    - "Value": **<*sys_user_session*>**, **<*sysevent*>**, **<*syslog*>**, **<*syslog_transaction*>**, **<*sys_user_preference*>**, **<*sys_ui_list*>**, **<*sys_ui_list_element*>**, **<*sys_db_cache*>**, **<*user_multifactor_auth*>**, **<*oauth_credential*>**
  3. Repeat steps in **3b** twice with these changes in the Name field.

ServiceNow displays the page with the said properties created.

![unnamed.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cde8276-eeca-c692-4faf-250d684943c2.png)
    - **<glide.security.snc_read_only_role.tables.exempt_*write*>**
    - **<glide.security.snc_read_only_role.tables.exempt_*delete*>**
