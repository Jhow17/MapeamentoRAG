---
title: "Rule center overview"
slug: "rule-center-overview"
status: "update"
updated: 2025-11-04T12:12:33Z
published: 2025-11-04T12:12:33Z
canonical: "helpcenter.securiti.ai/rule-center-overview"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Rule center overview

**Scenario**

As a data compliance officer, you need to prove your systems meet regulatory controls. Manually checking each control or gathering evidence from teams is slow and inconsistent. In Rule Center, you configure automated tests, rules that continuously verify compliance with specific controls, either automatically or through attestations for manual review. You also apply toxic combinations, a special type of graph-based test that detects risky configurations or relationships, such as excessive access or unprotected data. This centralizes compliance checks, helping you uncover risks early, resolve issues, and demonstrate compliance without scattered processes.

The rule center page contains details about the Tests. A test serves as a detailed plan that outlines the necessary steps to ensure compliance with the requirements specified in a control. These tests can be categorized into two primary types:

- **Automated Evaluation:** In this type of testing, you define expressions that are executed against the UDG. An expression represents a set of criteria used to evaluate whether a data asset complies with a specific control or meets defined compliance requirements. During automated evaluation, these tests are executed as graph queries built on top of the ingested metadata from connected and scanned cloud assets and data systems.

**Example**: Are all stores of sensitive data encrypted at rest?
- **Attestation or Manual Evaluation:** Unlike automated evaluations, attestation involves manual assessments where you validate compliance by reviewing one or more object attributes. This process requires you to examine specific aspects of a system or process to determine whether it aligns with the defined control requirements. Attestation is typically used when certain controls cannot be easily automated. These tests require you to confirm fulfillment of the control and upload supporting evidence to substantiate the attestation.

**Example**: Does your organization have a documented policy requiring employees to have background checks?

To access the rule center:

- In Securiti, open **Compliance**, and at the upper right corner of the compliance dashboard, click **Tests**.
- Or from the left navigation bar, select **Tests > Compliance Tests**.

> [!NOTE]
> **Note**
> 
> You can also access **Rule Center** through **Policies**.
> 
> 1. At the bottom of the Securiti dashboard, click **Policies**.
> 2. On the **Policies** page, at the top right corner, select **Rule Center > Tests**.

> [!NOTE]
> **Important**
> 
> Tests are no longer tied to the Compliance module. This update lets Compliance be offered as an add-on.
> 
> They are now included in the base Sensitive Data Intelligence license and no longer require Compliance to be enabled. The Compliance module continues to function as before.

#### Test execution

- Compliance tests are first executed on the day Compliance is enabled for a tenant.
- After that, tests automatically re-run on a weekly cycle, based on the day Compliance or Sensitive Data intelligence was enabled for the tenant. This schedule is fixed per tenant.
- When new connectors are added, the system automatically re-evaluates the tests after data becomes available.
- If posture scans have not completed successfully or required module i.e. Data Command Centre is not enabled, there may be no findings even though the tests have executed.

#### Rule center dashboard

The rule center is a generic page that contains all graph-based rules and compliance manual tests. There are categories of graph rules each with its left navigation bar. These are:

- Tests (Compliance manual tests and all graph-based rules)
- Cloud security posture rules

![Rule_center_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8fa28e79-4d40-c75f-b138-8707e0201428.png)

### Filtering the tests list

The search bar at the top of the list lets you search for the created test by its name or description.

Below the search bar, you can see various filter options to specify the criteria by which you want to filter tests. Click any of the filter options, choose values from their respective menu, and click **Apply**. As a result, the list updates to display only tests that meet the specified criteria.

The available filters are as follows:

- The **Status** menu lets you filter tests by their status, such as active or inactive.
- The **Test Name** menu lets you filter tests by their names.
- The **Type** menu lets you filter tests based on type, either **Expression** or **Attestation**.
- The **Severity** menu lets you filter tests according to their severity level.
- The **Risk Factor** menu lets you filter tests based on their associated risk factors. The risk factor defines the Impact of the Risk associated with the test.
- The **Frameworks** menu lets you filter the tests related to a specific framework.
- The **Owner** filter lets you filter the tests based on the email address of the test Owner.
- The **Tags** menu lets you filter tests based on keywords or phrases for tags.
- The **Entity Type** menu lets you filter tests based on the linked specific entity type that is supported as a node in the graph explorer.

> [!NOTE]
> **Note**
> 
> System-generated tests can be filtered based on a specific graph node rather than just an asset node. These tests are created using a defined entity type, not limited to cloud asset nodes only.
- The **Created Date** menu lets you filter tests based on their creation dates.
- The **Modified Date** menu lets you filter tests by their most recent modification dates.

Below the filters, you can view the following counts:

- Created tests
- Active tests
- **Violations** associated with the tests
- **Compliance Standards** linked to the tests

### Exploring tests

For every test displayed on the Rule Center dashboard, you can access the following details:

- Status
- Name
- Type
- Severity
- Entity type
- Risk factor
- Date created
- Last modified
- Findings
- Owner

> [!NOTE]
> **Note**
> 
> The count of passed assets and failed assets vary depending upon the [Securiti's organization-level](/v1/docs/system-settings-managing-organizations) you have selected.

- Click the down-arrow to expand the test for more details.
- Click **Options** (three dots) to view the test or graph view of the test.

> [!NOTE]
> **Note**
> 
> On the right side of the owner column, you can find the column selector. It lets you choose which columns to display in the tables listing test. This way, you can customize the view according to your preferences. You can also reset the selection to default settings.
- Below the column selection, you can click **Metadata Explorer** to view the complete metadata details of the test.

#### Creating widgets

You can see the **Create Widget** button on the right side of the **Create Test** button. This option lets you display test-specific widgets on the projects dashboard to track metrics, trendlines, and more.

1. Click **Create Widget**.
2. Enter relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).

A test outlines the actions needed to capture evidence to satisfy a control. Tests can take the form of automated evaluations, utilizing expressions executed against the UDG. Alternatively, they can involve manual assessments, where individuals provide answers, evaluating one or more object attributes. A single control may refer to multiple tests, and a single test can be used by multiple controls.

## Related

- [Test findings](/test-findings.md)
