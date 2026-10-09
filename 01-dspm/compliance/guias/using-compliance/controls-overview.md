---
title: "Controls overview"
slug: "controls-overview"
updated: 2025-11-04T12:15:37Z
published: 2025-11-04T12:15:37Z
canonical: "helpcenter.securiti.ai/controls-overview"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Controls overview

**Scenario**

As a data compliance officer, you may oversee compliance efforts across multiple frameworks. Each standard comes with its own set of controls, features such as encrypting sensitive data or enforcing access restrictions. Instead of building these from scratch, you can start with a rich library of preloaded controls. When needed, you add custom ones that match your internal policies. The result is less manual work, more precision, and full traceability for audits.

A control specifies specific requirements within regulations, standards, or best practices. For instance, it may include requirements like "encryption of sensitive data". During the tenant initialization process, our system automatically loads pre-defined compliance controls. However, you can also add custom controls that are tailored to the specific needs and requirements of your organization.

To access the list of predefined and customer controls:

- In Securiti, open **Compliance**, and at the upper right corner of the compliance dashboard, click **Controls**.
- Or from the left navigation bar, select **Controls > Compliance Controls**.

![Main_Compliance_db_Controls_hl.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdf0e762-349a-3e46-23d1-ba54ac22730d.png)

> [!NOTE]
> **Note**
> 
> Because frameworks are continuously updated based on the latest research and interactions of standards and legislation, additional controls may appear in releases reducing a customer’s progress towards compliance with the frameworks they are trying to comply with.

#### Controls dashboard

The controls dashboard lets you view the count of passed controls against the total controls created.

### Filtering controls

The search bar lets you search for the control by its name.

You can filter out controls related to a specific framework.

- **Active**: This menu lets you filter controls based on the status. The status can be:
  - **True**: The control is active.
  - **False**: The control is inactive.
- **Frameworks**: This menu lets you filter controls based on their reference to a specific framework
- **Owner**: This menu lets you choose an owner name from a list of all users assigned to controls, filtering the list to display only controls owned by the selected user.
- **Test Type**: This menu lets you filter controls by the type of associated tests. The tests can be:
  - Expression
  - Attestation

### Exploring controls

The list on the dashboard shows you all the controls in the compliance module.

Against each control, you can view its:

- Name
- Created date
- Last modified date
- Linked frameworks
- Failed tests against the total tests
- Owner
- Count of passed assets
- Count of failed assets

> [!NOTE]
> **Note**
> 
> The count of passed assets and failed assets vary depending upon the [Securiti's organization-level](/v1/docs/system-settings-managing-organizations) you have selected.

- Click the down arrow located between the **Status** and the **Name** of the control to expand the control for more details.
- Click **Options** (three dots) to view the created control.

> [!NOTE]
> **Note**
> 
> On the right side of the owner column, you can find the column selector. It lets you choose which columns to display in the table listing control. This way, you can customize the view according to your preferences. You can also reset the selection to default settings.
- Below the column selection, you can click **Metadata Explorer** to view the complete metadata details of the control.

#### Create custom controls

To create a custom control:

1. On the **Controls** list, in the upper right corner, click **Create Control**.
2. Enter the **Control Name**, **Description**, and select the **Framework** from the menu.
3. Further, select a Sub-category from its respective menus, select the tests you want to associate with the control, and add **Remediation** which is the suggested action or measure proposed to address and mitigate risks in case the control fails.

![create_control_form.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1550941-8072-ed17-779d-faf853aa27d7.png)
4. Once done, click **Create Control.**

#### Edit a control

1. On the **Controls** list, locate the card for the control you want to edit.
2. At the right end of the card, choose **Options** three dots) **> Edit**.
3. Update the required details and click **Update Control**.

#### Delete a control

To delete a control that you no longer require:

1. On the **Controls** list, locate the card for the control you want to delete.
2. At the right end of the card, choose **Options** (three dots) **> Delete.**

Securiti opens a confirmation box.
3. Click **Delete Control** to confirm deletion.

> [!NOTE]
> **Note**
> 
> You can only edit or delete custom controls. You cannot update or delete system controls.

#### Disable a control

When a control is created, it is now automatically enabled by default. You can manage the control’s status as follows:

To disable a control:

- Click **Status** toggle on the control’s card to disable it.

### Disabling a control linked to a framework

Disabling a control from the **Frameworks** page only affects its status within that specific framework. The control will still appear as enabled on the main Controls listing page.

To disable the control linked to a framework:

1. Navigate to the **Frameworks** page.
2. Expand the desired framework to view the linked controls.
3. Locate the control you want to disable and click **Status** toggle.

#### Duplicate a control

You can duplicate a custom control.

1. On the Frameworks list, select the framework.
2. To the middle right side of the page click **Option** (3 dots) next to the control card and select **Duplicate**.
3. To duplicate the control to the same framework:
  1. Click **to the same Framework**.
  2. Choose **category**.
  3. Choose **subcategory**. The control is duplicated in the selected subcategory.
4. To duplicate the control to a different framework:
  1. Click **to a different Framework**. A list of custom frameworks displays.
  2. Click on the required framework.
  3. Choose **category**.
  4. Choose **subcategory**. The control is duplicated in the selected subcategory.

#### Sorting controls

You can sort the listed controls in ascending or descending order by clicking **Name** and **Failed/Total tests** columns.

#### Creating widgets

You can see the **Create Widget** button on the right side of the **Create Control** button. This option lets you display control-specific widgets on the projects dashboard to track metrics, trendlines, and more.

1. Click **Create Widget**.
2. Enter the relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).

## Related

- [Rule center overview](/rule-center-overview.md)
