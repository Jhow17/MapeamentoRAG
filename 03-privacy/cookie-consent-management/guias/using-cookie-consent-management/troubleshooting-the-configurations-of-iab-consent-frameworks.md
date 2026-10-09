---
title: "Troubleshooting the configurations of IAB consent frameworks"
slug: "troubleshooting-the-configurations-of-iab-consent-frameworks"
updated: 2026-02-24T14:19:51Z
published: 2026-02-24T14:19:51Z
canonical: "helpcenter.securiti.ai/troubleshooting-the-configurations-of-iab-consent-frameworks"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Troubleshooting the configurations of IAB consent frameworks

This guide helps troubleshoot issues with IAB EU TCF v2.3 and IAB U.S. National configured Cookie banners on your domains. It assumes you have enabled one of these configurations in the management portal and deployed the consent code on your domain. The steps below often require opening the browser's developer tools and reloading the website to observe network calls and console messages.

Use the following table to quickly identify relevant details and guidance tailored to your specific needs:

| Aspect | Description |
| --- | --- |
| Intended Audience | This troubleshooting guide is specifically designed to assist internal stakeholders at Securiti, including the **Customer Success**, **Professional Services**, **Sales**, and **Quality Assurance** (QA) teams, in diagnosing and resolving issues that may arise during domain scans. |
| Preparation | Before you begin troubleshooting, you must ensure you have the necessary access to the tools and information mentioned throughout this guide, including developer tools, EFK logs, and the appropriate environment settings for your domain scans. |

> [!WARNING]
> **Important**
> 
> If the following steps do not resolve the issue, you can submit a detailed ticket to the development team for further analysis and assistance. You must attach any relevant error details, screenshots, and EFK logs to the ticket.

Use the following troubleshooting cases to diagnose issues encountered after deploying cookie banners and preference centers configured with the IAB consent Framework in response to customer queries:

### Case 1: Is IAB EU TCF v2.3 enabled for the domain and published?

1. Open the **Network** tab in developer tools.
2. Check the `config_active.json` file for the following attributes:

| Attribute | Description |
| --- | --- |
| `iab_tcf_locations: "all"` | Indicates IAB EU TCF v2.3 is enabled for all geolocations. If enabled for specific locations, this will list those country codes. |
| `iabeu_gdpr_enabled: true` | Indicates that at least one of IAB EU TCF v2.3 or IAB MSPA U.S. National is enabled and published. |

![Case-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11377f58-96ea-5436-cde4-8c33622bea21.png)

### Case 2: Is IAB MSPA U.S. National enabled for the domain and published?

1. Open the **Network** tab in developer tools.
2. Check the `config_active.json` file for the following attributes:

| Attribute | Description |
| --- | --- |
| `iab_usnat_locations: "all"` | Indicates IAB MSPA U.S. National is enabled for all geo-locations. If enabled for specific locations, this will list those country codes. |
| `iabeu_gdpr_enabled: true` | Indicates that at least one of IAB EU TCF v2.3 or IAB MSPA U.S. National is enabled and published. |

![Case-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1c243b76-a2cf-5ff0-5cac-c389cc18528d.png)

### Case 3: Is IAB EU TCF v2.3 Stub or GPP Stub loaded correctly?

For IAB EU TCF v2.3:

1. Open the **Console** tab.
2. Execute the following JavaScript snippet:

```javascript
__tcfapi('ping', 2, (pingReturn) => {
    console.log(pingReturn);
});
```
3. Ensure the response includes `"gdprApplies": true` and other relevant attributes.

![Case-3_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-916858d2-8b9e-9efd-9165-ab8d9d8d8e86.png)

For TCF or MSPA U.S. National:

1. Open the **Console** tab.
2. Execute the following command for the GPP stub:

```bash
__gpp("ping")
```
3. Verify the response includes attributes such as `"gppVersion": "1.0"` and `"apiSupport"`.

![Case-3_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25d9b72d-3539-ace8-2ee1-e7476a08c4ba.png)

### Case 4: Why is the Advanced Settings button disabled temporarily in TCF?

- The button is temporarily disabled to ensure the necessary information from the **Global Vendor List (GVL)** file is loaded in the background before opening the cookie Preference Center.

### Case 5: How to check if the TC String is generated after giving consent?

To receive real-time updates of the TC String, you must register a callback as explained below.

1. Open the **Console** tab.
2. Execute the following snippet:

```javascript
const callback = (tcData, success) => {
    console.log(success, tcData);
}
__tcfapi('addEventListener', 2, callback);
```

When consent is already submitted or submitted next, it returns the following response containing the `tcString` (some details are shortened):

```json
{
    "cmpId": 312,
    "cmpVersion": 1,
    "gdprApplies": true,
    "tcfPolicyVersion": 5,
    "eventStatus": "useractioncomplete",
    "cmpStatus": "loaded",
    "listenerId": 1,
    "tcString": "CQHaQQAQHaQQAE4ABCENBOFgAAAAAEPgABBoAAAThAJMNCogDLAkJCDQMIIEAKgrCAigQAAAAkDRAQAkDAp2BgEOsJEAAAUAAwQAgABBkACAAAAABCIAIACgQAAQCBQAAAAACAQAEDAACACwEAgABAdAhTAAgACwASMyIhTAhCASCAlsqEEgCBBXCAIMsACAREwEAAAAABWAAACwWAwJICVCQQJYQbQAAEACAQQAFCCTgwABAGbLUDgybQAA.YAAAAAAAAAAA",
    "isServiceSpecific": true,
    "useNonStandardTexts": false,
    "purposeOneTreatment": false,
    "publisherCC": "IN",
    "outOfBand": {
        "allowedVendors": {},
        "disclosedVendors": {}
    },
    "purpose": {
        "consents": {},
        "legitimateInterests": {
            "1": false,
            ...
            "11": true
        }
    },
    "vendor": {
        "consents": {},
        "legitimateInterests": {
            "1": false,
             ...
            "1249": true
        }
    },
    "specialOptins": {},
    "publisher": {
        ...
    },
    "enableAdvertiserConsentMode": false
}
```

![Case-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b0c0950-7be2-a97a-6fb6-1fbbd2081607.png)

> [!NOTE]
> **Note**
> 
> It prints a similar response upon each consent submission after you register the above callback.
> 
> In the case of TCF, we generate both the `tcString` and `gppString`. However, for IAB MSPA U.S. National, we generate only the `gppString`. We store the `tcString` in a cookie named `euconsent-v2` under the `https://iab-eu-tcf.securiti.ai` domain.

### Case 6: How to check if the GPP String is generated after giving consent?

1. Execute the following command in the **Console** tab:

```bash
__gpp("getData");
```
2. Ensure the response includes the `gppString`.

```json
{
    "sectionId": 3,
    "gppVersion": "1.0",
    "sectionList": [
        2
    ],
    "applicableSections": [
        2
    ],
    "gppString": "DBABMA~CQHaQQAQHaQQAE4ABCENBOFgAAAAAEPgABBoAAAThAJMNCogDLAkJCDQMIIEAKgrCAigQAAAAkDRAQAkDAp2BgEOsJEAAAUAAwQAgABBkACAAAAABCIAIACgQAAQCBQAAAAACAQAEDAACACwEAgABAdAhTAAgACwASMyIhTAhCASCAlsqEEgCBBXCAIMsACAREwEAAAAABWAAACwWAwJICVCQQJYQbQAAEACAQQAFCCTgwABAGbLUDgybQAA.YAAAAAAAAAAA",
    "pingData": {
        "gppVersion": "1.0",
        "cmpStatus": "loaded",
        "cmpDisplayStatus": "hidden",
        "apiSupport": [
            "tcfeuv2",
            "uspv1",
            "uspnatv1",
            ...
        ],
        "cmpId": 312,
        "cmpVersion": 1
    }
}
```

There are methods for obtaining various information. For more information, refer to the [IAB Tech Lab Consumer Usage Example](https://github.com/IABTechLab/iabgpp-es/tree/master/modules/cmpapi#consumer-usage-example).

### Case 7: How to verify the generated TC String?

- Use the decoder tool at [IAB TCF Decoder](/v1/docs/securiti-pods-and-elastic-pods) or [IAB GPP Decoder](/v1/docs/securiti-pods-and-elastic-pods) to compare the choices selected in the cookie preference center.

### Case 8: How to verify the generated GPP String?

- Use the decoder tool at [IAB GPP Decoder](/v1/docs/securiti-pods-and-elastic-pods) to compare the choices selected in the cookie preference center.

> [!NOTE]
> **Note**
> 
> Check the relevant sections are created correctly.

### Case 9: How to check if the generated `tcString` or `gppString` is sent to Securiti?

1. From the **Network** tab, check the `singleupload` API call and examine the payload. It should be similar to the following for IAB MSPA U.S. National:

```json
{
  "uuid": "20aca815-641f-4f68-9b3d-d898ce5e4381",
  "domain_id": 1753,
  "policy_version": 1,
  "gpc_signal": false,
  "iabeu_gdpr_consents": {
    "gpp_data": {
      "gpp_version": "1",
      "sections_list": "7,6",
      "gpp_string": "DBABzw~1YYY~BVQVAAAAAUA.QA",
      "cmp_id": 312,
      "usnat_string": "BVQVAAAAAUA.QA",
      "usnat_data": {
        "SharingNotice": 1,
        ...
      },
      "uspv1_string": "1YYY",
      "uspv1_data": {
        "Notice": "Y",
        ...
      }
    }
  }
}
```
2. For `tcString`:

```json
{
  "uuid": "20aca815-641f-4f68-9b3d-d898ce5e4381",
  "domain_id": 1258,
  "policy_version": 3,
  "gpc_signal": false,
  "iabeu_gdpr_consents": {
    "tc_string": "CQHaQQAQHaQQAE4ABCENBOFgAAAAAEPgABBoAAAThAJMNCogDLAkJCDQMIIEAKgrCAigQAAAAkDRAQAkDAp2BgEOsJEAAAUAAwQAgABBkACAAAAABCIAIACgQAAQCBQAAAAACAQAEDAACACwEAgABAdAhTAAgACwASMyIhTAhCASCAlsqEEgCBBXCAIMsACAREwEAAAAABWAAACwWAwJICVCQQJYQbQAAEACAQQAFCCTgwABAGbLUDgybQAA.YAAAAAAAAAAA",
    "tc_data": {
      "tc_string_creation_date": 1730419200,
      ...
    }
  }
}
```

Having the `iabeu_gdpr_consents` populated correctly indicates the successful upload of consent to the Securiti backend servers.

### Case 10: How to check if the IAB consent data is recorded in Securiti?

- For a given UUID (subject identifier) and `domain_id`, you can retrieve the cookie consent data using the following API:

![Case-10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6011176e-91b9-f8c3-0b20-2a19dd43c542.png)
  - `{{host}}/privaci/v1/consent/cookie/status`

### Case 11: How to validate advertisements behavior when IAB is in action?

The ads behavior can be specific to each domain's strategy. For TCF, personalized ads should not load until the user consents.

Verify network calls for ad content, such as:

- `https://securepubads.g.doubleclick.net/...`
- `https://match.adsrvr.org/track/cmf/generic?ttd_pid...`
- `https://rtb.mfadsrvr.com/sync?ssp=outbrain&amp;amp;ssp_user_id...`

Observe ad behavior with various consent choices.

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The framework is a set of controls which is available to you in order to remediate a risk by applying controls from different frameworks in a risk assessment.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Multi-State Privacy Agreement (MSPA) serves as a contractual framework designed to aid IAB publishers, advertisers, agencies, and ad tech intermediaries. Its purpose is to facilitate compliance with distinct U.S. state privacy laws. This is achieved by sending, receiving, and honoring standardized opt-out consent signals through the GPP.

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

A Global Vendor List (GVL) is a list of all vendors who have registered with, and participate in the IAB Transparency and Consent Framework (TCF).

A preference center helps organizations immediately and adequately honor consent preferences and consent revocations of their data subjects across multiple systems.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.
