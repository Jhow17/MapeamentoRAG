---
title: "Configuring DSR retention policy"
slug: "configuring-dsr-retention-policy"
updated: 2026-08-12T07:22:30Z
published: 2026-08-12T07:22:30Z
canonical: "helpcenter.securiti.ai/configuring-dsr-retention-policy"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR retention policy

You can configure the duration for which Securiti maintains closed DSRs and completed DSR reports in the DSR workspace. Securiti removes reports and closed DSRs once they reach the specified age. See [Understanding the DSR request process](/v1/docs/understanding-the-dsr-request-process) for more information.Understanding the DSR request process

1. In the Data Subject Rights module, choose **Settings > DSR Settings**.
2. Under the Retention Policy section, click **Edit** (pencil icon) on the right side to open retention settings in edit mode.

![Overview of DSR settings including retention policy and download configuration options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.04.00 PM.png)
3. Configure the number of days for which Securiti maintains DSR requests in the DSR workspace, and the duration for which completed DSR reports are available in the data subject portal, as shown below.

![Settings page displaying DSR retention policy and download configuration options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.21.26 PM.png)

> [!NOTE]
> **Note**
> 
> If you configure the private cloud storage, you can adjust the retention limit for closed DSRs in the DSR workspace to any period between **1 day** and a maximum of **36,500 days**. In case, if you do not configure the private cloud storage, you can set the maximum retention limit up to **1825 days**. In both cases, the retention period applies to DSR attachments as well. For more information on configuring the private cloud storage, see [Configuring private cloud storage](/v1/docs/system-settings-configuring-private-cloud-storage).
> 
> Similarly, for reports in the privacy central (data subject portal), you have the flexibility to choose a retention duration ranging from **1 day** to a maximum of **730 days**.
4. Near the upper right corner of the Duration Windows area, click **Save**.

Securiti sends only one reminder email to data subjects before DSR reports expire in Privacy Central (Data Subject Portal). The reminder is sent 2 days before the expiry date.

### Retention Period Management for DSR Access Levels

| DSR module access level | Default Retention Policy |
| --- | --- |
| Premium / Trial | Retention period is set to 730 days |
| Freemium / Free | Retention period is set to 30 days |

- For a tenant with DSR access set to Premium, changing the retention period of the DSR Workspace to 20 days (less than the Freemium default) and then switching to Freemium access, Securiti resets the retention period to 30 days. This change is logged in the audit trail.
- For a tenant with DSR access set to Fremium, changing the retention period of the DSR Workspace to 20 days (less than the Freemium default) and then updating access to Premium, Securiti resets the retention period to 730 days. This change is logged in the audit trail.
- If the DSR module is disabled, the limits would not be updated. And if the DSR module is reenabled without any change in DSR access level, the retention period would not be updated.
