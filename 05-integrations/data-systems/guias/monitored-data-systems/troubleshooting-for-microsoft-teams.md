---
title: "Troubleshooting guide for Microsoft Teams"
slug: "troubleshooting-for-microsoft-teams"
updated: 2026-09-28T07:12:17Z
published: 2026-09-28T07:12:17Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-microsoft-teams"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting guide for Microsoft Teams

This article covers the troubleshooting guide for Microsoft Teams connector.

# 1. Microsoft Teams Metadata Scan Fails with 403 Forbidden Error

**Issue**

While configuring **Microsoft Teams**, the metadata scan fails during the Scoping Inventory Sync.

The following error is observed:

```plaintext
An error occurred during Scoping Inventory Sync: GET https://graph.microsoft.com/v1.0/teams/<team-id>/channels: 403 {"error":{"code":"Forbidden","message":"Failed to execute GetChildThreadsV2Async."}}
```

**Cause**

The error occurs when the Azure application used for the Microsoft Teams configuration does not have the required Microsoft Graph API permission to access Teams channel information.

**Resolution**

Add the following **Microsoft Graph API permission** to the application in Azure:

`ChannelSettings.Read.All`

After adding the permission:

1. Grant **Admin Consent** for the newly added permission.
2. Verify that the permission is successfully applied to the Azure application.
3. Retry the **Microsoft Teams metadata scan**.

The metadata scan should complete successfully once the required permission is available.
