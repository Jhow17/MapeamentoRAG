---
title: "Acquire authentication credentials in Salesforce Chatter"
slug: "acquire-authentication-credentials-in-salesforce-chatter"
updated: 2026-07-31T09:55:50Z
published: 2026-07-31T09:55:50Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-salesforce-chatter"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Salesforce Chatter

1. Log in to Salesforce with your admin Credentials at <https://login.salesforce.com>.

Salesforce redirects you to your Sales Console.

> [!NOTE]
> **Note**
> 
> The procedure requires Salesforce Instance ID and app permission to activate the Connector.

![SF_Login_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e44cc672-dd29-a5d9-d370-15644212e94a(1).png)
2. In the left-hand menu on the dashboard, choose **Settings > Company Settings > Company Information** to access the Salesforce Instance ID.

![SF_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c571fe0-5c32-43ac-f117-bf57996ba61c(1).png)

To access Domain id, take note of the following before *.lightning.force.com*:

https://**foundry123--sbauto1**.lightning.force.com/ as shown.

![Domain_Id_SF.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef4f7a2a-58db-efd0-da00-df690fec3759(1).png)
3. Record the Instance/Domain id (whichever the case) to use later.
4. Click the gear icon at the upper right corner of the screen and then choose **Setup**.

Salesforce redirects you to the main Setup screen for your administrator account.

![SF_Dashboard-SalesConsole_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2700b2d-1b92-99c4-693d-446b43e40d62(1).png)
5. On the left sidebar Search field, search on the term “App” to locate the **App Manager**.

Salesforce shows you the list of apps active on your Salesforce suite.

![SF_SearchforAppandClickManager_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e840c52-c893-de6a-b073-b592ec14f129(1).png)
6. Click "New Connected App" near the upper right corner of the page.

![SF_AppManager_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a24f1407-7706-7c55-a5dd-f70a1122a2dd(1).png)
7. In the Basic Information area, apply the following settings:

| Connected App Name | Enter any convenient name |
| --- | --- |
| API Name | Enter any convenient name |
| Contact Email ID | Enter your email address as registered to the Securiti application. |

![SF_NewConnectedDetails_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea5e2ff1-5e7c-2719-a5ad-0d50e34c8860(1).png)
8. In the API (Enable OAuth Settings) fields, apply the following settings, then click **Save**:

| Enable OAuth Settings | Mark the checkbox. |
| --- | --- |
| Callback URL | Enter one of the following: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| Selected OAuth Scopes | Select all available scopes, then click **Add** to move them to Selected OAuth Scopes. |
| Require Secret for Web Server Flow | Mark the checkbox. |

![SF_NewConnectedDetails2_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd0c57a2-4cd8-8193-44e4-95dfb1d85fc4.png)
9. On the new app page, record the **Consumer Key** and **Consumer Secret** to use later when you activate the Connector in Securiti.
10. Click **Save**.

Salesforce opens a dedicated details page for the new app.

![SF_NewConnectionClientandSecret_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b32ce1fb-f8ac-3c48-420d-11b40434f4a9.png)
11. Click **Manage**, then **Edit Policies**, as shown below.

![SF_Manage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cf465f3-e950-521e-d88b-8bd2cbec198c(1).png)

![SF_EditAppPolicies_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3abf9ffe-c09e-1819-5c8d-a04efc1e638c(1).png)
12. Under the **OAuth Policies** section, change the IP Relaxation policy to **Relax IP Restrictions**, and mark the radio button for **Refresh Token is valid until revoked** as shown below.

![SF_EditAppPolicies3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a77ef2b7-a4e1-cd4c-af35-c91e572e4878(1).png)

> [!NOTE]
> **Note**
> 
> These settings prevent the SFDC Connector from encountering "expired Refresh Token errors."

App permission lets you assign it to the admin user. To enable permission in Salesforce Chatter:

1. On the home page in the left navigation menu go to **Administration > Users > Permission Sets**.
2. Click **New** in "Permission Sets".

![permission-sets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45da8c7f-e393-90b8-2c5d-9667f9b8ab32.png)
3. Under "permission set information", enter a value in **Label** and **API Name** fields as shown below.

![enter-label-and-api-name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7cb05cbf-aa46-7f22-5ad7-7bf6bd02ab91.png)
4. Click **Save**.
5. On the following page, in the Apps area, select **App Permissions**.

![select-app-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ca402a5-712d-5377-ede8-c971b0ff163b.png)
6. Click "Edit" and mark the **Query All Files** check box, then click **Save**.

![click-edit-and-mark-checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd1b526a-9df4-2ea4-536f-d569d7c002cf.png)
7. On the "Permission Changes Confirmation" dialog, select **Save** again as shown below.

![hit-save-to-change-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-655c5a05-1813-3a19-a794-10e6065f16f4.png)
8. Select **Manage Assignments**, and then **Add Assignments**.

![select-manage-assignments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7659a28f-60c8-b42c-b586-c15e11e9d9c9.png)

![select-admin-user-and-assign.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4362b2cb-2f0c-54ee-be2d-740b695de351.png)
9. Mark the checkbox for the admin user that you used to create the auth app, and click **Assign**.

Salesforce displays the assignment confirmation message as shown below.

![assignment-confirmation-message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81b8364c-12b0-5997-2195-c371cce6fbda.png)
10. Click **Done**.
11. Proceed to [Connect Salesforce Chatter connector with Securiti](/latest/docs/connecting-salesforce-chatter-connector-with-securiti).
