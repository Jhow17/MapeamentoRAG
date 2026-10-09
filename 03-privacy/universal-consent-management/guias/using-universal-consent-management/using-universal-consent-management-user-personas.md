---
title: "User Personas"
slug: "using-universal-consent-management-user-personas"
updated: 2026-07-21T09:59:03Z
published: 2026-07-21T09:59:03Z
canonical: "helpcenter.securiti.ai/using-universal-consent-management-user-personas"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# User Personas

Use the following table to understand the roles of different types of users and what they are responsible for in the Universal Consent Management module. From the **Responsibilities** column, use the links of the relative help topics to learn more about the responsibilities of the following roles.

| Role | Title in the module | Responsibilities |
| --- | --- | --- |
| Web Developer (Internal to your organization) | - Organization Admin - Module Owner | Implementing the [Form Consent code](/v1/docs/generating-and-embedding-the-form-consent-code) and [Universal Preference Center](/v1/docs/building-a-universal-preference-center) in your domain’s web consent form or codebase. A privacy professional is meant to perform this action. - [Installing the browser plugin](/v1/docs/installing-the-browser-plugin) - [Extracting the form JSON](/v1/docs/extracting-the-form-json) - [Importing the form JSON int Securiti](/v1/docs/importing-the-form-json-into-securiti) - [Testing the form code](/v1/docs/testing-the-form-code) |
| Integration Specialist (Internal to your organization) | - Organization Admin - Module Owner | - Planning, coordinating, and executing the following activities: - [Configuring a universal preference center](/v1/docs/building-a-universal-preference-center) - [Configuring a double opt-in preference center](/v1/docs/configuring-a-double-opt-in-preference-center) - [Configuring an explicit consent preference center](/v1/docs/configuring-an-explicit-consent-preference-center) - [Customizing the universal preference center](/v1/docs/customizing-your-preference-center) - [Integrating the universal preference center with an external website](/v1/docs/integrating-preference-center-with-external-website) - [Integrating the universal preference center with mobile applications](/v1/docs/preference-center-integration-with-mobile-applications) - [Configuring selective consent management](/v1/docs/selective-consent-management) - [Configuring the webhook export](/v1/docs/webhook-export) to downstream consent records from the module to your internal systems - [External UUID linking for the consent records](/v1/docs/external-uuid-linking-for-consent-records) - Collaborating with other internal stakeholders of your organization involved in setting up the Universal Consent Management module. |
| Data Protection Officer (DPO) | Super Admin | - Supervising the integration of the module. - Keeping an [audit trail](/v1/docs/audit-logs-for-universal-consent-management) of all the steps taken to comply with the request, to prove compliance in case of legal issues. - Ensuring the implementation of the [best practices in the organization for collecting the form consent](/v1/docs/best-practices-for-collecting-form-consent). |
| System Administrator or Portal Administrator | - Super Admin - Organization Admin - Module Owner | - Planning, coordinating, and supervising all following activities related to the integration of the Universal Consent Management module: - [Configuring processing purposes and consent purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes) - [Creating processing purpose categories](/v1/docs/processing-purpose-categories) - [Configuring custom parameters](/v1/docs/configuring-custom-parameters) - [Managing API consent sources](/v1/docs/managing-api-consent-sources) - [External UUID linking for the consent records](/v1/docs/external-uuid-linking-for-consent-records) - Evaluate any sensitive or confidential information that may need special handling, and apply appropriate measures to protect that sensitive data and information such as consent records of the data subjects during disclosure. |

A key role within your organization responsible for overseeing and ensuring compliance with data protection laws and regulations, such as the General Data Protection Regulation (GDPR) in the European Union. The primary responsibility of the DPO is to monitor the organization's data processing activities, assess potential risks to data subjects' privacy rights, and implement measures to mitigate those risks.

## Related

- [Securiti user roles in Universal Consent Management](/securiti-user-roles-in-universal-consent-management.md)
