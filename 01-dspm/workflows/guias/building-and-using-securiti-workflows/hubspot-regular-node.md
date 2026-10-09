---
title: "Hubspot"
slug: "hubspot-regular-node"
updated: 2025-10-30T19:05:38Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/hubspot-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Hubspot

Operates on HubSpot resources

| Parameters |
| --- |
| DataSource Name | The name of the HubSpot data system instance on which to operate |
| Resource | - Deal - Form - Ticket |
| Operation | The operation to perform on HubSpot |
| Create | Create a deal or ticket |
| Delete | Delete a deal or ticket |
| Get All | Get all deals or tickets |
| Get Recently Created | Get recently created deals |
| Get Recently Modified | Get recently modified deals |
| Get Fields | Get all fields of a form |
| Update | Update a ticket or deal |
| Form | The ID of the form to operate on |
| Additional fields | Some or all of: - Deal Name - Close Date - Amount - Deal Type - Associated Company - Associated Contacts - Skip validation - Submitted At |
| Filters | Properties | Select the properties of the deal to fetch in the response |
| Add Filter | - Since - Include Property Versions |
| Context | HubSpot usert... | Include this parameter and set it to the hubspotutk cookie value to enable cookie tracking on your submission |
| IP Address | The IP address of the visitor filling out the form |
| Page URI | The URI of the page the submission happened on |
| Page Name | The name or title of the page the submission happened on |
| Page ID | The ID of a page created on the HubSpot CMS |
| SFDC campaign | If the form is for an account using the HubSpot Salesforce Integration, you can include the ID of a Salesforce campaign to add the contact to the specified campaign |
| Go to Webinar | If the form is for an account using the HubSpot GoToWebinar Integration, you can include the ID of a Salesforce webinar to enroll the contact in that webinar when they submit the form |
| Legal Consent | Add either Consent or Legitimate Interest |
| Consent | Consent to Process | Whether or not the visitor checked the Consent to process checkbox |
| Text | The text displayed to the visitor for the Consent to Process checkbox |
| Legitimate Interest | Subscription Type | The ID of the specific subscription type that this form indicates interest to |
| Value | Set to True when using the 'Legitimate Interest' option, as it reflects the consent indicated by the visitor when submitting the form. |
| Legal Basis | The privacy text displayed to the visitor |
| Text | The privacy text displayed to the visitor |
| Form Fields | Field | Field to be updated |
| Value | Value to update the field with |
| Update fields | Some or all of: - Deal Name - Deal Stage - Close date - Amount - Deal Type |
