---
title: "Configuring an explicit consent preference center"
slug: "configuring-an-explicit-consent-preference-center"
updated: 2025-12-09T16:05:49Z
published: 2025-12-09T16:05:49Z
canonical: "helpcenter.securiti.ai/configuring-an-explicit-consent-preference-center"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring an explicit consent preference center

Certain regulations such as Quebec Commission to Access Information (CAI) don't let you reach out to the consumers or your data subjects without explicit consent from your data subjects for certain data processing and consent purposes. Securiti’s Explicit Consent configuration of preference center lets you comply with multiple regulations to obtain explicit consent from your data subjects. It offers exclusive **accept** and **reject** radio buttons against each consent purpose under the processing purpose, as shown below.

![Explicit-consent-default.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e38d7ee4-4961-974a-b56a-5c7899bee922.png)

![Explicit-consent-filled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e77fcae3-d5db-d397-de57-d4e9babe16ef.png)

Based on explicit consent preference center configuration, your data subjects must explicitly **grant** or **decline** their consents for a combination of processing purpose and consent purposes. If the data subjects don’t provide any consent for the processing and consent purposes, then Securiti considers this action as **No Consent**.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

To build an explicit consent preference center:

1. In Securiti, open **Universal Consent Management**, then choose **Universal Consent > Preference Center**.
2. On the Preference Center Dashboard page, near the upper right corner click **+ Add Preference Center** and create a preference center as explained in the [Building a universal preference center](/v1/docs/building-a-universal-preference-center).

![Add-preference-center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4f245b6-83f9-74e2-287a-027b6cc8ea81(1).png)
3. From the Opt-in Configuration section, mark the **Explicit Consent** radio button to build and host an explicit consent preference center where your data subjects can exclusively grant or decline consent for the processing and consent purposes, as shown below.

![step3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be368782-418a-3553-815a-3f994a854074.png)

When your data subjects click **Submit** on the Explicit Consent preference center without giving any consent, we record the consent status as **No Consent** as shown below. This no consent status only belongs to the Explicit Consent preference center.

![Screenshot_2023-11-20_at_2_20_05_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e8be080e-b5ee-8559-7582-f5c32dab0d00.png)
4. From the Explicit Consent Configuration section, you can customize the following:

![Screenshot_2023-11-20_at_2_22_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a66b6687-a84b-ce77-adfa-732200e1251c.png)
  - Accept Button Text
  - Reject Button Text
5. Complete the rest of explicit consent preference center configuration as explained in [Building a universal preference center](/v1/docs/building-a-universal-preference-center).
6. Review your explicit consent preference center, if it looks good then click **Publish**. If not, go back and make necessary changes.
7. On the Preference Center Dashboard page, find the entry for the new preference center and from the **URL** column, click **Copy** to copy the published link to the clipboard for later use. This is the link that you publish on your website for anyone who wants to configure their Consent Preferences.

![Screenshot_2023-11-20_at_2_28_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e70fbd7-11b1-8665-8e07-8b7b784d765b.png)
8. Work with your website team to publish the link to the preference center on your website.

The final layout of your preference center is based on two columns. The first column represents the processing purposes along with mapped processing purpose category labels, and the second one represents consent purposes, as shown below.

![step8_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e37938f3-4722-17cf-c829-9519e1167436.png)

Securiti lets you add custom translations for the texts of your explicit consent preference center. From the Preference Center Text Options section, enable the **Provide Translation Mapping** toggle and from the **Select Language** menu, select a language for which you want to add your custom translation, as shown below.

![step8_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86fc9ebf-ba8d-a610-08df-ac41815ae49f.png)

![step8_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5381d369-a53e-0ba8-83a3-1dfc3a4502c5.png)

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Customizing your universal preference center](/customizing-your-preference-center.md)
