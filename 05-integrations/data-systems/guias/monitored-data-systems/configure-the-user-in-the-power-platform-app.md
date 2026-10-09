---
title: "Configure the user in the Power Platform app"
slug: "configure-the-user-in-the-power-platform-app"
updated: 2026-07-28T11:08:25Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/configure-the-user-in-the-power-platform-app"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure the user in the Power Platform app

If you want to store and manage Credentials for the Microsoft Dynamics CRM data system:

1. Open [https://admin.powerplatform.microsoft.com/](https://admin.powerplatform.microsoft.com/) and sign in with the admin account you used to authorize the Microsoft Dynamics 365 CRM Suite Data system Connector.
2. Once you are signed in, expand the sidebar and choose **Environments**.

![Step2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ba90558-73cd-cd64-00bc-0b942d8b2518.png)

You’ll see a list of all the active Environments (applications) associated with your admin account.

![Step3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bacba6d8-8019-52a2-e66f-6725d19fd7b4.png)
3. From the list of Environments, select the Microsoft Dynamics 365 CRM Suite instance and choose **Settings** from the menu bar.

![Step4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e108442a-9e0b-9a2f-7b46-9e62807f0f59.png)
4. Inside Settings, expand **Users + Permissions** and select **Application users**.

![Step5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ce347db-69f1-10f0-2334-9d1a27fdf172.png)
5. Click **+ New app user** to create a new user.

![Step6.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a29f308-cbed-8259-121b-6223ed870802.jpg)
6. Inside the Create a new App user menu, do the following steps:
  1. Find and select the app that you created to activate the Microsoft Dynamics 365 CRM Suite Data system Connector.
  2. Select the Business unit (organization) that is connected to the Microsoft Dynamics 365 CRM Suite instance.
  3. Assign **Basic User** as a Security Role to this user or create a **Custom security role**. For more information, see [Assigning security roles in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/assigning-security-roles-in-microsoft-dynamics-365-crm-suite-self-hosted).
7. Click **Create** to create this user.

![Step8.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37467eb1-c0f7-2dcd-8da5-9b56f25e6c2b.jpg)

> [!NOTE]
> **Note**
> 
> The App ID corresponding to this user is similar to the Client ID of the app that was selected during user creation.

Once you create the user, you see it listed in Application users.

![Step9.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-830961cc-f3f7-cf1c-d9ea-6081ab50ed43.jpg)

The newly created user has an **Active** state by default. It must be in an Active state to use the HashiCorp vault with Microsoft Dynamics 365 CRM Suite.
8. Proceed to [Connect Microsoft Dynamics 365 CRM Suite (Self-hosted) connector with Securiti](/latest/docs/connect-microsoft-dynamics-365-crm-suite-self-hosted-with-securiti).
