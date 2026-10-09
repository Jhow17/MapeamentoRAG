---
title: "Acquire authentication credentials in InterSystems Cache"
slug: "acquire-authentication-credentials-in-intersystems-cache"
updated: 2026-07-10T05:34:08Z
published: 2026-07-10T05:34:08Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-intersystems-cache"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in InterSystems Cache

1. Login to InterSystems Cache instance.
2. Record the following parameters to use later:

> [!NOTE]
> **Note**
> 
> This procedure assumes that you have access to the Cache database before connector activation.

You can change default JDBC Credentials from system administration.
  - **Host** - Where IRIS is deployed.
  - **Port** - SuperServer port (*51773*)
  - **User** - Default user (*_SYSTEM*)
  - **Password** - Default password (*SYS*)
  - **Namespace** - Default namespace (*User*)
  - **Database** - Db you're connecting to.
3. Proceed to [Connecting InterSystems Cache (Legacy) with Securiti](/latest/docs/connecting-intersystems-cache-legacy-with-securiti).
