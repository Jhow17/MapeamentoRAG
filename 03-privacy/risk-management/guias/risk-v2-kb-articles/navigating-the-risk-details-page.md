---
title: "Navigating risk details"
slug: "navigating-the-risk-details-page"
updated: 2026-09-21T12:08:32Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/navigating-the-risk-details-page"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Navigating risk details

After you add a risk, Securiti shows you the details page. Clicking a risk in the list view also brings up its details.

## Risk Detail

On the Risk Detail page, Securiti lets you view the executive summary for that risk. Review the following items:

- In the header, information such as risk id, the levels of inherent and residual risk, risk owner are shown.
- “Basic Information” shows you the current risk status, the risk matrix, and details like description, recommendation, etc.
- The list of object shows you where the said risk is exists, for example, in Assessments or which controls are linked to it.
- To edit any information, in the upper left corner, click **Edit**. After applying your changes such as adding another reviewer, click **Save**.
- To link additional objects, click **Link Object** and follow [this](/latest/docs/create-risks-using-the-risk-register) procedure.
- To delete, select options **(three vertical dots)** and click **Delete Risk**. To create a new control for risk, click **Add Control**. The control is automatically linked.

> [!NOTE]
> Note
> 
> You can't create a control this way from the Controls Register, only from a risk's details page or using risk register list.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/object_list.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/options_menu.png)

Observe these caveats:
  - Only system admins can delete the risk.
  - Securiti shows you a confirmation popup before deleting the risk.
  - Once a risk is deleted, all existing object associations are also removed.
  - User with Super Admin role can no longer delete risk from the assessment except from the Risk Detail page.

### Pending Actions

If you added a risk reviewer(s) when creating the risk, Securiti shows you the “Pending Actions” menu on the details page. Choose either:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot%202026-03-31%20at%2012.18.00%E2%80%AFPM.png)

- “Propose Remediation” - you must enter a remediation proposal. Additionally, you can include a URL or a file attachment as evidence and click **Submit Remediation**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.18.54 PM.png)
- “Request Exception” - you must enter a reason. Optionally, add any URL or file attachment and click **Request Exception**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.20.24 PM(1).png)

As reviewer, click **Review Remediation** or **Review Exception**. On the following popup, you can “Send Back” risk or approve the action.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 1.05.05 PM.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 1.05.29 PM.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.25.03 PM.png)

“Risk Activities” shows the audit log for proposed remediations and requested exceptions. You can filter by remediations or exceptions, or view all activities by default.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.28.11 PM.png)

When a remediation is approved, Securiti opens up the Adjust Effective Rating popup where you can set the new, or select existing risk level \ score.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.27.01 PM.png)Click **Save** to apply changes to the risk. No popup is shown for approving an exception.

The updated risk details show you the new residual risk level \ score and the risk status. For example, if there was no change, the risk value shows you *48* before and after while the risk status changes from Risk Flagged to Risk Retained, and so on.

For more information, see the following:

- [Creating Question Logics in assessment template](/latest/docs/creating-question-logics-in-assessment-template)
- [Understanding Workflow Stages and assessment use cases](/latest/docs/understanding-workflow-stages-and-assessment-use-cases)
