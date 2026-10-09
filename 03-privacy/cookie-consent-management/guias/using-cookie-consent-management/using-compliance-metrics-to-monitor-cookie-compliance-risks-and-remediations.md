---
title: "Using Compliance Metrics to monitor cookie compliance risks and remediations"
slug: "using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations"
updated: 2026-08-10T08:54:18Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using Compliance Metrics to monitor cookie compliance risks and remediations

**Scenario**

As a Data Privacy or Compliance Officer, you need a quick way to gauge your organization's overall cookie compliance posture across many domains and jurisdictions. For instance, if compliance scores drop after a product launch, you need to spot the trend, find the domains driving it, and get the failed tests remediated. With Securiti's Cookie Compliance Metrics, you can track compliance scores over time, see where risk concentrates, and monitor remediation progress from one place.

The Compliance Metrics give you an aggregated, visual view of cookie compliance posture across your scanned domains. Use these widgets to track overall cookie compliance health, identify high-risk domains, understand which tests fail most often, and monitor remediation progress over time.

> [!NOTE]
> **Note**
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether the [Compliance Dashboard](/latest/docs/using-the-compliance-dashboard-to-remediate-cookie-compliance-risks) is included in your plan and whether your tenant meets the eligibility requirements for its activation. Access to the Compliance Metrics dashboard is included with the Compliance Dashboard.

## Key considerations

Review the following before using the Cookie Compliance Metrics:

| **Consideration** | **Description** |
| --- | --- |
| Scan status | Securiti includes only domains with a successful compliance scan in these widgets. It excludes domains with a failed or in-progress scan. |
| Jurisdiction scope | By default, widgets include all jurisdictions that you have scanned. |

## Compliance Metrics widgets

The **Metrics** tab includes the following widgets to help you evaluate compliance posture, identify risks, and track remediation progress across scanned domains.

### Overall Compliance Score

This widget shows the overall compliance score across scanned domains. Securiti calculates this score by averaging all successful individual domain compliance scans and excludes domains with Failed or in-progress scans, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Overall-Compliance-Score-Metrics.png)

Securiti calculates each domain's compliance score based on how well the domain meets cookie consent requirements across all applicable tests for the selected jurisdiction.

`Compliance Score = (Sum of Test Contributions ÷ Number of Applicable Tests) × 100`

Securiti uses the test status of each applicable compliance test to calculate the compliance score, as shown in the following table:

| **Test Status** | **Score contribution** |
| --- | --- |
| Passed | 1.0 |
| Remediated | 1.0 |
| User-Accepted Risk | 0.5 |
| User-Excluded Risk | 0 |
| Failed | 0 |

> [!NOTE]
> **Note**
> 
> Securiti includes only applicable tests in the final compliance score. Securiti excludes **Not Applicable** tests because they do not apply to the selected jurisdiction.

### Compliance Overview

This widget shows a consolidated view of key compliance metrics across domains, including critical risk domains, failed tests, and successful remediation rate, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Overview-Metrics.png)

Use the following table to understand the tiles available in the **Compliance Overview** widget:

| **Tile** | **Description** |
| --- | --- |
| Critical Risk Domains | Shows domains with compliance issues that require immediate attention. Click the **Critical Risk Domains** tile to view domains with a **Non-Compliant** compliance score in the **Dashboard** tab. |
| Failed Tests | Shows the total number of failed compliance tests across scanned domains. Click the **Failed Tests** tile to view domains with failed compliance tests in the **Compliance Dashboard**. |
| Successful Remediation Rate | Shows the percentage of failed compliance tests that users have successfully remediated. |

### Portfolio Risk Distribution

This widget shows how domains are distributed based on their overall compliance posture. Securiti categorizes domains by compliance score into **Non-Compliant**, **Partially Compliant**, **Mostly Compliant**, and **Compliant**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Portfolio-Risk-Distribution-Metrics.png)

> [!NOTE]
> **Tip**
> 
> You can click a category in the legend to show or hide that category in the graph, as shown below. When you hide a category, Securiti strikes through the category name in the legend.
> 
> 
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Portfolio-Risk-Distribution-Hidden-Segment.png)

Use the following table to understand the categories available in the **Portfolio Risk Distribution** widget:

| **Category** | **Description** |
| --- | --- |
| Non-Compliant | Shows domains with the lowest compliance scores that require immediate attention. Click the **Non-Compliant Domains** segment in the portfolio risk distribution bar to view domains with a **Non-Compliant** compliance score in the **Compliance Dashboard**. |
| Partially Compliant | Shows domains that meet some compliance requirements but still have significant gaps. Click the **Partially Compliant** segment in the portfolio risk distribution bar to view domains with a **Partially Compliant** compliance score in the **Compliance Dashboard**. |
| Mostly Compliant | Shows domains that satisfy most compliance requirements but still require minor improvements. Click the **Mostly Compliant** segment in the portfolio risk distribution bar to view domains with a **Mostly Compliant** compliance score in the **Compliance Dashboard**. |
| Compliant | Shows domains that satisfy all evaluated compliance requirements. Click the **Compliant** segment in the portfolio risk distribution bar to view domains with a **Compliant** compliance score in the **Compliance Dashboard**. |

### Test Distribution by Status

This widget shows how compliance test results are distributed across different statuses, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Test-Distribution-by-Status-Metrics.png)

Use the following table to understand the bars available in the **Test Distribution by Status** widget:

| **Bar** | **Description** |
| --- | --- |
| Passed | Shows compliance tests that passed successfully. Click the **Passed** bar to open the **Dashboard** tab where **Test Status** is **Passed**. |
| Remediated | Shows compliance tests that users have remediated. Click the **Remediated** bar to open the **Dashboard** tab where **Test Status** is **Remediated**. |
| Failed | Shows compliance tests that failed and may require review or remediation. Click the **Failed** bar to open the **Dashboard** tab where **Test Status** is **Failed**. |
| User-Excluded Risks | Shows compliance risks that users exclude from active evaluation. Click the **User-Excluded Risks** bar to open the **Dashboard** tab where **Test Status** is **User-Excluded Risk**. |
| User-Accepted Risks | Shows compliance risks that users accepted instead of remediating. Click the **User-Accepted Risks** bar to open the **Dashboard** tab where **Test Status** is **User-Accepted Risk**. |
| Not Applicable | Shows compliance tests that do not apply to the scanned domain or selected jurisdiction. Click the **Not Applicable** bar to open the **Dashboard** tab where **Test Status** is **Not Applicable**. |

### Failed Test Distribution

The **Failed Test Distribution** widget shows which compliance test types fail most frequently across scanned domains. Securiti calculates this widget based on the total number of failed occurrences for each test type, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Failed-Test-Distribution-Metrics.png)

Use the following table to understand the test type segments available in the widget:

| **Test type** | **Description** |
| --- | --- |
| Tracker Categorization Validation | Shows failed tests related to tracker categorization validation. Click the **Tracker Categorization Validation** segment to open the **Dashboard** tab where **Tests** is **Tracker Categorization Validation** and **Test Status** is **Failed**. |
| Consent Banner Detection | Shows failed tests related to cookie banner detection. Click the **Consent Banner Detection** segment to open the **Dashboard** tab where **Tests** is **Consent Banner Detection** and **Test Status** is **Failed**. |
| Reject All Functionality Test | Shows failed tests related to reject-all functionality. Click the **Reject All Functionality Test** segment to open the **Dashboard** tab where **Tests** is **Reject All Functionality Test** and **Test Status** is **Failed**. |
| GPC Signal Detection | Shows failed tests related to Global Privacy Control signal detection. Click the **GPC Signal Detection** segment to open the **Dashboard** tab where **Tests** is **GPC Signal Detection** and **Test Status** is **Failed**. |
| Others | Shows failed tests from other compliance test types. Click the **Others** segment to open the **Dashboard** tab where **Tests** includes the corresponding test types and **Test Status** is **Failed**. |

### Failed Test Distribution by Severity

The **Failed Test Distribution by Severity** widget shows how failed compliance tests are distributed across severity levels. Securiti groups failed tests by the severity assigned to each test, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Failed-Test-Distribution-by-Severity-Metrics.png)

Use the following table to understand the severity levels available in the widget:

| **Severity** | **Description** |
| --- | --- |
| Very High | Shows failed compliance tests with **Very High** severity. Click the **Very High** segment to open the **Dashboard** tab where **Severity** is **Very High** and **Test Status** is **Failed**. |
| High | Shows failed compliance tests with **High** severity. Click the **High** segment to open the **Dashboard** tab where **Severity** is **High** and **Test Status** is **Failed**. |
| Medium | Shows failed compliance tests with **Medium** severity. Click the **Medium** segment to open the **Dashboard** tab where **Severity** is **Medium** and **Test Status** is **Failed**. |
| Low | Shows failed compliance tests with **Low** severity. Click the **Low** segment to open the **Dashboard** tab where **Severity** is **Low** and **Test Status** is **Failed**. |
| Very Low | Shows failed compliance tests with **Very Low** severity. Click the **Very Low** segment to open the **Dashboard** tab where **Severity** is **Very Low** and **Test Status** is **Failed**. |

### Aging Buckets - Risks

This widget shows how long unresolved compliance risks have remained open. Securiti groups risks into predefined aging buckets based on the time since Securiti first detected them, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Aging-Buckets-Risks-Metrics.png)

Use the following table to understand the aging buckets available in the widget:

| **Bucket** | **Description** |
| --- | --- |
| Critical | Shows unresolved failed tests that have remained open for **14+ days**. |
| Stale | Shows unresolved failed tests that have remained open for **8-14 days**. |
| Aging | Shows unresolved failed tests that have remained open for **2-7 days**. |
| New | Shows unresolved failed tests detected in the **last 24 hours**. |

You can click an aging bucket to review the corresponding failed tests in the **Compliance Dashboard**. When you click an aging bucket, Securiti opens the **Dashboard** tab where **Test Status** is **Failed** and **Scanned On** matches the selected aging range.

For instance, if you click the **Aging** bucket on August 4, Securiti opens the **Dashboard** tab where **Test Status** is **Failed** and **Scanned On** is between July 28, 2026, and August 3, 2026, as shown below.

### Remediation Distribution

The **Remediation Distribution** widget shows remediation tasks by status and remediation type. It includes pending and completed tasks for **Manual Remediation** and **Auto-Remediation**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remediation-Distribution-Metrics(1).png)

> [!NOTE]
> **Tip**
> 
> When you hover over a legend item in the **Remediation Distribution** widget, Securiti highlights the bars for that remediation type and dims the other remediation type in the graph. For instance, when you hover over **Auto-Remediation**, Securiti highlights the **Auto-Remediation** bars and dims the **Manual Remediation** bars, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Auto-Remediation-Hover.png)
> 
> 
> 
> You can click a legend item to show or hide that remediation type in the graph. When you hide a remediation type, Securiti strikes through the item name in the legend, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Auto-Remediation-Hide.png)

Use the following table to understand the clickable bars in the **Remediation Distribution** widget:

| **Bar** | **Description** |
| --- | --- |
| Pending Manual Remediation | Shows failed tests that require manual remediation. Click the **Pending Manual Remediation** bar to open the **Dashboard** tab where **Test Status** is **Failed** and **Remediation type** is **Manual**. |
| Pending Auto-Remediation | Shows failed tests that support auto-remediation. Click the **Pending Auto-Remediation** bar to open the **Dashboard** tab where **Test Status** is **Failed** and **Remediation type** is **Auto**. |
| Completed Manual Remediation | Shows manual remediation tasks that users have completed or accepted as risk. Click the **Completed Manual Remediation** bar to open the **Dashboard** tab where **Test Status** is **Remediated** or **User-Accepted Risk**, and **Remediation type** is **Manual**. |
| Completed Auto-Remediation | Shows auto-remediation tasks that users have completed or accepted as risk. Click the **Completed Auto-Remediation** bar to open the **Dashboard** tab where **Test Status** is **Remediated** or **User-Accepted Risk**, and **Remediation type** is **Auto**. |

### Top Pending Remediations by Assignee

This widget shows the assignees with the highest number of pending remediation tasks. Securiti ranks assignees by the total number of unresolved tasks assigned to them, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Top-Pending-Remediations-By-Assignee-Metrics(1).png)

You can click an assignee row in the widget to review the corresponding failed tests in the **Compliance Dashboard**. When you click an assignee row, Securiti opens the **Dashboard** tab where the **Remediator** is the selected assignee and **Test Status** is **Failed**.

### Domains at Risk

This widget shows domains with compliance issues, including their compliance score, number of failed tests, and most recent compliance scan date. Securiti sorts the results to surface domains that need attention, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Domains-at-Risk-Metrics.png)

You can click a domain row in the widget to review the corresponding compliance scan results in the **Compliance Dashboard**. When you click a domain row, Securiti opens the **Dashboard** tab where the **Domain URL** is the selected domain.

For instance, if you click `https://securiti.ai`, Securiti opens the **Dashboard** tab where the **Domain URL** is `https://securiti.ai/`, as shown below.

## Related

- [Using the Compliance Dashboard to remediate cookie compliance risks](/using-the-compliance-dashboard-to-remediate-cookie-compliance-risks.md)
