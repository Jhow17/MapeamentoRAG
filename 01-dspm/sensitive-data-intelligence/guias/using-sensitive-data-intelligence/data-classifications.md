---
title: "Data classifications"
slug: "data-classifications"
status: "update"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/data-classifications"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Data classifications

Data classification is the process of inspecting your data content to identify sensitive and risky information. The data discovery function of Securiti utilizes advanced detection techniques, including AI and ML, to auto-detect and classify data based on the 100's of data elements and personal data attributes configured. Modern machine learning, pattern-matching techniques, and regular expressions (regexes) are used to identify sensitive files such as financial statements. The platform then groups files into high-level categories such as sales, finance, and academia. There is also a library of data classification templates called content profiles for PII, PCI-DSS, GDPR, ITAR, PHI/HIPAA, FERPA, GLBA, and so on.

You can create your own custom data elements, detection rules, and criteria to be used for data classification of the following:

- [Configuring custom data element types](/v1/docs/configuring-custom-data-element-types)
- [Configuring content profiles](/v1/docs/configuring-content-profiles)
- [Configuring document categories and types](/v1/docs/configuring-document-categories-and-types)
- [Configuring dictionaries](/v1/docs/configuring-dictionaries)
- [Configuring file formats](/v1/docs/configuring-file-formats)
- [Using exact data indexes and profiles](/v1/docs/using-exact-data-indexes-and-profiles)

Securiti scans the documents for data classification based on a language and detects the relevant data elements for that locality.

### Supported localities and languages for data classification

#### **Locality**

Locality encompasses the various regions we support worldwide, including countries like the United States, the United Arab Emirates, Australia, and so on. Each locality is associated with specific data elements that pertain to its unique characteristics. For every supported locality, we support all the necessary data elements such as Address, Street, City Name, Country, Province, and government identifiers, for example, the SSN is specific US and is not available to other localities. To view system data elements supported by Securiti, see [Supported system data element types](/v1/docs/system-data-element-types).

These tailored data elements ensure that our services are accurately aligned with the distinct requirements and standards of each locality we operate in, enabling precise and effective global support.

The following list provides the localities supported:

- AE - United Arab Emirates
- AR - Argentina
- AT - Austria
- AU - Australia
- BE - Belgium
- BG - Bulgaria
- BR - Brazil
- CA - Canada
- CL - Chile
- CN - China
- CO - Columbia
- CY - Cyprus
- CZ - Czech Republic (Czechia)
- DE - Germany
- DK - Denmark
- EE - Estonia
- EG - Egypt
- ES - Spain
- FI - Finland
- FR - France
- GR - Greece
- HK - Hong Kong
- HR - Croatia
- HU - Hungary
- ID - Indonesia
- IE - Ireland
- IL - Israel
- IN - India
- IQ - Iraq
- IT - Italy
- JO - Jordan
- JP - Japan
- KR - South Korea
- LT - Lithuania
- LU - Luxembourg
- LV - Latvia
- MT - Malta
- MX - Mexico
- MY - Malaysia
- NL - Netherlands
- NO - Norway
- NZ - New Zealand
- OM - Oman
- PA - Panama
- PE - Peru
- PH - Philippines
- PK - Pakistan
- PL - Poland
- PT - Portugal
- PY - Paraguay
- QA - Qatar
- RO - Romania
- SA - Saudi Arabia
- SE - Sweden
- SG - Singapore
- SI - Slovenia
- SK - Slovakia
- TH - Thailand
- TR - Turkey
- TW - Taiwan
- UA - Ukraine
- UK - United Kingdom
- US - United States
- VN - Vietnam
- ZA - South Africa

#### **Language**

Language support lets Securiti to seamlessly scan documents in the languages that we support.

For example, if you want to identify data elements specific to the Chinese locality and the documents are in the Chinese language, Securiti scans the documents in Chinese characters and identifies the Chinese-specific data elements. To enable a specific language for your locality, you must contact [support@securiti.ai](mailto:support@securiti.ai).

The following list provides the languages supported:

- Arabic
- Czech
- Dutch
- English
- French
- German
- Hebrew
- Indonesian
- Italian
- Japanese
- Korean
- Norwegian
- Portuguese
- Simplified Chinese
- Spanish
- Swedish
- Thai
- Vietnamese

> [!NOTE]
> **Note**
> 
> For a specific locality, Securiti scans the documents and detects relevant data elements accordingly. If a specific language is not listed above, or you have documents in other languages, contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

## Related

- [Data Elements](/data-elements.md)
- [Using exact data indexes and profiles](/using-exact-data-indexes-and-profiles.md)
