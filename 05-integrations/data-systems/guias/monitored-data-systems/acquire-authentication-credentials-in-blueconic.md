---
title: "Acquire authentication credentials in Blueconic"
slug: "acquire-authentication-credentials-in-blueconic"
updated: 2026-06-10T18:37:14Z
published: 2026-06-10T18:37:14Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-blueconic"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Blueconic

1. Log in to Blueconic.

> [!NOTE]
> **Note**
> 
> This procedure assumes you have access to your Blueconic creds before activating the connector. See the [steps to create an application](https://support.blueconic.com/hc/en-us/articles/202608251-BlueConic-API-Access-Connection-) for more information.
2. Blueconic uses the following activation params:
  1. Consumer key
  2. Consumer secret
  3. Domain
3. For Blueconic "Domain":

| Account type | Domain |
| --- | --- |
| Sandbox | https://<*domain.name*>.blueconic.net/ **domain.name** is your Domain for connector activation. |
| Prod | https://<*domain*>.blueconic.net/ **domain** is your Domain for connector activation. |
4. Proceed to [Connecting Blueconic with Securiti](/latest/docs/connecting-blueconic-with-securiti).
