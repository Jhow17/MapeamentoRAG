---
title: "Reverting files"
slug: "reverting-files-from-the-data-remediation-dashboard"
status: "update"
updated: 2026-09-16T10:24:50Z
published: 2026-09-16T10:24:50Z
canonical: "helpcenter.securiti.ai/reverting-files-from-the-data-remediation-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Reverting files

If a file was quarantined in error or has been reviewed and cleared, you can revert it to restore it to its original location and make it accessible again. You can revert a file even if the policy that originally quarantined it has been modified, disabled, or deleted.

For example, a policy mistakenly quarantined a file containing standard financial reports due to a pattern match. After reviewing the file and confirming that it poses no risk, you can revert it to restore access for the intended users, even if the original quarantine policy has since been deactivated or deleted.

To revert file(s):

1. Select the file(s) and click **Revert**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BJLQV708.png)
2. Mention the reason for reverting the file(s), as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LS6H80ZC.png)
3. (Optional) Select **Revert files quarantined by other policies** as well to include files quarantined by other policies, and click **Revert Files** to confirm, as shown below.

> [!NOTE]
> Note
> 
> - You can revert files regardless of the policy that originally quarantined them, even if the policy has been modified, disabled, or deleted.
> - When you revert files quarantined by different policies, Securiti uses the quarantine information associated with each file to restore it to its original location.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5AF367RC.png)
