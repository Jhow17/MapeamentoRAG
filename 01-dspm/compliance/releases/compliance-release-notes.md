---
title: "Compliance release notes"
slug: "compliance-release-notes"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/compliance-release-notes"
area: dspm
modulo: compliance
tipo: release
data_captura: 2026-10-06
---

# Compliance release notes

## 1.151

### Release updates - September 2026

#### Expanded compliance coverage with Indonesia PDPL and Singapore PDPA

**Indonesia Personal Data Protection Law (PDPL)**

The Personal Data Protection Law (Law No. 27 of 2022) is Indonesia's first comprehensive data protection law, effective October 2024. It applies to any entity processing personal data within Indonesia, or outside Indonesia where processing affects Indonesian data subjects. The law establishes data subject rights, lawful bases for processing, and controller and processor obligations, enforced through administrative sanctions of up to 2% of annual revenue and criminal penalties.

Securiti now lets you operationalize Indonesia PDPL compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Data Subject Rights | Enforce rights to access, correction, deletion, withdrawal of consent, objection to automated decision-making, and portability of personal data. |
| Visual Data Processing Devices in Public Places | Apply requirements for the use of visual data processing devices in public spaces, including notice and purpose limitation obligations. |
| Joint Controllers | Establish and document arrangements between joint controllers, including allocation of responsibilities and communication of arrangements to data subjects. |
| Consent | Obtain valid, specific, informed, and unambiguous consent as a lawful basis for processing personal data. |
| Children's Data & Parental Consent | Apply heightened protection requirements for processing personal data of children, including obtaining verifiable parental consent. |
| Personal Data of Persons with Disabilities | Apply specific protections for personal data of persons with disabilities, ensuring equitable treatment and appropriate safeguards. |
| Data Processing Principles | Enforce the core principles of lawfulness, purpose limitation, data minimization, accuracy, retention limitation, integrity, and accountability. |
| DSR Fulfillment & Processing Records | Maintain records of data processing activities and fulfill data subject requests within required timeframes. |
| Data Protection Impact Assessment | Conduct DPIAs for high-risk processing activities to identify and mitigate privacy risks before processing begins. |
| Security of Personal Data | Implement technical and organizational measures to protect personal data against unauthorized access, disclosure, alteration, and destruction. |
| Consent Withdrawal & Restriction of Processing | Honor withdrawal of consent and restrictions on processing promptly, and cease processing where consent is the only lawful basis. |
| Data Retention & Disposal | Retain personal data only for as long as necessary and securely dispose of it once the retention period has ended. |
| Breach Notification | Notify the supervisory authority and affected data subjects of personal data breaches within required timeframes. |
| Processor Obligations | Ensure processors act only on controller instructions and implement appropriate security and compliance measures. |
| Accountability | Demonstrate compliance with the PDPL through documentation, policies, and governance structures. |
| Lawful Basis | Establish and document a valid lawful basis for each processing activity, including consent, contractual necessity, legal obligation, vital interests, or legitimate interests. |
| Data Protection Officer | Appoint a DPO where required and ensure the DPO has the authority, resources, and access needed to perform their duties. |
| Personal Data Transfers | Ensure cross-border transfers of personal data comply with PDPL requirements, including adequate protection standards in the recipient country. |

**Singapore Personal Data Protection Act (PDPA)**

The Personal Data Protection Act 2012 (PDPA) is Singapore's principal data protection law, last amended in 2020. It applies to private-sector organizations collecting, using, or disclosing personal data in Singapore, with exemptions for public agencies and employees acting in the course of employment. The law establishes obligations on consent, purpose limitation, access and correction, data protection, retention, cross-border transfers, breach notification, and a Do Not Call registry regime, enforced by the Personal Data Protection Commission.

Securiti now lets you operationalize Singapore PDPA compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Accountability and Compliance | Designate a Data Protection Officer, implement data protection policies, and maintain accountability for PDPA compliance across the organization. |
| Legal Basis for Collection, Use and Disclosure | Establish a valid legal basis for each collection, use, or disclosure of personal data, including consent, legitimate interests, or other exceptions under the PDPA. |
| Purpose Limitation and Notification | Collect, use, and disclose personal data only for purposes that a reasonable person would consider appropriate, and notify individuals of those purposes. |
| Access to and Correction of Personal Data | Honor individuals' rights to access and correct their personal data held by the organization within required timeframes. |
| Care of Personal Data | Implement reasonable security measures to protect personal data against unauthorized access, collection, use, disclosure, copying, modification, or disposal. |
| Notification of Data Breaches | Assess, document, and notify the Personal Data Protection Commission and affected individuals of notifiable data breaches within required timeframes. |
| Reporting of Terminated Telephone Numbers | Report terminated telephone numbers to the Do Not Call registry to prevent unauthorized marketing messages to reassigned numbers. |
| Compliance Requirements for Specified Messages | Ensure marketing messages sent to Singapore telephone numbers comply with Do Not Call registry obligations, including opt-out mechanisms and sender identification. |
| Prohibition on Dictionary Attacks and Address-Harvesting | Prohibit the use of dictionary attacks and address-harvesting software to generate or collect telephone numbers for marketing purposes. |
| Cooperation with Regulatory Investigations | Cooperate with Personal Data Protection Commission investigations and produce requested documents and information within required timeframes. |

For more information, see [Compliance frameworks](/latest/docs/using-the-framework-dashboard).

---

## 1.150

### Release updates - August 2026

No updates

---

## 1.149

### Release updates - July 2026

#### Introducing new compliance tests for AWS Aurora DSQL

Securiti now includes new graph-based compliance tests for Amazon Web Services (AWS). These tests help you enforce encryption best practices and deletion protection for Aurora DSQL clusters.

**Graph Tests for AWS**

| Cloud | Service | Test | Severity |
| --- | --- | --- | --- |
| AWS | Aurora DSQL | Ensure AWS Aurora DSQL Cluster uses customer managed encryption key (CMEK) for data encryption. | High |
| AWS | Aurora DSQL | Ensure deletion protection is enabled for AWS Aurora DSQL Cluster. | High |

For more information, see [Rule center](/latest/docs/rule-center-overview).

---

## 1.148

### Release updates - June 2026

#### Expanded compliance coverage with new frameworks

**Chile's Law No. 21.719**

Chile’s Law No. 21.719 is Chile's modern data protection framework governing the collection, use, storage, and transfer of personal data. Effective December 1, 2026, it establishes comprehensive requirements for lawful data processing, strengthens individuals' privacy rights, defines obligations for controllers and processors, and introduces enforcement by the Agencia de Protección de Datos Personales (APDP).

With this release, Securiti lets you operationalize Chile's Law No. 21.719 compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Principles of Processing | Apply eight core principles: lawfulness and fairness, purpose limitation, proportionality, data quality, accountability, security, transparency and information, and confidentiality. |
| Data Subject Rights | Enforce rights to access, rectification, erasure, opposition, portability, and blocking of personal data processing. |
| Lawful Basis for Processing | Establish lawful grounds for processing, including freely given, specific, unambiguous, and informed consent, or one of five alternative grounds under Art. 13. |
| Privacy Notice, Third-party Processing & DPO Appointment | Provide comprehensive privacy notices, govern processor relationships through written contracts, and designate an operational contact point where required. |
| Data Security & Breach Notification | Apply security measures appropriate to the risk of processing and report breaches to the APDP without undue delay. |
| Processing of Sensitive Personal Data | Apply heightened protection requirements for sensitive, health, biometric, and children's and adolescents' personal data. |
| Personal Data Transfer & Impact Assessment | Manage domestic and international personal data transfers and conduct data protection impact assessments for high-risk processing. |

**OSFI Canada Guideline B-13**

The Technology and Cyber Risk Management Guideline sets out OSFI's expectations for managing technology and cyber risks at all federally regulated financial institutions in Canada, including banks, foreign bank and insurance branches, life and P&C insurers, and trust and loan companies. The framework is applied on a risk-based basis, proportional to each institution's size, nature, scope, complexity of operations, and risk profile.

With this release, Securiti lets you operationalize OSFI Canada Guideline B-13 compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Governance and Risk Management | Govern technology and cyber risks through clear accountabilities and structures, supported by comprehensive strategies and frameworks. |
| Technology Operations and Resilience | Maintain a stable, scalable, and resilient technology environment through robust operating and recovery processes. |
| Cyber Security | Maintain a secure technology posture that ensures the confidentiality, integrity, and availability of technology assets. |

**NIST Privacy Framework**

The NIST Privacy Framework is a voluntary, technology-neutral tool developed by the National Institute of Standards and Technology to help organizations of all sizes manage privacy risks across the complete data life cycle. Published on January 16, 2020, it provides a common language and structured approach for identifying and addressing privacy risks arising from data processing, helping organizations build customer trust, fulfill compliance obligations, and communicate privacy practices effectively.

With this release, Securiti lets you operationalize NIST Privacy Framework compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Inventory and Mapping | Develop and maintain a comprehensive understanding of the data processing performed by systems, products, and services, including the data, individuals, purposes, environments, and flows. |
| Business Environment | Identify and communicate the organization's role in the data processing ecosystem, establish mission priorities, and identify the systems, products, and services that support those priorities. |
| Risk Assessment | Understand the privacy risks to individuals arising from data processing and the resulting impacts to the organization, and prioritize and respond to those risks. |
| Data Processing Ecosystem Risk Management | Establish processes to identify, assess, and manage privacy risks across the data processing ecosystem through policies, assessments, contracts, and routine evaluations. |
| Governance Policies, Processes, and Procedures | Implement a governance structure that informs the management of privacy risk through privacy policies, defined roles, legal and regulatory management, and integration of privacy into governance. |
| Risk Management Strategy | Establish a risk management strategy with stakeholder-agreed processes and clearly expressed risk tolerance informed by the organization's role in the data processing ecosystem. |
| Awareness and Training | Provide privacy awareness education and training to the workforce, senior executives, privacy personnel, and third parties engaged in data processing. |
| Monitoring and Review | Conduct ongoing review of the privacy posture, including risk re-evaluation, policy and training updates, compliance assessment, response to problematic data actions, and tracking of complaints. |
| Data Processing Policies, Processes, and Procedures | Maintain policies and procedures to manage data processing authorizations, enable data subject rights, and align the data lifecycle with the system development lifecycle. |
| Data Processing Management | Manage data to enable individual participation, data quality, and data minimization, including access for review, alteration, deletion, destruction per policy, and standardized transmission. |
| Disassociated Processing | Process data in ways that increase disassociability, limiting observability, linkability, individual identification, and inferences about individuals. |
| Communication Policies, Processes, and Procedures | Maintain policies and procedures that increase transparency of data processing practices and associated privacy risks. |
| Data Processing Awareness | Ensure individuals and organizations have reliable knowledge of data processing practices and privacy risks through communication mechanisms, feedback channels, and breach notifications. |
| Data Protection Policies, Processes, and Procedures | Maintain security and privacy policies, processes, and procedures to manage the protection of data across configuration, backups, response and recovery, human resources, and vulnerability management. |
| Identity Management, Authentication, and Access Control | Limit access to data and devices to authorized individuals, processes, and devices, managed consistent with the assessed risk of unauthorized access. |
| Data Security | Protect data consistent with the organization's risk strategy to maintain confidentiality, integrity, and availability across the data lifecycle. |
| Maintenance | Perform system maintenance and repairs consistent with policies, processes, and procedures, including controls for remote maintenance. |
| Protective Technology | Manage technical security solutions to ensure the security and resilience of systems, products, services, and associated data. |

**Quebec Law 25**

Quebec Law 25 (Act Respecting the Protection of Personal Information in the Private Sector, chapter P-39.1) governs the collection, use, communication, retention, and destruction of personal information by enterprises operating in Quebec. It establishes obligations around governance, consent, transparency, data subject rights, breach notification, and privacy impact assessments, and introduces a registration regime for personal information agents.

With this release, Securiti lets you operationalize Quebec Law 25 compliance through a comprehensive set of controls and automation across the following categories:

| Category | Description |
| --- | --- |
| Governance & Accountability | Designate a person in charge of personal information protection, establish governance policies and practices proportionate to activities, conduct privacy impact assessments for system projects, and respond to confidentiality incidents. |
| Data Collection & Processing Principles | Collect personal information only for a serious and legitimate purpose, limited to what is necessary, by lawful means, kept accurate and up to date, and used only for its collected purpose, with privacy by default. |
| Consent Management | Obtain clear, free, informed, and purpose-specific consent valid only for the time necessary to achieve its stated purpose, with the right to withdraw consent for commercial or philanthropic prospecting at any time. |
| Communication & Transfer | Communicate personal information to third parties without consent only in specific circumstances defined by law, with a prior privacy impact assessment for cross-border transfers and separate rules for service providers and archival agencies. |
| Destruction & Anonymization | Destroy or anonymize personal information once the purpose for which it was collected or used has been achieved, subject to any applicable statutory retention period. |
| Data Subject Rights | Comply with data subject requests for access, portability, rectification, cessation of dissemination, and de-indexation or re-indexation of hyperlinks to personal information. |
| Personal Information Agents | Register with the Commission for establishing files on individuals and communicating credit reports. |

For more information, see [Compliance frameworks](/latest/docs/using-the-framework-dashboard).

---

## 1.147

### Release updates - June 2026

No updates
