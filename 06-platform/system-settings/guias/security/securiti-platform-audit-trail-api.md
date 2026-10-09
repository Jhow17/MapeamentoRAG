---
title: "Audit trail API"
slug: "securiti-platform-audit-trail-api"
updated: 2026-08-19T13:42:49Z
published: 2026-08-19T13:42:49Z
canonical: "helpcenter.securiti.ai/securiti-platform-audit-trail-api"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Audit trail API

### Authentication

The Securiti API uses API keys to authenticate requests. You can view and manage your API keys in Securiti under **System Settings > Integrations > Credentials > API Keys**:

1. Log into Securiti with your admin credentials.
2. Click **Settings**, then choose **Organizational > Access Management > API Keys** and provision an API key of type **User**.
3. Download the key and its secret and keep them safe. Your Securiti access permissions are inherited by the API key. You can provision multiple keys and use them with different applications. Ideally, you should use a "service" user account for such API keys.
4. Pass the key and secret as request headers X-API-KEY and X-API-SECRET respectively.
5. Add header X-TIDENT in all API requests. You must set the value to "Tenant Identifier" which you can retrieve from **Securiti > Settings > General > Basic Information**.

> [!NOTE]
> **Important**
> 
> You must pass the X-TIDENT header along with the API key and secret for every API call.

```plaintext
'X-API-KEY: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' 
'X-API-SECRET: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 
'X-TIDENT: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'
```

### Reporting query

```bash
POST {{reporting-api-server-url}}/reporting/v1/stored_queries/execute
```

```json
{
    "name": "get_audit_trail",
    "skip_cache": true,
    "response_config": {
        "format": 1
    },
    "order_by": [
        "event_time",
        "id"
    ],
    "pagination": {
        "type": "limit-offset",
        "offset": 0,
        "limit": 100
    },
    "filter": {
        "op": "gte",
        "field": "event_time",
        "value": 1622476258381
    }
}
```

Sample response:

```json
{
    "status": 0,
    "message": "Request completed successfully",
    "data": [
        {
            "activity_type": "login",
            "associated_items": null,
            "changed_values": null,
            "event_time": 1618933647673,
            "id": "xsP373gBa6qsvCBBEqWM",
            "ip_address": "127.0.0.1",
            "is_impersonated_user": false,
            "item": {
                "user_email": "dev@securiti-dev.net"
            },
            "message": "User dev@securiti-dev.net logged in",
            "object_type": "session",
            "source": "",
            "user_agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:88.0) Gecko/20100101 Firefox/88.0",
            "user_email": "dev@securiti-dev.net"
        },
        {
            "activity_type": "create",
            "associated_items": null,
            "changed_values": null,
            "event_time": 1619085421550,
            "id": "wmgC-XgB8IVAhTpv-CxJ",
            "ip_address": "192.168.65.6",
            "is_impersonated_user": false,
            "item": {
                "connector_id": 1
            },
            "message": "Asset Database Created",
            "object_type": "asset_sync_connector",
            "source": "",
            "user_agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 11_2_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.128 Safari/537.36",
            "user_email": "dev@securiti-dev.net"
        }
    ]
}
```

Response fields:

| activity_type | Activity type of the log (e.g: create, update, delete etc) |
| --- | --- |
| associated_items | Items associated with the audit log |
| changed_values | Values that were modified by the action |
| event_time | Time of the event |
| id | Unique identifier for the audit log |
| ip_address | IP address of the user whose action generated this audit log |
| is_impersonated_user | Is set to true if the action was performed by our system on behalf of the user |
| item | Object that identifies the item on which action was performed |
| message | Actual audit log |
| object_type | Object type of the log (e.g: user, session etc) |
| source | Source of the audit log (e.g: workflow) |
| user_agent | User agent of the system that performed the action |
| user_email | Email of the user who performed the action. If `is_impersonated_user` is true, this is the email of a user who was impersonated by the system |

### Pagination

Pages can be traversed using pagination options in the query:

```json
"pagination": {
    "type": "limit-offset",
    "offset": 100,
    "limit": 200
}
```

Maximum value for the limit is 10,000. The greater the limit, the more time the API takes to process and return the response.

However, there’s a maximum limit of offset to be 10,000. To continue traversing we recommend you use a range filter on the event_time:

```json
"filter": {
    "op": "gte",
    "field": "event_time",
    "value": 1622476258381
}
```

### Strategy for ingesting audit logs

1. Fetch `event_time` and id of the last log from the checkpoint (OR initialize `event_time` to 0 and last log id to “”)
2. Pass the `event_time` to the range filter of the query. With a pagination limit of 5000 and offset of 0.

If the results length is zero, halt the current iteration.
3. If the last log id is not empty, traverse the logs and look for that id. When found, only ingest the logs into the system after that point.
4. Save the `event_time` and id of the last log (logs are ordered by event_time and id) as checkpoint for the next iteration.

### Caveats

> [!NOTE]
> **Note**
> 
> It may take up to 30 seconds for the system to report audit trails.

An API key is a unique identifier used to connect to, or perform, an API call.

An Object or an Object Question is an entity that holds data and is part of the Assessment V2 Object and Field Framework. For example, a Data Mapping entity such as an Asset or a Process is an Object. This can also mean any entity in the source of truth module and not limited to Data Mapping is considered an Object that you can use to create object questions in the assessment.

## Related

- [Opening Securiti applications](/securiti-platform-opening-securiti-applications.md)
- [Viewing the Securiti audit log](/securiti-platform-viewing-the-securiti-audit-log.md)
