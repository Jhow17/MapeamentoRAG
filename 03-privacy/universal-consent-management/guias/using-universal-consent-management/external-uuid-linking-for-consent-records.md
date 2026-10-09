---
title: "External UUID linking for consent records"
slug: "external-uuid-linking-for-consent-records"
updated: 2025-12-09T16:19:09Z
published: 2025-12-09T16:19:09Z
canonical: "helpcenter.securiti.ai/external-uuid-linking-for-consent-records"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# External UUID linking for consent records

When recording consent from multiple sources, the challenging bit is to link those consents together that belong to the same data subject. There is a possibility that your data subject may provide their consent for the first time with their email (UUID) and later on, with their phone number (UUID). In this case, you want to ensure that you are recording and honoring the latest consent given by the data subject. With external ID linking, Securiti lets you cross map the different UUIDs of the same data subject with each other.

> [!NOTE]
> **Note**
> 
> This functionality is only available via APIs.

The external ID linking feature maps these multiple UUIDs for a data subject against a single and unique primary identifier via a [POST API endpoint for external ID linking](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/External_ID_linking). So when you update one consent using a specific UUID, that update is reflected over all of the consents for the IDs linked with the same primary key. You can also delink the linked UUIDs at any given time by using the same API endpoint as per the consent preference of the data subject.

> [!NOTE]
> **Important**
> 
> - Securiti lets you **link** and **delink** the UUIDs at any time, irrespective of when the last consent was recorded.
> - This is a general feature and applies to any consent type such as preference center, forms, and consent records.

For instance, a data subject John Doe may have the following UUIDs:

| UUID | Value |
| --- | --- |
| Name | John Doe |
| Email | john@email.com |
| Phone number | 555-555-5555 |

### Recording consents before external ID linking

John Doe does not have any consent currently recorded in the universal consent module and plans to record their consent for the first time.

- A new consent record **CR1** is uploaded for the first time by passing the **john.doe@example.com** (email) as data subject identifier.
- A second consent record **CR2** is now uploaded by passing **555-555-5555** (phone number) as data subject identifier.
- Finally, a third consent record **CR3** is uploaded by passing **John Doe** (name) as data subject identifier.

There are now three individual consent records of John Doe in the system which are not linked together. Without enabling external ID linking, the retrieval of consent record by **email** only returns **CR1**. Similarly, retrieval of consent records by **phone number** or **name** returns **CR2** or **CR3** respectively. You can link the aforementioned UUIDs (name, email, and phone number) to a primary identifier to make it easy for you to fetch all consent records at once by using that primary identifier.

### Linking external IDs

You can link the UUIDs of John Doe together with a **POST API** endpoint for external ID linking that includes the **primary identifier** in the following CSV format.

```plaintext
primary_id,uuid,org_id,i
```

| Input Format | Description |
| --- | --- |
| primary_id | Primary identifier |
| UUID | The UUID with which the consent record was uploaded such as name, email of phone number of John Doe |
| org_id | The organization ID of the data subject. |
| i | Action for the linking operation |
| d | Action for the delinking operation |

You can use the following request body in the API and you must add a new row for a new UUID:

```plaintext
primary_id,uuid,org_id,action
1234,john@example.com,1,i
1234,555-555-5555,1,i
1234,John Doe,1,i
```

> [!NOTE]
> **Note**
> 
> The request body must be in CSV format and you must add new rows for additional UUIDs in the request body to link them together.

Securiti also lets you retrieve all the linked IDs for a specific primary identifier via a [GET API](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Fetch_linked_UUIDs) call.

### Reading consents after external ID linking

After you perform the external ID linking:

- Retrieval of consent records by any of the data subject identifiers such as **name**, **email** or **phone number** returns all consent records **CR1**, **CR2** and **CR3**.
- You can retrieve consent records from the preference center based on the latest record. For instance, if a data subject declines a consent using email as UUID and then grants the consent at a later time using the phone number as UUID, the latest action is considered the final consent. This final change is displayed in the preference center.

### Delinking the external IDs

Securiti also lets you delink the data subject identifiers. To delink any or all of the UUIDs, simply use the action “**d**” instead of “**i**” in the request body of the API as shown below:

```plaintext
primary_id,uuid,org_id,action
1234,john@example.com,1,d
1234,555-555-5555,1,d
```

Once the UUIDs are delinked, the retrieval of consent record depends upon the UUID with which that consent record was uploaded. For more information, see [Multiple Data Subject Identifiers for consent records](/v1/docs/multiple-data-subject-identifiers-for-consent-records).

> [!NOTE]
> **Note**
> 
> External ID linking is also applicable while accessing the preference center.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Multiple Data Subject Identifiers for consent records](/multiple-data-subject-identifiers-for-consent-records.md)
- [Using the Unique Subject Identifier setting](/using-the-unique-subject-identifier-setting.md)
- [Universal Consent Management API reference](/universal-consent-management-api-reference.md)
