---
title: "Configuring risk settings in V2"
slug: "configuring-settings-in-risk-v2"
updated: 2026-07-20T10:38:05Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-settings-in-risk-v2"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring risk settings in V2

Risk settings control the scoring framework, risk levels, and aggregation methodology used across your risk program. Only Risk Admins can access and edit risk settings.

To open risk settings, from the Securiti Main Menu, click **Risk Management**, then select **Settings > Risk Settings**.

Risk V2 supports two scoring frameworks: Linear and Risk Matrix. The framework you configure applies globally to all risks in your tenant. You can customize risk levels, scoring, and aggregation methodology within your chosen framework.

## Scoring framework

Risk Matrix is the default scoring framework in Risk V2. You can switch between Linear or Risk Matrix from risk settings. Because the two use different scoring models, switching frameworks requires existing risks to be remapped to the new framework.

To switch:

1. On the Risk Settings page, click **Edit**.
2. Under General Risk Settings, click the **Linear** or **Risk Matrix**.
3. Near the upper right corner, click **Apply Changes**. To discard, click **Reset**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.21.25 PM(1).png)

## Risk level configuration

You can update the label, score, and color assigned to each risk level directly in risk settings.

To update:

1. Click the risk field you want to update.
2. Edit the **Risk Level Label**, **Set Risk Score**, and **Set** **Risk Color** values to suit.
3. (Optional) To add a new risk level, click **+ Add Risk Level**. To delete a risk level, click the delete icon next to the relevant row.
4. To save, click **Apply Changes** or **Reset** to discard changes in the risk settings.

When you update a risk level label, every existing risk carrying that label updates to reflect the new label for both inherent and residual risk. When you update a risk score, Securiti recalculates aggregate risk values using the new score. Any risk created after the update uses the new label or score by default in the risk picker.

## Matrix setup

When Risk Matrix is selected as the scoring framework, you can configure the matrix dimensions, axis labels, and cell scores.

To configure:

1. Click **Edit Matrix** in the **Risk Matrix Setup** section of risk settings.
2. Configure the matrix size using the grid size dropdown in the matrix editor.
3. Edit individual cell scores directly in the matrix grid within the editor.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-07 at 2.10.55 PM.png)

> [!NOTE]
> Note
> 
> The minimum grid size is 3×3 and the maximum is 10×10. Reducing the matrix grid size from the current setup may impact existing risks and may require remapping.
> 
> Also, updating a cell score triggers recalculation of aggregate risk values for existing risks mapped to that cell.
4. Once done, click **Save Configuration** to close and exit the editor.
5. (Optional) In the Risk Matrix Setup section, configure axis labels:
  1. Severity (X-axis)
  2. Likelihood (Y-axis)
    1. To edit an axis name, click the pencil icon next to **Severity** or **Likelihood**.
    2. Adding a new or editing an existing dimension updates corresponding label entry to the relevant axis.
6. To save, click **Apply Changes** or **Reset** to discard changes in the risk settings.

## Risk aggregation methodology

Risk aggregation determines how Securiti calculates an overall risk outcome when multiple risks contribute to the same object or scope, such as an assessment, asset, vendor, or process.

You can select one of the following options in risk settings:

- **Mean**: calculates the average risk score across contributing risks
- **Median**: uses the middle score which reduces the effect of outliers
- **Maximum**: uses the highest individual risk score contributing to the roll-up

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-07 at 2.21.08 PM.png)

Securiti uses your configured risk level thresholds to classify aggregated results as Very High, High, Medium, Low, or Very Low. Aggregation applies to both aggregated inherent risk and aggregated residual risk.

## Confirm Changes dialog

When you click Apply Changes in risk settings, Securiti displays the Confirm Changes dialog before applying any updates. The dialog lists each pending change as a separate row. Once confirmed, changes apply to existing risks immediately. The previous state of affected risks is not restored automatically. To return to previous values, you must manually edit the settings and apply the changes again.

Each row in the dialog includes the following:

- **Value Type**: the type of change being applied - Risk Type Changed, Risk Level Updated, Risk Score Updated or Aggregation Method Updated.
- **Current Value**: the previous risk framework, label, score or aggregation methodology.
- **New Value**: the updated risk framework, label, score or aggregation methodology.
- **Risks Impacted**: the number of risks affected by the change. It displays a dash for changes where a count does not apply.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-07 at 2.11.32 PM.png)

The following Value Types may appear depending on the changes made:

| Value Type | Description |
| --- | --- |
| Risk Type Changed | The scoring framework is switching between Linear and Risk Matrix |
| Aggregation Method Updated | The aggregation methodology is changing |
| Matrix Dimension Added | A new row or column is being added to the risk matrix |
| Risk Level Updated | A risk level label is changing; shows the number of risks impacted |
| Risk Score Updated | A risk level score is changing; displays the score and associated risk level label together, for example "25 · Very High" |
| Severity Label Added | A new severity label is being added to the matrix X-axis |
| Likelihood Label Added | A new likelihood label is being added to the matrix Y-axis |
| Risk Level Deleted | A relevant risk level row is being deleted |

To apply all changes, click **Apply Changes**. To discard, click **Cancel**.

> [!NOTE]
> Note
> 
> While recalculation is in progress, Securiti locks risk settings from editing and displays a message indicating that you can’t edit settings until recalculation completes.
