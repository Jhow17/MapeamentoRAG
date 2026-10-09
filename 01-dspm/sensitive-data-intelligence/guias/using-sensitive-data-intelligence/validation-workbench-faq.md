---
title: "Validation Workbench FAQ"
slug: "validation-workbench-faq"
updated: 2026-04-07T09:04:25Z
published: 2026-04-07T09:04:25Z
canonical: "helpcenter.securiti.ai/validation-workbench-faq"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Validation Workbench FAQ

#### **Q:** Why are validated classifications not visible in the session?

**A:** a.If a previously validated classification is edited outside the Validation Workbench, such as in the **Structured Data Discovery**, **Unstructured Data Discovery**, or **Table Training**. In that case, it will be marked as unvalidated and must be reviewed again within the Validation Workbench.

b. If a discovery scan is deleted, all classifications associated with that scan, whether validated or unvalidated, will be permanently removed.

#### **Q:** Why aren’t additional classifications displayed after clicking **Accept** and **Review More**?

**A:** The Validation Workbench samples a randomized set of classified data to streamline the validation process. If all available randomized classifications have already been reviewed and validated, no additional classifications will be presented for further review.

#### **Q:** How to set classification preferences for successive scans?

**A:** In the **Sensitive Data Intelligence** module, choose **Scan Definitions > Scan Details**. Under the **Scope**, select **Advanced settings** and set your preferred preferences for classification.

![Settings for data classification preferences and sensitive data discovery options displayed on screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-10 at 5.54.21 PM.png)

| Perform Classification on columns and tables previously learned | Retain manually classified elements and content profiles | Behaviour (Result) |
| --- | --- | --- |
| Enabled | Enabled | All columns are rescanned, but manual and accepted classifications are preserved. Only system-generated classifications change. |
| Enabled | Disabled | Full reclassification. All previous manual and system classifications can be overwritten. Risk of losing user-reviewed classification. All counts of the session will reset. |
| Disabled | Enabled | Previously validated columns/tables are skipped. Manual and accepted classifications are retained. Only unvalidated data is classified. |
| Disabled | Disabled | Scans the database for any data changes. (e.g., renamed columns, new tables, new columns, etc.) |

#### Q: Does Securiti Sovereign Deployment support the Validation workbench?

**A:** No, Securiti Sovereign Deployment does not currently support the Validation Workbench.

#### Q": What can I review in an unstructured validation workbench session?

**A:** You can review a set of detections instead of manually reviewing every file. This helps improve classification accuracy while reducing review effort. In the Validation Workbench dashboard, you can visualize the following:

- Detected evidence
- Data element
- File name
- File location
- Data system instance

#### Q: Can I review more detections in an existing session?

**A:** Yes, you can review more detections in an existing validation workbench session.
