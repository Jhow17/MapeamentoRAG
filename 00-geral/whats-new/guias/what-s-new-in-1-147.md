---
title: "What's New in 1.147"
slug: "what-s-new-in-1-147"
updated: 2026-08-12T08:37:48Z
published: 2026-08-12T08:37:48Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-147"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.147

## Narrow Outlook Searches in Internal DSRs

When an internal user is filing a DSR on behalf of a data subject, the Outlook search usually needs to focus on a narrow slice of communications, like performance discussions between a specific manager and HR. Internal DSRs now let you scope the Outlook (Self-Hosted) search by keyword and specific mailbox addresses. Add terms like "Performance" and pick the mailboxes that matter, and the search returns only those threads. The review covers what's actually relevant to the request, not the full mailbox set, and the DSR response gets built on a tighter evidence base.

[Learn more in docs](/latest/docs/opening-dsr-requests-on-behalf-of-data-subjects)

![Microsoft Outlook search interface for mailboxes and keywords with a search button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Scoped Search for Internal DSR Requests (Outlook).jpg)

---

## Isolate Sensitive Azure Files

Imagine that a sensitive file gets flagged in your Azure Files data system and you need it out of circulation while you figure out what to do with it. File Quarantine policies now support Azure Files for central quarantine, so when a file gets flagged, you can move it to a designated quarantine location and hold it there for review. The file is isolated, accessible for investigation, and nothing happens to it until you decide.

[Learn more](/latest/docs/using-quarantine-destinations)

![Icons representing different file types with a cursor highlighting document files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Isolate Sensitive Azure Files.png)

---

## Remove Incorrect Labels from Files

If a file gets the wrong label, you need a way to correct it without having to delete or re-upload the file. The Data Labeling Remediation dashboard now supports a Remove Label operation, so you can remove specific incorrect or outdated labels from selected files or clear all labels at once. For Google Drive, which supports multiple labels per file, you can remove one or more labels in a single operation. For Microsoft Information Protection (MIP), which supports only a single label per file, removing the label leaves the file with no label applied.

[Read more in docs](/latest/docs/using-data-remediation-dashboards)

![Interface for removing selected labels in data labeling software with options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Remove Labels from Files.jpg)

---

## Track and Monitor your Data Tagging Policies

Say a Data Tagging policy runs overnight and you want to verify its results. Instead of manual tracking, you can now open Run History directly from the policy and view a complete record of its execution. For each run, you can see key details such as the Policy Name, Status, Start Time, and the count of Processed, Succeeded, Skipped, and Failed nodes. For more detail, open Step Details to track individual step progress, review start times, and view any error messages. For example, you run a policy across 10,000 nodes and see that 8,500 succeeded and 1,500 failed. You open Step Details and find that all the failed nodes share the same error message that the tagging service was temporarily unavailable. Once the service is back up, you rerun the policy for the affected nodes.

[See how to configure the policy](/latest/docs/configuring-data-tagging-policy)

![Steps to manage data tagging policy and access insights effectively.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Track and Monitor Your Data Tagging Policies.jpg)
