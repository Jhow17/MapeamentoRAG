---
title: "Configuration steps for non-admin users in ServiceNow Tables"
slug: "configuration-steps-for-non-admin-users-in-servicenow-tables"
updated: 2025-10-31T06:56:24Z
published: 2025-11-03T07:34:02Z
canonical: "helpcenter.securiti.ai/configuration-steps-for-non-admin-users-in-servicenow-tables"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuration steps for non-admin users in ServiceNow Tables

If you are a non-admin user, you must follow these steps to authenticate the ServiceNow Tables Connector in Securiti.

#### Assign roles to the non-admin user

1. On the ServiceNow dashboard, in the left-hand navigation, select **Organization> Users**.
2. In the User ID Column, click to select the user you want to assign roles.

![unnamed5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e12192ac-99ae-7bef-5012-8790c89aacda(1).png)
3. Near the bottom of the page, select the Roles tab and click **Edit**.

![unnamed4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a64fe022-e14b-8eec-80e4-3688c42c557a(1).png)
4. On the **Edit Members** page, from "Collection", search and select and the following roles. On the right side of the page, add the following roles to the **Roles List**. Click on **Save**.
  - **<*snc_platform_rest_api_access*>**: The role lets you access the following Platform Rest APIs.
    - Table API
    - Import Set API
    - Aggregate API
    - Attachment API
  - **<*admin*>**: This is the System Administrator role. The role provides access to all system features, functions, and data, regardless of security constraints.
  - **<*snc_read_only*>**: The role prevents you from creating, updating, or deleting records in the Database. Adding this role ensures only read-only access even if the admin role is assigned.

![unnamed3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad8390e1-050d-c509-f25c-47ade3dfc06d(1).png)

#### Create exception properties for OAuth Tables

For the non-admin user, you must configure Table exemptions (create, update, and delete restrictions) for OAuth Authentication to work.

> [!NOTE]
> **Note**
> 
> If you happen to use Basic Authentication to activate the ServiceNow Tables Connector, you may skip this section.

1. On the ServiceNow dashboard, in the left-hand navigation search filter, enter **<*sys_properties.list*>** and press enter. The right-hand pane under System Properties displays the complete list of properties.

![unnamed2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d4ec31e-106d-40c7-38b7-929d3b6058ba(1).png)
2. In the search box at the top of the page, search for these properties individually and verify they already exist.
  - **<*glide.security.snc_read_only_role.tables.exempt_create*>**
  - **<*glide.security.snc_read_only_role.tables.exempt_write*>**
  - **<*glide.security.snc_read_only_role.tables.exempt_delete*>**
3. If the above properties do not exist, use the matching procedure below to add them.
  1. Near the upper left corner of the page, click **New**.
  2. Enter the values in the form as shown below.

![unnamed1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-395bec5e-1f66-8e40-07ea-73cac5864641(1).png)
    - "Name": **<*glide.security.snc_read_only_role.tables.exempt_create*>**
    - "Type": string
    - "Value": **<*sys_user_session*>**, **<*sysevent*>**, **<*syslog*>**, **<*syslog_transaction*>**, **<*sys_user_preference*>**, **<*sys_ui_list*>**, **<*sys_ui_list_element*>**, **<*sys_db_cache*>**, **<*user_multifactor_auth*>**, **<*oauth_credential*>**
  3. Repeat steps in **3b** twice with these changes in the Name field.

ServiceNow displays the page with the said properties created.

![unnamed.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cde8276-eeca-c692-4faf-250d684943c2(1).png)
    - **<glide.security.snc_read_only_role.tables.exempt_*write*>**
    - **<glide.security.snc_read_only_role.tables.exempt_*delete*>**

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
