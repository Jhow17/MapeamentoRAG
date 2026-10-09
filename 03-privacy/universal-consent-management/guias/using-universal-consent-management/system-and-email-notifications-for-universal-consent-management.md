---
title: "System and email notifications for Universal Consent Management"
slug: "system-and-email-notifications-for-universal-consent-management"
updated: 2026-04-24T07:37:09Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/system-and-email-notifications-for-universal-consent-management"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# System and email notifications for Universal Consent Management

Securiti sends notifications when key actions occur, providing visibility into important activities and changes across the platform. For instance, when you download consent records, the generated report is sent directly to your email inbox instead of appearing in the portal. Depending on the event type, Securiti sends notifications to your email inbox and, in some cases, also displays them as system notifications.

The following table summarizes the notifications Securiti support, including the triggering action, notification channels, point of origin in the UI, and email subject line.

| Use Case | Notification Type | Notify | Email Customization | Point of origin (UI Location) | Subject |
| --- | --- | --- | --- | --- | --- |
| Downloading records | Email | Action Initiator | No | Universal Consent Dashboard | UCM Consent Report Generated Successfully |
| Delete records | Email | Action Initiator | No | Universal Consent Dashboard | Universal Consent Deletion Completed Successfully |
| Export unique users | Email | Action Initiator | No | Universal Consent Metrics | Download Universal Consent Unique Users Report |
| Downloading records | Email | Action Initiator | No | Legacy Universal Consent Data | Universal Consent Report - Legacy Dashboard: `TENANT_NAME` |
| Deleting records | Email | Action Initiator | No | Legacy Universal Consent Data | Universal Consents Deletion Successful |
| Generate consent usage report | Email | Action Initiator | Yes (File type selection `PPT` & `PDF`) | Consent Usage Metrics | Consent Usage Metrics Report |
| Exporting rules | Email | Action Initiator | Yes (File type selection `CSV` , `JSON`, & `EXCEL`) | Rules Matrix | Rules Matrix Report |
| Sharing rules | Email | Recipient | Yes (File type selection `CSV` , `JSON`, & `EXCEL` \| Message) | Rules Matrix | Rules Matrix Report Shared |
| Creating instance | Email & System | Action Initiator | No | Integrations | [Securiti] Data System "Salesforce (Legacy)" instance "`INSTANCE NAME`" has been created. |
| Deleting instance | Email & System | Action Initiator | No | Integrations | [Securiti] Data System "Salesforce (Legacy)" instance "`INSTANCE NAME`" has been deleted. |
| Updating instance | Email & System | Action Initiator | No | Integrations | [Securiti] Data System "Salesforce (Legacy)" instance "`INSTANCE NAME`" has been updated. |
| Exporting consent records (Successful export) | Email | Action Initiator | No | Export Consent Data | Your Universal Consent Data Export Is Ready |
| Exporting consent records (Successful export with no data) | Email | Action Initiator | No | Export Consent Data | No Universal Consent Data Available for Export |
| Exporting consent records (Failed export) | Email | Action Initiator | No | Export Consent Data | Consent Data Export Failed |

Securiti replaces the `TENANT_NAME` and `INSTANCE_NAME` in the email subjects with your tenant and instance names.

The following table describes the key attributes mentioned above:

| Attribute | Description |
| --- | --- |
| Use Case | Defines the specific event or activity in Securiti that triggers a notification. |
| Notification Type | Identifies the category of notification generated, such as an email notification or a system/portal notification. |
| Notify | Shows whether Securiti sends the notification to the action initiator’s inbox or the recipient. |
| Email Customization | Determines whether you can configure notification email preferences. |
