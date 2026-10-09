---
title: "Focused search scope for Microsoft 365 Outlook (Self-Hosted) in internal DSRs"
slug: "focused-search-scope-for-microsoft-365-outlook-self-hosted-in-internal-dsrs"
updated: 2026-06-25T12:37:35Z
published: 2026-06-25T12:37:35Z
canonical: "helpcenter.securiti.ai/focused-search-scope-for-microsoft-365-outlook-self-hosted-in-internal-dsrs"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Focused search scope for Microsoft 365 Outlook (Self-Hosted) in internal DSRs

**Scenario**

As a Data Privacy Officer, you often need to narrow DSR searches to communications relevant to a specific investigation or request. Broad automated searches can return excessive records across multiple accounts and conversations, increasing review effort and exposing unrelated data. With scoped smart search, you can limit searches using specific keywords and selected mailboxes to retrieve focused results. This helps you review relevant results faster, reduce unnecessary data exposure, and improve DSR investigation efficiency.

## Introduction

Securiti lets you define a focused search scope for internal DSR processing to target only relevant communications. This capability currently supports Microsoft 365 Outlook (Self-Hosted) Smart Search. Instead of returning all communications related to a data subject, scoped smart search limits results to communications relevant to a specific request or investigation.

For example, you can limit searches to selected manager and HR mailboxes and use keywords related to performance discussions or termination context to retrieve communications tied to the data subject.

> [!NOTE]
> Note
> 
> This feature is available only for internal DSRs and requires Microsoft 365 Outlook (Self-Hosted) with the Enable DSR Automation via Scan-less Smart Search option enabled. It does not support discovery scans.
> 
> When the DSR owner submits a DSR on behalf of a data subject, they can set the search scope. A data subject cannot set the search scope while submitting DSR details to the DSR owner.
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Prerequisites

- DSR scoping feature is enabled on your tenant.
- In the Microsoft 365 Outlook (Self-Hosted) connector, mark Enable DSR Automation via Scan-less Smart Search checkbox to enable smart search.
- Required Microsoft Graph API permissions are configured.
- Appliance version is 1.147.0-01rc or later.

## Configuring scoped search for an internal DSR

1. Follow the steps in Opening DSR requests on behalf of data subjects to create an internal DSR request.
2. On the Create DSR page, mark the **Scope for Search in Data Systems** checkbox.
3. In the **Data System** menu, select the Outlook data system. This menu lists only Microsoft 365 Outlook (Self-Hosted) connectors that have the **Enable DSR Automation via Scan-less Smart Search** option enabled. Outlook connectors configured for discovery scans do not appear in this list.
4. In the **Scope for Search** menu, select one or both of the following:

![Form for data subject request with highlighted search scope and mailbox options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-17 at 7.18.56 PM.png)
  1. **Add Keywords for Search** — limits results to emails that contain specific keywords.
  2. **Limit search to following mailboxes** — restricts the search to specific mailbox addresses.
5. If you selected **Add Keywords for Search**, type each keyword in the field and press Enter. Securiti searches for each keyword in lowercase, uppercase, and title case.
6. If you selected **Limit search to following mailboxes**, type each mailbox address in the field and press Enter. You can add up to 50 addresses.
7. Complete the remaining fields and click **Submit Request**.

When you specify both keywords and mailboxes, Securiti returns only emails that match both the keyword search and the data subject Identifier search.

> [!NOTE]
> Note
> 
> The scope you define applies only to the Microsoft 365 Outlook (Self-Hosted) data system. For all other data systems, Securiti creates tasks and subtasks as normal, without applying any scoping. This applies regardless of how your DSR form is configured:
> 
> - If your DSR form uses a form rule with a task template that includes Microsoft 365 Outlook (Self-Hosted) alongside other data systems, scoping applies only to the Outlook connector. Tasks and subtasks for all other data systems in the template are created as normal.
> - If your DSR form uses the Automation section to include multiple data systems directly, scoping applies only to the Outlook connector in that list. All other data systems process the DSR request as normal.

Once you submit the request and Securiti creates the DSR tasks, you can verify the configured scope directly from the DSR Workbench.

1. Open the DSR in the Workbench.
2. In the upper right corner, click Subject Details in the top-right corner.
3. In the panel that appears, select the **Data Subject Details** tab and expand **Scope for Search in Data Systems**.

![Data Subject Rights request details for John Doe, including tasks and search scope.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-17 at 7.23.44 PM.png)

The configured connector is listed along with the keywords and mailboxes you defined for the search scope.

### How scoped search works

When you submit the internal DSR, Securiti sends the mailbox and keyword scope to the Outlook connector. The connector then:

- Searches only the specified mailboxes, specifically the inbox and sent folders.
- Searches for the data subject's identifiers in the email body, attachments, headers, and subject line.
- Returns only emails that match both the identifier search and the keyword search.
