---
title: "Evaluating tests in a project"
slug: "evaluating-tests-in-a-project"
updated: 2025-11-03T04:46:11Z
published: 2025-11-03T04:46:11Z
canonical: "helpcenter.securiti.ai/evaluating-tests-in-a-project"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Evaluating tests in a project

Automated tests run on the data systems defined in the graph expression and are executed on a weekly cycle. In contrast, the manual test, known as Attestation, requires manual evaluation.

1. In Securiti, open **Compliance** and select a project from the Current Projects list from the left panel.

![Search_projects.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-187275ff-946e-e275-c9b1-cd28a86830da.png)
2. Select the framework and further expand respective **Category > Sub-Category > Control >Test**.
3. To evaluate the manual test:

The graphical representation of the test displays its connection to the relevant controls and project as nodes. Click on a node to view the information related to it.

![evaluating_tests_graphical_representation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fd1ca67-581e-ae34-4586-82ce53654f9a.png)

When the evidence is provided the status of the manual test is changed to **Passed**.

The test automatically fails after the duration of its validity has passed.

To replace an existing evidence, click **Fail Test**. The existing evidence is removed and you can now replace the evidence.
  - Click the test. A popup window displays.
  - Upload the evidence files or provide a link that the system should use to complete the test successfully.

![Updated_upload_evidence_UI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d598c04-f8d5-ab39-a84b-f9a5dffe46ee.png)
  - Click **Submit**. The evidence file is displayed with the frequency and relevant details.

### Accessing assets for an automated test

Automated tests are evaluated at most weekly as new data is added to the scope. If the test fails, it shows a list of the failed assets only.

1. In Securiti, open Compliance and select a project from the **Current Projects** list from the left panel.
2. Select the framework and further expand respective **Category > Sub-Category > Control > Test**.
3. Open the automated test that has been evaluated and explore the following details:
  - At the top, you can view the test details including, Name, Severity, Frequency etc.

![Screenshot_2025-09-19_at_4_08_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e982def-54d2-e9b6-4336-7be21cf2da72.png)
  - The Status section shows you the status of the tests in percentage. The donut chart at the right side visually represents the ratio of passed (green) to failed (red) tests.
  - Below the Status section, the graphical visualization shows how the test is connected to other compliance, governance, and operational components within the system. It provides a relationship map to understand dependencies, impact, and accountability.

![Screenshot_2025-09-19_at_4_08_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f683790-8d22-d3e0-cc28-ca8bc78f82bd.png)
  - Below the graphical visualization, you can explore the relationship map details further in tables. This table interface is divided into two panels:
    - The left panel lists the components associated with the test and their respective counts.
    - Click on any component in the left panel to view detailed information in the right panel.

### Muting tests in a project

You have the option to mute a test if the required evidence to be uploaded is not available. The test is muted for the duration of the set frequency for the test. For example, if the frequency for providing evidence for the test is monthly, the mute status of the test will remain for one month. After the time period according to the set frequency is finished, the status of the test will change to Failed.

1. In Securiti, open **Compliance** and select a project from the Current Projects list from the left panel.
2. Select the framework and further expand respective **Category**>**Sub-Category**>**Control** >**Test**.
3. To mute the manual test:
  1. Click the test. A popup window displays.
  2. Click **Mute**.
4. In the input field for reason, enter a reason for muting the test. For example, the reason is “**The report to be submitted will be available in one week**”. The **Submit** button is activated.
5. Click **Submit**.
6. To provide the evidence:
  1. Open the muted test.
  2. Click **Un-mute**.
  3. Provide the evidence with a document or a link.
  4. Click **Submit**.
