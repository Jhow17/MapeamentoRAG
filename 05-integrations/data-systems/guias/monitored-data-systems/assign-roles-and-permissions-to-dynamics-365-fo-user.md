---
title: "Assign roles and permissions to Dynamics 365 Finance & Operations user"
slug: "assign-roles-and-permissions-to-dynamics-365-fo-user"
updated: 2026-07-20T20:13:17Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/assign-roles-and-permissions-to-dynamics-365-fo-user"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Assign roles and permissions to Dynamics 365 Finance & Operations user

Perform the following steps to assign roles and permissions to the Dynamics 365 F&O user.

1. Log in to your Dynamics Finance & Ops account using the URL provided by the Microsoft Dynamics 365 team.
2. On the Dashboard in the left sidebar, choose **Modules > System administration > Users > Users**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assign-roles-and-permissions-to-dynamics-365-fo-user-en-image-tldov4cx.png)
3. On the **Users** page, search for the user who plans to activate the connector in Securiti. Make sure the specific user exists in the users list. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assign-roles-and-permissions-to-dynamics-365-fo-user-en-image-udkezj4i.png)
4. Locate the user in the **Users** page, and click on the user's email to assign the roles.
5. On the **User’s role** page, click **Assign roles**.
6. On the **Assign role** to user dialogue box, assign the following roles, and click **OK**.
  - System administrator
  - System user
    - Office integration power user
    - Power Automate administrator
  - User secure groups ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assign-roles-and-permissions-to-dynamics-365-fo-user-en-image-v7sapi96.png)
7. On the left sidebar, choose **Modules > System administration > Setup > Microsoft Entra ID applications.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assign-roles-and-permissions-to-dynamics-365-fo-user-en-image-3lk54uxd.png)
8. On the top of the **Microsoft Entra ID applications** page, click **New**.
9. On the following page, add the following information:
  1. Add the **Client Id** of the Azure app you created earlier.
  2. Enter a convenient name in the Name column.
  3. Add the **User ID** to assign the app credentials to the user. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assign-roles-and-permissions-to-dynamics-365-fo-user-en-image-ezlk2l9n.png)
10. Proceed to [Connect Microsoft Dynamics 365 Finance & Operations Connector in Securiti](/latest/docs/connect-microsoft-dynamics-365-finance-operations-connector-with-securiti).
