---
title: "Synchronizing assets from Okta"
slug: "synchronizing-assets-from-okta"
updated: 2026-04-24T10:57:08Z
published: 2026-04-24T10:57:08Z
canonical: "helpcenter.securiti.ai/synchronizing-assets-from-okta"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Synchronizing assets from Okta

> [!NOTE]
> **Important**
> 
> We assume you have the System Administrator role for your connector instance before configuring the asset sync via Okta.

You can synchronize Securiti with an Okta instance to import assets into your Securiti Data Mapping Automation module. This feature is not available to all accounts; contact Securiti support for details and to activate this feature for your Securiti account.

Perform the following procedures in sequence.

### Create an API token in Okta

1. Log in to Okta with your admin credentials.
2. Open **Security > API**, then click the **Tokens** tab.
3. Click **Create Token**.
4. On the Create Token popup, enter a descriptive name for the new token and click **Create Token**.

The popup shows you the Token Value for the token you just created.
5. On the Create Token popup, record the Token Value to use later.
6. Click **OK, Got it** to dismiss the popup.

### Record your Okta instance ID

1. At the top of any Okta admin console page, expand the area that shows your user account details.
2. Record the portion of the URL immediately before .okta.com as shown below.

![Okta_instance_ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0969fd03-84b6-3f36-5f3e-5b7b0ec9f26a.png)

This portion of the URL is your instance ID. In this example the instance ID is "dev-123456".

### Activate the Okta asset connector in Securiti

1. In Securiti open **Settings > Data Systems**, or from the System Settings page, select **Data Systems > Data Systems (Monitored)**.
2. Under “Integrations”, click **CMDB Systems**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Navigation_path(2).png)

In the upper right corner of the page, click **Add CMDB Systems**.
3. Choose the card for “Okta” to create a new instance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add_new_CMDB_data_system(2).png)

> [!NOTE]
> Note
> 
> The updated flow to access CMDB data systems is not available to all accounts; contact your Securiti representative for details and to activate this feature for your Securiti account.
4. On the Basic Information tab, apply the following settings:

| Setting | Description |
| --- | --- |
| Instance Name | Enter a convenient name for the instance. |
| Owner | Choose additional co-owners for the instance if you want. By default you are the instance owner. |
5. Click **Create Instance and continue**.

Securiti advances you to the Instance Setup tab.
6. On the Instance Setup tab, apply the following settings:

| Setting | Description |
| --- | --- |
| Instance ID | Paste the Instance ID you recorded in [Record your Okta instance ID](/v1/docs/synchronizing-assets-from-okta). |
| API Token | Paste the Token Value you recorded in [Create an API token in Okta](/v1/docs/synchronizing-assets-from-okta). |
7. (Optional) Use the scheduling tools to schedule regular scans, and also to schedule exclusion periods.
8. Near the bottom of the page, click **Save**.
9. Click **Activate Connector**.

Securiti tests the credentials and information you provided to check whether they give it access necessary to scan Okta for assets
10. (Optional) Click **Run a scan now** to immediately scan Okta for assets.
