---
title: "Universal preference center integration with mobile applications"
slug: "preference-center-integration-with-mobile-applications"
updated: 2026-01-08T11:05:17Z
published: 2026-01-08T11:05:17Z
canonical: "helpcenter.securiti.ai/preference-center-integration-with-mobile-applications"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Universal preference center integration with mobile applications

Securiti lets you integrate its universal preference center with your developed mobile applications via the following APIs:

- [Read Configuration API](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/fetch_preference_center_for_uuid)
- [Save Consent API](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Upload_consent_via_preference_center)

To integrate the preference center with your mobile application:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Preference Center**.
2. From the upper right corner of the page, click **+ Add Preference Center** and create a new preference center as defined in [Building a universal preference center](/v1/docs/building-a-universal-preference-center).
3. After building your preference center, customize it to suit as defined in [Customizing your universal preference center](/v1/docs/customizing-your-preference-center).
4. Configure some processing purposes and consent purposes for your preference center as defined in [Configuring processing purposes and consent purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes).
5. On the left side of the preference center builder, enable the **Location Intelligence** toggle after configuring the processing and consent purposes as shown below.

![Screenshot_2023-05-16_at_8_14_53_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7dced991-1ff1-78a8-e471-acf80fc721d1.png)
6. Publish your configured preference center, open it again and from the upper right corner of the preference center builder copy the **Preference Center** **ID** and **Tenant Auth Token** values as shown below.

![Screenshot_2023-05-16_at_8_00_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66e9e45d-eb4a-a2a7-7786-73a022a779b7.png)
7. Pass the copied value of the **Preference Center** **ID** as the header value of `X-CMP-PrefCenter-Id` and pass the copied value of the **Tenant Auth Token** as the header value of the `X-Auth-Token` in the headers section of the [Read Configuration API](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/fetch_preference_center_for_uuid).
8. Now, build the UI of your mobile application using **metadata** and **purposeTree**.

> [!NOTE]
> **Important**
> 
> You must keep the **Purpose IDs** associated with the form elements of the UI.
9. Build the **Submit** button, and on submit call the [Save Consent API](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Upload_consent_via_preference_center) with the proper payloads as mentioned in the API reference.

> [!NOTE]
> **Note**
> 
> - You must pass the copied values of the **Preference Center** **ID** and **Tenant Auth Token** as the header values of `X-CMP-PrefCenter-Id` and `X-Auth-Token` in the headers section of the Save Consent API respectively.
> - `X-CMP-UUID` is the mandatory **data subject ID** that must be managed by the mobile application.
10. Store the consent payload in the `LocalStorage` of the developed mobile application to show the previous consent to your data subjects when they revisit the preference center via the mobile application.

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Universal Consent Management API reference](/universal-consent-management-api-reference.md)
