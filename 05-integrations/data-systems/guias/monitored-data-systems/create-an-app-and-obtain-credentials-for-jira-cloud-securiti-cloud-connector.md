---
title: "Create an app and obtain credentials for Jira Cloud (Securiti Cloud) connector"
slug: "create-an-app-and-obtain-credentials-for-jira-cloud-securiti-cloud-connector"
updated: 2026-08-03T04:47:26Z
published: 2026-08-03T04:47:26Z
canonical: "helpcenter.securiti.ai/create-an-app-and-obtain-credentials-for-jira-cloud-securiti-cloud-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create an app and obtain credentials for Jira Cloud (Securiti Cloud) connector

Perform the following procedures to create an application and obtain Credentials for Jira Cloud (Securiti Cloud) Connector.

### Creating an application in Jira

To create an app in Jira:

1. Go to [Atlassian Developer Console](https://developer.atlassian.com/console/myapps).
2. Log in to your Atlassian Developer account.

If you do not have access, contact your Information Technology (IT) administrator to provide you access to Atlassian Developer tools.
3. On the dashboard in the top right corner, click round profile icon, and choose **My apps** under **DEVELOPER CONSOLE**.

![My-apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cbfd6353-3a48-6866-f67a-149ecb11d2e5(1).png)
4. On the **My apps** page, click **Create > OAuth 2.0 Integration**, as shown below.

![OAuth2_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb5d05ac-a17b-defc-597c-04c5916e0582(1).png)
5. On the **Create a new OAuth 2.0 (3LO) Integration** page, apply the following settings:
  1. Enter a convenient name for a newly created Jira OAuth Integration app. See the example below.

*Jira for Securiti*
  2. Mark the checkbox for **I agree to be bound by Atlassian's developer terms** after the reading the terms.
  3. Click **Create**.

![create-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-062cdee7-9766-655c-8f4e-5d83a983bf3a(1).png)

It redirects you to Overview of newly created OAuth 2.0 App.

![Overview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-beea0b2f-3fad-0628-b317-055a08648150(1).png)

### Assigning permissions to OAuth 2.0 app

Perform the following steps to assign Permissions to OAuth 2.0 app created for Jira Cloud Self-hosted Connector.

1. On the left sidebar of your OAuth 2.0 page, click **Permissions**.
2. On the **Permissions** page, in the **Action** Column of Scopes Table, click **Add** next to **Jira API**.

![add-Jira-APi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b878e4e0-7e01-ca22-5d08-4c8ee1eb1282(1).png)

When you click **Add**, it converts the **Add** button to **Configure**.
3. In the **Jira API** scopes Row, click **Configure**.

![Configure-API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78fab01c-73ca-3129-c36d-bba3508f46b5(1).png)
4. On the **Jira API** page under the **Classic scopes** tab in **Jira platform REST API**, click **Edit Scopes**.

![edit-scope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-167176cc-d735-6fd5-c0d3-6321c480d9a0(1).png)
5. On the **Edit Jira platform REST API** popup, perform the following steps to assign Permissions.
  1. Mark the checkboxes for the following Permissions.
    - **read:jira-work**
    - **read:jira-user**
    - **write:jira-work**

For more information on understanding Permissions and use cases, see [3. Use cases and permissions for Jira Cloud](/v1/docs/jira-cloud-connectors-1).
  2. Click **Save**.

![select-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eddbd8ee-4851-9c3e-f0ca-35428a6ae694(1).png)
6. Proceed to the section below to continue with the app creation and Authentication process.

### Acquiring authentication credentials

1. On the left sidebar, and select **Authorization** from the left-hand menu.
2. Click **Configure** opposite to OAuth 2.0 (3LO), as shown below.

![add-authorization.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1984b28d-d6df-4bc5-c48a-787e9ed5cbb0(1).png)
3. On the following page, add the following callback URL in the Callback URL field:

![add-url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35ee2a4e-2fc1-845e-9550-bfd2ae94d7ee(1).png)

Then click **Save changes**.
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
4. On the left sidebar, click **Settings**.
5. On the **Settings** page, record the use them later for Connector Activation.
  - **Client ID**
  - **Secret**

![record-ids.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71b1b919-e40d-55e2-9da4-01705442939f(1).png)
6. Proceed to [Connecting Jira Cloud (Securiti-Cloud) with Securiti](/latest/docs/connecting-jira-cloud-securiti-cloud-with-securiti).
