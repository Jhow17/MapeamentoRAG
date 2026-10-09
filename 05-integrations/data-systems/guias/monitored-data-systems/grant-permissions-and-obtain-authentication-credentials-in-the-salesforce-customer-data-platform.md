---
title: "Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform"
slug: "grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform"
updated: 2026-07-31T11:06:28Z
published: 2026-07-31T11:06:28Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform

Salesforce Customer Data Platform data system uses client ID and secret to activate the connector in Securiti.

> [!WARNING]
> **Important**
> 
> We assume you have a Salesforce CDP Instance running on your Salesforce account or you're the admin of your Salesforce account to be able to configure the required permissions before activating the connector.

Use the matching procedure below.

1. Log in to your Salesforce homepage.
2. In the upper right corner of the page, click **Setup**.

On the following page, click your user to assign 'CDP Roles.'

![assign-roles-salesforce-cdp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31baf50d-7d57-b0b6-42da-62725032d1dd.png)
3. In **Permission Set Assignments**, click **Edit Assignments**.

![image.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3cf69c2-83aa-ae21-cff5-8eafe5b681fa.png)
4. Add the following user-level permission(s):
  - **(Legacy) Data Cloud User**

![step-4-salesforce-cdp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1460b2e-5c5e-fd1b-be1d-afa7df257bdb.png)

Click **Save**

![image__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87f2683f-dca1-d73f-ffc3-9948d50cc993.png)
5. Select **Apps > App Manager** in the left sidebar on the Setup page for Data Cloud.

In the upper right corner of the page, click **New Connected App**.

![unnamed7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78f90e0e-0ced-48df-a29d-839f61d7a41c.png)
6. Enter the required information and select these OAuth Permissions for your app, as shown below.

When you're done, click **Save** at the top of the page.
  - **Access the identity URL service (id, profile, email, address, phone)**
  - **Add one of the following URLs in the "Callback URL" field according to the environment being used:**
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
  - **Manage Data Cloud Identity Resolution (cdp_identityresolution_api)**
  - **Manage user data via APIs (api)**
  - **Perform ANSI SQL queries on Data Cloud data (cdp_query_api)**
  - **Perform requests at any time (refresh_token, offline_access)**

![step-5-salesforce-cdp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e22aa2b-9cf4-f4e4-40d8-11576a21930e.png)

![unnamed8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-849c3695-a5c2-6bb8-5dc5-794f9ce40c1e.png)

> [!WARNING]
> **Important**
> 
> Unselect the **Require Proof Key for Code Exchange (PKCE) Extension for Supported Authorization Flows** checkbox if already marked to avoid error during activation.

To obtain Client ID (Consumer Key) and Client Credentials (Consumer Secret):

1. Click the **Manage Consumer Details** button.

![newstep-1-salesforce-cpd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c07b3d58-93f9-56cd-67e7-b91448e5286e.png)
2. Record the **Consumer Key** and **Consumer Secret** for later use in the Consumer Details section.

![newstep-2-salesforce-cdp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-80844a3c-305f-86dd-fcc7-0214ab4e94ce.png)
3. From the URL in the address bar, record the "Instance ID" for Activation.

An example of the format is "d10000000p6ereay-dev-ed".

![newstep-3-salesforce-CDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a1555e1-1c43-7766-41e2-e6a832b6a226.png)
4. Proceed to [Connecting Salesforce Customer Data Platform with Securiti](/latest/docs/connecting-salesforce-customer-data-platform-with-securiti).
