---
title: "Configuring integration with private and shared Microsoft channels"
slug: "configuring-integration-with-private-and-shared-microsoft-channels"
updated: 2026-09-22T05:26:25Z
published: 2026-09-22T05:26:25Z
canonical: "helpcenter.securiti.ai/configuring-integration-with-private-and-shared-microsoft-channels"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring integration with private and shared Microsoft channels

Microsoft Teams currently allows apps only in public channels and does not allow the addition of app in private or shared channels. To address this limitation, to integrate your app with private and shared channels, you must add a private user bot. This private user bot is created in your Microsoft Teams account and linked to Securiti. To interact with your app in your private channel, tag the Private User Bot and ask your query. This private user bot responds on behalf of your app.

### Prequisites

To enable integrations with private and shared channels, you must have the following:

- The created private user bot must be a member of the client’s Microsoft tenant.
- You must have the **Office 365 Business license** (Microsoft 365 Business Basic / Microsoft 365 Business Standard) to post queries and receive responses to messages. It is mandatory to have Microsoft 365 license to enable integration of your app with MS Teams private channel. The Microsoft 365 license is required to work with the Microsoft Teams Graph APIs, therefore, without it, the private user bot cannot respond to your query through an Access Token. You can assign the license through the Microsoft Admin panel.

### Creating Private User Bot

To create your private user bot:

1. Go to your [Azure](http://portal.azure.com) portal.
2. Go to your Microsoft Entra ID.

![MS_Entra_ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e7a92add-83e3-6b48-7fb9-c3c639a65327(1).png)
3. On the left panel, click **Manage > Users**.

![Azure_left_panel_-_Users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58df7ba7-5600-a1c2-de94-5e2c578002de(1).png)
4. On the Users page, click **New User > Create New User**.

![Azure_Users_page_Create_new_User.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24171983-1df3-4603-737b-5ac88de0fee2(1).png)

The **Create New User** form displays.

![Azure_-_Create_New_User_form.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd67d2d9-211e-a78b-5e7d-b4ac79318953(1).png)
5. Enter the following information:
  1. User Principal Name
  2. Demo display name
  3. Password
6. Click **Next: Properties**.
7. Click **Create**. The user is listed.

![Created_User.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-416aa010-2491-36dd-8a2d-dbbe3d2f0bde(1).png)
8. Once the user is created successfully, link the user to your Microsoft Account.

### Link Private User to Microsoft Account

To link the created private user to your Microsoft account:

1. To add the Microsoft365 license, go to your Microsoft admin portal.
2. Go to **Home > Licenses**.

![MS_365_licences_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca7df824-bd97-7fd7-d025-c1ece4e4bb58(1).png)
3. Click on any Microsoft 365 business license.

> [!NOTE]
> **Note**
> 
> You can select any Microsoft 365 business license.

![MS_365_business_standard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4710228a-be9c-9564-ecfc-d08bd1197132(1).png)
4. Click **Assign Licenses**.

![Assign_License_MS_365_business_standard_copy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00087ed2-cb82-6f38-5cc2-a9e284b5f206(1).png)

The **Assign Licenses to users** form displays.
5. Enter the name or email address of the created user.

![Assign_Licenses_to_users_form.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-092b38ea-952b-9ba8-9595-68d7c3c57b03(1).png)
6. Click **Assign**.
7. Once the user is assigned, add it to your Securiti tenant. The assigned user is connected to your MS Teams app on your Securiti tenant.

> [!NOTE]
> **Note**
> 
> One Microsoft tenant can have one bot assigned. If you have a bot assigned, disconnect that and connect the new User.

#### Adding Private User Bot on Securiti

To add a private user bot:

1. Go to the **Gencore AI > Settings > Gencore AI > Messaging Integrations** page.
2. To the right of your Microsoft Teams app, click the **Details** option.

![MSTeams_Details_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12c70de4-a747-a881-a7e0-9e882d5299fa(1).png)

A **Connection Details** popup displays.

![Connection_Details_Upt_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-276613c6-e9d3-a3c8-7fb4-59e0be2aaaf4(1).png)
3. Under the **Whitelist URL** section, copy the URL. This URL must be whitelisted on the Azure Portal.

![Connection_Details_Upt_Labelled_Whitelist.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc1d4dc6-579c-97b7-847d-5c061128b820(1).png)
4. To whitelist the URL on the Azure Portal:
  1. Go to your [Azure](http://portal.azure.com) portal.
  2. Navigate to the **Authentication** page.

![Azure_-_Authentication_Section.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ff245cb-0251-8d84-0338-1d69cf7deb9b(1).png)
  3. Under **Platform Configurations**, click **Add a platform**.

![Add_a_platform.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-817e9b5f-76d8-55f4-d4aa-3ab8c35f4c87(1).png)
  4. On the right side panel, select **Web**.
  5. Under Configure Web, place the copied URL.

![Azure_Configure_Web.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b57a6c4e-0561-f3a4-b5ee-77ffc60ae245(1).png)
  6. Click **Configure**.

![Configure_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cdd9aaf-cba2-1bb7-5fe7-f44d3c95012b(1).png)
5. On Securiti , in the **Connection Details** popup, click **Connect Bot**.

![Connection_Details_Upt_Labelled_Connect_Bot.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d6ff2e7-39f6-b90a-6cc6-377bdc0c908b(1).png)
6. Log in to your Microsoft account using the credentials of the created private user.
7. After successful log in, the bot is successfully connected.

![PrBot_Connected_Accounts.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96039643-e9d5-cda2-31b7-c5965f25c79b(1).png)
8. To disconnect the bot, click **Disconnect Bot**.

### Adding Private User Bot to your MS Teams Team/Channels

To add the private user bot as a member to your MS Teams Team:

1. Go to your Microsoft Teams app.
2. Select the Team you want to add the private user bot to.
3. Go to the **Members** tab. If the Bot User is not a member of the team, you must first add the Bot User to the team and then to the desired channel.
4. Click **Add Member**.
5. Enter the email address for the private user bot.
6. Click **Add**.
7. When the user is added to your private channel, [link your pipeline to the channel](/latest/docs/configuring-user-portal-pipelines#linking-genai-pipelines).Messaging App Integrations

When the channel is successfully linked to your pipeline and the private user bot is ready to communicate, a welcome message appears on the Microsoft Teams private channel.

If no welcome message is displayed, check that the prerequisites are addressed. Refer to the FAQs section for more information.

#### Frequently Asked Questions (FAQs)

---

### FAQ

#### Q: **Why am I not able to integrate my private user bot with Securiti?**

A: Ensure the following:

- Integrate Securiti with any one of your public Microsoft Teams channels.
- Add a Microsoft 365 Business license.

#### Q: **How do I connect private user bot to connect my channel?**

A: Ensure the following:

- Connect your private user bot from the Messaging App Integrations page on Securiti.
- Add a Microsoft 365 Business license.

#### Q: **Why am I not able to integrate my private MS Teams channel with Securiti?**

A: Ensure the following:

- Copy the **Allowlist URL** on Securiti and add it to your Azure Portal.
- Add relevant permissions for the private user bot.
- Add a Microsoft 365 Business license.

#### Q: **Why is my user bot not responding?**

A: Ensure the following:

- Add a Microsoft 365 Business license.
- The user bot is added as a member of the team and the relevant channel.
- Attach the pipeline to the relevant channel.

#### Q: **Why did I not receive the Welcome message after linking the pipeline?**

A: Ensure the following:

- Copy the **Allowlist URL** on Securiti and add it to your Azure Portal.
- Add relevant permissions for private user bot.
- Add a Microsoft 365 Business license.
- The user bot is added as a member of the team and the relevant channel.
- Attach the pipeline to the relevant channel.

#### Q: **My private user bot user was working before. Why has it stopped responding?**

A: Ensure the following:

- The private user bot is not removed.
- The attached pipeline is not disconnected from the relevant channel.

## Related

- [Configuring custom messaging apps](/configuring-custom-messaging-apps.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
