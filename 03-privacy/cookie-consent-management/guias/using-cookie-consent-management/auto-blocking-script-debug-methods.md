---
title: "Auto blocking script debug methods"
slug: "auto-blocking-script-debug-methods"
updated: 2026-09-03T06:44:13Z
published: 2026-09-03T06:44:13Z
canonical: "helpcenter.securiti.ai/auto-blocking-script-debug-methods"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Auto blocking script debug methods

Securiti lets you use the following auto blocking debug methods to print blocked and unknown initiators.

| Debug Method | Description |
| --- | --- |
| `window.printScrtBlockedResources()` | Use this debug method to print all **blocked** resources. |
| `window.printScrtUnknownResources()` | Use this debug method to print all **unknown** initiator resources. |

> [!WARNING]
> **Important**
> 
> To use the `window.printScrtUnknownResources()` debug method, you must enable the **Auto Blocking** and **Auto Blocking Unknown Initiator** toggles from the **Consent Code** tab, as shown below.
> 
> 
> 
> ![Screenshot_2023-09-11_at_12_21_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f45b15c-c7da-d331-75bc-81754d5de175(1).png)

To use the aforementioned debug methods:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Open the scanned domain for which you have auto blocking enabled and go to the **Consent Code** tab.
3. Make sure that both **Auto Blocking** and **Enable Auto Blocking Unknown Initiator** toggles are enabled, as shown below.

![Screenshot_2023-09-11_at_12_21_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f45b15c-c7da-d331-75bc-81754d5de175(1).png)
4. Copy all code blocks and deploy them in your web server as defined in [Deploying your website cookie consent banner](/v1/docs/deploying-your-website-cookie-consent-banner).
5. Open your deployed cookie banner and from this webpage, enter the inspect mode.
6. Switch to the **console** tab from the inspect mode.
7. Type any the debug method commands that you want to execute and press enter, as shown below.

![Screenshot_2023-06-09_at_12_39_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e2752f9-49b8-939a-45d6-10f28ff82aaa.png)

Initiator (in the context of web requests) is an entity that triggers a request for a resource such as a web page, an image, or a script to be loaded from a server. Initiators help in tracking and data collection because they can be associated with third-party domains that set tracking cookies or collect data.
