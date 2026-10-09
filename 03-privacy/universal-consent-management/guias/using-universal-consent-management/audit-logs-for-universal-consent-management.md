---
title: "Audit logs for Universal Consent Management"
slug: "audit-logs-for-universal-consent-management"
updated: 2025-11-05T07:34:53Z
published: 2025-11-05T07:34:53Z
canonical: "helpcenter.securiti.ai/audit-logs-for-universal-consent-management"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Audit logs for Universal Consent Management

Securiti generates and maintains audit logs for the Universal Consent Management module when you perform the following actions:

## Universal Preference Center

- Create a preference center
- Update a preference center
- Delete a preference center
- Publish a preference center

> [!NOTE]
> **Note**
> 
> Securiti does not maintain audit logs when you make only small textual or cosmetic changes in the preference center.

## Form Consent

- Create a new end-point for form-based consent
- Delete an existing end-point from form-based consent
- Publish an end-point for form-based consent
- When consent upload failure occurs from any of the following sources:

For instance, when your uploaded consent records fail because of database issues such as data transaction failure.

> [!NOTE]
> **Note**
> 
> When consent upload failure occurs, Securiti retries **five** times to upload the consent records before maintaining the audit log.
  - Form
  - Preference center
  - Consent APIs
  - Consent narrow path (Selective consent management)

## Custom Parameters

- Create a custom parameter
- Update a custom parameter
- Clone a custom parameter
- Delete a custom parameter

## Processing Purposes

- Create a processing purpose
- Update a processing purpose
- Clone a processing purpose
- Delete a processing purpose

## Processing Purpose Categories

- Create a processing purpose category
- Update a processing purpose category
- Clone a processing purpose category
- Delete a processing purpose category

## Consent Purposes

- Create a consent purpose
- Update a consent purpose
- Clone a consent purpose
- Delete a consent purpose

## Rules Matrix

- Add a rules matrix
- Edit a rules matrix
- Activate a rules matrix
- Deactivate a rules matrix
- Delete a rules matrix

## Platform Integrations

- Create a platform integration job
- Activate a platform integration job
- Deactivate a platform integration job
- Delete a platform integration job

## API Consent Sources

- Create a consent source
- Update a consent source
- Clone a consent source
- Delete a consent source

## Success Page

- Create a success page
- Update a success page
- Clone a success page
- Delete a success page

## Related

- [Viewing the Securiti audit log](/securiti-platform-viewing-the-securiti-audit-log.md)
