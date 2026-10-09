---
title: "Troubleshooting guide for Workday connector"
slug: "troubleshooting-guide-for-workday-connector"
updated: 2025-10-31T06:38:55Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/troubleshooting-guide-for-workday-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting guide for Workday connector

This section covers troubleshooting for the following issues when configuring the Workday Data system Connector.

### Connector activation failed or unable to find data in the learning results or discovery scan results

> [!NOTE]
> **Note**
> 
> The troubleshooting steps apply if you have activated the Workday Connector using the **Basic Authentication** type only.

If Connector Activation fails or no data is visible after a Cloud Connector completes Learning or a Self-hosted Connector completes a Discovery scan, the issue may be due to an incorrect username, password, or a locked account.

To resolve these problems, verify the following details.

1. **Verify username.**

Double check and verify that the value added for **User** in **Basic Authentication** is in the following format: username@tenant.
2. **Verify password**

Double-check and verify that the value added for the **Password** is correct.
3. **Verify account locked status**

If Authentication fails with valid Credentials, verify that the account used to activate the Connector is unlocked. Workday might lock the account if it was previously used to activate the Connector with an incorrect **Password**.
  1. To check if the account used to activate the Connector is locked, log in with an admin account on Workday.
  2. Search and select the **Integration System User Security Configuration** report.
  3. From the list, find the **Integration System User** you used to activate the Connector.
  4. Click on the **three dot menu** (Related Actions) beside your username and select **Security Profile** > **View Workday Account** from the menus.

![view-workday-account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf6dc361-ecbd-9caa-b383-e5347c8bd1ea.png)
  5. On the **Workday Account for Person** page, scroll down and look for **Locked Out due to Excessive Failed Signon Attempts**.

![WD-for-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05db7c35-ffa4-5b43-e369-46db4406967b.png)

If the information in **Locked Out due to Excessive Failed Signon Attempts** is not visible on the account details page, the account is not locked out due to failed attempts (invalid username or password)

### Unlock integration system user account

When a user activates the Workday Connector using an invalid username or password, the API returns an error immediately. However, the system is designed to retry API requests upon error a few times before giving up. Due to retries with invalid Credentials, Workday sometimes locks the account.

There are two ways to unlock a locked-out account.

- **Reset Password.**

Reset the password for the locked out account to unlock the account immediately.
- **Use manage workday accounts task**
  1. Search and select the **Manage Workday Accounts** task.
  2. Select **Unlock Workday Accounts** and **Include Selected Workday Accounts** options.
  3. Search and select the user you want to unlock.
  4. Click **Ok** to unlock the account.

![manage-WD-Ac.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf142b97-4a2c-3ea8-9ace-5138f8f076b1.png)
  5. You can follow the steps above in the **Verify account locked status** section to verify the account locked-out status.

### Allowlist IP addresses in case of restriction

If you have enforced restrictions on IP addresses in Workday, the Workday Connector in Securiti would not be able to connect to your Workday account through APIs.

Perform the steps below to check if your Workday account has blocked any API action after Connector Activation failed.

1. Log in to your Workday admin account.
2. Search and select **Signons and Attempted Signons** report.

The new popup appears.

It shows the list of all the sign-on attempts performed through the selected account.

![sign-ons.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f422391c-ecf2-cae7-c31c-7e4ee5e0d91d.png)

If sign-on attempts are marked as failed due to an invalid Authentication policy, the API actions might be blocked due to IP restrictions in an Authentication policy.
  1. Set the **time ranges**.
  2. Choose **Select Workday Accounts**, search, and select the I**ntegration System User** you used to activate the Workday Connector.
  3. Check the **Show Signon Attempts with an Invalid User Name** option to show invalid attempts.
  4. Click **Ok** once the Configuration is complete.

![attempted_signons.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2ed7f64-003e-c170-4065-d08f060145fe.png)
3. Whitelist the IP addresses in Workday used by Securiti's system before proceeding.

The same **Signons and Attempted Signons** report also shows blocked sign-on attempts due to an invalid username or password.

![signon-failed.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f1b8aaa-c788-8881-b5ab-70851888349d.png)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
