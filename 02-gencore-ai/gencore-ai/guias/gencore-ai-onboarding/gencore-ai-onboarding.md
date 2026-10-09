---
title: "Gencore AI onboarding"
slug: "gencore-ai-onboarding"
status: "update"
updated: 2026-06-10T05:58:06Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/gencore-ai-onboarding"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Gencore AI onboarding

With Gencore AI onboarding, you can ease your onboarding with Gencore AI tenant.

The Gencore AI onboarding streamlines the GenAI pipeline creation process by guiding you through configuration steps directly within the pipeline interface. Unlike configuring data systems and providers manually, which requires navigating to separate sections for set up and configuration, Gencore AI onboarding provides configuration nodes on the left panel within the pipeline. These nodes prompt you to to add each component as you build their first pipeline. This in-context, guided approach reduces setup complexity and ensures a more seamless and user-friendly onboarding experience.

There are two ways for onboarding the Gencore AI module:

- [Regular onboarding](/latest/docs/regular-gencore-ai-onboarding)
- [Frictionless onboarding](/latest/docs/frictionless-gencore-ai-onboarding)

You can choose one type of onboarding at a time. By default, Gencore AI module providers regular onboarding process.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Prerequisites

To onboard to Gencore AI, ensure the following steps are complete:

- You must have added [data sources and active connectors](/latest/docs/managing-data-system-connectors).
- You must have valid [LLM and embeddings models credentials](/latest/docs/configuring-llm-providers).
- You must have valid [Vector Database model credentials](/latest/docs/configuring-vector-storage-providers).
- For entitlement support, ensure your pipeline is eligible for entitlement enforcement by fulfilling all pre-requisites.
  - Configure a data source on the Datasource Panel for your GenAI pipeline. Your [data source must be supported](/latest/docs/supported-data-sources) by Gencore AI entitlement functionality.
  - You must configure data Inventory sync for data systems. For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - After configuring Data Inventory Sync, In Gencore AI, execute your GenAI pipeline.
  - Once the files are ingested, perform an Access Scan after the pipeline execution is complete.

## Related

- [Regular Gencore AI Onboarding](/regular-gencore-ai-onboarding.md)
- [Frictionless Gencore AI Onboarding](/frictionless-gencore-ai-onboarding.md)
- [Getting Started with GenAI pipelines](/getting-started-with-genai-pipelines.md)
