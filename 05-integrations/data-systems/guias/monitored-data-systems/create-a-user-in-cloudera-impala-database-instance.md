---
title: "Create a user in Cloudera Impala database instance"
slug: "create-a-user-in-cloudera-impala-database-instance"
updated: 2026-07-02T21:02:37Z
published: 2026-07-02T21:02:37Z
canonical: "helpcenter.securiti.ai/create-a-user-in-cloudera-impala-database-instance"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a user in Cloudera Impala database instance

> [!NOTE]
> **Important**
> 
> This procedure assumes that you have an active database instance of Cloudera Impala available with admin access before connector activation.

Perform the following procedure to create a user in the Clouder Impala database instance.

1. Access the Hue portal via browser by entering the following URL.

`http://{your_cloudera_instance}:8888`

Replace the "{your_cloudera_instance}" part of the browser with your Cloudera Server IP. See the example below for the URL with the Cloudera server.

`http://111.222.111.22:8888`
2. Log in to the Hue portal using your admin credentials.

![login.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e6b3cfc-2278-567e-9c9d-2d01c79aad98.png)
3. On the top right in navigation, hover over the "username" menu, then click **Manage Users**.

![user-icon.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1fd75f40-49cd-c138-94c3-0982f646380e.png)
4. On the top of the **User Admin** page, click **Groups** tab. Make sure the **default** group has **impala access** permission in the **Permissions** column.

You can verify that **impala access** permission is available in the permissions list as shown below.

![groups-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1247816f-ada3-d1df-01df-3833e7b7e9ca.png)
5. On the top of the page, click **Users** tab. On the right side of the page, click **Add user**.

![add-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76d776b1-4df9-3491-d982-5b54dd39eb72.png)
6. On the **Create user** page, perform the following steps to create a user.
  1. On the **Step 1: Credentials (required)** tab, add the following parameters.

| Parameters | Description |
| --- | --- |
| Username | Enter a convenient username for the new user. See the example below. `Securiti-user` Record this username for the later use in the connector activation. |
| New Password | Enter a secure password for new user. Record this password for later user in the connector activation. |
| Password confirmation | Enter the password again to confirm the new password. |
| Create home directory | Mark the checkbox for **Create home directory**. |

Click **Next**.

![step1-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a27d686f-6f0b-9d74-8da3-3f76313226b3.png)
  2. On the **Step 2: Names and Groups** tab, add the following parameters.

| Parameter | Descritpion |
| --- | --- |
| First name | Enter your first name. See an example below. `John` |
| Last name | Enter your last name. See an example below. `Doe` |
| Email address | Enter your email address. See an example below. `John@testmail.com` |
| Group | Make sure you mark the checkbox for default under **Groups** section. |

Click **Next**.

![step2-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6d45d30-b64b-dbc8-6b81-1d6b074b5238.png)
  3. On the **Step 3: Advanced** tab, make sure **Active** checkbox is marked.

![step3-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3880b3d-5e38-46dc-580e-1afdbecfe8e3.png)
  4. Click **Add user**.

It redirects you to **Hue Users** page where you can see the details of new created user.
7. Before moving connector activation topic, you must have the following credentials:
  - Cloudera server IP
  - Username
  - Password
  - Port (Default port is 21050)
8. Proceed to [Connecting Cloudera Impala with Securiti](/latest/docs/activate-the-cloudera-impala-connector-in-securiti).
