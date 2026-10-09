---
title: "Acquire authentication credentials in Go File Room"
slug: "acquire-authentication-credentials-in-go-file-room"
updated: 2026-07-07T07:01:34Z
published: 2026-07-07T07:01:34Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-go-file-room"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Go File Room

Go File Room only offers subscription-based account access. This document assumes that you have access to the administration portal and can obtain the necessary activation parameters.

> [!NOTE]
> **Important**
> 
> Ensure the service account has read access to the drawers and indexes that must be scanned. To set up the required Permissions, contact your Go File Room account administrator.

1. Log in to Go File Room with your administrator Credentials and collect the following information:

| Parameter | Description |
| --- | --- |
| User Email | Go File Room service account email with sufficient privileges to read the required drawers and indexes email. |
| Password | Password for the service account. |
| API Key | Access from your organization’s Go File Room developer portal. [https://developerportal.thomsonreuters.com/home](https://developerportal.thomsonreuters.com/home) |
| Tenant prefix | Record your Go File Room tenant prefix. For example, if your GoFileRoom access URL is **qed.gofileroom.com**, “qed” is your account parameter. |
2. Proceed to [Connecting Go File Room with Securiti](/latest/docs/connecting-go-file-room-with-securiti).
