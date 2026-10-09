---
title: "Acquire authentication credentials in Drift"
slug: "acquire-authentication-credentials-in-drift"
updated: 2025-10-30T19:52:55Z
published: 2025-11-03T06:14:28Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-drift"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Drift

Drift data systems use the client id and secret to establish a successful Connection in Securiti.

Use the matching procedure below.

1. > [!NOTE]
> **Note**
> 
> We assume you have a Drift Instance running or you're the account admin, so you have *read* Permissions for contacts and users and *write* permission for GDPR.

Log in to your Drift account.

(Optional) If you haven't, you can create a trial account for Drift at [https://start.drift.com/login](https://start.drift.com/login).
2. On the dashboard, near the bottom-left corner of the sidebar, select **Switch apps > developer platform**.

![switch_apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5bebad6b-5b90-79b4-4b18-e41fd945bc5a.png)

Drift redirects you to the following [link](/v1/docs/securiti-pods-and-elastic-pods).
3. On the following page, click **Build Your App**.

![build_your_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f6b82f3-cddb-3f22-295b-4bc6196e0341.png)
4. In Display Information, enter the details for your app, such as App Name, etc.

![display_information.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83e79001-faa1-335a-26d9-019c1d894a30.png)
5. In the left sidebar, click **Oauth and Scopes**, and in the Add Redirect URL field, enter the redirect URL that applies from the list below.

![redirect_url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c42e198-11d5-73f1-dfff-e17e58406f4f.png)
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
6. Scroll to the bottom of the page, and in the Add Permissions by Scopes field, select these Permissions by entering them, as shown below.
  - **contact_read** in Contacts
  - **user_read** in Users
  - **gdpr_write** in Data Privacy

![oauth_&amp;_scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb5ad6ce-cc33-97b7-6fd2-17c95a2c93c5.png)
7. In the left sidebar, click **App Credentials**.
8. Record your **Client ID** and **Secret ID** for later use.

![client_id_&amp;_secret_id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e56648e-6dc1-0965-f043-1b075aff981d.png)
9. Proceed to [Activate the Drift connector in Securiti](/v1/docs/activate-the-drift-connector-in-securiti).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
