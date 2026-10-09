---
title: "Managing Securiti API keys"
slug: "managing-credentials-managing-securiti-api-keys"
updated: 2026-08-28T09:29:25Z
published: 2026-08-28T09:29:25Z
canonical: "helpcenter.securiti.ai/managing-credentials-managing-securiti-api-keys"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing Securiti API keys

You use Securiti API keys to authenticate Securiti API integrations. You can provision multiple keys and use them with different applications. API keys inherit the Securiti permissions of the user who created them. Passing these keys as headers is mandatory to make any API request effectively.

As an example, the following CURL command is used to **create a new user** in Securiti's platform. The command shows the required headers and their respective values.

You can get more details on the API usage in the [System settings API reference](https://securiti-doc-router.securiti.xyz/modules/system-settings/apidocs/index.html).

```bash
curl -X 'POST' \
  'https://app.securiti.ai/core/v1/admin/users' \
  -H 'accept: application/json' \
  -H 'X-API-KEY: XXXXXXXXXXXXXXXXXX' \
  -H 'X-API-SECRET: XXXXXXXXXXXXXXXXXX' \
  -H 'X-TIDENT: XXXXXXXXXXXXXXXXXX' \
  -H 'Content-Type: application/json' \
  -d '{
  "first_name": "john",
  "last_name": "doe",
  "email": "johndoe@xyz.com",
  "role": "SuperAdmin",
  "user_type": 1,
  "access_profile_id": 1234,
  "org_units": [
    0
  ],
  "user_name": "johndoe@xyz.com"
}'
```

### Creating a new API Key

> [!WARNING]
> Important
> 
> Effective from release 1.147, users with the Partner user type cannot create, regenerate, or manage API keys in a customer tenant. To run automated workflows on a customer's behalf, use a Service Account and its own API key instead. For more information, see [Create Service Accounts and API Keys](/latest/docs/create-service-accounts-and-api-keys-en).

1. In Securiti, click **Settings** and choose **Organizational > Access Management > API Keys**.
2. On the **API Keys** page, click **Generate API Credentials**.
3. On the **Generate API Access Credentials** popup, apply these settings, then click **Generate**:

| Setting | Description |
| --- | --- |
| API Scope | All API Access | Use this API key type to generate API keys for authentication purposes when executing API endpoints for all Securiti modules except Universal Consent Management or Privacy Central. |
| Consent | Use this API key type to generate API keys for authentication purposes when executing API endpoints only for the **Universal Consent Management** module. |
| Privacy Central DSR | Use this API key type to generate API keys for authentication purposes when executing API endpoints only for the **Privacy Central** dashboard. |
| Authentication Type | API Key Pair | Use to authenticate with the API key and secret. > [!NOTE] > **Note** > > Simple API keys do not expire; you are responsible for periodically regenerating the API keys as per your company infosec policies. |
| OAuth | Use to generate an OAuth token with limited lifespan. |

Securiti shows you the API Key Details popup.
4. Copy the API Secret, and save it in a safe place so you can use it with the API.

> [!NOTE]
> **Note**
> 
> Securiti only shows you the API Secret once, when you initially create the API key. If you lose the API Secret, you must regenerate the key and obtain a new secret.
5. In the **Name** box, enter a convenient name.
6. In the **API Key Description** box, enter a convenient description that helps you remember what the API key is for.
7. Click **Save**.

### Deleting an API key

1. In Securiti, click **Settings** and choose **Organizational > Access Management > API Keys**.
2. Next to the key you want to delete, click **Options** (three dots) **> Revoke**.

Securiti prompts you to confirm.
3. Click **Yes, Revoke Access**.

### Regenerating a simple API key

1. In Securiti, click **Settings** and choose **Organizational > Access Management > API Keys**.
2. Next to the simple key you want to regenerate, click **Options** (three dots) **> Regenerate**.

Securiti opens the API Details popup to show you the new key and secret.
3. Copy the API Secret, and save it in a safe place so you can use it with the integration.
4. If you want, edit the API description to suit.
5. Click **Save**.

### Editing the description of an API key

1. In Securiti, click **Settings** and choose **Organizational > Access Management > API Keys**.
2. Next to the key for which you want to edit the description, click **Options** (three dots) **> Edit Description**.

Securiti opens the API Description popup to let you edit the description.
3. Edit the API description to suit.
4. Click **Save**.

## Related

- [Managing Webhook URLs](/managing-credentials-managing-webhook-urls.md)
- [Managing SSH keys](/managing-ssh-keys.md)
- [Using keyrings in Securiti](/creating-keyrings.md)
