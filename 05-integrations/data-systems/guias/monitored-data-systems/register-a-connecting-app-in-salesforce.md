---
title: "Register a connecting app in Salesforce"
slug: "register-a-connecting-app-in-salesforce"
updated: 2026-03-10T05:18:49Z
published: 2026-03-10T05:18:49Z
canonical: "helpcenter.securiti.ai/register-a-connecting-app-in-salesforce"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register a connecting app in Salesforce

> [!WARNING]
> **Important**
> 
> - The below procedure must be performed from the Lightning Experience UI.
> - You must perform steps outlined below with a Salesforce Admin role or profile.

1. Log in to [Salesforce](https://login.salesforce.com) with your admin Credentials.

Salesforce redirects you to the Console.

![SF_Login_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e44cc672-dd29-a5d9-d370-15644212e94a.png)
2. In the left-hand menu on the dashboard, choose **Settings > Company Settings > Company Information** to access the Salesforce "Instance ID".

![SF_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c571fe0-5c32-43ac-f117-bf57996ba61c.png)

To access "Domain id", record the portion of the URL before *.lightning.force.com*, for example:

https://**foundry123--sbauto1**.lightning.force.com/ as shown.

![Domain_Id_SF.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef4f7a2a-58db-efd0-da00-df690fec3759.png)
3. Record the Instance/Domain id (whichever the case) to use later.
4. Click the gear icon at the upper right corner of the screen and then choose **Setup**.

Salesforce redirects you to the main Setup screen for your administrator account.

![SF_Dashboard-SalesConsole_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2700b2d-1b92-99c4-693d-446b43e40d62.png)
5. On the left sidebar Search field, search on the term “App” to locate the **App Manager (from Lightning Experience UI)**.

Salesforce shows you the list of apps active on your Salesforce suite.

![SF_SearchforAppandClickManager_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e840c52-c893-de6a-b073-b592ec14f129.png)
6. Click **New Connected App** near the upper right corner of the page.

![SF_AppManager_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a24f1407-7706-7c55-a5dd-f70a1122a2dd.png)
7. In the **Basic Information** area, apply the following settings:

| **Setting** | **Description** |
| --- | --- |
| Connected App Name | Enter any convenient name |
| API Name | Enter any convenient name |
| Contact Email ID | Enter your email address as registered to the Securiti application. |

![SF_NewConnectedDetails_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea5e2ff1-5e7c-2719-a5ad-0d50e34c8860.png)
8. In the API (Enable OAuth Settings) fields, apply the following settings:

> [!WARNING]
> **Caution**
> 
> Unselect the **Require Proof Key for Code Exchange (PKCE) Extension for Supported Authorization Flows** checkbox if already marked to avoid error during Activation.
> 
> ![unselect_PKCE_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52148343-b092-4787-bea9-b97a33910110.png)

| **Setting** | **Description** |
| --- | --- |
| Enable OAuth Settings | Mark the checkbox. |
| Callback URL | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| Selected OAuth Scopes | Select these scopes to apply, then click **Add** to move them to Selected OAuth Scopes (AKA Permissions): - Access the identity URL service (id, profile, email, address, phone) - Full access (full access) - Manage user data via APIs (api) - Perform requests at any time (refresh_token, offline_access) ![salesforce_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2909fe85-f8f4-1066-55e7-c39709166491.png) |
| Require Secret for Web Server Flow | Mark the checkbox. |
9. Click **Save**.

Salesforce opens a dedicated details page for the new app. Near the bottom of the page, click **Manage Consumer Details**.

![manage_consumer_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1634c424-fcc2-c514-b00d-2da83b2416ba.png)
10. On the page for the new app, record the **Consumer Key** and **Consumer Secret** to use later.

Click **Back to Manage Connected Apps**.

![consume_key_&amp;_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ceb5fba8-04bc-ba01-b033-6a78e6d09e49.png)

> [!NOTE]
> **Note**
> 
> We recommend you wait for at least 30 minutes before using the parameters to activate the Salesforce Connector.
11. Click **Manage**, then **Edit Policies** as shown.

![SF_Manage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cf465f3-e950-521e-d88b-8bd2cbec198c.png)

![SF_EditAppPolicies_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3abf9ffe-c09e-1819-5c8d-a04efc1e638c.png)
12. Under the **OAuth Policies** section, change the IP Relaxation policy to **Relax IP Restrictions**, and mark the radio button for **Refresh Token is valid until revoked** as shown below.

> [!WARNING]
> **Important**
> 
> Keep in mind that even if the Token has default settings configured to never expire, it still expires after 5 more access Token calls. In such cases, the only solution is to request a new access Token by reconfiguring the Connector. Refer to the [official documentation](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_request_manage.htm&amp;type=5) for more information.

![SF_EditAppPolicies3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a77ef2b7-a4e1-cd4c-af35-c91e572e4878.png)

> [!NOTE]
> **Note**
> 
> These settings prevent the SFDC Connector from encountering "expired Refresh Token errors."
13. To include your Salesforce objects in DSR search.
  1. In **Setup > Object Manager**
  2. Select your Salesforce object and on the **Details** page, click **Edit**.

![salesforce_objects.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21b2eb5f-dbba-1941-aeaa-3c39ab6736e4.png)
  3. At the bottom of the page, under **Search Status** section, mark the **Allow Search** checkbox as shown below. This makes your custom objects searchable by Securiti's DSR.

![salesforce_allowsearch.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a91b717-e6c0-3a55-bf48-abfd7c76116a.png)

1. Proceed to [(New UI) Connecting Salesforce (Legacy) with Securiti](/latest/docs/new-ui-connecting-salesforce-legacy-with-securiti), [(New UI) Connecting Salesforce (Securiti Cloud) with Securiti](/latest/docs/new-ui-connecting-salesforce-securiti-cloud-with-securiti), or [Activate the Salesforce (Legacy) connectors in Securiti](/v1/docs/activate-the-salesforce-legacy-connectors-in-securiti).
