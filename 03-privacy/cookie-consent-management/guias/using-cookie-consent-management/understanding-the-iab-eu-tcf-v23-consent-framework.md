---
title: "Understanding the IAB Europe TCF v2.4 consent framework"
slug: "understanding-the-iab-eu-tcf-v23-consent-framework"
updated: 2026-04-07T10:46:14Z
published: 2026-04-07T10:46:14Z
canonical: "helpcenter.securiti.ai/understanding-the-iab-eu-tcf-v23-consent-framework"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding the IAB EU TCF v2.3 consent framework

IAB EU TCF v2.3 is the updated version of the Transparency and Consent Framework by [IAB Europe](https://iabeurope.eu/wp-content/uploads/TCF_V-CMP_comms_TheReleaseOfTCFv.2.3-Mandatory%E2%80%98DisclosedVendorsSectionUpdateContactInfo-Reminder_190625_IABEurope.pdf) which requires full compliance by **February 28, 2026**.

## Key changes

A key change in TCF v2.3 requires CMPs to include a mandatory Disclosed Vendors segment in all TC Strings. This change resolves ambiguity for vendors that process data for special purposes under the lawful basis of legitimate interest. When the CMP explicitly lists the vendors presented to the data subject, it confirms that each vendor declaring a special purpose has been disclosed and is permitted to operate under that purpose. After the deadline, IAB TCF compliance checks will treat any TC String without the Disclosed Vendors segment as non compliant with the TCF.

## Updated TC String format

Based on the IAB EU TCF v2.3 update, CMPs must create the TC String with three distinct segments joined together with a dot character. The required format is:

[[Core String](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#the-core-string)].[[Disclosed Vendors](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#disclosed-vendors)].[[Publisher TC](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#publisher-purposes-transparency-and-consent)]

Under the IAB EU TCF v2.3 upgrade, CMPs include the Core String and Disclosed Vendors segments in every TC String, while they may include the Publisher TC segment when needed. The following table explains the details of each segment:

| TC String segment | Description |
| --- | --- |
| Core String | The CMP includes all details required to communicate basic vendor transparency and consent. |
| Disclosed Vendors | The CMP records all vendors it disclosed to the data subject. |
| Publisher TC | The publisher includes its own transparency and consent signals in this segment, separate from the general TC String. |

## Guidance on the IAB EU TCF v2.3 transition period

Moreover, the IAB provides [key clarifications](https://iabeurope.eu/wp-content/uploads/TCF_V-CMP_comms_AdditionalClarificationsOnTCF2.3TransitionPeriodAndReleaseOfTheTCFjSLibraryUpdate_190825_IABEurope.pdf) for the TCF v2.3 transition period:

| Topic | Guidance |
| --- | --- |
| TC String validity | TC Strings created before the February 28, 2026 deadline remain valid even if they do not include the Disclosed Vendors segment. After the deadline, CMPs must include this segment in all newly created TC Strings for them to be considered valid. |
| Updating existing TC Strings | CMPs that maintain a record of Disclosed Vendors can update existing TC Strings by adding the Disclosed Vendors segment without changing the lastUpdated field. If they do not have this record, CMPs should wait for data subjects to renew or change their choices. |
| Technical notes | CMPs do not need to resurface any UI to accommodate the TC String changes. The IAB updated the TCF Type Script Library iabtcf-es to align with the TCF v2.3 Technical Specifications. The TCF policy version remains 5.0, and the presence of the Disclosed Vendors segment indicates v2.3 compliance. |
| Vendor support | CMPs must continue to set the Legitimate Interest bit to 1 for vendors that support only Special Purposes and have not yet adopted v2.3. |

Consent Management Platform (CMP) is a software solution that helps businesses and organizations collect and manage personal information and consents of the consumers (data subjects) in line with data protection laws and regulations like the EU’s GDPR, California’s CCPA, or Brazil’s LGPD.
