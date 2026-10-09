---
title: "IAB GPP commands for Europe TCF v2.4 and MSPA U.S. National Approach"
slug: "iab-gpp-commands-for-eu-tcf-v22-and-mspa-us-national-approach"
updated: 2026-02-10T07:41:51Z
published: 2026-02-10T07:41:51Z
canonical: "helpcenter.securiti.ai/iab-gpp-commands-for-eu-tcf-v22-and-mspa-us-national-approach"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# IAB GPP commands for EU TCF v2.3 and MSPA U.S. National Approach

You can use the following commands in the console of your webpage to encode or decode consent information with the IAB GPP framework.

- `__gpp("addEventListener", callback?, parameter?)`
- `__gpp("getField", callback?, parameter?)`
- `__gpp("getGPPData", callback?, parameter?)`
- `__gpp("getSection", callback?, parameter?)`
- `__gpp("hasSection", callback?, parameter?)`
- `__gpp("removeEventListener", callback?, parameter?)`

To use the aforementioned commands:

1. Configure your cookie banner with either IAB GPP TCF **v2.3** or MSPA U.S. National Approach as explained in [Configuring an IAB EU TCF v2.3 cookie consent banner](/v1/docs/configuring-an-iab-eu-tcf-v22-cookie-consent-banner) or [Configuring an IAB MSPA U.S. National cookie consent banner](/v1/docs/configuring-an-iab-mspa-us-national-cookie-consent-banner).
2. Deploy this cookie banner on your organizational website as defined in [Deploying your website cookie consent banner](/v1/docs/deploying-your-website-cookie-consent-banner).
3. Now go to your website and interact with the deployed cookie banner. For instance, give consent against any or all cookie categories and enter the inspect mode from the same webpage.
4. Switch to the **console** tab from the inspect mode.
5. Type any IAB GPP command that you want to use and press enter, as shown below.

![IAB_GPP_v1_1_Console.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe02c700-5b06-6b8f-8bb1-8fb8dbcdb270.png)

The console displays the results according to the executed command.

For more information, see [IAB](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform/blob/main/Core/CMP%20API%20Specification.md) [IAB Global-Privacy-Protocol](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform/blob/main/Core/CMP%20API%20Specification.md).

### Command usage examples

The following table describes the usage of IAB GPP commands. You can use these commands for both IAB GPP **EU TCF v2.3** and **MSPA U.S. National Approach** consent framework configured cookie banners.

| Command | Description |
| --- | --- |
| `addEventListener` | Use the `addEventListener` command to define a callback function (or a postmessage to respond to for cross-domain case) that can be used to detect changes in the CMP. |
| `getField` | Use the `getField` command to receive a specific field out of a certain section. > [!NOTE] > **Note** > > The command may return null when the CMP is not yet loaded. |
| `getGPPData` | Use the `getGPPData` command to receive the current version of the (encoded) GPP String. You can pass the GPP string along the supply chain. > [!NOTE] > **Note** > > The command may return null when the CMP is not yet loaded. |
| `getSection` | Use the `getSection` command to receive the (parsed) object representation of a section of a certain specification. > [!NOTE] > **Note** > > The command may return null when the CMP is not yet loaded. |
| `hasSection` | Use the `hasSection` command to detect if the CMP has generated a section of a certain specification. > [!NOTE] > **Note** > > The command may return null when the CMP is not yet loaded. |
| `ping` | Use the `ping` command to determine the state of the CMP. |
| `removeEventListener` | Use the `removeEventListener` command to remove an existing event listener. |

### Command fields

Use the following table of fields in the aforementioned IAB GPP commands:

| Section Name | Section ID | Field | Data Type/Value |
| --- | --- | --- | --- |
| tcfeuv2 | 2 | `Version` | 6 bit int Value is 2. |
| tcfeuv2 | 2 | `Created` | Datetime Updated when fields are set. |
| tcfeuv2 | 2 | `LastUpdated` | Datetime Updated when fields are set. |
| tcfeuv2 | 2 | `CmpId` | 12 bit int |
| tcfeuv2 | 2 | `CmpVersion` | 12 bit int |
| tcfeuv2 | 2 | `ConsentScreen` | 6 bit int |
| tcfeuv2 | 2 | `ConsentLanguage` | 2 character country code |
| tcfeuv2 | 2 | `VendorListVersion` | 12 bit int |
| tcfeuv2 | 2 | `PolicyVersion` | 6 bit int Value is 2 |
| tcfeuv2 | 2 | `IsServiceSpecific` | Boolean |
| tcfeuv2 | 2 | `UseNonStandardStacks` | Boolean |
| tcfeuv2 | 2 | `SpecialFeatureOptins` | Boolean array of size 12 |
| tcfeuv2 | 2 | `PurposeConsents` | Boolean array of size 24 |
| tcfeuv2 | 2 | `PurposeLegitimateInterests` | Boolean array of size 24 |
| tcfeuv2 | 2 | `PurposeOneTreatment` | Boolean |
| tcfeuv2 | 2 | `PublisherCountryCode` | 2 character country code |
| tcfeuv2 | 2 | `VendorConsents` | Integer array of variable size |
| tcfeuv2 | 2 | `VendorLegitimateInterests` | Integer array of variable size |
| tcfeuv2 | 2 | `PublisherRestrictions` | Integer array of variable size |
| tcfeuv2 | 2 | `PublisherPurposesSegmentType` | 3 bit int Value is 3 |
| tcfeuv2 | 2 | `PublisherConsents` | Boolean array of size 24 |
| tcfeuv2 | 2 | `NumCustomPurposes` | 6 bit int |
| tcfeuv2 | 2 | `PublisherCustomConsents` | Boolean array where size is set by the `NumCustomPurposes` field |
| tcfeuv2 | 2 | `PublisherCustomLegitimateInterests` | Boolean array where size is set by the `NumCustomPurposes` field |
| tcfeuv2 | 2 | `VendorsAllowedSegmentType` | 3 bit int Value is 2 |
| tcfeuv2 | 2 | `VendorsAllowed` | Integer array of variable size |
| tcfeuv2 | 2 | `VendorsDisclosedSegmentType` | 3 bit int Value is 1 |
| tcfeuv2 | 2 | `VendorsDisclosed` | Integer array of variable size |
| uspv1 | 6 | `Version` | 6 bit int Value is 1 |
| uspv1 | 6 | `Notice` | 2 bit int |
| uspv1 | 6 | `OptOutSale` | 2 bit int |
| uspv1 | 6 | `LspaCovered` | 2 bit int |
| uspnatv1 | 7 | `Version` | 6 bit int Value is 1 |
| uspnatv1 | 7 | `SharingNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SaleOptOutNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SharingOptOutNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `TargetedAdvertisingOptOutNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SensitiveDataProcessingOptOutNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SensitiveDataLimitUseNotice` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SaleOptOut` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SharingOptOut` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `TargetedAdvertisingOptOut` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `SensitiveDataProcessing` | 2 bit int array of size 12 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `KnownChildSensitiveDataConsents` | 2 bit int array of size 2 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `PersonalDataConsents` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `MspaCoveredTransaction` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `MspaOptOutOptionMode` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `MspaServiceProviderMode` | 2 bit int 0 = Not applicable 1 = Yes 2 = No |
| uspnatv1 | 7 | `GpcSegmentType` | 2 bit int Value is 1 |
| uspnatv1 | 7 | `GpcSegmentIncluded` | Boolean Default is true |
| uspnatv1 | 7 | `Gpc` | Boolean |

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Multi-State Privacy Agreement (MSPA) serves as a contractual framework designed to aid IAB publishers, advertisers, agencies, and ad tech intermediaries. Its purpose is to facilitate compliance with distinct U.S. state privacy laws. This is achieved by sending, receiving, and honoring standardized opt-out consent signals through the GPP.

A stack is a combination of Purposes or Special Features, and it can also be a combination of Purposes and Special Features used by participants (Vendors) in the IAB EU TCF v2.2 consent framework. It serves as a viable alternative or addition to the more detailed Purpose and Special Feature descriptions made visible to the data subjects in the UI prior to the data subjects being able to give their consent.

A feature refers to one of the aspects of processing personal data within the IAB EU TCF v2.2 consent framework. These are outlined in the Policies or Specifications and are employed to achieve one or more Purposes. Unlike Purposes, the data subjects do not have a separate choice for each Feature; their choices are tied to the overarching Purposes.

Purpose refers to one of the designated reasons for handling data, including the personal data of individuals, by those involved in the IAB EU TCF v2.2 consent framework. These reasons are outlined in the Policies or Specifications, and Vendors declare a Legal Basis for them in the Global Vendor List (GVL). The data subjects are given a choice, such as granting consent or expressing objection based on the Legal Basis for processing, facilitated by the CMP.
