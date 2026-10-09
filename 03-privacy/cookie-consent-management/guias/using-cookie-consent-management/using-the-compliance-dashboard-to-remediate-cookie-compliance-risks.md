---
title: "Using the Compliance Dashboard to remediate cookie compliance risks"
slug: "using-the-compliance-dashboard-to-remediate-cookie-compliance-risks"
updated: 2026-09-30T05:56:43Z
published: 2026-09-30T05:57:27Z
canonical: "helpcenter.securiti.ai/using-the-compliance-dashboard-to-remediate-cookie-compliance-risks"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Compliance Dashboard to remediate cookie compliance risks

**Scenario**

As a Privacy or Compliance Officer, you need a centralized view of cookie compliance risks across your domains. For instance, if a domain fails specific compliance checks, your team needs to quickly understand the issue, review supporting evidence, and assign the right owner for remediation. With Securiti’s Compliance Dashboard in the Cookie Consent Management module, you can review compliance scan results, identify risk areas, and track remediation activity from one place.

The Compliance Dashboard helps you review and remediate the cookie compliance scan results at the domain level. It shows the latest successful compliance scan for each domain and gives visibility into compliance scores, test outcomes, severity, remediation guidance, remediator ownership, and excluded tests. The dashboard displays the results in a visual format, giving your privacy, compliance, and marketing teams a centralized place to review identified risks and manage remediation activity.

> [!NOTE]
> Note
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

After a compliance scan completes, Securiti makes the latest successful scan results available in the dashboard. You can then review risks, assign ownership, take remediation action, and track compliance activity from one place. When you download or share a report, you can receive it through email. Securiti sends the generated report to the selected recipients through a secure email link.

> [!CAUTION]
> Caution
> 
> Consent Agent provides compliance insights for informational purposes only and does not constitute legal advice. Securiti does not accept liability for any decision you make based on these insights.

## Key considerations

Review the following considerations before using the Compliance Dashboard:

| Consideration | Description |
| --- | --- |
| Dashboard population | New tenants do not show compliance scan data until you request and complete compliance scans for selected domains through **Build with AI**. |
| Partial dashboard information | If the Compliance Dashboard displays partial information for a URL, the data might be from an older compliance scan that does not include all the information required by the dashboard. To refresh the data and display the latest compliance metrics, run a new compliance scan for the affected domain. |
| Latest scan results | The Compliance Dashboard shows only the latest successful scan for each domain. It does not show domain scan history in the current version. |
| Test outcome interpretation | The passed test count does not automatically indicate how many tests failed. Remaining tests may include failed tests, not applicable tests, user accepted risks, or user excluded risks. Use the **Excluded Tests** view to review tests excluded from active compliance evaluation. |
| Banner content updates | Review and update the first layer of the cookie banner when remediation guidance requires cookie banner content changes. |

## Procedure

To run a compliance scan and review the results in the Compliance Dashboard:

> [!WARNING]
> Important
> 
> The compliance scanner detects cookie banners from the following Consent Management Platform (CMP) providers:
> 
> - Securiti
> - OneTrust
> - CookieYes
> - Usercentrics
> - TrustArc
> 
> If your domain uses a CMP provider that isn't listed, the compliance scan might not detect the cookie banner, which can affect your compliance test results.

1. In Securiti, open Cookie Consent Management, and choose **Explorers > Compliance Dashboard**.

> [!NOTE]
> Note
> 
> If no compliance scans have run yet, Securiti shows the dashboard with no available data, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-No-Data-Available.png)
2. From the upper right corner, click **Build with AI**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-Build-with-AI.png)
3. In the **Consent Agent** sidebar on the left, enter a prompt to assess a domain for cookie compliance, such as “Assess `www.securiti.ai` for cookie compliance”, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Agent-Compliance-Prompt.png)
4. Press enter, or from the bottom right click the black arrow icon to submit your input.
5. Select one of the following options to let or restrict the Consent Agent’s actions, as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Get-User-Consent.png)

| Option | Configuration |
| --- | --- |
| Deny | Immediately stops the Consent Agent from performing the requested action. The compliance scan request gets cancelled. |
| Allow for this session | Lets the Consent Agent perform actions for the current session only. Consent Agent requests consent again in a new session. |
| Allow once | Lets the Consent Agent perform the specific action one time. Consent Agent requests consent again for subsequent actions. |

Once you grant consent, the Consent Agent initiates the compliance scan for the selected domain.
6. The Consent Agent shows the scan ID and the current scan status. The scan progresses through the following stages:

| `Stage | Description |
| --- | --- |
| Scanning | Securiti analyzes website pages and tracking technologies. |
| Processing | Securiti computes the compliance assessment against regulatory frameworks. |
| Done | Securiti completes the scan and makes the results available for review. |

> [!NOTE]
> Tip
> 
> If the scan is still in progress, check the status again later. You can ask the Consent Agent to check the scan status again. If the agent provides a scan ID, you can use it to retrieve or reference the compliance assessment.

Once the scan completes, return to the **Compliance Dashboard**. Securiti displays the latest successful compliance scan result for the scanned domain.
7. (Optional) Mark the checkbox next to the domain or scan result for which you want to download the report.
  1. Click **Download Report** to send the generated report via email, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-Download-Report.png)

> [!NOTE]
> Note
> 
> Securiti lets you share the generated report with anyone inside or outside Securiti via an email link which remains valid for **7 days**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Email(1).png)

## Assigning remediators to compliance risks

After reviewing compliance test results, you can assign a remediator to define ownership or use the Consent Agent to review remediation guidance for a selected issue.

To assign a remediator or review remediation guidance:

1. Mark the checkbox next to the test or risk for which you want to assign a remediator.
2. Click **Assign Remediator**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-Assign-Remediator-button.png)
3. On the **Assign Remediator** popup, from the **Assign Remediator** menu, select the user who should own the remediation, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assign-Remediator(1).png)
4. On the **Assign Remediator** popup, click **Save**.
5. Mark the checkbox next to the test or risk for which you want to review remediation guidance.
6. Click **Remediate**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-Remediate-button.png)

Securiti opens the **Consent Agent** sidebar and adds the remediation prompt for the selected compliance issue, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remediation-Prompt.png)
7. Press enter, or from the bottom right click the black arrow icon to apply the recommended remediation changes.

> [!WARNING]
> Important
> 
> After Consent Agent applies remediation changes, test the updated configuration using the Testing Code before deploying it to your live environment. Verify that the cookie banner appears correctly for the site visitors, and proceed with deployment only after confirming that the changes work as expected.

## Reviewing excluded tests

The **Excluded Tests** view in the Compliance Dashboard lets you review compliance tests that you exclude from active evaluation. You can also include excluded tests again when you want Securiti to evaluate them in future compliance scans.

Use the following table to understand how excluded and included tests work:

| Test type | Description |
| --- | --- |
| Excluded tests | When you exclude a test, Securiti creates a persistent exclusion rule for future compliance scans. The current scan results do not change, but Securiti skips the excluded test in each future scan until you include it again. |
| Included tests | When you include a previously excluded test, Securiti removes the exclusion rule and returns the test to active compliance evaluation. In future scans, the test can pass, fail, or require action again. |

To review excluded tests:

1. From the upper right corner of the Compliance Dashboard, click **Options** (three dots).
2. From the menu, select **Excluded Tests**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Coompliance-Dashboard-Excluded-Tests.png)
3. From the **Excluded Tests** table, select the domain whose excluded tests you want to review, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Excluded-Tests-table.png)
4. Review the excluded tests associated with the selected domain.
5. To include an excluded test again, click **Options** (three dots) next to the test, and select **Include Test**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Include-Test.png)

## Filtering the Compliance Dashboard

You can use filters on the Compliance Dashboard to narrow down and analyze compliance scan results based on specific attributes such as:

- Domain
- Scan ID
- Status
- Jurisdiction
- Severity
- Remediation type
- Remediator
- Test Owner
- Domain Group
- Scanned date

Filters help you quickly focus on the compliance results most relevant to your audit, investigation, or remediation needs.

To view the filters, click the **+** icon above the Compliance Dashboard table, as shown below. The filters panel opens, showing a searchable list of available filter properties.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-Filters.png)

> [!NOTE]
> Tip
> 
> Securiti lets you apply multiple filters at the same time to further refine the results.

The following filters are available on the Compliance Dashboard:

| Filter | Description |
| --- | --- |
| Domain | Filters compliance scan results by domain name. You can match domains that contain a specific value. |
| Scan ID | Filters compliance scan results by scan ID. This is useful when you want to review results for a specific compliance scan. |
| Status | Filters compliance tests by outcome. Available values include **Failed**, **Passed**, **Remediated**, **User-Excluded Risk**, and **User-Accepted Risk**. |
| Jurisdiction | Filters compliance test results by jurisdiction. Available values include **EU** and **US**. |
| Severity | Filters compliance test results by severity level. Available values include **Very High**, **High**, **Medium**, and **Low**. |
| Remediation | Filters compliance test results by remediation type. Available values include **Auto** and **Manual**. |
| Remediator | Filters compliance test results by the user assigned to remediate the issue. You can search for and select a remediator from the available user list. |
| Test Owner | Filters compliance test results by the user assigned as the test owner. You can search for and select a test owner from the available user list. |
| Domain Group | Filters compliance scan results by domain group. You can match domain groups that contain a specific value. |
| Scanned On | Filters compliance scan results based on the scan date. You can filter by dates that are **equal to**, **not equal to**, **before**, **after**, or **between** selected dates. |

## Related

- [Using Compliance Metrics to monitor cookie compliance risks and remediations](/using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations.md)
- [Configuring cookie consent experiences using Build with AI](/configuring-cookie-consent-experiences-using-build-with-ai.md)
