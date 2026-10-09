---
title: "Flurry"
slug: "flurry-connectors"
status: "update"
updated: 2026-07-20T09:50:40Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/flurry-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Flurry

---

Flurry is a mobile app analytics platform for Android and iOS that helps developers and product teams optimize app experiences by analyzing user activity across their app portfolio. It provides insights into user engagement, retention, audience segmentation, and in-app behavior, making it a widely adopted analytics solution for mobile-first organizations managing multiple applications simultaneously.

The Flurry connector lets you integrate your Flurry environment with Securiti to discover and govern mobile analytics and user behavioral data collected across your app portfolio.

Flurry falls under the category of Monitored, Scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Flurry (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- For Securiti Cloud connector:
  - Flurry application-based authentication
    - API Key for authentication

### Prerequisites for configuring Flurry connector

#### 1. Admin access

You must have admin access in Flurry to generate a Token to authenticate your connector.

For more information, see [Acquire the API access token in Flurry](/latest/docs/acquire-the-api-access-token-in-flurry).

#### 2. Use cases and permissions for Flurry

This table covers use cases and permissions required for Flurry (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to create a new **Programmatic User** in Flurry application. - Access to create an account and obtain **Access Token**. | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Flurry (Securiti Cloud) connector with Securiti

To configure the Flurry connector, perform the procedures in the following topics:

1. [Acquire the API access token in Flurry](/latest/docs/acquire-the-api-access-token-in-flurry).
2. [Connect the Flurry connector with Securiti](/latest/docs/connect-flurry-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Flurry](/latest/docs/fulfilling-dsr-requests-for-flurry).

If you are using enhanced DSR processing, see [Understanding enhanced DSR request processing](https://helpcenter.securiti.ai/docs/understanding-identifiers-for-dsr-request-processing) for a list of the data element types supported as identity PD.

An API key is a unique identifier used to connect to, or perform, an API call.

A token is a small piece of data, typically in the form of a string, that serves as an authentication or authorization mechanism. It is used to verify the identity of a user or application and grant access to specific resources or functions. Tokens are commonly used for security and access control in API interactions.
