---
title: "Create a custom Security role for Dataverse in the Dynamic CRM app."
slug: "create-a-custom-security-role-for-dataverse-in-the-dynamic-crm-app"
updated: 2026-07-06T03:56:08Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/create-a-custom-security-role-for-dataverse-in-the-dynamic-crm-app"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a custom Security role for Dataverse in the Dynamic CRM app.

> [!NOTE]
> **Note**
> 
> This procedure assumes you have admin access to Microsoft Power Platform.

## Create a custom security role

Perform the following steps to create a custom Security role for Dataverse application.

1. Log in to your [Microsoft Power Platform account](https://admin.powerplatform.microsoft.com/) with admin Credentials.
2. On the **Dashboard**, expand the left sidebar using the hamburger icon.
3. On the left sidebar, click **Environments**. It shows a list of all the active Environments (applications) associated with your admin account.
  1. Select the **Microsoft Dynamics 365 CRM Suite** Instance from the Environments list.
  2. On the top of the page, click **Settings**.

![leftside-custom.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc9e3644-e9ba-6216-af57-5f3ceeb39895(1).png)
4. On the **Settings** page, expand **Users + Permissions** and select **Security roles**.

![Setting-roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71f709bc-4b7f-05b5-de90-e040114908f9.png)
5. On the **Security roles** page at the top, click **New Role**.

![security-new-role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e94acf30-f716-4a6b-59ad-23346604aac1.png)
6. On the **Create New Role** page, configure the following parameters:

| Parameters | Exaplanation |
| --- | --- |
| Role Name | Enter a convenient Role Name for this custom role. |
| Business unit | Select the Business unit from the menu. |
| When a role is assigned to a Team | Select the privilege role from the menu. |
| Include App Opener priviliges for running Model-Driven-Apps | Mark the checkbox for this option. |

Click **Create**.

![security-create-role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f39a511-e0c2-e7a4-4845-7137ee17078e.png)
7. On the newly created role page, assign the read permission to each Table in the list using the following procedure.
  1. In the **Read** Column, assign the permission by selecting **Organization** so that the data within the organization can be scanned at the top.

![org-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bac1442-1ef6-f808-1de8-dd2354a0e0a4.png)
  2. You can copy the Permissions of one Table and apply to other tables instead of doing the same operation for all tables.

> [!NOTE]
> **Note**
> 
> Copy Table Permissions only appears if you select at least one Table from the list to copy permission to other tables.
    1. At the top of the page, click Click **Copy Table Permissions**.

![copy-table-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fbabcdfb-f2c4-0320-9195-44305a808afb.png)
    2. Mark the checkboxes for the tables you want to copy the Permissions to and click **Save**.

![copy-perm-to.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-01a92caa-bfdc-8897-2082-75a817dddf01.png)
8. Proceed to [Grant permissions and obtain credentials in Microsoft Dataverse](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dataverse) to complete the remaining section of Authentication Credentials.
