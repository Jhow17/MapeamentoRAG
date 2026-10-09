---
title: "Multiple Data Subject Identifiers for consent records"
slug: "multiple-data-subject-identifiers-for-consent-records"
updated: 2025-12-09T16:18:58Z
published: 2025-12-09T16:18:58Z
canonical: "helpcenter.securiti.ai/multiple-data-subject-identifiers-for-consent-records"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Multiple Data Subject Identifiers for consent records

When relaying consents from multiple source systems, source systems may rely on different data subject identifiers (UUIDs) to connect the consent to a specific data subject. This can be challenging when trying to manage consent records for the same data subject across different data systems.

> [!NOTE]
> **Important**
> 
> Securiti does not allow you to unlink the identifiers once they are cross-mapped. You must ensure the quality of the data using multi UUIDs.

The Universal Consent Management module can pass multiple UUIDs for a consent record and cross-maps these identifiers to make reporting on the consent of data subjects easier.

> [!NOTE]
> **Note**
> 
> This functionality is only available via APIs.

#### Example

Data subject John Doe may have the following UUIDs:

- Name: **John Doe**
- Email: **john.doe@example.com**
- Phone number: **555-555-5555**

John Doe does not have any consent currently recorded in the universal consent module.

> [!NOTE]
> **Important**
> 
> The UUIDs are case sensitive and Securiti only supports the **lower case parameters** currently.

### Using new multiple identifiers

- Once you upload a new consent record **CR1** by passing the **John Doe** (name) and **john.doe@example.com** (email) as data subject identifiers.
  - **John Doe** (name) and **john.doe@example.com** (email) are now considered as multiple data subject identifiers.
  - Retrieval of consent records by either **John Doe** (name) or **john.doe@example.com** (email) now returns **CR1**.
  - Retrieval of consent records by **555-555-5555** (phone number) returns **no records**.
- When you upload a new consent record **CR2** by passing **555-555-5555** (phone number) as the data subject identifier.
  - Consent retrieval by **555-555-5555** (phone number) now only returns **CR2**.
  - Retrieval of consent records by either **John Doe** (name) or **john.doe@example.com** (email) still continues to only return **CR1**.
- A third consent record **CR3** is now uploaded by passing **John Doe** (name) and **555-555-5555** (phone number) as data subject identifiers.
  - Retrieval of consent records by either **John Doe** (name) or **john.doe@example.com** (email) now returns **CR1** and **CR3**.
  - Retrieval of consent records by **555-555-5555** (phone number) returns **CR2** and **CR3**.

### Supported Use Cases

#### Recording consents

While recording or uploading consent, you can use the following APIs to pass the composite UUIDs:

- Integrate preference center using direct path using the [direct path API endpoint](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/pf_direct_path).
- Upload consent purposes using the [schedule upload consent API endpoint](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Consent%20upload).
- Subscribe and unsubscribe consent purposes using [narrow path link API endpoint](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#tag/Consent-Success-Pages).

#### Reading consents

While retrieving a previously uploaded consent record, you can use the following APIs to fetch the consent record using the composite UUIDs:

- Fetch consent status using the [fetch uploaded consents API endpoint](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Fetch%20all%20uploaded%20consents).
- Read the latest consent status using the [fetch latest consent status API endpoint](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Fetch_latest_consent_purpose).

#### 

A consumer or other member of the general public whose personal data is held by a controller or processor.

## Related

- [External UUID linking for consent records](/external-uuid-linking-for-consent-records.md)
- [Using the Unique Subject Identifier setting](/using-the-unique-subject-identifier-setting.md)
- [Universal Consent Management API reference](/universal-consent-management-api-reference.md)
