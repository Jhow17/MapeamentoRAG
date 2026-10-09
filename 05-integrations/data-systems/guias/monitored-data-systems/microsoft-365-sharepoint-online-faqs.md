---
title: "Microsoft 365 SharePoint Online FAQs"
slug: "microsoft-365-sharepoint-online-faqs"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/microsoft-365-sharepoint-online-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 SharePoint Online FAQs

This article answers frequently asked questions about the Microsoft 365 SharePoint Online connector.

### Authentication and credentials

This section covers the FAQs related to Microsoft 365 SharePoint Online authentication and activation credentials.

****Why does the connector and IAM metadata source require a certificate and Thumbprint credentials in addition to the OAuth Client ID and Secret?****

Connecting to SharePoint Online for SharePoint Site Inventory, Sensitive data scanning, and Access Intelligence scanning requires the use of two distinct Microsoft APIs:

- Microsoft Graph APIs
- SharePoint Administrative APIs

The **Microsoft Graph** API is fully compatible with Client ID and Client Secret Credentials, which can be assigned to the Azure Application that serves as the Integration point with Securiti.

However, the **SharePoint Administrative APIs** are not fully compatible with OAuth Client ID and Client Secret Credentials. Because of this limitation, the following information cannot be collected, which impacts key customer use cases.

****What are the missing use cases without certificate-based credentials in SharePoint Online?****

If you connect SharePoint Online with Securiti using Certificate-based Credentials, the following use cases are missed:

- SharePoint Site sharing properties cannot be retrieved:
  - Prevents Securiti from reporting on internal vs external site sharing scope.
  - Prevents Securiti from gathering Permissions information on SharePoint objects.
- Permissions data for SharePoint cannot be retrieved:
  - Blocks the ingestion of necessary data for reporting on file and site access within SharePoint.

****What are the requirements to generate certificate-based credentials for SharePoint Online?****

All customers connecting to SharePoint Online must generate a public and private key using OpenSSL (available by default on most Linux-based systems and installable on Windows PowerShell).

| Key type | Purpose |
| --- | --- |
| Public-auth-cert.pem | Upload the public key to the Azure App. This generates a Certificate Thumbprint, which Securiti requires as part of the Configuration. |
| Private-auth-key.pem | Provide the private key to the Securiti portal to facilitate Authentication |

### Selective site access and permissions

The FAQs below cover the SharePoint Online selective sites access applications and permissions.

****Why are two different Azure applications required to** **Scan only selected sites****?****

Two separate Azure applications are required because the permissions serve different purposes:

1. Selective Sites Access application:
  - Assigned the `Sites.Selected` permission
  - By itself, this permission doesn't allow access to any site collections
  - It is effectively a placeholder that enables the application to be granted site-specific Permissions later.
2. Full Control application (Provisioning application):
  - Assigned the `Sites.FullControl.All` permission
  - Used by a tenant/global administrator to explicitly grant the “Selective Sites Access” application permission to specific sites.

This separation ensures that:

- The access application (app with `Sites.Selected` permission) only operates on sites that have been deliberately authorized.
- The provisioning application (app with `Sites.FullControl.All` permission) holds broader rights but is used solely for granting and managing site Permissions, not for Connector Activation.

****Do you need the Full Control application to scan only the granted SharePoint sites?****

No, SharePoint Online Connector requires only the Selective Sites Access application to scan the granted sites. Securiti doesn’t use the Full Control application for scanning.

Full Control application is used only internally by the customer to fetch site information and grant access Permissions to the Selective Sites Access application.

****Why do you need the Full Control application at all?****

You need the Full Control application internally to:

- Query the Microsoft Graph API for all SharePoint sites
- Retrieve site IDs
- Grant Permissions to the Selective Access application.

Securiti doesn’t connect to or use **Full Control application**. It remains fully under your control. Without the Full Control application, there is no way to grant the Selective Access application the rights through Postman that it needs on specific sites. On its own, `Sites.Selected` permission provides no access, which means Securiti cannot scan any sites.

****What does the** `Sites.FullControl.All` **allow** **Securiti** **to do?****

The Full Control application uses the Microsoft Graph permission `Sites.FullControl.All`. With this permission, the application acts as a tenant-wide SharePoint administrator through Microsoft Graph. It discovers sites and grants or revokes per-site access for other applications.

When you enable the **Scan only selected sites** option during Connector Activation, the Full Control application grants rights to the Selective Access application. Securiti connects only to the Selective Access application, not to the Full Control application.

****If the Full Control permission is granted, does** **Securiti** **gain visibility into all SharePoint Online sites and the ability to scan them?****

No, Securiti cannot see all sites unless you hand it the Full Control app Credentials, which the selective-access setup avoids. The Selective Sites Access app only has `Sites.Selected` permission, giving it no access until an admin grants specific site access via Graph API mentioned below, using the Full Control app context. Securiti then scans only the sites you have granted.

*POST /sites/{site-id}/Permissions*

****With the selective sites option, if permissions are changed using the Full Control application, do those changes apply to all users who access the site?****

No, granting Permissions through POST /sites/{site-id}/Permissions applies only to the specified application registration. It does not change user Permissions or group memberships. Customers keep their original access; the change affects only what the application can do on that site.

****How does** **Securiti** **authenticate to SharePoint Online with the Selective Sites Access application?****

Securiti authenticates using app-only OAuth through Microsoft Entra ID to obtain Credentials. The Selective Site Access application presents its OAuth Credentials (Client ID and secret) and Certificate Credentials to obtain an app-only access Token. Using this Token, Securiti communicates directly with Microsoft Graph and SharePoint APIs.

****Do you need admin credentials to activate the connector with the app that has Selective Sites access?****

Admin Credentials are required when setting up SharePoint Self-hosted with selective sites access. An administrator must verify the Client ID and Client Secret during Connector Activation. This step serves as a security safeguard, ensuring that the Connection to your Microsoft 365 SharePoint Online Data system is explicitly approved by an authorized administrator.

****Why are SharePoint usage statistics (expected file count, storage usage, and site count) unavailable when the connector is configured with “****Scan only selected sites****”?****

When the SharePoint connector is configured with “**Scan only selected sites**,” it is restricted to only the specific sites you select. This limited access prevents the connector from reading tenant-wide usage data, such as the total number of sites, expected file count, and overall storage usage.

As a result, Securiti cannot collect or display usage statistics for the entire SharePoint environment.

****What permissions are required to use the Files Quarantine feature with selective sites access?****

To use the Files Quarantine feature with selective sites access, you must meet the following requirements:

- You must grant the `Sites.Selected` Microsoft Graph API application permission to the Selective Sites Access application.
- Additionally, you must assign the `Write` role to each SharePoint Online site retrieved using Postman through token verification with the Full Control application.

For more information, see [Obtain authentication credentials for SharePoint Online selective sites access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access).

### Scan coverage and file versions

The FAQs below cover the SharePoint Scanning capabilities and limitations.

****Does the SharePoint connector process all file versions during a Discovery Scan or Data Inventory Sync, or only the latest version?****

Securiti processes only the current (latest) version of each file rather than the full version history. As a result, the actual scannable data may be significantly lower than the reported storage footprint. For example, 80 TB, including version history, may be reduced to 70 TB when considering only current versions.

****How does the quarantine diagnostic report determine permission status for SharePoint Online?****

During quarantine diagnostics, Securiti checks multiple SharePoint sites to verify that quarantine permissions are correctly configured. The diagnostic continues checking sites until it finds a successful result or exhausts all sites. If at least one accessible site with the correct permissions is found, the diagnostic report shows the quarantine permission status as allowed. A failure on an individual site does not cause the overall diagnostic to fail.
