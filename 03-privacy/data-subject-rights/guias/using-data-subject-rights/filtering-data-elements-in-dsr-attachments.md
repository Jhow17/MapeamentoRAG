---
title: "Filtering data elements in DSR attachments"
slug: "filtering-data-elements-in-dsr-attachments"
updated: 2026-09-23T09:28:36Z
published: 2026-09-23T09:28:36Z
canonical: "helpcenter.securiti.ai/filtering-data-elements-in-dsr-attachments"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Filtering data elements in DSR attachments

**Scenario**

As a Data Privacy Officer, you sometimes want to hold back specific data elements from a subtask attachment, without withholding the data subject's entire record. For instance, a data system might store a rewards number or a frequent flyer number that you do not want to send to a data subject. You can exclude just that element, while every other data element for that data subject still appears in the attachment.

## Overview

Securiti lets you control which data elements appear in the subtask attachment for unstructured data systems, by configuring a rule to include or exclude specific elements.

- If you leave data elements unredacted, Securiti highlights only those elements and redacts everything else it finds for the data subject.
- If you redact data elements, Securiti redacts those elements for the data subject and highlights every other data element it finds.

> [!CAUTION]
> Caution
> 
> Global data protection regulations generally require data controllers to provide or act upon all discovered personal data of data subjects in response to data requests, and apply exceptions only on a case-by-case basis. This feature lets you generically suppress identified personal data in the disclosure to a data subject, and redactions configured this way could lead to non-compliance. You must ensure redactions meet your legal obligations.

1. In the Data Subject Rights module, choose **Settings > Form Builder.** Choose the form you want to use, or create a new one.
2. Go to the **Rules** tab and click **Add Rules**. On the Rule Details page, mark the **Data Element Redaction** checkbox.

![Form builder interface showing data element redaction option for DSR rules.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-23 at 12.19.50 PM.png)
3. Choose **Data elements to leave unredacted** or **Data elements to redact**. In the **Data elements to redact** menu, select the data elements to apply, then click **Create Rule**.

![Details of DSR form settings including data element redaction options and workflows.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-23 at 12.25.13 PM.png)

> [!NOTE]
> Note
> 
> - The **Data elements to redact** menu lists data elements from your Sensitive Data Intelligence module (Data Classification > Data Elements), including any custom data elements you have configured there. If your tenant does not use Sensitive Data Intelligence, this menu shows the standard system data element list instead. For more information, see [Data Elements](/latest/docs/data-elements).
> - If a DSR request matches more than one rule with this filter configured, and any matching rule excludes data elements, Securiti applies that exclusion and ignores any inclusion rules that also match.
> - If a data subject submits additional details that trigger a rule re-evaluation, such as through request clarification, Securiti recalculates the data element filter based on the rules that match after the update. For more information, see [Request Clarification in DSR](/latest/docs/request-clarification-in-dsr).

This filter applies only to the data subject's own data, and works independently of the existing DSR Redaction setting, which controls whether Securiti redacts data belonging to other people found in the same file.

### Viewing filtered data elements in the workbench

In the DSR workbench, the **Subject Details** panel shows **Redacted Data Elements in the Report** or **Unredacted Data Elements in the Report** section. This section lists the data elements the filter applied to for the DSR form used to raise the request.

![Data subject access request details for Keith Gordon, including redacted elements and deadlines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-23 at 2.10.10 PM.png)

Securiti still searches and matches the full record for the data subject, based on the primary identifier such as email. This filter only changes what appears in the final output. It does not change what Securiti searches for or finds. To see this directly, open a subtask for an unstructured data system, scroll down to Object & Data Element discovery, then click **Preview Data Element found in object**.

![Data Subject Rights request dashboard showing tasks and discovered data elements for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 6.13.59 PM(1).png)

![Data subject view displaying selected data elements and options for attachment.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 6.14.50 PM.png)

#### Caveats

- Securiti supports this filter only for unstructured data systems.
- If you clone a rule, Securiti copies its data element filter list as-is, even if you have disabled a data element in that list in Sensitive Data Intelligence. Securiti only re-validates the list, and removes any disabled elements, the next time you update the cloned rule.

For more information, see [Configuring rules in the DSR form](/latest/docs/configuring-rules-in-the-dsr-form).
