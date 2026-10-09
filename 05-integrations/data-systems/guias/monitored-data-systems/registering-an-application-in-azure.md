---
title: "Registering an application in Azure"
slug: "registering-an-application-in-azure"
updated: 2026-06-23T06:48:01Z
published: 2026-06-23T06:48:01Z
canonical: "helpcenter.securiti.ai/registering-an-application-in-azure"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Registering an application in Azure

1. Log in to your Microsoft Azure admin console.
2. From the left hand navigation, choose **Azure Active Directory > App registrations**.
3. Click **+ New registration**. Azure shows you the Register an Application page as shown below.

![register1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d5ba917-3ff5-ee3d-42dd-dd0a40bd09a8.png)
4. Apply the following settings:

| Name | Any convenient name, for example: “Securiti Connector for OneDrive.” |
| --- | --- |
| Supported Account types | Choose **Accounts in this organizational directory only**. |
| Redirect URI | Choose **Web** and enter one of the following URLs: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
5. Near the bottom of the page, click **Register**.

Azure opens the page for the new application.

![register2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ca97e4f-f824-bf14-2968-6618787f3f0b.png)
6. Next to the Application (client) ID, click **Copy to Clipboard** as shown below.

![register3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a5f4c28-a2cc-968e-6e59-c9251b409fb0.png)
7. **Obtain Tenent ID or Domain**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain. ![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(2).png)
  4. Record the **Tenant Name** from **Primary Domain** for the Connector Activation.

**Tenant Name** is initial part of the domain. If *testdomain.onmicrosoft.com* is the domain. **testdomain** is the Tenant Name.
8. Record the application ID so that you can use it when you create an Microsoft 365 Instance in Securiti.
9. Proceed to [Configuring the application secret](/v1/docs/configuring-the-application-secret-en).
