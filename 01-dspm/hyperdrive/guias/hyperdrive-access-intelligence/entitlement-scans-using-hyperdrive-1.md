---
title: "Hyperdrive Entitlement Scan"
slug: "entitlement-scans-using-hyperdrive-1"
updated: 2026-08-03T06:23:50Z
published: 2026-08-03T06:23:50Z
canonical: "helpcenter.securiti.ai/entitlement-scans-using-hyperdrive-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Entitlement Scan

## **Overview**

Entitlement Scan in Hyperdrive provides visibility into who, and what, can access Data systems across connected data systems. It captures entitlement metadata from source systems to help you map access and ownership, identify over-exposed data, and validate that permissions align with intended access policies.

With Entitlement Scan, you can identify users, groups, AI agents, and applications that hold access to your data, and scope Gencore AI pipelines with confidence.

## **How Entitlement Scan Works**

Entitlement Scan collects entitlement metadata from connected data systems and correlates it with data inventory and sensitivity classifications to generate an access map of who, and what, can reach each resource.

### Prerequisites

Before configuring Entitlement Scan for Microsoft 365 OneDrive, ensure the following requirements are completed:

#### Connector setup

Ensure the Microsoft 365 OneDrive connector is configured and synced.

For detailed setup instructions of all the required steps, see:

- [Microsoft 365 (Hyperdrive)](/latest/docs/microsoft-365)
- [Configure Data Inventory Sync](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive)

## **Key Components**

- **Entitlement Metadata**Captured from source systems and includes access grants, permissions, and ownership records for discovered resources.
- **Data Inventory**Provides metadata about data resources such as files, sites, and mailboxes.
- **Identity and Access Entities**Users, groups, AI agents, and applications that hold access to, or control over, discovered resources.
- **Sensitive Data Classification**Identifies regulated or sensitive data within the resources that entitlements map to.

## **Entitlement Scan in hyperdrive for specific Data Systems**

To configure Entitlement Scan for specific data systems in hyperdrive, visit:

- [Entitlement Scan for Microsoft 365](/latest/docs/hyperdrive-entitlement-scan-for-m365)
- [Entitlement Scan for Microsoft Outlook](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-365-outlook)
- [Entitlement Scan for Microsoft OneDrive](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-onedrive)
- [Entitlement Scan for Microsoft SharePoint Online](/latest/docs/hyperdrive-entitlement-scan-for-m-sharepoint-online)
- [Entitlement Scan for Microsoft Teams](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-teams)

Entitlement scan identifies the privileges and permissions an entity, such as a user, application, or AI agent, holds for a specific data object such as file.

Data systems refer to the system where your data is stored. That can be in the form of files (text, audio, video), databases (tables and schemas), and streaming data (data in motion). Securiti supported most of the structured, unstructured, and streaming data systems.
