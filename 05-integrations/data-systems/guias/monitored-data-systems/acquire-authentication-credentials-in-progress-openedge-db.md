---
title: "Acquire authentication credentials in Progress OpenEdge DB"
slug: "acquire-authentication-credentials-in-progress-openedge-db"
updated: 2026-07-08T03:19:35Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-progress-openedge-db"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Progress OpenEdge DB

## Logging in Progress OpenEdge DB Cloud

1. Log in to the Progress OpenEdge DB Cloud.

1. Record these parameters to use later:
  - Host Name (machine's public IP on which Progress DB is installed)
  - Port
  - User Name
  - Password
  - Database Name

## Creating a Machine

1. To create a machine with Progress OpenEdge DB installed:
  1. Near the bottom of the **Product Showroom** page, Click **Create** in "Published Deployments".
  2. On the same page, click **Start** in "My Deployments".
  3. Then click **Connect** in "My Instances". This connects Progress DB to Remote Desktop Protocol (RDP).

![Product-Showroom_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6628fae0-7550-e93d-5b01-3c13c8c277b4.png)
2. Go to **Start > Programs > Progress OpenEdge > Proenv** to access the Progress DB terminal in Windows.

## Creating a Database

1. Create a Database by typing in **prodb <db-name>** in the terminal.

You can assign any name to it which then becomes your **Database Name**.
2. Start the Database by typing in **proserve <db-name>** in the terminal.
3. Enter any number for **Port**, as shown below.

![Port-Number_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f3a90eac-ddaf-c169-537c-80666af1f452.png)
4. Shut down the Database by typing in **proshut <db-name>** in the terminal.

## Creating a User

1. To create User:
  1. Repeat steps 1-2 above in [Creating a Database](/latest/docs/acquire-authentication-credentials-in-progress-openedge-db#create-a-database).
  2. Initiate the Data Administration Tool from the terminal by using:
    - **prowin32 dbname -p _admin.p** on Windows
    - **prowin3dbname -p _admin.p** on Windows (64)
  3. From the "Database Administration" menu, select **Admin > Security > Edit User List**.

![Edit-User-List_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f763d7ed-a859-9db9-0705-aaa278364761.png)
  4. On the following dialog, set your **User Name** and **Password**. Then click **Add**, as shown below.

![Add_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a8f5d68-c54a-c283-a903-093d1f40b2f3.png)

It is recommended to use "SYSPROGRESS" as the User Name.
  5. Click **OK**.
2. Proceed to [Connect Progress OpenEdge DB connector with](/latest/docs/connect-progress-openedge-db-connector-with-securiti) Securiti.
