---
title: "Troubleshooting for Google Cloud Storage connector"
slug: "troubleshooting-for-google-cloud-storage-connector"
updated: 2025-10-31T07:44:24Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-google-cloud-storage-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Google Cloud Storage connector

This topic covers a troubleshooting guide for common errors and issues for the Google Cloud Storage Connector.

### Common errors during IAM Service Account authentication

When using IAM service account Authentication for impersonation, we recommend you follow the best practices below to avoid errors.

- Grant the minimum required Permissions.
- Regularly rotate and audit service account keys to reduce security risks.
- Use service account impersonation instead of sharing service account keys directly. Impersonation provides a secure and controlled method for delegating access.
- Monitor service account activity through Cloud Audit Logs to ensure that service accounts are being used as intended.
- Use short-lived tokens instead of persistent keys to enhance security.

Below are some common errors and their solutions for IAM Service Account Authentication:

| Error | Solution |
| --- | --- |
| "Request had insufficient Authentication scopes" | Update the VM's OAuth scopes to include the below scope: `https://www.googleapis.com/auth/cloud-platform` |
| "Permission 'iam.serviceAccounts.getAccessToken' denied on resource" | Ensure the source service account has been granted the **Service Account Token Creator** role on the target service account |
| "Service account not found" or "Resource does not exist" | Verify that the service account email addresses are correct and that the accounts exist in the specified project. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
