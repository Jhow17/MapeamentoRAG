---
title: "Microsoft Purview Information Protection"
slug: "microsoft-purview-information-protection-connectors"
status: "update"
updated: 2026-09-30T06:22:01Z
published: 2026-09-30T06:22:17Z
canonical: "helpcenter.securiti.ai/microsoft-purview-information-protection-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Purview Information Protection

The Microsoft Purview Information protection connector integrates your Microsoft Purview Information protection with Securiti. As a scanless connector, it doesn’t require data scanning or classification.

MPIP falls under the category of [Monitored, Unstructured data systems](/latest/docs/managing-data-system-connectors).

> [!NOTE]
> **Note**
> 
> Microsoft Purview Information Protection connector only appears in the connectors list when the policy framework module is enabled for your tenant. Contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Supported connector type and module

| Connector type | Module supported |
| --- | --- |
| Microsoft Purview Information Protection (Securiti-cloud) | Not supported (Scanless) |

### Supported authentication methods

For Microsoft Purview Information Protection, the OAuth-based authentication method is supported.

### Prerequisites for configuring the Microsoft Purview Information Protection connector

#### 1. Admin Access in Microsoft Entra

A Microsoft Entra Global Administrator role is required for connector authentication.

#### 2. Relevant Microsoft Subscriptions

You must have the Sensitivity Labels functionality enabled in Microsoft Purview. It applies to the following Microsoft subscriptions:

- Microsoft 365: E3, E5, A3, A5, F1, F3, and Business premium.
- Office 365: E3, E5, A3, and A5.
- OneDrive: Business (plan 2)
- Azure Information Protection Premium P1 or P2.
- Enterprise Mobility and Security (EMS) E3 or E5.
- For more information on supported Microsoft subscriptions, see [Microsoft Purview Information Protection sensitivity labeling](https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-purview-service-description#microsoft-purview-information-protection-sensitivity-labeling).

#### 3. Enabled labels in Microsoft Purview

Securiti can use only labels that are published through Microsoft Purview label publishing policies. If a label is not published or is restricted by the policy scope, it does not appear in Securiti and cannot be applied through data labeling policies.

When multiple label publishing policies apply, Microsoft Purview enforces the policy with the highest priority. For more information, see Microsoft’s documentation on [Create and configure sensitivity labels and their policies](https://learn.microsoft.com/en-us/purview/create-sensitivity-labels?tabs=classic-label-scheme).

#### 4. Use case and permissions for Microsoft Purview Information Protection

This section covers use cases and permissions required for Microsoft Purview Information protection connector.

| Use case | Permission | Explanation of use case |
| --- | --- | --- |
| Data labelling policy | **Graph API permission:** `User.Read` | Lets you sign in to the application using your Microsoft account. The application can access your basic profile information, including your name, email address, and job title. |
| **Graph API permission:** `User.Read.All` | High privilege: Lets the application read the full profile of all users in your organization, including manager and department details. |
| **Graph API permission:** `Content.Writer` | Lets the application encrypt documents and apply Microsoft Purview sensitivity labels to help protect data from unauthorized access. |
| **Graph API permission:** `UnifiedPolicy.Tenant.Read` | Lets the application read your organization’s security and data classification policies used to protect information. |
| **Azure Rights Management Service (RMS) permission:** `Content.SuperUser` | Lets the application to decrypt Azure Rights Management (Azure RMS) protected files so existing encrypted sensitivity labels can be changed or removed. |

### Connect Microsoft Purview Information Protection connector with Securiti

To activate the Microsoft Purview Information Protection connector, proceed to [Connecting Microsoft Purview Information Protection with Securiti](/latest/docs/new-ui-connecting-microsoft-purview-information-protection-with-securiti).
