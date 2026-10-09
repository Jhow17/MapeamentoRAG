---
title: "Restoring a previous SDK version"
slug: "restoring-a-previous-sdk-version"
updated: 2026-08-27T11:36:52Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/restoring-a-previous-sdk-version"
stale: true
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Restoring a previous SDK version

Securiti's SDK restoration functionality acts as a safety net and lets you easily restore the previous stable SDK version if the latest one doesn't meet your needs or has unexpected issues. Securiti lets you combine a previously deployed cookie configuration version with a previous SDK version for restoration. Deployed cookie configuration version contains all of the changes that you’ve configured from the management portal and applied to your domain’s cookie banner and preference center.

This functionality is useful when our latest SDK version is incompatible with your domain. It lets you quickly restore a previous stable SDK version if the newest one causes issues or fails to meet your needs, eliminating the need to wait for a patch or fix.

> [!NOTE]
> **Note**
> 
> - If this functionality is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - The following roles can access and use this functionality:
>   - Super Admin
>   - Organization Admin
>   - Module Owner

When you restore a previous SDK version, Securiti shows you a yellow banner at the top of the Cookie Configuration page indicating that you are using a restored SDK version, as shown below.

![Yellow-banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13d462c4-9a30-f6bc-39c2-b26b9e28341f.png)

### Key considerations

When restoring a previously deployed SDK version, consider the following:

- Securiti lets you restore versions associated with the **five most recent SDK releases**. This limit is based on SDK releases, not the age of a deployment. As Securiti releases new SDK versions, deployments associated with SDK versions outside this five-release window are no longer available for restore.
- Your domain must have **at least two published cookie configuration versions** available after Securiti enables this functionality for your tenant.
- Restore behavior depends on your SDK deployment method:

| Deployment Model | SDK restore behavior |
| --- | --- |
| Automatic SDK deployment | Restoring a previous deployment restores the **cookie configuration associated with that deployment**. It does not roll back the SDK version. Your domain continues to use the latest SDK version. However, if you select a different SDK version during the restore flow, your domain uses the selected SDK version instead. |
| Manual SDK deployment | Restoring a previous deployment can restore the **SDK version associated with that deployment**, provided it falls within the supported five-release window. |
- Any new publish uses the **latest SDK version**. If you manually restore an earlier SDK version, publishing the cookie configuration again upgrades the deployed SDK to the latest version.
- Restoring a previous configuration may limit functionality that depends on configuration introduced in a later version.
- After you restore a previous version, the configuration displayed in the management portal may differ from the configuration currently deployed on your domain. The management portal continues to show your current configuration, while your domain uses the configuration associated with the restored deployment.
- If you plan to make significant configuration changes and want to preserve the current configuration as a restore point, you can publish it without making any changes. This creates a new restore point within the supported restore window.
- When you restore a previous configuration, Securiti also restores its associated custom `CSS` to maintain the cookie banner and preference center styling from that deployment.

### Procedure

To restore previously deployed SDK version back to the domain:

1. In Securiti, open Cookie Consent Management and choose **Cookie Consent > Domains**.
2. Click the domain for which you want to restore a previous SDK version.
3. On the Cookie Configuration page, from the upper right corner, click **Deployed Version History**, as shown below.

![Restore_access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbad1149-332b-fd84-1030-dd4aaed869d8.png)
4. On the Deployed Version History page, from the far right side of the previously deployed cookie configuration version that you want to restore with an SDK version, click **Restore**, as shown below.

![Restore-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73507020-ca1f-a555-7cbe-9c2add4947f1.png)

> [!WARNING]
> **Important**
> 
> Securiti strongly recommends:
> 
> - You preview the cookie banner and preference center with the SDK version that you want to restore, before restoring it. From the right side of the previously deployed cookie configuration version that you want to restore, click **Options** (three dots), and select **Preview**, as shown below. ![SDK-preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19f935b7-0609-c7e0-82e4-e7790381b8c3.png)
> 
> Near the upper side of the Cookie Banner Preview page, from the **SDK Version** menu, select the SDK version that you want to restore. Then, from the **Banner Location** and **Preview Language** menus, select the respective location and language in which you want to preview the cookie banner and preference center, as shown below.
> 
> ![Preview-SDK-menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a744a296-70a4-839a-876d-8db79c567878.png)
> - You thoroughly test the SDK version that you want to restore in your QA or staging environment before restoring it. From the right side of the previously deployed version that you want to restore, click **Options** (three dots), and select **Copy Test Code**, as shown below. This action copies the test code to the clipboard, and you can paste this JavaScript test code snippet at the beginning of the `&lt;head&gt;` tag in your QA or staging domain for testing purposes.
> 
> ![SDK-test-code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1aea6080-d166-f871-a258-f10e5ed75291.png)
5. On the **Restore Deployed Version** popup:
  1. From the **Select SDK Version** menu, select a previous SDK version that you want to restore to your domain, as shown below.

> [!WARNING]
> **Important**
> 
> To make an informed decision about which SDK version to restore, click [Cookie Consent SDK change log](/v1/docs/cookie-consent-management-sdk-change-log) to view detailed information in the SDK change log help topic.

![Restore-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a23ac10d-8547-4f96-0eea-41f4dabe35dd.png)

- In the **Change Note** text field, enter the reason to restore this particular previous SDK version.
- Once done, near the bottom of the popup, click **Restore**, as shown below.

![Restore-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74a5ce97-e2cc-ed7f-97e1-45b92b37ac34.png)

Securiti shows you a success message near the upper right corner of the page, after successful restoration of the SDK version to your domain.

Securiti places the restored SDK version at the top of the Deployed Versions table. From the right side of the restored SDK version, click the arrow to view the maintained history of restored SDK version, as shown below.

![Restored-SDK-placement.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c6f8ffc-dbf1-b340-8349-be92e36166d4.png)
