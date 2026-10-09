---
title: "Creating custom Slack apps"
slug: "creating-custom-slack-app"
updated: 2026-04-27T13:10:09Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/creating-custom-slack-app"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating custom Slack apps

To create a custom Slack messaging application:

1. Create the custom Slack app.
2. Configure the custom Slack app.
3. Connect the custom Slack app in Messaging Integrations.
4. Connect your GenAI pipeline with your custom slack app channel.

### Create the custom Slack App

To create your Slack App:

1. In the **Custom Apps** section, click **+ Add Custom App**.
2. Select Slack as the messaging app.

![Slack_Custom_App_Create_1_Labelled_Slack.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e3c20236-252c-d4d3-fb75-a2fe5e2fdf4d(2).png)
3. Enter a **name** for your custom app.

![Slack_Custom_App_Name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99f23741-8222-5f94-bd46-a56fca453a48(2).png)
4. To save changes, click **Save & Continue**. The **Custom Messaging App** popup appears.

![Slack_Custom_App_Create_App_Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6b5c2d42-56ba-302e-6707-e5ea9d83a3d9(2).png)

### Configure the custom Slack App

The **Custom Messaging App** popup appears with a visual guide for configuration.

![CMS-CMSA_popup_Setup_Guide.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f4f606a9-4d12-8efe-e595-04f9ab9060ea(2).png)

To configure your custom app:

1. On the **Custom Messaging App** popup, click **Create App**. This opens the Slack portal where you can configure the app.

![CMS_-_CMSA_Create_App_button_L.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9146ec17-defd-c29e-a7c5-f9f20e834a14(4).png)
2. Complete the configuration steps in Slack.
3. Return to the popup and click **Save and Continue** to move to the **Credentials** step.

![CMS_-_CMSA_Create_App_Save_and_Continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4e18b0c-11bd-c42e-7e41-2a0f23db5943(2).png)
4. In the **Credentials** tab, enter the credentials from [Slack App configuration](/v1/docs/creating-custom-slack-app):
  1. **Client ID**.
  2. **Client Secret**.
  3. **Signing Secret**.

![CMS-CMSA_Credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4a53380-0c0c-e374-a5ae-e7e01e122778(2).png)
5. To save and add your custom app, click **Save and Add**.

![CMS-CMSA_Credentials_Save_Add.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d840109-d776-7635-8820-f03b963b877c(2).png)

Your app is listed but disabled by default.

![List of Slack apps with their configuration status and creation dates displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/disabled custom app - slack.png)
6. To activate the app, toggle the **Active** switch.

![CMS-Enabled_Created_CMSA.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c42e6154-4b6a-4e73-9ee5-15f33d0e2db8(2).png)

#### Configure the App on Slack

When Securiti directs you from the **Custom Messaging App** popup to your Slack Portal, a popup displays.

1. Log in to your Slack account.
2. Select **Gencore Messaging Integrations** as your workspace.

![gencore_workspace_Slack_main.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ed2351b-1664-d936-db29-907a1156d398(2).png)
3. Click **Next**.

![gencore_workspace_Slack_next.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7def34e1-8b9e-07a4-0b18-83e8e6cf84c9(2).png)
4. Review the summary.

![CMS-CMSA_review_Summary.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10a6dd44-d5d6-4bb6-891e-ad7006fc4840(2).png)
5. Click **Create**.

![CMS-CMSA_review_Summary_Create.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba3ae16e-197b-2a4b-d9a9-cdafef68377d(2).png)

Slack displays the **Basic Information** section with credentials:
  - App Credentials:
    - App ID
    - Date of App Creation
    - Client ID
    - Client Secret
    - Signing Secret
    - Verification Token
  - App Tokens
  - Display Information

![Custom_App_-_Slack_Basic_Info.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3df1d78f-406f-47c3-dce5-6c3d9df23788(2).png)
6. Secure the following **App Credentials** to be used in [configuring your custom Slack app](/v1/docs/creating-custom-slack-app):
  - Client ID
  - Client Secret
  - Signing Secret

#### Managing the custom Slack App

You can edit or delete your custom Slack app using the **Options** (three-dot menu) next to the app listing.

- Edit configuration
- Delete

![CMS-Options_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0962349-195d-096b-a11b-f34c81823919(2).png)

#### Editing Slack App configuration

To edit the configuration for the Slack app, to the right of the custom app, click the **Options** (three-dot menu):

1. Click **Edit configuration**. The **Download Manifest** tab displays.

![CMS-Options_Edit_conf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ecf4ad9-9799-a5e0-05aa-ad8941dba808(2).png)
2. To download the manifest to be edited, click **Download**.

![CMS-Edit_Download_Manifest_Download.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b48f2e9-5d63-3f8a-90b1-d119913494c7(2).png)
3. To access the **Credentials** tab, click **Save and Continue**

![CMS-CMSA_Edit_Conf_Credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a44fbf23-88ed-6d6e-75ee-f0d7e912010d(2).png)
4. Update any or both of the credentials as needed:
  - Client Secret
  - Signing Secret
5. To save the updates, click **Update**.

![CMS-CMSA_Edit_Conf_Credentials_Update.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1821565-14ef-8dc6-909c-29ccd7b5d87a(2).png)

#### Deleting the custom Slack App

To delete your custom Slack app, to the right of the custom app, click the **Options** (three-dot menu):

1. Click **Delete**.:
  - **Configured app**: f the app is already linked to a pipeline, the **Disconnect (app name)** popup displays.

> [!NOTE]
> **Note**
> 
> You must disconnect a pipeline before deleting the custom app.
    1. Keep the **"Confirm your agreement to disconnect pipelines linked to this messaging service"** toggle.

![Disconnect_SlackCustomApp_Confirm_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a7a5e6b-7550-b2f0-f76b-5851a266f9f1(2).png)
    2. To remove the app, click **Disconnect**. Your custom app is deleted.

![Disconnect_SlackCustomApp_Disconnect.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e67ea62-24ef-04c6-5098-d1c18b2df393(2).png)
  - **Non-configured app**: If your custom app is not configured and not integrated with a pipeline, the confirmation popup for deletion displays.

![CMS-Delete_Confirmation_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fdca7cde-dc0b-562f-63ae-bd6201b39260(2).png)
    1. To confirm deletion, click **Delete Custom Application**. Your custom app is deleted.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(166).png)

### Integrating the custom Slack App with Securiti

Once integrate your custom Slack application with Securiti:

1. In the **Custom Apps** section, click **Connect** next to your Slack app.
2. In the Slack permissions popup, click **Allow**.

![CMS-CMSA_Allow_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fadf6bf2-8307-bc36-92c8-673d292bdfd5(2).png)

The custom application is connected.

### Connecting your pipeline to custom Slack app

Once your custom Slack app is connected, connect your pipeline to your custom Slack app.

1. Go to **Gencore AI**>**GenAI Pipelines** dashboard.
2. Open the GenAI pipeline you want to connect to your custom Slack app. In the **Messaging App Integrations** node, your custom Slack app is listed.

![Listed slack apps](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/slackcustomapp-listed.png)
3. To connect the pipeline to the channel:

The pipeline is successfully linked to your Slack channel.
  1. Click **Select Channel** dropdown.
  2. Select the channel **"all-gencore-messaging-integrations"**.

### Interacting with your custom Slack app

To interact with your custom Slack app:

1. Open your Slack workspace.
2. Select the channel **"all-gencore-messaging-integrations"**.
3. Tag your custom app and ask your query. The app responds with insights based on the connected pipeline’s knowledge base.

![CMS-CMSA_integrated_in_channel.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d3fac07-4066-103f-31b8-712046b5ea7c(2).png)

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

## Related

- [Configuring standard messaging apps](/configuring-standard-messaging-app.md)
- [Messaging app integrations](/messaging-app-integrations.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
