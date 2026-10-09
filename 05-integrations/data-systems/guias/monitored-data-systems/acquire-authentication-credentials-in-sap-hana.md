---
title: "Acquire authentication credentials in SAP HANA"
slug: "acquire-authentication-credentials-in-sap-hana"
updated: 2026-07-31T11:54:58Z
published: 2026-07-31T11:54:58Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-sap-hana"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in SAP HANA

1. SAP HANA Data system Connector requires the following parameters for Activation:

> [!NOTE]
> **Note**
> 
> We assume you have access to an active SAP HANA Database or its admin to obtain Credentials and grant SELECT privileges to all databases that require a scan before Connector Activation.
  - **Host** - The hostname or IP address of the SAP Instance.
  - **Port** - Port of the SAP Instance. The default value is "39041".
  - **User** - Username of the user for SAP Instance ([see below](/v1/docs/acquire-authentication-credentials-in-sap-hana)).
  - **Password** - Password for the user
  - **Database** - Name of the Database you want to scan.
2. Log in to SAP HANA.
3. To create and authorize User:

> [!NOTE]
> **Note**
> 
> This step documents how to create and authorize a user other than the system user.
  1. On the SAP HANA Administration Console, select **Systems** view **> Security > User**, then choose **New User**, as shown below.

![Creating_New_User.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27cd1145-e9d1-1081-3279-2cf63bf7b006.png)
  2. Enter a username and password in the New User tab, then mark the **No** radio button for "Force password change on the next logon".

![unnamed__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c398dfc-e1f4-a749-05ce-a7c8666cb64d.png)

> [!NOTE]
> **Note**
> 
> It prevents the requirement to change the password in the future.
  3. Near the upper right corner, click **Deploy** (green button), as shown below.

![unnamed__2_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-178e2837-8cb5-86da-a69e-ebcbfe0eb1bc.png)

You get a notification display confirming that the "TPCH user has been created."
4. Next, you must add roles and privileges. Use the matching procedure below:
  1. In the TPCH User window, select the Granted Roles tab, as shown below.

![unnamed__3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-085f5363-dea3-2a39-dd7a-ca4571445dc8.png)

Click **Add** (plus sign) and enter the following command to grant this role to the user:

```plaintext
RESTRICTED_USER_JDBC_ACCESS
```
5. Proceed to [Connecting the SAP HANA with Securiti](/latest/docs/connecting-the-sap-hana-with-securiti).
