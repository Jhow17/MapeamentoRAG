---
title: "Hyperdrive"
slug: "hyperdrive"
status: "update"
updated: 2026-09-14T18:14:47Z
published: 2026-09-14T18:14:50Z
canonical: "helpcenter.securiti.ai/hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive

> [!NOTE]
> Note
> 
> If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Hyperdrive is a next-generation Data Security Posture Management (DSPM) discovery and scanning architecture designed to accelerate data inventory syncs and discovery scans for unstructured data systems. It operates by breaking large scan operations into smaller tasks that run in parallel within the Outpost environment and then consolidating the results at the end for completeness. The stateless process relies entirely on Securiti Outpost deployed on a dedicated AWS account to manage the changes in scanning activities. When scanning activity is low, the architecture can scale down to zero, ensuring efficient resource utilization while maintaining high performance when needed.

## Securiti Outpost deployment

Securiti Outpost is the customer-hosted scanning infrastructure that utilizes the Securiti offered Hyperdrive connectors. It consists of an automatically scaling public cloud infrastructure deployment with a minimum idle footprint.

> [!NOTE]
> Note
> 
> If this Securiti Outpost is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Securiti supports the following outpost deployment models:

| Deployment model | Description |
| --- | --- |
| Hybrid deployment with Outpost | Hybrid deployment with Outpost offers a Self-hosted deployment model designed to deploy in your own cloud infrastructure, utilizing its services and cloud functions. With the types of cloud services it utilizes and the cloud functions it creates, it can scale to an infinite level for scanning data. This architecture makes it suitable for scanning a high amount of unstructured data in a very short period of time. For deployment, Securiti provides you with a template to deploy the complete Outpost infrastructure in your cloud environment. The template lets you deploy all the resources and connectivity between the services on its own. It provides you with complete control over the Outpost infrastructure once it is deployed. > [!NOTE] > Note > > Hyperdrive Outpost deployment model currently supports only AWS cloud. Each deployment creates and configures cloud services and resources, and the deployment process incurs its own cost. You must deploy the Outpost in your cloud after fully meeting the prerequisites and additional requirements to avoid additional cost. For more information on deploying Outpost in AWS, see [Securiti Outpost - AWS](/latest/docs/securiti-outpost). |
| Full SaaS Hyperdrive deployment | Full SaaS Hyperdrive deployment provides a fully hosted and managed infrastructure solution for customers who require seamless scanning of large unstructured datasets without managing cloud resources. Hosted in Securiti’s cloud environment, it eliminates the need to deploy and maintain infrastructure, making it an ideal choice for businesses with restricted cloud services or limited computing resources. This solution scans unstructured data at high scale and adapts to your data size. For more information on Securiti Hosted Outpost, see [Securiti Hosted Outpost](/latest/docs/securiti-hosted-outpost). |

## Supported data systems and features

Securiti doesn’t support the following features for data systems using Hyperdrive:

- DSR indexing
- DSR Scanless Smart Search
- Exact Data Matching (EDM) index creation
- Instant classification

Use this table to understand the features that are supported for specific data systems:

| Data Systems | Data Inventory Sync |  | Discovery scan | Policies |  |
| --- | --- | --- | --- | --- | --- |
|  | File inventory | User and group entitlements | File Activity | Classification Sampling via Metadata Clustering | AI Agents Discovery | OCR and Document Type Detection | Exact Data Matching | File Clustering | Files Quarantine | Data Labeling | ROT |
| Amazon S3 | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Confluence Cloud | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Google Cloud Storage | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Google Drive (Google Workspace) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Gmail (Google Workspace) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Microsoft 365 SharePoint Online | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Microsoft 365 OneDrive | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Microsoft 365 Outlook | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Microsoft Teams | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| NFS | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ |
| SMB | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |

An Outpost deployment model that runs in your own AWS account. Securiti provides a CloudFormation template to provision the infrastructure, giving you full control over it.

A fully hosted Outpost deployment model that runs entirely in Securiti's cloud. You don't manage any infrastructure, but only your data source connectors.
