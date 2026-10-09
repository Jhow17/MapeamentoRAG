---
title: "Using the Risk Register list view"
slug: "using-the-risk-register-list-view"
updated: 2026-08-11T02:55:40Z
published: 2026-08-11T02:55:40Z
canonical: "helpcenter.securiti.ai/using-the-risk-register-list-view"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Risk Register list view

**Scenario**

As a Data Compliance Officer, you're responsible for following up on risks identified in objects. Without a centralized view, tracking status and ownership is difficult. By using the risk register, you log flagged items, assign owners, and monitor resolution progress. This structured approach ensures no risk goes unaddressed and supports a continuous improvement cycle for compliance. For example, users can filter risks by status and export the risk register contents to a CSV file for further analysis.

Securiti lets you view all risks in the risk register. To access, on the Securiti homepage, under “Apps”, select **Risk Management > Risk Register**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 11.07.00 AM.png)

The risk list view shows essential information on the types of risks that exist in your organization against assessments and data mapping objects. Quickly search for a desired risk using the search bar by specifying risk ID or its description. Moreover, you can add risks directly via [risk register](/latest/docs/create-risks-using-the-risk-register#create-risk).

On the list view, use the ‘Column Selector (grid icon)’ to arrange columns to suit. The list of columns range from risk status and linked object types to inherent risk, residual risk, risk owner, and other risk-related items. Tags assigned to risks through assessment template logic are also available as a column. To display it, enable **Tags**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.34.38 PM.png)

For more information, see [Assessments list](/latest/docs/using-the-internal-assessments-list-view).

## Risk filters

You have the ability to sort risks by their property and create “Saved Views” to access commonly-used filters. You can choose from risk properties such as “Linked Object”, “Risk Recommendation”, “Risk Reviewer”, etc. and their operator chips to narrow down the selection.

For more information, see [Assessment filters](/latest/docs/assessments-list-filter-panel-and-saved-views).

### Risk Status filters

The filters below explain what each status mean.

- **Flagged -** when you create a risk.
- **Retained Pending -** when you request an exception.
- **Reduced Pending -** when you propose a remediation.
- **Retained Extended -** when you request an exception and the exception is approved. After that you propose a remediation.
- **Reduced -** when the proposed remediation is accepted but at the same risk level.
- **Retained -** when the requested exception is approved.

## Importing and exporting risks

You can also import and export risks using the register.

1. Near the upper right corner of the page, click **Import** and select a CSV file to import risk.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.35.57 PM.png)
2. Similarly, to export, mark the checkbox for your desired risk(s) and click **Export**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-31 at 12.39.21 PM(1).png)

You can export multiple risks at a time in CSV format. Securiti sends an email containing the download link.

Proceed to [Create risks using risk register](/latest/docs/create-risks-using-the-risk-register).
