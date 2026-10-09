---
title: "Set up DocuSign API access credentials"
slug: "set-up-docusign-api-access-credentials"
updated: 2026-07-03T06:42:48Z
published: 2026-07-03T06:42:48Z
canonical: "helpcenter.securiti.ai/set-up-docusign-api-access-credentials"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Set up DocuSign API access credentials

1. Log in to your DocuSign account.

Docusign redirects you to the Developers Sandbox homepage.
  - Use this URL for a demo account, see an example below:

`&lt;https://account-d.docusign.com&gt;`
  - Use this URL for a permanent account, see an example below:

`&lt;https://account.docusign.com&gt;`
2. In the upper-right corner of the page, click **Admin**.

![homepage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-757f1b1f-4332-c6ff-62ab-57a0180d7c33.png)
3. On the left sidebar, scroll down to the **Integrations** section, and click **Apps and Keys**.

![apps-and-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-444906e4-ea5d-f6d0-1e55-a16d818ff43c.png)

DocuSign redirects you to the API and Integration Key Information page for developers.
4. On the **Apps and Keys** page, click **Add App and Integration Key**.

> [!NOTE]
> **Note**
> 
> If you have already created an app, you can edit the existing app to add the App and Integration Key.

![add-key-btn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13f07934-dff0-756b-03bc-6204f8ecfcea.png)
5. On the **Add Integration Key** popup, enter an appropriate **App Name** for the API key you are setting up, and click **Create App**.

![integration-key-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae8b51b2-0a15-8a13-fd34-c51aed024ffa.png)

It redirects you to the newly created app page for your created API key.
6. Only the following page under the **General Info** section, records the **Integration Key** to use later as the **Client ID** in connector activation.

![copy-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95948b50-21ae-08d3-c3a1-772268e1ef94.png)

> [!NOTE]
> **Note**
> 
> The integration key shown is a dummy value for the purposes of this documentation.
7. Scroll further down this page to configure the following settings:
  - Under **User Authentication**, in "Is your application able to securely store a client secret," mark the radio button for **Yes**.
  - Under "Authentication Method for your App Authorization Code Grant," clear the checkbox for **Require Proof Key for Code Exchange (PKCE)**.

> [!NOTE]
> **Note**
> 
> We recommend you wait before proceeding with the connector authentication, as the configuration change may take a few minutes to reflect. Otherwise, the app shows an error at the time of activation.
  - Under **Secret Keys**, click **+ Add Secret Key**.

Record the generated **Secret Key** to use later as the **Client Secret** in connctor activation.

![authentication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c766c531-b219-18ad-0a4c-2404d5313a84.png)
8. In the **Advanced settings** section, add one of the following URLs in **Redirect URIs** field:

![add-url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6a536a4-18b4-650e-dde8-c511c912485f.png)
  - US cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
9. Click "**Save**" at either the top or bottom of the screen to save the configured API settings.

![save_api_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac284660-2d77-f4b1-ebc2-46120774b392.png)

> [!NOTE]
> **Note**
> 
> At this point, the app needs promotion to the live account for which a review of 20 or more successful requests is needed through a developer account denoted by "account-d" (in this case).
10. To promote the app:
  1. On the top left of the navigation bar, click **Home**.
  2. On the **Home** page, click **Start** menu.
  3. On the **Start** menu, choose **Envelopes** > **Sign a Document**.

![docusign_signature.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fcd22611-56e7-8b3b-5e7a-6bb31171b560.png)
  4. Sign a document with at least 50 files in the “account-d” DocuSign account, as shown below.

![sign-a-document.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0506d008-ac5c-9f0a-9348-2a01769bf3f5.png)

> [!NOTE]
> **Note**
> 
> You can input one-liner texts in these files and aim for a higher count so that the number of 20 successful requests is achieved even if some requests fail. In this example, it is 50.
  5. After signing is completed, use "account-d" as Environment, in addition to Client Id and Secret (that you previously acquired).
11. Manage users access on their behalf:
  1. In the upper-right corner of the page, click **Admin**.

![homepage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-757f1b1f-4332-c6ff-62ab-57a0180d7c33.png)
  2. On the left sidebar under the **USERS AND GROUPS**, choose **Users**.
  3. On the **Users** page, locate the user whose settings you want to manage, then click **Action** next to their name.
  4. From the **Action** menu, select **Manage Shared Access**.

![list_of_Users_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33d2595a-0ffa-42bc-45c3-2f0c137330c5.png)
  5. On the **Shared Access** page under **Share with others** tab, click **Share Access With Others**.

![shared-access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e503419f-09b2-bb42-9ccf-9e44bb3541b3.png)
  6. On the **Share access with others** page under the **Select Permissions** section, mark the radio button for **Allow to manage on behalf of <user>**. For more information on permissions to share envelopes access with other users, see [DocuSign documentation](https://support.docusign.com/s/document-item?language=en_US&amp;bundleId=oeq1643226594604&amp;topicId=obf1692128351600.html&amp;_LANG=enus).

![permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89575db4-9f33-fd87-a0cf-d01b06dfde43.png)
  7. (Optional) Under the **Set Duration** section, select the **Start Date** and **End Date** for shared access. Then, click **Next**.
  8. Under the **Select Users** section, mark the checkboxes next to each user you want to include. This action grants other users the ability to manage the selected users’ envelopes.

For example, if you are logged-in as Mujtaba and wants to use your account to activate the connector, sharing Nouman’s envelope access with you means that Securiti scans scan both your envelopes and Nouman’s envelopes.

> [!NOTE]
> **Note**
> 
> You can't select the users whose envelopes are already shared.

![mark_the_checkboxes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aeb9164c-69be-dbe6-ba6a-adc5fffb1a50.png)
  9. Repeat the above steps from **c** to **h** to include more user's envelopes in the scan.
  10. Scroll down to bottom of the page, and click **Save**.
12. For Self-hosted connector activation, you need an extra parameter (**Account ID**). Perform the following steps to save this:
  1. On the left sidebar, choose **INTEGRATIONS** > **Apps and Keys**.
  2. On the **Apps and Keys** page under the **My Account Information** section, record the **API Account ID** by clicking on the **Copy to clickboard** icon.

![ACCOUNT-ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a11cc9f-8bcc-83d4-b534-5c147fde65c0.png)
13. Proceed to [Connecting DocuSign (Self-hosted) with Securiti](/latest/docs/activate-the-docusign-connector-in-securiti) or [Connecting DocuSign (Securiti Cloud) with Securiti](/latest/docs/connecting-docusign-securiti-cloud-with-securiti)
