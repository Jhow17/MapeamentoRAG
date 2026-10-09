---
title: "Acquire authentication credentials in Confluence Data Center"
slug: "acquire-authentication-credentials-in-confluence-data-center"
updated: 2026-06-23T07:16:55Z
published: 2026-06-23T07:16:55Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-confluence-data-center"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Confluence Data Center

Confluence Data Center uses the PAT (Personal Access Token) authentication method. Following activation parameters are required to activate Confluence Data Center.

- Host URL - A complete host URL or IP address for Confluence (Self-hosted) data system.
- Personal Access Token - Access Token generated from Confluence application settings.

> [!NOTE]
> **Important**
> 
> A personal access Token must be created from the Administrator account as you can access other user's data from the Administrator account PAT, only.
> 
> The administrator account is the one that has access to the Confluence administration as shown in screenshot below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(631).png)
> 
> You can access Confluence Spaces if you are added as a member with view only or selective permissions in User Groups in the Confluence Data Center. See [this section](/v1/docs/acquire-authentication-credentials-in-confluence-data-center#adding-users-with-nonadministrative-permissions-in-confluence-data-center), for more information.

To acquire authentication credentials.

1. Connect your Confluence Data Center Self-hosted application to an appliance and save the **host URL or IP address** with port number, to log into the application.
2. Log in to [https://developer.atlassian.com/](/v1/docs/securiti-pods-and-elastic-pods) at your host IP address and port.
3. To create **Personal Access Token**, near the upper right corner of the page from your user profile, select **Settings**.

![CDC_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b9d01176-a441-58b8-f030-359b9bcdd3ce.png)
4. From the left menu, select **Personal access tokens** to create a Token.

![createtoken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ffd37a5-60d0-ddb6-4fcc-1add5024f114.png)
5. Enter the Token name and uncheck the **Automatic expiry** box to never expire the Token. Click **Create**.

![CDC_create_pat.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5db579b-0087-799e-ae68-077ac08922da.png)
6. Confluence displays a page listing all access tokens with their expiry dates. Copy the PAT you created and save it to use later.

![personal-access-token-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a606149f-7b9d-47de-5d4e-50f520f5c5d7.png)
7. Proceed to [Connecting Confluence Data Center with Securiti](/latest/docs/connecting-confluence-data-center-with-securiti).

#### Adding users with non-administrative permissions in Confluence Data Center

You can still access Spaces in case you do not wish to use an administrator account. To add member with limited permissions in Confluence Data Center.

1. Log in to Confluence Data Center application.
2. Go to **Profile** and select **Administer User** from the left menu.
3. On the left sidebar, select **Groups**. And click **Add Group** to create a group named **Securiti**. Alternatively, use this link to access groups: /admin/users/browsegroups.action

![cdc_groups.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-77d967f7-3206-977f-b701-9b8ced89e2ef.png)
4. Click **Save**.
5. Click **Add members** to add users of your choice to the group.

![cdc_groupmembers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a4f9c52-2605-ce89-7f66-7fc05b6f9f1d.png)
6. Go to this link: admin/permissions/doeditdefaultspacepermissions.action to give access permissions to the group members. Select **Manage permissions** for your group.

![cdc_manage_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1a6629d-4612-20bb-8dd6-b1fa99b870fa.png)
7. Click **Edit Permissions** to set the permissions of your choice. For example, to set only view permissions, select **All View**. You can also add any restrictive space in **Individual Spaces**. Click **Save all**, after setting permissions to suit.

![cdc_set_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3499195c-7880-a81c-eb7d-bebe28ff173d.png)
