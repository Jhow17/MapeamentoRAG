---
title: "System and email notifications for Mobile App Consent Management"
slug: "system-and-email-notifications-for-mobile-app-consent-management"
updated: 2026-04-06T17:29:11Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/system-and-email-notifications-for-mobile-app-consent-management"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# System and email notifications for Mobile App Consent Management

This help article explains the email notifications available in the Mobile App Consent Management module. The following table summarizes the supported notifications, including the action that triggers the notification, the recipients of the notification, any available email customization options, the point of origin in the UI, and the subject line used in the notification email.

| Notification trigger | Point of origin (UI location) | Notifies | Email customization | Email subject |
| --- | --- | --- | --- | --- |
| Downloading live app records | Mobile Consent Reporting Dashboard – Download Report | Action Initiator | No | Mobile Consent Reporting Dashboard Export for the Tenant: `&lt;Tenant-Name&gt;` |
| Export Mobile Apps | Mobile Apps page – Export As | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | App list information report: `&lt;Tenant-Name&gt;` |
| Downloading Total Unique Users data | Consent Usage Metrics – Unique Users widget | Action Initiator | No | Consolidated Unique Users Report Ready: `&lt;Tenant-Name&gt;` |
| Generate Consent Usage Metrics report | Consent Usage Metrics – Generate Report | Action Initiator (+ Recipient) | Yes (File type selection `PPTX` or `PDF`) | Consent Usage Metrics Report |
| Generate report for SDKs and Permissions in scanned app | Scan & Reports – Overview / SDKs / Permissions | Action Initiator | No | SDK and Permission Success Report: `&lt;Tenant-Name&gt;` |
| Generate report for AI-suggested SDKs and Permissions | Scan & Reports – AI Suggestions | Action Initiator | No | AI Classification Report Ready: `&lt;Tenant-Name&gt;` |
