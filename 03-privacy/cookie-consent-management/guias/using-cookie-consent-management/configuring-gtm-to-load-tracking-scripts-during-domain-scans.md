---
title: "Configuring GTM to load tracking scripts during domain scans"
slug: "configuring-gtm-to-load-tracking-scripts-during-domain-scans"
updated: 2026-07-20T09:21:27Z
published: 2026-07-20T09:21:27Z
canonical: "helpcenter.securiti.ai/configuring-gtm-to-load-tracking-scripts-during-domain-scans"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring GTM to load tracking scripts during domain scans

Securiti's website scanner sends a `securiti_scanning` event before starting a domain or compliance scan. You can use this event in Google Tag Manager (GTM) to temporarily load GTM-managed tracking scripts during a scan. This helps Securiti discover cookies and trackers that GTM-managed tags might not otherwise activate during scanning.

## Key considerations

Review the following considerations before configuring GTM for scan-based tracking script detection:

- This functionality currently only supports Google Tag Manager (GTM).
- Securiti does not automatically configure GTM containers.
- You must manually add the **Securiti Scanning** trigger to the tags that load tracking technologies.
- Existing consent and category-based triggers remain unchanged and continue to control visitor-facing consent behavior.
- The scanning trigger is used only to enable the scanner to discover GTM-managed cookies and trackers during scans.

> [!WARNING]
> **Important**
> 
> Securiti only sends the `securiti_scanning` event during a scan. To enable cookie and tracker discovery, you must configure the required GTM variable, trigger, and tag associations. Without this configuration, GTM-managed tracking technologies may not be detected during scans.

## Prerequisites

This functionality requires configuration within your GTM container.

During a scan, Securiti sends the following data layer event:

```json
{
  "event": "securiti_scanning",
  "SecuritiScanning": true
}
```

Before configuring the scan trigger, make sure you can access the GTM container used by the domain that you want to scan.

## Procedure

To configure GTM for scan-based tracking script detection, you must:

1. Create a GTM data layer variable.
2. Create a custom-event trigger.
3. Associate the trigger with tags that load tracking scripts.

## Sequence of Procedures

Follow the procedures in the sections below in sequence:

### Step 1 - Create a Data Layer variable

To create a data layer variable:

1. Sign in to your Google Tag Manager account.
2. Open the container used by the domain you want to scan.
3. From the panel on the left, navigate to **Variables**.
4. Below the **User-Defined Variables** section, click **New**.
5. Select **Variable Configuration**.
6. From the **Variable Type** menu, select **Data Layer Variable**.
7. In the **Data Layer Variable Name** text field, type `SecuritiScanning`.

> [!NOTE]
> **Note**
> 
> Keep the default option in the **Data Layer Version** menu.

1. From the upper right corner, click **Save**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/one(1).png)

The variable stores the value that Securiti sends during scanning. GTM uses this variable in the custom event trigger that you create in the next step.

### Step 2 - Create a Securiti scanning trigger

To create the Securiti scanning trigger:

1. From the panel on the left, navigate to **Triggers**.
2. From the upper right corner, click **New**.
3. Enter the trigger name `Securiti Scanning`.
4. Select **Trigger Configuration**.
5. From the **Trigger Type** menu, select **Custom Event**.
6. In the **Event Name** text field, type `securiti_scanning`.
7. From the **This trigger fires on** section, mark the **Some Custom Events** radio button.
8. In the **Fire this trigger when an Event occurs and all of these conditions are true** section, enter the following values:

| Field | Operator | Value |
| --- | --- | --- |
| `{{SecuritiScanning}}` | equals | true |

1. From the upper right corner, click **Save**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/two.png)

This trigger activates whenever Securiti initiates a scan and sends the `securiti_scanning` event.

### Step 3 - Associate the trigger with tracking tags

To save the tag for each GTM tag that loads cookies, pixels, analytics scripts, advertising technologies, or other tracking scripts:

1. Navigate to **Tags**.
2. From the **Tags** table, select the tag you want to update. This opens the tag in preview mode.
3. Click **Edit** (pencil icon) next to **Tag Configuration** to enable tag editing.
4. In the **Triggering** section, add the **Securiti Scanning** trigger.
5. Retain the tag's existing consent-based triggers.
6. From the upper right corner, click **Save**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/three.png)

> [!NOTE]
> Note
> 
> The tag should contain both:
> 
> - Its existing consent or category trigger.
> - The **Securiti Scanning** trigger.

This configuration enables the tag to continue functioning normally for visitors while also allowing Securiti scans to activate the tag and detect the associated tracking technologies.

#### Updating tags in bulk

If you're updating multiple tags, you don't need to repeat these steps for each tag. GTM lets you apply the trigger to multiple tags in a single action.

1. In your GTM container, navigate to **Tags**.
2. Select the checkboxes next to each tag you want to update. To select every tag on the page, select the checkbox in the table header.
3. Click the **Edit triggers** icon in the toolbar above the list.
4. In the panel that opens, select the checkbox next to **Securiti Scanning**.
5. Click **Save**.
6. Click **Submit** to publish the change to your live GTM container.

## Publishing your changes

To publish your GTM changes:

1. Click **Submit** in GTM.
2. Review the changes.
3. Publish your updated container.

## Verifying the configuration

After publishing the container:

1. Run a domain scan or compliance scan in Securiti.
2. Confirm that GTM receives the `securiti_scanning` event.
3. Verify that the configured tags fire when the event occurs.
4. Review the scan results to confirm that the associated cookies and trackers are detected.

Google Tag Manager (GTM) is a tag management system that lets organizations set up and manage website or mobile app tags without frequently changing the application code. It uses containers, tags, triggers, and variables to control when tracking, analytics, marketing, or consent-related scripts run across digital properties.
