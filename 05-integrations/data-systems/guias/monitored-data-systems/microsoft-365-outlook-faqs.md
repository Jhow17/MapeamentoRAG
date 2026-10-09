---
title: "Microsoft 365 Outlook FAQs"
slug: "microsoft-365-outlook-faqs"
updated: 2026-06-23T06:35:09Z
published: 2026-06-23T06:35:09Z
canonical: "helpcenter.securiti.ai/microsoft-365-outlook-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 Outlook FAQs

This article answers frequently asked questions about the Microsoft 365 Outlook connector.

### DSR automations and limitations

This section covers the FAQs related to Microsoft 365 Outlook DSR automations and its limitations.

****For a Data Subject Request (DSR), can** **Securiti** **find a user's personal data in emails exchanged between other employees, where the user is not a direct sender or recipient?****

Yes, Securiti can identify this data, provided the user's email address is explicitly mentioned in the email body or attachment. The Microsoft 365 Outlook Connector searches the full body and attachments of emails within the scan scope.

If the user's email address, such as `john.doe@test.xyz` is present in the email body or within an attachment, it is included in the DSR search results.

However, if the user’s email address is not explicitly present and only the user’s name is mentioned, the Connector may not return that data in the search results.

****If DSR Smart Search is enabled but no Groups or Users are selected in the scans, what is the default behavior for handling API user search permission errors?****

Smart Search (scanless) DSR and “Data Inventory and Entitlements Sync Scopes” are completely independent. Smart Search doesn’t rely on any pre-scanning, and those scopes are not relevant in the case of Smart Search.

> [!NOTE]
> Note
> 
> You must assign `Mail.Read` permission to the Azure application to get DSR results.

****Is there a programmatic retry for a certain number of attempts before moving on to the next user, until all users have been queried?****

The current programmatic retry limit for each user is 50 attempts. If the error is unskippable DSR task will move to the fail state.

****If a customer enables Groups or Users in the scan scope while only Smart Search is enabled, does this also affect the DSR Smart Search scope?****

No, scan scopes only apply to Data Inventory and Entitlements scanning. It does not affect DSR Smart Search.

****What happens if the customer changes between DSR Robotic Automation and DSR Smart Search options?****

Yes, Securiti lets you switch between DSR Robotic Automation and DSR Smart Search.

****What happens to the Outlook connector if the Reports.Read.All permission is not granted?****

The Outlook connector does not fail if `Reports.Read.All` permission is missing. The permission applies only during connector activation and authentication, where it makes a one-time API call to generate an estimated summary of the total number of mailboxes and the overall data volume in the Outlook account. The connector logs these results in the module audit trail to give customers an idea of the data size to be processed and to assist with debugging.

`Reports.Read.All` permission provides only an estimate; the figures may not exactly match the actual statistics. This permission remains optional and does not affect data processing or any module that the connector participates in.

****Does Smart Search DSR for Outlook scan all folders and mailboxes?****

Yes. Smart Search DSR for Outlook (Self-hosted) searches at the user level, not at the folder level. It queries the Microsoft Graph messages collection across the entire mailbox, which includes both standard and custom folders such as Inbox, Sent Items, Archive, Deleted Items, and any subfolders.

Make sure the app has the required permissions to read message bodies and attachments, as described in the permissions section in Microsoft 365 Outlook connectors.

****For a Data Subject Request (DSR), can Securiti find a user's personal data in emails exchanged between other employees, where the user is not a direct sender or recipient?****

Yes, Securiti can identify this data, provided the user's email address is explicitly mentioned in the email body or attachment. The Microsoft 365 Outlook connector searches the full body and attachments of emails within the scan scope.

If the user's email address, such as [john.doe@test.xyz](mailto:john.doe@test.xyz) is present in the email body or within an attachment, it is included in the DSR search results.

However, if the user’s email address is not explicitly present and only the user’s name is mentioned, the connector may not return that data in the search results
