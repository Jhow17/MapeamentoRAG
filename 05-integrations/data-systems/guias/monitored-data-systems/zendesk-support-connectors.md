---
title: "Zendesk Support"
slug: "zendesk-support-connectors"
status: "new"
updated: 2026-07-16T07:47:41Z
published: 2026-07-16T07:47:41Z
canonical: "helpcenter.securiti.ai/zendesk-support-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Zendesk Support

Zendesk is a business customer service suite that includes several software tools for content and customer relationship management.

Zendesk complies with GDPR and the Privacy Shield Framework, which lets it transfer and process personal data in compliance with American and European legislative requirements.

Archived logs of Zendesk support tickets submitted by users are usually deleted automatically, but the redaction of any of the contents of these support tickets must be done manually. The USER API within Zendesk platforms can delete and export stored data. Zendesk has stated that it may replicate service data at its discretion for the explicit purposes of backup, archival, and auditing through Amazon Web Services (AWS).

Zendesk Support falls under the category of Monitored and is a combination of Structured and Unstructured data systems.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

### Connect Zendesk Support (Self-hosted) connectors with Securiti

To configure the Zendesk Support connector, perform the procedures in the following topics:

1. [Granting minimum permissions for Zendesk Support (Self-hosted)](/latest/docs/granting-minimum-permissions-for-zendesk-support-self-hosted)
2. [Register an application in Zendesk Support (Self-hosted)](/latest/docs/register-an-application-in-zendesk-support-self-hosted)
3. [Connecting Zendesk Support with Securiti (Self-hosted)](/latest/docs/connecting-zendesk-with-securiti-self-hosted)
4. [Configuring Data Inventory Sync for Zendesk Support (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted)
5. Configure discovery scan

### Connect Zendesk Support (Securiti-Cloud) connectors with Securiti

To configure the Zendesk Support connector, perform the procedures in the following topics:

1. [Granting minimum permissions for Zendesk Support (Securiti hosted)](/latest/docs/granting-minimum-permissions-for-zendesk-support-securiti-hosted)
2. [Register an application in Zendesk Support (Securiti hosted)](/latest/docs/register-an-application-in-zendesk-support-securiti-hosted)
3. [Connecting Zendesk Support with Securiti (Securiti hosted)](/latest/docs/connecting-zendesk-support-with-securiti-securiti-hosted)
4. [Configure discovery scans in Zendesk Support (Self-hosted)](/latest/docs/configure-discovery-scans-in-zendesk-support)

### Additional resources

- [Fulfilling DSR requests for Zendesk Support (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-zendesk-support)
- [Fulfilling DSR requests for Zendesk Support (Securit-Cloud)](/latest/docs/configure-discovery-scans-in-zendesk-support-securiti-hosted)
- [Configuring General permissions for Zendesk Support (Securit-Cloud)](/latest/docs/configuring-general-permissions-for-smartsheet-securiti-hosted)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
