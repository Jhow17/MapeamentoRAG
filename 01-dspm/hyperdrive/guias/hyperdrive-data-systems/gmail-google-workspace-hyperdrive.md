---
title: "Gmail (Google Workspace) (Hyperdrive)"
slug: "gmail-google-workspace-hyperdrive"
status: "update"
updated: 2026-09-26T20:00:27Z
published: 2026-09-26T20:00:36Z
canonical: "helpcenter.securiti.ai/gmail-google-workspace-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Gmail (Google Workspace) (Hyperdrive)

Securiti lets you connect your Gmail (Google Workspace) using Hyperdrive mode with self-hosted connector.

Gmail is an email service developed by Google for businesses and enterprises, offering you a platform to send, receive, and organize your emails. Google Workspace is a [monitored, unstructured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

## Supported connector type and features

Use the following table to understand the features supported for Gmail Self-hosted connector using Hyperdrive mode:

| Connector type | Supported modules features |
| --- | --- |
| Gmail (Google Workspace) (Self-hosted) | - Discovery scan - Data Inventory Sync and Entitlement Sync - Activity Analysis |

## Supported deployments

- Hybrid deployment with Outpost
- Full SaaS Hyperdrive deployment

## Supported authentication methods

- OAuth-based authentication

### Keyring support

- Keyring support is not available for data systems using Hyperdrive mode.

## Supported items for inventory and classification scans

Securiti supports the following items for Gmail (Google Workspace) inventory and classification scans:

- All the domains present in the data system
- All the groups present in the domain
- All the users present in the group
- All the folders present for the users
- All the message body content and attachments in the folder

## Prerequisites

Complete the following prerequisites to authenticate the Gmail (Google Workspace) Self-hosted:

### 1. Outpost deployment

To configure Gmail connector using Hyperdrive mode, you must use one of the following deployment methods:

- [Hybrid deployment with AWS Outpost](/latest/docs/hybrid-deployment-with-outpost)
- [Full SaaS deployment](/latest/docs/full-saas-outpost-deployment)

### 2. Admin access

You must be an admin for your Google account to create projects and allow scopes.

### 3. Permissions required

This section covers use cases and permissions required for Gmail (Google Workspace) self-hosted connectors to leverage Hyperdrive features:

| Permissions | Purpose |
| --- | --- |
| `https://www.googleapis.com/auth/admin.directory.customer.readonly` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read the organization's primary domain name, and verifies that users belong to the organization before adding them to the entitlements graph. |
| `https://www.googleapis.com/auth/admin.directory.user.readonly,` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read all workspace users (email, name, org unit, admin status), and build the full user inventory for access mapping. |
| `https://www.googleapis.com/auth/admin.directory.domain.readonly,` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read all domains configured in the workspace and defines the scope or boundary of the scan. |
| `https://www.googleapis.com/auth/admin.directory.group.readonly` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read groups and their membership and maps which users belong to which groups. |
| `https://www.googleapis.com/auth/gmail.readonly` | This permission is required for Discovery Scan, Data Inventory Sync, and Entitlement Scan. It lets Securiti read email messages, headers, body, attachments, and mailbox delegate relationships. This permission also scans email content for sensitive data, and for incremental sync via email history |
| `https://www.googleapis.com/auth/drive.metadata.readonly` | This permission is required for Discovery Scan, Data Inventory Sync, and Entitlement Scan. It lets Securiti read metadata, such as name, type, size, owner, sharing for Drive files. This permission also discovers follow Drive-linked attachments found inside emails. |
| `https://www.googleapis.com/auth/drive.photos.readonly` | This permission is required for Discovery Scan. It lets Securiti read image files stored in Drive. Required alongside `drive.metadata.readonly` during discovery scan because Google's API separately gates access to photos. |
| `https://www.googleapis.com/auth/admin.reports.audit.readonly` | This permission is required for Activity Analysis. Lets you retrieve audit log data from Google Workspace, including user and admin activity events in Gmail. Required to collect activity logs for Activity Analysis, including Gmail audit log events and admin domain-wide delegation grant events. |

### Connect Gmail with Securiti

To configure the Gmail (Google Workspace) connector using Hyperdrive mode, perform the procedures in the following topics:

1. [Configure Hybrid deployment with AWS Outpost or use Full SaaS deployment](/latest/docs/hyperdrive-deployment)
2. [Prerequisites and obtaining authentication credentials for Gmail (Self-hosted) (Hyperdrive)](/latest/docs/prerequisites-and-obtaining-authentication-credentials-in-google-apps-1)
3. [Connecting the Gmail (Google Workspace) (self-hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-google-workspace-gmail-message-body-attachments-securiti).
4. [Configure discovery scans in Gmail (Google Workspace) (self-hosted) (Hyperdrive)](/latest/docs/configure-discovery-scans-in-g-suite-gmail-message-body-attachments-1).
5. [Configure Data Inventory Sync for Gmail (Google Workspace) (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive)
6. [Configure Activity Analysis scan for Gmail (Google Workspace) (Hyperdrive)](/latest/docs/configure-activity-analysis-for-gmail-google-workspace-hyperdrive)

####
