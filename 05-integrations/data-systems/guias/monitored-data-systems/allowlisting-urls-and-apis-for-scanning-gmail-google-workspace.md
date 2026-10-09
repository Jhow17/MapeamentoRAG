---
title: "Allowlisting URLs and APIs for Gmail data inventory sync"
slug: "allowlisting-urls-and-apis-for-scanning-gmail-google-workspace"
updated: 2026-06-23T20:11:56Z
published: 2026-06-23T20:11:56Z
canonical: "helpcenter.securiti.ai/allowlisting-urls-and-apis-for-scanning-gmail-google-workspace"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Allowlisting URLs and APIs for Gmail data inventory sync

Allowlist the following APIs between your deployed Securiti Pod and the Gmail APIs to run Data Inventory Sync successfully.

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://www.googleapis.com/admin/directory/v1/customer/my_customer/domains | Fetch all configured workspace domains |
| 2 | GET | https://www.googleapis.com/admin/directory/v1/users/ | List all workspace users |
| 3 | GET | https://www.googleapis.com/admin/directory/v1/users/{userId} | Get a specific user's primary email |
| 4 | GET | https://www.googleapis.com/admin/directory/v1/groups/ | List all workspace groups |
| 5 | GET | https://www.googleapis.com/admin/directory/v1/groups?userKey={email} | List groups a specific user belongs to |
| 6 | GET | https://www.googleapis.com/admin/directory/v1/groups/{groupId}/members | List members of a specific group |
| 7 | GET | https://www.googleapis.com/admin/directory/v1/customer/my_customer/orgunits | List all organizational units |
| 8 | GET | https://www.googleapis.com/gmail/v1/users/{userId}/labels | List mailbox labels/folders for a user |
| 9 | GET | https://www.googleapis.com/gmail/v1/users/{userId}/settings/delegates | List mailbox delegates for a user |
| 10 | GET | https://www.googleapis.com/gmail/v1/users/{userId}/messages | List emails in a mailbox |
| 11 | GET | https://www.googleapis.com/gmail/v1/users/{userId}/messages/{messageId} | Get email metadata (headers, date, sender) |
| 12 | GET | https://www.googleapis.com/gmail/v1/users/{userId}/messages/{messageId}/attachments/{attachmentId} | Download email attachment data |
