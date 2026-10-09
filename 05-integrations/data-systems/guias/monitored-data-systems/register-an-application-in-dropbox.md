---
title: "Register an application in Dropbox"
slug: "register-an-application-in-dropbox"
updated: 2026-03-10T04:33:51Z
published: 2026-03-10T04:33:51Z
canonical: "helpcenter.securiti.ai/register-an-application-in-dropbox"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Dropbox

1. Log into your [Dropbox](/v1/docs/securiti-pods-and-elastic-pods) account.

Dropbox redirects you to your Dropbox home page
2. Near the lower right corner of the page, click **...** and choose **Developers**.

![C00315.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d51d9f09-00c3-3d2c-5799-6726975fadd9.png)
3. Click **Create apps**.

![C00316.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8714917e-c233-bcea-550f-b25b573b1540.png)
4. Apply the following settings to your new app:

| API | **Scoped access** is selected as default. |
| --- | --- |
| Type of access | Choose **Full Dropbox - Access to all files and folders in a user's Dropbox**. |
| App name | Enter any convenient name. |

![select_API_dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4b9ca72b-585a-6d5b-1662-07667ba513ca.png)

Dropbox redirects you to the Settings page for your new app.
5. Select **No expiration** from the "Access Token expiration" menu, as shown below.

![access_token_expiration_dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-456f772a-9fa2-82d8-e2c4-87466d42a437.png)
6. On the following page, select the "Permissions" tab and set the following scopes for API level permission:

![permissions_dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1cc8f9ae-6134-4003-3301-b72c934d1467.png)
  - `Account_info.read`
  - `Files.metadata.read`
  - `Files.content.read`
  - `Sharing.read`
  - `Team_info.read`
  - `Team_data.member`
  - `Team_data.team_space`
  - `Members.read`
  - `Events.read`
  - `Groups.read` (permission only required if you want to configure a Discovery scan with the Data system).
7. On the settings page for your new app, record the App key and App secret as shown below to use later.

![C00318.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a128504e-eb08-5f69-b46a-15d7e97a6eda.png)
8. For Redirect URL, enter one of the following URLs:
  - US Cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
9. Record the team name to use it for activating the Dropbox Connector at Securiti.
  1. On the left sidebar, click **Admin console**.

![step-9a-dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53a34c38-cc07-2fe6-02eb-b26d1157e535.png)
  2. On the **Settings** page, click **Team profile**.

![step-9b-dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21bac297-ca37-87c8-3cb2-fc54bb244b2f.png)
  3. On the Team profile page, record the Team name for later use.

![step-9c-dropbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3595fe0f-d4da-1f4a-e4a1-2d28c5245cc8.png)

1. Proceed to [Activate the Dropbox connector in Securiti](/v1/docs/activate-the-dropbox-connector-in-securiti), [(New UI) Connecting Dropbox (self-hosted) with Securiti](/latest/docs/new-ui-connecting-dropbox-with-securiti)

or [(New UI) Connecting Dropbox (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-dropbox-securiti-cloud-with-securiti).
