---
title: "Reopening closed DSRs"
slug: "reopening-closed-dsrs"
updated: 2026-08-30T07:13:16Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/reopening-closed-dsrs"
stale: true
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Reopening closed DSRs

**Scenario**

As a Data Privacy Officer, you sometimes need to act on a closed DSR after the fact. For instance, you might discover new information about the data subject, or find that a request was closed in error. You might also need to revisit a request for legal or compliance review, or in response to a regulator follow-up. Instead of creating a new DSR request to handle this, you can reopen the closed request and continue working on it directly.

## Overview

Securiti lets you reopen a closed DSR request instead of creating a new one when additional work is needed. A Super Admin must enable this capability first. For more information, see [Configuring DSR reopening.](/latest/docs/configuring-dsr-reopening)

> [!CAUTION]
> Caution
> 
> Most global privacy laws and regulations do not generally permit retroactive revisions or amendments to a closed DSR request. You are responsible for determining whether reopening a request, and any resulting deadline recalculation, is permitted under the laws that apply to it. Using this feature might require a documented reason for reopening, consideration of the impact on regulatory deadlines, and notification to the data subject.

1. Open the closed DSR request in the DSR workbench.
2. From the upper right corner, click the **More Actions** menu (three dot icon), then click **Reopen DSR**.

![DSR access request details for David Smith, including decline reason and task progress.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-25 at 4.39.44 PM.png)
3. Choose a deadline option:

> [!NOTE]
> Note
> 
> - If you choose **Start New Deadline from Reopen Date**, you can extend the deadline again later, even if the request was already extended before it was closed.
> - If you choose **Resume Previous Deadline** and the request is not yet overdue, you can extend the deadline only if it was not already extended before, and only if the applicable regulation allows an extension.
> - If you choose the **Resume Previous Deadline** option and the request is already overdue, you cannot extend the deadline at all.
  - **Resume Previous Deadline**: Securiti keeps the original deadline. For instance, if the request was submitted with a 10-day deadline and would have been due September 4, reopening it on September 3 and resuming the deadline still leaves it due September 4.
  - **Start New Deadline from Reopen Date**: Securiti recalculates the deadline using the DSR form's deadline configuration at the time the request was originally submitted, starting from the reopen date. In the same example, reopening on September 3 with this option sets a new 10-day deadline from September 3, regardless of any changes made to the form's deadline setting since the request was submitted.
4. Choose a reason from the **Reason** menu, or add a custom reason. This field is mandatory.

The Reason menu includes the following predefined options:
  - Additional information about the data subject found
  - Request closed in error and fulfillment response requires correction
  - Incomplete scan or processing activity or data system identified
  - Legal or compliance review
  - Regulator inquiry or follow-up
  - Other (specify)

If none of these match your situation, choose Other and enter a custom reason. Securiti records the reason you choose or enter in the audit log.
5. Mark Re-scan DSR to have Securiti rescan the request as part of reopening it. If you leave this checkbox cleared, Securiti reopens the DSR request without rescanning it, and you must rescan it manually afterward. For more information, see [Re-scanning DSR requests](/latest/docs/re-scanning-dsr-requests).

![Confirmation prompt for reopening a Data Subject Rights request with various options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-25 at 1.21.14 PM(1).png)
6. For a digital request, you can optionally send the data subject an email notifying them of the reopening. Edit the email content if needed. For an internal request, mark the checkbox confirming you have communicated the reopening to the data subject yourself, since Securiti cannot email a data subject for internal requests.
7. Click **Proceed.**

### Caveats

You cannot reopen a DSR request in the following cases:

- You have not enabled the reopening DSR settings.
- The request is not yet closed.
- The data subject has raised an appeal for the request.
- The data subject has deleted the request from Privacy Central.
- Securiti is still processing a publish or reject operation for the request.
