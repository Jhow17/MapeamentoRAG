---
title: "Enable the enterprise_content scope in Box"
slug: "enable-the-enterprise-content-scope-in-box"
updated: 2025-12-11T10:39:01Z
published: 2025-12-11T10:39:01Z
canonical: "helpcenter.securiti.ai/enable-the-enterprise-content-scope-in-box"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Enable the enterprise_content scope in Box

To use enhanced DSR Automation for your Box data system instance, you must provide the `enterprise_content` scope for your Box application, as described below.

## Obtain your Client ID and Customer EID

Follow this procedure to obtain your Client ID and Customer EID in the Box console. If you are activating a new Box connector, you have probably already recorded the application client ID and can skip ahead to the steps for Enterprise ID.

1. Sign in to the Box developer console with your admin credentials.
2. Open your application
3. Click the **Configuration** tab.
4. Scroll down to the OAuth 2.0 Credentials area and record the Client ID to use later.
5. Browse to this URL to open the Account & Billing page:

[https://app.box.com/master/settings/accountBilling](https://app.box.com/master/settings/accountBilling)
6. If necessary, click the **Account & Billing** tab.
7. Record the **Enterprise ID** shown on that page to use later.

## Submit a case

1. Submit a new request to [Box support](https://support.box.com/hc/en-us).
2. Sign in to Box with your admin credentials.
3. Click **Submit a Case**.
4. Apply the following settings:

| What can we help you with | Choose **Developer/API issue** |
| --- | --- |
| Briefly summarize your issue or question | Copy and paste the following text: **Need to enable the "enterprise_content" scope in my application.** |
5. Near the bottom of the page, click the **Proceed** button.
6. On the next page, apply the following settings:

| API Key/Client ID | Enter the Client ID you obtained in [Obtain your Client ID and Customer EID](/v1/docs/enable-the-enterprise-content-scope-in-box#obtain-your-client-id-and-customer-eid). |
| --- | --- |
| Give us more details | Copy and paste the following text: **I'm trying to search the file contents by using this search API: https://developer.box.com/reference/get-search/ I want the matches found for all users in one API call. I don't want to hit the API separately for each user separately. I read the API documentation and this scope parameter https://developer.box.com/reference/get-search/#param-scope can serve my purpose but the enterprise scope is not enabled by default. I need you to enable this support for my Box account** |
| Priority | Choose **High** |
| Are there other contacts you would like copied on updates? | (Optional) Provide email addresses for follow-up. |
| Customer EID | Enter the Customer EID you obtained in [Obtain your Client ID and Customer EID](/v1/docs/enable-the-enterprise-content-scope-in-box#obtain-your-client-id-and-customer-eid). |
7. Click **Submit**.
8. Wait for Box support to confirm that they have enabled the `enterprise_content` scope before proceeding.
