---
title: "Google Analytics"
slug: "google-analytics-connectors"
status: "new"
updated: 2026-04-28T03:50:56Z
published: 2026-04-28T03:50:56Z
canonical: "helpcenter.securiti.ai/google-analytics-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Analytics

Google Analytics is a web analytics service provided by Google that tracks and reports website traffic. It helps you analyze visitor behavior, track website performance, and gather insights into user engagement, acquisition channels, and conversion metrics. By integrating Google Analytics with Securiti, you can scan and secure your data. Google Analytics fall under [Monitored, scanless data systems](/latest/docs/managing-data-system-connectors),

### Supported connector type and module

| Connector type | Module supported |
| --- | --- |
| Google Analytics (Securiti cloud) | DSR Automation |

### Supported authentication methods

For Google Analytics, the OAuth-based authentication method is supported.

### Prerequisites for configuring the Google Analytics connector

#### 1. Admin access

- You must be an admin for your Google account to create projects and allow scopes.
- You must have the admin role in your Securiti accounts.

#### 2. Enable APIs in Google Workspace

In the Google Workspace account, enable the following APIs:

- Google Analytics API
- Admin SDK API

#### 3. Use cases and permissions for Google Analytics

This section covers use cases and permissions required for Google Analytics Securiti cloud connector.

#### Use case and permissions

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| Data Subject Requests (DSR) Automation | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/analytics, https://www.googleapis.com/auth/analytics.user.deletion, https://www.googleapis.com/auth/analytics.edit, https://www.googleapis.com/auth/analytics.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, ``` | These permissions build the Personal Data Index for DSR Automation. |

### Connect Google Analytics connectors with Securiti

This section covers the methods to integrate your Google Analytics with Securiti using the cloud connector.

**New UI**

#### Steps to connect the Google Analytics ( Securiti cloud) connector with Securiti

To activate the Google Analytics connector, perform the procedures in the following topics:

1. [Prerequisites and obtaining authentication credentials in Google apps](/latest/docs/google-analytics-connectors-prerequisites-and-obtaining-authentication-credentials-in-google-apps).
2. [(New UI) Connecting Google Analytics with Securiti](/latest/docs/new-ui-connecting-google-analytics-with-securiti).

See [Fulfilling DSR requests for Google Analytics](/latest/docs/fulfilling-dsr-requests-for-google-analytics) for more information about how Securiti uses the Google Workspace data and Google Analytics to respond to DSR requests.

**Classic UI**

#### Steps to connect the Google Analytics ( Securiti cloud) connector with Securiti

To activate the Google Analytics connector, perform the procedures in the following topics:

1. [Prerequisites and obtaining authentication credentials in Google apps](/latest/docs/google-analytics-connectors-prerequisites-and-obtaining-authentication-credentials-in-google-apps)
2. [Activate the Google Analytics connectors in Securiti](/latest/docs/activate-the-google-analytics-connectors-in-securiti)

See [Fulfilling DSR requests for Google Analytics](/latest/docs/fulfilling-dsr-requests-for-google-analytics) for more information about how Securiti uses the Google Workspace data and Google Analytics to respond to DSR requests.
