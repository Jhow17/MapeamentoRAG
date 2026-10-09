---
title: "Prerequisites for Salesforce CRM connector"
slug: "prerequisites-for-salesforce-crm-connector"
updated: 2026-07-31T10:50:34Z
published: 2026-07-31T10:50:34Z
canonical: "helpcenter.securiti.ai/prerequisites-for-salesforce-crm-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Salesforce CRM connector

You must fulfil the following prerequisites before proceeding with connecting Salesforce CRM with ​Securiti:

- You must use the Lightning Experience UI to create and configure your connected app, as described in the steps below.
- You must use a Salesforce user with the System Administrator role or a profile that includes the required permissions to create a connected app and manage OAuth settings.:
  - `View Setup and Configuration`
  - `Customize Application`
  - `Modify All Data`

For more information, see [this Salesforce article](https://help.salesforce.com/s/articleView?id=000384657&amp;type=1).

> [!NOTE]
> Note
> 
> Complete this step only if you need to create a connected app in Salesforce to obtain the **consumer key** and **consumer secret**, which are required to activate the Salesforce CRM connector in Securiti.
> 
> If you already have these keys, as described in the steps below, you only need a user with the **API User** profile to activate the connector. This is the recommended least-privilege option. However, you can also use a **System Administrator** account if needed.
- You must configure outbound network access from Securiti pod to the following Salesforce base URL to enable connection with the data system instance. Update your security groups, firewall rules, or network policies to permit access to the below URL:

`https://{{instance_id}}.my.salesforce.com`

Replace the `{{instance_id}}` with your Salesforce instance ID.

This document covers procedures for the following:

- Acquiring authentication credentials for the Salesforce CRM connector
- Configuring permissions for API User profile
- Enabling permission for unstructured data scanning
- Configuring integration with CyberArk Vault

You need the following credentials for Salesforce CRM:

- Consumer Key (recorded during App creation)
- Consumer Secret (recorded during App creation)
- Instance ID

#### Acquiring authentication credentials

Use the matching procedure below to provide permissions and acquire authentication credentials in Salesforce CRM.

1. Log in to [Salesforce](https://login.salesforce.com) with your admin credentials.
2. In the left-hand menu on the dashboard, choose **Settings > Company Settings > Company Information** to access the Salesforce "Instance ID".

Record the portion of the URL before *.lightning.force.com* as the instance ID for your Salesforce organization.

For example, if your Salesforce URL looks like: `https://na85.lightning.force.com/lightning/settings/personal/PersonalInformation/home`

**na85** is the instance ID which is used to make all the API calls.
3. From the **Setup** page, search for **App Manager (from Lightning Experience UI)** and select **New Connected App**.

![salesforce_crm_appmanager.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fd609aa-4d1c-b402-be82-a771981f8e39.png)
4. Fill the form for your new application as shown in the screenshot below.
  - In the **Basic Information** area, apply the following settings:

| Connected App Name | Enter any convenient name |
| --- | --- |
| API Name | Enter any convenient name |
| Contact Email ID | Enter your email address as registered to the Securiti application. |

![SF_NewConnectedDetails_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea5e2ff1-5e7c-2719-a5ad-0d50e34c8860(2).png)
  - In the **API (Enable OAuth Settings)** section, enable the checkbox **Enable OAuth Settings** and apply the following settings.

> [!WARNING]
> **Caution**
> 
> Unselect the **Require Proof Key for Code Exchange (PKCE) Extension for Supported Authorization Flows** checkbox if already marked to avoid error during activation.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(646).png)

![unselect_PKCE_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52148343-b092-4787-bea9-b97a33910110(1).png)

| Enable OAuth Settings | Mark the checkbox. |
| --- | --- |
| Callback URL | Enter the Securiti app URL according to the environment being used. - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| Selected OAuth Scopes | Select these scopes to apply, then click **Add** to move them to Selected OAuth Scopes (AKA Permissions): - Access the identity URL service (id, profile, email, address, phone) - Manage user data via APIs (api) - Perform requests at any time (refresh_token, offline_access) ![selected_oauth_scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad7ec21d-0339-e474-00c9-745a2cd7805c.png) |
| Require Secret for Web Server Flow | Mark the checkbox. |
| Require Secret for Refresh Token Flow | Mark the checkbox. |
5. At the bottom of the page, click **Save** and **Continue** on the next screen after all the required permissions and details have been added.

![salesforce_crm_continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1da49717-8bed-3b4b-c056-cf36a8d49563.png)
6. Salesforce opens a dedicated details page for the new app. Near the bottom of the page, click **Manage Consumer Details** and record the following to use later.

![salesforce_crm_manageconsumer_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-988d9f53-0f87-a058-b110-a4e899639fd8.png)

![salesforcecrm_consumerkeyandsecret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a93e6eea-d032-5add-89be-8f71153194eb.png)

Click **Back to Manage Connected Apps**.

> [!NOTE]
> **Note**
> 
> We recommend you wait for at least 30 minutes before using the parameters to activate the Salesforce Connector.
  - Consumer Key
  - Consumer Secret
7. Click **Manage**, then **Edit Policies** as shown.

![SF_Manage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cf465f3-e950-521e-d88b-8bd2cbec198c(2).png)

![SF_EditAppPolicies_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3abf9ffe-c09e-1819-5c8d-a04efc1e638c(2).png)
8. Under the **OAuth Policies** section, change the IP Relaxation policy to **Relax IP Restrictions**, and mark the radio button for **Refresh Token is valid until revoked** as shown below.

> [!NOTE]
> **Note**
> 
> These settings prevent the SFDC Connector from encountering "expired Refresh token errors."

![SF_EditAppPolicies3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a77ef2b7-a4e1-cd4c-af35-c91e572e4878(2).png)

> [!WARNING]
> **Important**
> 
> Keep in mind that even if the token has default settings configured to never expire, it still expires after 5 more access token calls. In such cases, the only solution is to request a new access token by reconfiguring the Connector. Refer to the [official documentation](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_request_manage.htm&amp;type=5) for more information.

For self-hosted connectors, if you choose not to relax IP restrictions, configure secure communication by allowlisting the required IPs, as described in the steps below.
  1. Identify the public IP of your Securiti pod and add it to your organization’s allowlist. For more information, see Allowlisting IPs for data system connectors.
  2. Allowlist your Salesforce instance URL in your firewall or proxy settings to enable outbound communication from Securiti to Salesforce, as described in this topic above.
9. Enable permissions for unstructured data scanning as shown in the section below, and proceed to [Connecting Salesforce CRM with Securiti](/latest/docs/connecting-salesforce-crm-with-securiti).

#### Configuring permissions for API User profile

> [!NOTE]
> Note
> 
> Skip this step if you are using the System Administrator account.

Once the connected app is created, you can activate the connector using a user with the **API User** profile. If you are not using a **System Administrator** account, configure the connected app to let your API User authorize it.

The connected app’s **Permitted Users** policy controls who can grant authorization.

To configure the policy for the API User profile:

1. In **Setup**, go to **App Manager** and select your connected app.
2. Select **Manage > Edit Policies**
3. In **Edit Policies**, under **Permitted Users**, select one of the following:
  - **Admin approved users are pre-authorized****:** This setting enables only specific profiles or permission sets to access the app.

> [!WARNING]
> Warning
> 
> If you use **Admin approved users are pre-authorized**, users not added explicitly see the following error:
> 
> `OAUTH_APP_ACCESS_DENIED`
  - **All users may self-authorize**: This setting lets any user authorize via OAuth prompt.

  

1. If you are using **Admin approved users are pre-authorized**, assign profiles or permission sets using the procedure below.
  1. Set **Permitted Users = Admin approved users are pre-authorized****.**
  2. Scroll to **Profiles** or **Permission Sets**, and add one of the following:
    - API User profile
    - A Permission Set assigned to your user.
  3. Save changes.

If **API Access Control** is enabled, verify that your app is showing under **Approved Connected Apps**.

![Salesforce CRM app details including OAuth policies and user profiles information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/salesforce_nonadminuser.png)

#### Enabling permission for unstructured data scanning

You must enable the **Query All Files** permission set for the user activating the connector in Securiti to fetch and scan all files across all users in the system.

When this permission is enabled:

- Securiti retrieves all files, including those in non-member libraries and unlisted groups.
- Users cannot edit, upload new versions, or delete files they don’t have access to.

For more information, see [Salesforce documentation on Query All Files](https://help.salesforce.com/s/articleView?id=release-notes.rn_experiences_files_query_all.htm&amp;language=en_US&amp;release=246&amp;type=5&amp;utm_source=chatgpt.com).

  

> [!WARNING]
> Warning
> 
> If the **Query All Files** permission is not assigned to the user activating the connector, Securiti fetches only the files owned by that user. Files belonging to other users are not retrieved due to Salesforce API restrictions.

To enable the **Query All Files** permission set for unstructured scanning of all files in the system.

1. Go to **Set Up > Permission Set** and click **New** to add a new permission set.

![salesforcecrm_setupbutton.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f1d25cf-9113-69ee-f195-5fcd8dc404fa.png)

![salesforcecrm_newpermissionset.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14a97918-1770-62d1-cc19-d1a61bc056f4.png)
2. On the pop-up, enter your preferred details, such as label and API name, and click Save.

![salesforcecrm_permissionset_values.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81268cc9-5f58-64f3-949d-b885227e4b8f.png)
3. Click **App Permissions** on the new page you are directed to.

![salesforcecrm_apppermissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37e6b019-5e86-6ee0-1f95-3af64133cfac.png)
4. Click **Edit** to edit the permissions' properties.

![salesforcecrm_editbutton.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da4ef133-c16a-4761-3609-0452fdc7662b.png)
5. Navigate to the bottom of the Permissions page and mark the **Query All Files** checkbox. Click **Save**.

![salesforcecrm_queryallfiles_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aedcd5bb-8f31-0fb3-b630-d86d035ea49c.png)
6. On the same page, click **Manage Assignments**.

![salesforcecrm_manageassignments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ddd3cb2b-d2e8-05d0-6d3f-d6c395168c55.png)
7. Click **Add Assignment** and select your admin user. Click **Next**.

![salesforcecrm_addassignment_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dceb331a-796b-0a75-24e9-1adccc6e347c.png)

![salesforcecrm_selectuser_next.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa9001ec-c944-1692-3fa5-2458ddc13075.png)
8. On the new page, click **Assign** to assign this permission set to the admin user activating the Salesforce CRM connector in Securiti.

![salesforcecrm_assignbutton.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7dbc157-66c6-208c-0152-454d27f52c62.png)

#### Configuring integration with CyberArk and CyberArk Conjur vaults

To use CyberArk Vault for your Salesforce CRM credentials, you must verify the following settings for your Salesforce connected app.

1. Verify that the Client credentials Flow is enabled for your connected app, as described below:
  1. In **Setup > Manage Apps > Connected App**, click **Edit** for your connected app, as shown below.

![salesforcecrm_editapp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a11be92-ce2c-3e3d-b360-0787db8f1e25.png)
  2. Mark the **Enable Client Credentials Flow** checkbox if not already, as shown below.

![salesforcecrm_clientcredsflow_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8829541d-feef-4bc1-ee62-ece109e1c64d.png)
  3. Click **Save**.
2. Verify the user assignment to your connected app. Salesforce requires a specific user to be associated with client credentials. Follow the procedure below to assign a user.
  1. In **Setup > Manage Apps > Connected App**, click **Manage** for your connected app, as shown below.

![salesforcecrm_manageapp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ed59da41-dfe8-b987-e489-7863450ce877.png)
  2. Click **Edit Policies** for your application, as shown below.

![salesforcecrm_editpolicies.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11d394d3-ad2c-e1e2-44c0-dcc8bb064ea3.png)
  3. Under the **OAuth Policies** section, in the **Permitted Users** field, verify that **Admin approved users are pre-authorized** is selected.
  4. Under the **Client Credentials Flow** section, in the **Run As** field, add a user to be associated with the client credentials flow, as shown below.

![salesforcecrm_permittedusers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-743ace3b-ddee-5171-d8b4-b892677f873b.png)
  5. Edit the profile of your assigned user and enable your app under the **Connected App Access**, as shown below.

![salesforcecrm_editconnectedapps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89f131c7-7aee-9c7b-eab4-a072923f056d.png)

![salesforcecrm_connectedappsenable.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d4c4c95-a463-83d3-9146-d3f13b68b7f6.png)

Proceed to [Connecting Salesforce CRM with Securiti](/latest/docs/connecting-salesforce-crm-with-securiti).
