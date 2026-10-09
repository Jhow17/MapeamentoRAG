---
title: "Troubleshooting for Google Drive (Google Workspace) (Hyperdrive)"
slug: "troubleshooting-for-google-drive-google-workspace"
updated: 2026-07-20T20:58:02Z
published: 2026-07-20T20:58:02Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-google-drive-google-workspace"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Google Drive (Google Workspace) (Hyperdrive)

This section covers the troubleshooting steps in case of authentication and scanning failures.

### Discovery scan failure due to disabled Drive and Doc services

Sometimes, the Google Drive (Google Workspace) connector cannot perform discovery scans and return errors. It can be due to the **Drive** and **Docs service** being disabled. It is normally done to restrict the service option to limited users. Due to disabling the Drive and Docs service, Discovery scan errors can occur.

Perform the following steps to enable Doc and Drive services in Google Admin Console.

1. On the **Google Admin Console**, choose **Apps** > **Google Workspace** > **Drive and Docs**.
2. On the **Drive and Docs** page, click **Service status**.
3. Check if the service is disabled for the user attempting to authorize the Google Drive Connection.

> [!NOTE]
> **Note**
> 
> The service can be turned on or off for all users or specific users based on Groups or Organizational Units.
4. Ensure the service is enabled for the user via the admin email that you used while activation and reconfiguring the connector.

### Google Drive authentication failures

In case your connection fails with an `HTTP 401` error or a `permission issue` message, and the issue persists even after reconnection attempts, the error can have the following causes:

- Incorrect or invalid authentication keys are being used during Connector setup.
- The user account being used for the connection does not have the required license.
- The required roles, privileges, or API scopes are misconfigured.

To resolve the issue:

1. Ensure the user account used for the connector has an active Google Workspace license.
2. Verify the required permissions are configured as documented in [Using super admin role for Google Drive (Google Workspace) (Self-Hosted) (Hyperdrive)](/latest/docs/prerequisites-for-g-suite-google-drive-1).
3. Generate a new set of authentication keys for your account.
4. Re-authenticate the connector with the new keys.
