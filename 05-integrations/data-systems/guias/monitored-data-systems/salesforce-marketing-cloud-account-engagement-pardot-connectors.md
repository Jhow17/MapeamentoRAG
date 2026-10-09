---
title: "Salesforce Marketing Cloud Account Engagement (Pardot)"
slug: "salesforce-marketing-cloud-account-engagement-pardot-connectors"
status: "new"
updated: 2026-04-06T07:07:28Z
published: 2026-04-07T04:09:15Z
canonical: "helpcenter.securiti.ai/salesforce-marketing-cloud-account-engagement-pardot-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Salesforce Marketing Cloud Account Engagement (Pardot)

Pardot is a marketing automation tool designed to help businesses streamline and enhance their marketing efforts. It supports lead generation, nurturing, and scoring, and enables businesses to optimize their marketing campaigns across different channels, such as email, social media, and content marketing. Securiti integrates with Pardot connector for Privacy Platform Integration to extract consent from the Pardot objects.

Pardot falls under the [category of monitored, scanless connector](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Salesforce Marketing Cloud Account Engagement (Pardot) (Securiti Cloud) | Universal Consent Management (Privacy Platform Integration) |

### Supported authentication methods

Pardot supports the following authentication types for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| OAuth | - Business Unit ID - Consumer ID - Consumer Secret |

### Prerequisites for configuring Pardot in Securiti

You must complete these prerequisites before connecting your Pardot connector with Securiti

#### 1. Create a connected app in Salesforce

- Create a connected app as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5).

For more information on fetching token, see [Salesforce documentation on OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&amp;type=5).

#### 2. Acquire client credentials

- Record the Consumer ID and secret for your app. Fetch the Business ID as described in [Salesforce documentation for Account Engagement Business ID](https://help.salesforce.com/s/articleView?id=000381973&amp;type=1).

#### 3. Permissions and use cases for Pardot

- In **App Manager**, under the **API (Enable OAuth Settings)** section, add the following scopes in the **Selected OAuth Scopes**.

| Modules use case | Constraint | Scopes | Explanation of use case |
| --- | --- | --- | --- |
| Privacy Platform Integration | Privacy Platform Integration is currently supported for the Securiti Cloud connector only | - `Manage Pardot Services (pardot_api)` - `Access and manage your data (api)` | These scopes enable Securiti to fetch Pardot Prospects for extracting consents as part of the Privacy Platform Integration. |

#### 4. Connect Pardot (Securiti Cloud) connector with Securiti

To configure the Pardot (Securiti Cloud) connector, perform the following steps:

1. Create a connected app as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5) and fetch credentials, as described above.
2. [Activate the Salesforce Marketing Cloud Account Engagement (Pardot) (Securiti Cloud) connector in Securiti](/v1/docs/activate-the-salesforce-marketing-cloud-account-engagement-pardot-securiti-cloud-connector-in-securiti).
3. [Configure Pardot integration in Securiti](/v1/docs/pardot).

#### 4. Connect Pardot (Securiti Cloud) connector with Securiti

**New UI**

To configure the Salesforce Marketing Cloud Account Engagement (Pardot) (Securiti Cloud) connector, perform the following steps:

1. Create a connected app as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5) and fetch credentials, as described above.
2. [(New UI) Connecting Salesforce Marketing Cloud Account Engagement (Pardot) with Securiti](/latest/docs/new-ui-connecting-salesforce-securiti-cloud-with-securiti-1).
3. [Configure Pardot integration in Securiti](/latest/docs/pardot).

**Classic UI**

To configure the Salesforce Marketing Cloud Account Engagement (Pardot) (Securiti Cloud) connector, perform the following steps:

1. Create a connected app as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5) and fetch credentials, as described above.
2. [Activate the Salesforce Marketing Cloud Account Engagement (Pardot) (Securiti Cloud) connector in Securiti](/latest/docs/activate-the-salesforce-marketing-cloud-account-engagement-pardot-securiti-cloud-connector-in-securiti).
3. [Configure Pardot integration in Securiti](/latest/docs/pardot).
