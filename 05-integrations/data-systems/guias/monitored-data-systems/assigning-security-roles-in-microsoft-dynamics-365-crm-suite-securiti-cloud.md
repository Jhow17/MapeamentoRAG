---
title: "Assigning security roles in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)"
slug: "assigning-security-roles-in-microsoft-dynamics-365-crm-suite-securiti-cloud"
updated: 2026-07-28T10:56:42Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/assigning-security-roles-in-microsoft-dynamics-365-crm-suite-securiti-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Assigning security roles in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)

After you have obtained the account domain, you can select one of the following options for security role for Microsoft Dynamics 365 CRM Suite Connector.

1. **Basic User**: Selecting this option scans only the tables you have read access to. See the procedure below to assign the **Basic User** role.
2. **Custom Security Role**: We recommend creating a custom security role for your Dynamics CRM Connector. See the matching procedure below to create a custom security role.

### Assigning Basic User role in the Power Platform admin center

1. Log in to [Power Platform admin center](https://admin.powerplatform.microsoft.com/) and sign in with an admin account which is used to provide authorization during Microsoft Dynamics 365 CRM Suite Connector Activation.
2. On the admin center dashboard, in the left sidebar, click **Environments**. The page displays all the active Environments (applications) associated with your admin account.

![select_environments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae5e3149-a85d-6162-e16a-5cba10fc35d4.png)

![dynamicCRM_allEnvironments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f86b1ca-33af-64f5-231a-319b5802e299.png)
3. From the top of the page, click **Settings** for your Microsoft Dynamics 365 CRM Suite Instance.

![click_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6876c651-a780-f438-4237-2b6d50969f36.png)
4. Expand the **Users + Permissions** section, select your user and from the top Row of the page, select **Manage Security Roles**.

![unnamed4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52fcbced-5176-5f4a-88b1-b78daf1489cd.png)
5. Choose **Basic User**.

![dynamicsCRM_basicuser.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a58e173-4fe6-22dc-9f1a-41502928c9a1.png)
6. (Optional) If you do not have the user present, you can add one by clicking Add user and entering their email address.

### Creating custom security role in the Power Platform admin center

1. Log in to [Power Platform admin center](https://admin.powerplatform.microsoft.com/) and sign in with an admin account which is used to provide authorization during Microsoft Dynamics 365 CRM Suite Connector Activation.
2. On the admin center dashboard, in the left sidebar, click **Environments**. The page displays all the active Environments (applications) associated with your admin account.

![select_environments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae5e3149-a85d-6162-e16a-5cba10fc35d4.png)

![dynamicCRM_allEnvironments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f86b1ca-33af-64f5-231a-319b5802e299.png)
3. From the top of the page, click **Settings** for your Microsoft Dynamics 365 CRM Suite Instance.

![click_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6876c651-a780-f438-4237-2b6d50969f36.png)
4. Expand the **Users + Permissions** section and select **Security Roles**.

![dynamicsCRM_securityroles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c78017dd-db55-926e-2635-021ad1f1e5e9.png)
5. From the top left corner of the page, click **New Role.**

![dynamicsCRM_newrole.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de6ccd66-50b7-1ad4-7ddc-9c2b795df80f.png)
6. Enter the values such as name, business unit for your role as shown in the screenshot below.

![dynamicsCRM_createnewrole.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c0345be-3878-c4c8-e9b6-81497dad3b7b.png)
7. In the **Tables** section, assign Permissions for the **Read** Column by selecting your organization. Securiti scans the data within the organization selected.

![dynamicsCRM_readcolumn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b3c2bd7-986d-311c-0ddd-b3ad1b4ea54a.png)
8. From the top of the page, click **Copy Table Permissions** to apply same Permissions to all tables you want to include in scanning.

![dynamicsCRM_copytablepermissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65be70cc-4fc4-37e8-eb3b-4f9cddceca2d.png)
9. Select the tables you want to copy the Permissions to and click **Save**.

![dynamicsCRM_selectTables.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e93a7a0-2cb5-e11b-5ad2-c3a6a6b32cb4.png)
10. Proceed to [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-securiti-cloud).
