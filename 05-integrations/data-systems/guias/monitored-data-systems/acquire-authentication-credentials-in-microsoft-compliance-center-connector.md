---
title: "Acquire authentication credentials in Microsoft Compliance Center connector"
slug: "acquire-authentication-credentials-in-microsoft-compliance-center-connector"
updated: 2026-07-20T20:10:54Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-microsoft-compliance-center-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Microsoft Compliance Center connector

## Logging in Microsoft Compliance Center

1. Log in to Microsoft Compliance Center account.
2. Microsoft Compliance Center uses the Privacy management module to run DSR and **Domain (or Account Id)** for Connector Activation.

> [!WARNING]
> **Important**
> 
> Domain (or Account Id) is your Office 365 tenant identifier. This is usually your company domain, for example, "democo.org".

## Acquiring authentication credentials

1. To record Tenant ID and domain for Connector Activation:
  1. Log in to your Azure Portal.
  2. On the top left, click **hamburger** icon.
  3. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  4. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976.png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
2. To enable Privacy management:

> [!NOTE]
> **Note**
> 
> This procedure assumes you have the required Microsoft or Office 365 license before enabling Privacy management. See [Get started with privacy management](https://docs.microsoft.com/en-us/microsoft-365/compliance/privacy-management-setup?view=o365-worldwide) for more information.
> 
> Also, the procedure informs how to set up the Privacy management trial. You can skip to the assigning roles section below if you've purchased the license.
  1. Visit [https://compliance.microsoft.com/](https://compliance.microsoft.com/)
  2. Select **Priva Subject Rights Requests** in the left-hand menu under Solutions.

On the welcome screen, click **Visit the Microsoft 365 admin center to get your trial license**, as shown below.

![Free_trial.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a60c121f-68fb-6ac0-a8f5-5cec5d7db411.png)

![Click_to_avail_free_trial.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48311677-b8ba-5dc1-d317-241f3d06be6a.png)
  3. Click **Start free trial**, then **Try now** on the following pages, as shown below.

![Start_free_trial.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86d3f3c4-bfec-5166-4819-ce0c4b485a97.png)

![Try_now.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b310bb60-4eb2-0f85-aeaf-4c75ac4731ee.png)
  4. Click **Continue** to confirm order receipt.

![order_receipt.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4399bee2-a233-a342-45f7-a63424dada9c.png)
  5. It then redirects you to the homepage of the admin portal indicative of the trial license added for Privacy management, as shown below.

![Display_screen.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f204fd1d-6381-f8f6-251d-fa5534e0fcb6.png)
  6. (Optional) To check for the Privacy management module in your Microsoft products list, visit [https://admin.microsoft.com/adminportal/home?#/subscriptions](https://admin.microsoft.com/adminportal/home?#/subscriptions), as shown below.

![Your_products.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-876fe32f-eae9-b598-d255-2257be681e68.png)
3. After you've enabled the Privacy management module, you must assign the required roles. Use the matching procedure below:
  1. On the Microsoft Compliance home page, select **Permissions** from the left-hand menu.

![permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4bef171-11af-6d4f-be22-39208b173782.png)
  2. Select **Compliance Center > Roles** under Permissions & roles, as shown below.

![permissions_and_roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5634d07e-b481-f157-71c6-c3cabcd2db5e.png)
  3. On the Compliance center roles page, mark the checkbox to the left of the group name you want to add users.
  4. Click **Edit role group** on the flyout menu for that group, as shown below.

![edit_role_group.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce807611-cef3-19ba-40e6-0610915e2bf7.png)
  5. Select **Choose members**, then click on **Choose members** again under Editing Choose members window.
  6. Click **+ Add** to add members to the group, as shown below.

![add_members.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8fdfc3ce-0ef4-a7cf-f95c-894d0c7fbdbe.png)
  7. Mark the checkboxes against the names you want to add and click **Add** at the bottom, as shown below.

![add.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6821f24d-5ad8-a161-9029-58166832f179.png)
  8. Once you've selected the members, click **Done** and then **Save**.

![done.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50f31107-2f0f-49dc-6492-0f8a051701a5.png)

![save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b7cbdf9-c2ef-a9dd-1fb6-d183d0852850.png)
  9. Now click **Close.**

![close.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e59e209-348b-874b-2bc6-fa1bdc423144.png)

> [!NOTE]
> **Important**
> 
> It may take up to 30-45 minutes for licenses or roles to apply.
  10. On the following page, click **Agree and continue**. After which, you can start creating requests, as shown below.

![agree_and_continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9556ce9-7001-7342-cda0-9d5dfccd6163.png)

![agree_and_continue_contd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92fc6b73-d912-1f29-59c8-2beebbf93476.png) ![create_requests.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8f67545-5d78-4309-e9d6-9827418850a2.png)
4. Now you must assign the Privacy management license to those users you added in [Step 3](/latest/docs/acquire-authentication-credentials-in-microsoft-compliance-center-connector#acquiring-authentication-credentials).
  1. Visit your Admin portal at [admin.microsoft.com](https://admin.microsoft.com).
  2. On the User management card, click **Add user**, as shown below.

![User_management_card.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-206ecd59-e898-8085-aad1-1eb70c5d9d9d.png)
  3. Set up the Basics (name, display name, username, etc.).
  4. On the Product licenses, mark the checkbox for **Privacy management - risk**, as shown below.

![Mark_the_Privacy_management_-_risk_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0713e35c-a606-7e3b-d33c-feb22ff479fc.png)

Click **Next.**
  5. Configure any Optional settings and then Finish to complete the process.
  6. As shown below, you'd get the following message when you assign the license to the concerned user.

![license_assigned_message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27aed26b-8b36-7964-54a9-de6f1e2b6e3d.png)
5. Proceed to [Connecting Microsoft Compliance Center connector with](/latest/docs/connecting-microsoft-compliance-center-with-securiti) Securiti.
