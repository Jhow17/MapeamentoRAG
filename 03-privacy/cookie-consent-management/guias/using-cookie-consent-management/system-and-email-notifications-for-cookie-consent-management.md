---
title: "System and email notifications for Cookie Consent Management"
slug: "system-and-email-notifications-for-cookie-consent-management"
updated: 2026-04-23T05:48:04Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/system-and-email-notifications-for-cookie-consent-management"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# System and email notifications for Cookie Consent Management

This topic describes the email and portal notifications available in the Cookie Consent Management module. The following table summarizes the supported notifications, including the action that triggers the notification, the recipient of the notification, available email customization options, the point of origin in the user interface, and the subject line used in the notification email.

| Use case | Point of origin (UI location) | Notifies | Email customization | Email subject | Link expiration time |
| --- | --- | --- | --- | --- | --- |
| Download consent records | Cookie Consent Dashboard > Download Records | Action Initiator | No | Cookie Consent Report Generated Successfully | 7 Days |
| Download Unique Users data | Cookie Consent Metrics > Unique Users widget > Download CSV | Action Initiator | No | Cookie Consent Unique Users Report Generated Successfully | 7 Days |
| Send weekly cookie consent reports to all cookie domain owners | Schedule Consent Report page | Domain Owners | No | Weekly Consent Report | 7 Days |
| Schedule consent metrics report | Schedule Consent Metrics Report page | Action Initiator | Yes (File type selection `PPTX` or `PDF`) | Weekly Cookie Consent Metrics Report | 7 Days |
| Download Total Unique Users data | Consent Usage Metrics > Unique Users widget > Download CSV | Action Initiator | No | Consolidated Unique Users Report Ready: <Tenant-ID> | 7 Days |
| Generate cookie report | Domains page > Select domain(s) > Generate Cookie Reports | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`; report options combined or separate) | Cookie Information Report For The Tenant: <Tenant-Name> | 7 Days |
| Export domain list | Domains page > Select domain(s) > Export Domain List | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | Domain list information report: <Tenant-Name> | 7 Days |
| Send notification to owners when cookie changes are detected | Cookie Configuration > Basic Information tab > Send notification to all owners when changes to cookie are detected | Domain Owners | No | - | 7 Days |
| Share consent codes via email | Cookie Configuration > Consent Code & Custom CSS > Share codes via email | Action Initiator | Yes (Include message) | Consent Code For The Tenant: <Tenant-Name> | 7 Days |
| Export Applied Tracker (Single) | Cookie and Tracker Library > Applied Trackers > Any Tracker > Export As | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`; add recipients; include message) | Cookie & Tracker Library Report Shared | 7 Days |
| Export Applied Trackers (Bulk) | Cookie and Tracker Library > Applied Trackers > Bulk Actions > Export | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`; add recipients; include message) | Cookie & Tracker Library Report Shared | 7 Days |
| Share Applied Tracker (Single) | Cookie and Tracker Library > Applied Trackers > Any Tracker > Share | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | Cookie & Tracker Library Report Shared | 7 Days |
| Share Applied Trackers (Bulk) | Cookie and Tracker Library > Applied Trackers > Bulk Actions > Share | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | Cookie & Tracker Library Report Shared | 7 Days |
| Export Unapplied Tracker (Single) | Cookie and Tracker Library > Unapplied Trackers > Any Tracker > Export As | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`; add recipients; include message) | Unapplied Tracker Library Report | 7 Days |
| Export Unapplied Trackers (Bulk) | Cookie and Tracker Library > Unapplied Trackers > Bulk Actions > Export | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`; add recipients; include message) | Unapplied Tracker Library Report | 7 Days |
| Share Unapplied Tracker (Single) | Cookie and Tracker Library > Unapplied Trackers > Any Tracker > Share | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | Unapplied Tracker Library Report | 7 Days |
| Share Unapplied Trackers (Bulk) | Cookie and Tracker Library > Unapplied Trackers > Bulk Actions > Share | Action Initiator | Yes (File type selection `JSON`, `Excel`, or `CSV`) | Unapplied Tracker Library Report | 7 Days |
| Export consent data | Export Consent Data | Action Initiator | No | Your Consent Data Export is Ready | Exported files remain available for 30 days. |
