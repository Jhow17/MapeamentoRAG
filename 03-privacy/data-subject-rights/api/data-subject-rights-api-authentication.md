---
title: "API authentication"
slug: "data-subject-rights-api-authentication"
updated: 2026-08-28T09:31:03Z
published: 2026-08-28T09:31:03Z
canonical: "helpcenter.securiti.ai/data-subject-rights-api-authentication"
stale: true
area: privacy
modulo: data-subject-rights
tipo: api
data_captura: 2026-10-08
---

# API authentication

The Privacy Central API uses API keys to authenticate requests. You can view and manage your API keys in the Securiti Portal under **Settings > Organizational > Access Management > API Keys**.

### Authenticate with API key and secret

1. Log into Securiti with your admin credentials.
2. Go to **Settings > System > API Keys** and provision an API key of type **DSR**.
3. Download the key and its secret and keep them safe.

Your Securiti access permissions are inherited by the API key. You can provision multiple keys and use them with different applications. Ideally, you should use a “service” user account for such API keys.
4. Pass the key and secret as request headers X-API-KEY and X-API-SECRET respectively.
5. Add header "X-TIDENT" in all API requests; set the value of this header to "Tenant Identifier," which you can retrieve from within Securiti under **System Settings > General > Basic Information**.

> [!NOTE]
> Note
> 
> You cannot execute Privacy Central APIs using Service Account API keys.
