---
title: "Understanding the Terraform template"
slug: "understanding-the-azure-terraform-template"
updated: 2026-02-10T05:30:29Z
published: 2026-02-10T05:30:29Z
canonical: "helpcenter.securiti.ai/understanding-the-azure-terraform-template"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Understanding the Terraform template

## Overview

The Terraform configuration provisions a Securiti Service Principal in Microsoft Azure with read-only access across one or more Azure subscriptions. It lets Securiti discover and monitor Azure resources such as Azure OpenAI, Storage Accounts, Cognitive Services, and Microsoft Purview.

You use this configuration during Azure onboarding to securely grant Securiti visibility into your cloud environment without providing write access.

## How the Terraform configuration works

When you run this Terraform configuration, it performs the following actions:

- Creates an Microsoft Entra ID application with required Microsoft Graph API permissions.
- Creates a Service Principal (Enterprise Application) for the application.
- Generates a client secret for authentication.
- Grants admin consent for Microsoft Graph permissions:
  - Directory.Read.All
  - Policy.Read.All
  - Reports.Read.All
- Creates custom Azure roles for accessing:
  - Azure OpenAI
  - Azure Cognitive Services
- Assigns the built-in Reader role across the specified Azure subscriptions.
- Optionally configures Microsoft Purview access using REST API scripts.
- Sends the created credentials to Securiti to complete onboarding and start discovery.

> [!NOTE]
> Note
> 
> If the first subscription in the onboarding subscription list does not have access to the Azure Service Principal, the Terraform execution will fail, even if the subsequent subscriptions have the required permissions and access. To avoid this, move a subscription where the Service Principal has the required permissions to the first position in the subscription list.
